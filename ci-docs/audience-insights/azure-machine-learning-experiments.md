---
title: Azure 机器学习试验
description: 在 Dynamics 365 Customer Insights 中使用基于 Azure 机器学习的模型。
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4c04a1d08aba152ce91d452ae2300c1ce0fc79e5d6980ac506dc40d9914c9fca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033161"
---
# <a name="use-azure-machine-learning-based-models"></a>使用基于 Azure 机器学习的模型

Dynamics 365 Customer Insights 中的统一数据是构建可生成其他业务见解的机器学习模型的来源。 Customer Insights 与机器学习工作室（经典）和 Azure 机器学习集成以使用您自己的自定义模型。 有关基于机器学习工作室（经典）生成的试验示例，请参考[机器学习工作室（经典）试验](machine-learning-studio-experiments.md)。 

## <a name="prerequisites"></a>先决条件

- Customer Insights 访问权限
- 有效的 Azure Enterprise 订阅
- [统一客户配置文件](data-unification.md)
- 已配置[将实体导出到 Azure Blob 存储](export-azure-blob-storage.md)

## <a name="set-up-azure-machine-learning-workspace"></a>设置 Azure 机器学习工作区

1. 有关创建工作区的不同选项，请参阅[创建 Azure 机器学习工作区](/azure/machine-learning/concept-workspace#-create-a-workspace)。 为了获得最佳性能，请在地理位置距离 Customer Insights 环境最近的 Azure 区域中创建工作区。

1. 通过 [Azure 机器学习工作室](https://ml.azure.com/)访问您的工作区。 可通过多种[交互方式](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction)与您的工作区进行交互。

## <a name="work-with-azure-machine-learning-designer"></a>使用 Azure 机器学习设计器

Azure 机器学习设计器提供了一个视觉对象画布，您可以在其中拖放数据集和模块，这类似于机器学习工作室（经典）。 如果进行了相应配置，从设计器创建的批处理管道可以集成到 Customer Insights 中。 
   
## <a name="working-with-azure-machine-learning-sdk"></a>使用 Azure 机器学习 SDK

数据科学家和 AI 开发人员使用 [Azure 机器学习 SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) 生成机器学习工作流。 当前，使用 SDK 训练的模型无法与 Customer Insights 直接集成。 若要与 Customer Insights 集成，需要使用该模型的批处理推理管道。

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>与 Customer Insights 集成的批处理管道要求

### <a name="dataset-configuration"></a>数据集配置

您需要创建数据集，才能使用从 Customer Insights 到批处理推理管道的实体数据。 这些数据集需要在工作区中进行注册。 当前，我们仅支持采用 .csv 格式的[表格数据集](/azure/machine-learning/how-to-create-register-datasets#tabulardataset)。 与实体数据对应的数据集需要参数化为管道参数。
   
* 设计器中的数据集参数
   
     在设计器中，打开 **在数据集中选择列**，然后选择 **设置为管道参数**，可在其中提供参数的名称。

     > [!div class="mx-imgBorder"]
     > ![设计器中的数据集参数化。](media/intelligence-designer-dataset-parameters.png "设计器中的数据集参数化")
   
* SDK 中的数据集参数 (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>批处理推理管道
  
* 在设计器中，训练管道可用于创建或更新推理管道。 当前，仅支持批处理推理管道。

* 使用 SDK，您可以将管道发布到终结点。 当前，Customer Insights 将在机器学习工作区中与批处理管道终结点中的默认管道相集成。
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>将管道数据导入到 Customer Insights 中

* 设计器提供[导出数据模块](/azure/machine-learning/algorithm-module-reference/export-data)，允许将管道的输出导出到 Azure 存储。 当前，模块必须使用数据存储类型 **Azure Blob 存储** 并对 **数据存储** 和相对 **路径** 进行参数化。 Customer Insights 在管道执行期间使用产品可访问的数据存储和路径替代这些参数。
   > [!div class="mx-imgBorder"]
   > ![导出数据模型配置。](media/intelligence-designer-importdata.png "导出数据模型配置")
   
* 在使用代码编写推理输出时，您可以在工作区中将输出上传到 *已注册数据存储* 内的路径。 如果路径和数据存储在管道中进行了参数化，Customer insights 将能够读取和导入推理输出。 当前，支持采用 csv 格式的单个表格输出。 路径必须包含目录和文件名。

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]