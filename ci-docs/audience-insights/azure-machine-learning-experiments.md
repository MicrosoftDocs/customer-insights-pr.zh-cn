---
title: Azure 机器学习试验
description: 在 Dynamics 365 Customer Insights 中使用基于 Azure 机器学习的模型。
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267895"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="6cb56-103">使用基于 Azure 机器学习的模型</span><span class="sxs-lookup"><span data-stu-id="6cb56-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="6cb56-104">Dynamics 365 Customer Insights 中的统一数据是构建可生成其他业务见解的机器学习模型的来源。</span><span class="sxs-lookup"><span data-stu-id="6cb56-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="6cb56-105">Customer Insights 与机器学习工作室（经典）和 Azure 机器学习集成以使用您自己的自定义模型。</span><span class="sxs-lookup"><span data-stu-id="6cb56-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="6cb56-106">有关基于机器学习工作室（经典）生成的试验示例，请参考[机器学习工作室（经典）试验](machine-learning-studio-experiments.md)。</span><span class="sxs-lookup"><span data-stu-id="6cb56-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6cb56-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="6cb56-107">Prerequisites</span></span>

- <span data-ttu-id="6cb56-108">Customer Insights 访问权限</span><span class="sxs-lookup"><span data-stu-id="6cb56-108">Access to Customer Insights</span></span>
- <span data-ttu-id="6cb56-109">有效的 Azure Enterprise 订阅</span><span class="sxs-lookup"><span data-stu-id="6cb56-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="6cb56-110">统一客户配置文件</span><span class="sxs-lookup"><span data-stu-id="6cb56-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="6cb56-111">已配置[将实体导出到 Azure Blob 存储](export-azure-blob-storage.md)</span><span class="sxs-lookup"><span data-stu-id="6cb56-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="6cb56-112">设置 Azure 机器学习工作区</span><span class="sxs-lookup"><span data-stu-id="6cb56-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="6cb56-113">有关创建工作区的不同选项，请参阅[创建 Azure 机器学习工作区](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace)。</span><span class="sxs-lookup"><span data-stu-id="6cb56-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="6cb56-114">为了获得最佳性能，请在地理位置距离 Customer Insights 环境最近的 Azure 区域中创建工作区。</span><span class="sxs-lookup"><span data-stu-id="6cb56-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="6cb56-115">通过 [Azure 机器学习工作室](https://ml.azure.com/)访问您的工作区。</span><span class="sxs-lookup"><span data-stu-id="6cb56-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="6cb56-116">可通过多种[交互方式](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction)与您的工作区进行交互。</span><span class="sxs-lookup"><span data-stu-id="6cb56-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="6cb56-117">使用 Azure 机器学习设计器</span><span class="sxs-lookup"><span data-stu-id="6cb56-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="6cb56-118">Azure 机器学习设计器提供了一个视觉对象画布，您可以在其中拖放数据集和模块，这类似于机器学习工作室（经典）。</span><span class="sxs-lookup"><span data-stu-id="6cb56-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="6cb56-119">如果进行了相应配置，从设计器创建的批处理管道可以集成到 Customer Insights 中。</span><span class="sxs-lookup"><span data-stu-id="6cb56-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="6cb56-120">使用 Azure 机器学习 SDK</span><span class="sxs-lookup"><span data-stu-id="6cb56-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="6cb56-121">数据科学家和 AI 开发人员使用 [Azure 机器学习 SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) 生成机器学习工作流。</span><span class="sxs-lookup"><span data-stu-id="6cb56-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="6cb56-122">当前，使用 SDK 训练的模型无法与 Customer Insights 直接集成。</span><span class="sxs-lookup"><span data-stu-id="6cb56-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="6cb56-123">若要与 Customer Insights 集成，需要使用该模型的批处理推理管道。</span><span class="sxs-lookup"><span data-stu-id="6cb56-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="6cb56-124">与 Customer Insights 集成的批处理管道要求</span><span class="sxs-lookup"><span data-stu-id="6cb56-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="6cb56-125">数据集配置</span><span class="sxs-lookup"><span data-stu-id="6cb56-125">Dataset Configuration</span></span>

<span data-ttu-id="6cb56-126">您需要创建数据集，才能使用从 Customer Insights 到批处理推理管道的实体数据。</span><span class="sxs-lookup"><span data-stu-id="6cb56-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="6cb56-127">这些数据集需要在工作区中进行注册。</span><span class="sxs-lookup"><span data-stu-id="6cb56-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="6cb56-128">当前，我们仅支持采用 .csv 格式的[表格数据集](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset)。</span><span class="sxs-lookup"><span data-stu-id="6cb56-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="6cb56-129">与实体数据对应的数据集需要参数化为管道参数。</span><span class="sxs-lookup"><span data-stu-id="6cb56-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="6cb56-130">设计器中的数据集参数</span><span class="sxs-lookup"><span data-stu-id="6cb56-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="6cb56-131">在设计器中，打开 **在数据集中选择列**，然后选择 **设置为管道参数**，可在其中提供参数的名称。</span><span class="sxs-lookup"><span data-stu-id="6cb56-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="6cb56-132">![设计器中的数据集参数化](media/intelligence-designer-dataset-parameters.png "设计器中的数据集参数化")</span><span class="sxs-lookup"><span data-stu-id="6cb56-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="6cb56-133">SDK 中的数据集参数 (Python)</span><span class="sxs-lookup"><span data-stu-id="6cb56-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="6cb56-134">批处理推理管道</span><span class="sxs-lookup"><span data-stu-id="6cb56-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="6cb56-135">在设计器中，训练管道可用于创建或更新推理管道。</span><span class="sxs-lookup"><span data-stu-id="6cb56-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="6cb56-136">当前，仅支持批处理推理管道。</span><span class="sxs-lookup"><span data-stu-id="6cb56-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="6cb56-137">使用 SDK，您可以将管道发布到终结点。</span><span class="sxs-lookup"><span data-stu-id="6cb56-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="6cb56-138">当前，Customer Insights 将在机器学习工作区中与批处理管道终结点中的默认管道相集成。</span><span class="sxs-lookup"><span data-stu-id="6cb56-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="6cb56-139">将管道数据导入到 Customer Insights 中</span><span class="sxs-lookup"><span data-stu-id="6cb56-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="6cb56-140">设计器提供[导出数据模块](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data)，允许将管道的输出导出到 Azure 存储。</span><span class="sxs-lookup"><span data-stu-id="6cb56-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="6cb56-141">当前，模块必须使用数据存储类型 **Azure Blob 存储** 并对 **数据存储** 和相对 **路径** 进行参数化。</span><span class="sxs-lookup"><span data-stu-id="6cb56-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="6cb56-142">Customer Insights 在管道执行期间使用产品可访问的数据存储和路径替代这些参数。</span><span class="sxs-lookup"><span data-stu-id="6cb56-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6cb56-143">![导出数据模型配置](media/intelligence-designer-importdata.png "导出数据模型配置")</span><span class="sxs-lookup"><span data-stu-id="6cb56-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="6cb56-144">在使用代码编写推理输出时，您可以在工作区中将输出上传到 *已注册数据存储* 内的路径。</span><span class="sxs-lookup"><span data-stu-id="6cb56-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="6cb56-145">如果路径和数据存储在管道中进行了参数化，Customer insights 将能够读取和导入推理输出。</span><span class="sxs-lookup"><span data-stu-id="6cb56-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="6cb56-146">当前，支持采用 csv 格式的单个表格输出。</span><span class="sxs-lookup"><span data-stu-id="6cb56-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="6cb56-147">路径必须包含目录和文件名。</span><span class="sxs-lookup"><span data-stu-id="6cb56-147">The path must include the directory and filename.</span></span>

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