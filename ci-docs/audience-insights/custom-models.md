---
title: 自定义机器学习模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用来自 Azure 机器学习的自定义模型。
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668892"
---
# <a name="custom-machine-learning-models"></a>自定义机器学习模型

**智能** > **自定义模型** 允许您基于 Azure 机器学习模型管理工作流。 工作流帮助您选择要从中生成见解的数据，并将结果映射到统一客户数据。 有关生成自定义 ML 模型的详细信息，请参阅[使用基于 Azure 机器学习的模型](azure-machine-learning-experiments.md)。

## <a name="responsible-ai"></a>负责 AI

预测提供创建更好的客户体验、改进业务功能和创收流的功能。 强烈建议您在预测针对其影响的价值以及以道德方式引入的偏见之间进行权衡。 了解有关 Microsoft 如何[处理负责 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) 的详细信息。 您还可以了解特定于 Azure 机器学习的[负载机器学习的技术和流程](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml)。

## <a name="prerequisites"></a>先决条件

- 当前，此功能支持通过[机器学习工作室（经典）](https://studio.azureml.net)和 [Azure 机器学习批处理管道](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines)发布的 Web 服务。

- 您需要与 Azure Studio 实例关联的 Azure Data Lake Gen2 存储帐户才能使用此功能。 有关详细信息，请参阅[创建 Azure Data Lake Storage Gen2 存储帐户](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>添加新工作流

1. 转到 **智能** > **自定义模型** 并选择 **新工作流**。

1. 在 **名称** 字段中为自定义模型指定易于识别的名称。

   > [!div class="mx-imgBorder"]
   > ![“新建工作流”窗格的屏幕截图](media/new-workflowv2.png "“新建工作流”窗格的屏幕截图")

1. 在 **包含 Web 服务的租户** 中，选择包含 Web 服务的组织。

1. 如果您的 Azure 机器学习订阅与 Customer Insights 在不同的租户中，请为所选组织选择使用您的凭据 **登录**。

1. 选择与您的 Web 服务相关联的 **工作区**。 其中列出了两个部分，一个用于 Azure 机器学习 v1（机器学习工作室（经典）），另一个用于 Azure 机器学习 v2（Azure 机器学习）。 如果您不确定哪个工作区适合您的机器学习工作室（经典）Web 服务，请选择 **任意**。

1. 在 **包含您的模型的 Web 服务** 下拉菜单中选择机器学习工作室（经典）Web 服务或 Azure 机器学习管道。 然后选择 **下一步**。
   - 了解有关[在机器学习工作室（经典）中发布 Web 服务](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)的详细信息
   - 了解有关[使用设计器在 Azure 机器学习中发布管道](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)或使用 [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 进行发布的详细信息。 
     > [!NOTE]
     > 您的管道必须在[管道终结点](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)下发布。

1. 对于每个 **Web 服务输入**，从访问群体见解中选择匹配的 **实体**，然后选择 **下一步**。

   > [!div class="mx-imgBorder"]
   > ![配置工作流](media/intelligence-screen2-updated.png "配置工作流")

1. 在 **模型输出参数** 步骤中，设置以下属性：
   - 机器学习工作室（经典）
      1. 输入您希望 Web 服务输出结果流入的输出 **实体名称**。
   - Azure 机器学习
      1. 输入您希望管道输出结果流入的输出 **实体名称**。
      1. 从下拉列表中选择批处理管道的 **输出数据存储参数名称**。
      1. 从下拉列表中选择批处理管道的 **输出路径参数名称**。
      
      > [!div class="mx-imgBorder"]
      > ![模型输出参数窗格](media/intelligence-screen3-outputparameters.png "模型输出参数窗格")

1. 从 **结果中的客户 ID** 下拉列表中选择标识客户的匹配属性，然后选择 **保存**。
   
   > [!div class="mx-imgBorder"]
   > ![将结果与客户数据关联窗格](media/intelligence-screen4-relatetocustomer.png "将结果与客户数据关联窗格")

1. 您将看到 **已保存工作流** 屏幕，其中包含有关工作流的详细信息。    
   如果您为 Azure 机器学习管道配置了工作流，访问群体见解将附加到包含该管道的工作区。 访问群体见解将在 Azure 工作区上获取 **参与者** 角色。

1. 选择 **完成**。

1. 现在，您可以从 **自定义模型** 页面运行工作流。

## <a name="edit-a-workflow"></a>编辑工作流

1. 在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号，然后选择 **编辑**。

1. 您可以在 **显示名称** 字段中更新工作流的可识别名称，但不能更改已配置的 Web 服务或管道。 选择 **下一步**。

1. 对于每个 **Web 服务输入**，您可以从访问群体见解中更新匹配的 **实体**。 然后选择 **下一步**。

1. 在 **模型输出参数** 步骤中，设置以下属性：
   - 机器学习工作室（经典）
      1. 输入您希望 Web 服务输出结果流入的输出 **实体名称**。
   - Azure 机器学习
      1. 输入您希望管道输出结果流入的输出 **实体名称**。
      1. 选择测试管道的 **输出数据存储参数名称**。
      1. 选择测试管道的 **输出路径参数名称**。

1. 从 **结果中的客户 ID** 下拉列表中选择标识客户的匹配属性，然后选择 **保存**。
   您需要从包含类似于客户实体的客户 ID 的值的推理输出中选择一个属性。 如果您的数据集中没有这样的列，请选择可唯一标识该行的属性。

## <a name="run-a-workflow"></a>运行工作流

1. 在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号。

1. 选择 **运行**。

您的工作流也会在每次计划刷新后自动运行。 了解有关[设置计划刷新](system.md#schedule-tab)的详细信息。

## <a name="delete-a-workflow"></a>删除工作流

1. 在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号。

1. 选择 **删除**，然后确认删除。

将删除您的工作流。 您创建工作流时创建的 [实体](entities.md)将保留，并且可以从 **实体** 页查看。
