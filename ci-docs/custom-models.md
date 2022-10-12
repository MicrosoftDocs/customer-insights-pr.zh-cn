---
title: 自定义机器学习模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用来自 Azure 机器学习的自定义模型。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609730"
---
# <a name="custom-machine-learning-models"></a>自定义机器学习模型

> [!NOTE]
> 对机器学习工作室（经典）的支持将于 2024 年 8 月 31 日结束。 我们建议您在该日期之前过渡到 [Azure 机器学习](/azure/machine-learning/overview-what-is-azure-machine-learning)。
>
> 自 2021 年 12 月 1 日起，您将无法创建新的机器学习工作室（经典）资源。 截止到 2024 年 8 月 31 日，您可以继续使用现有机器学习工作室（经典）资源。 有关详细信息，请参阅[迁移到 Azure 机器学习](/azure/machine-learning/migrate-overview)。

自定义模型允许您基于 Azure 机器学习模型管理工作流。 工作流帮助您选择要从中生成见解的数据，并将结果映射到统一客户数据。 有关生成自定义 ML 模型的详细信息，请参阅[使用基于 Azure 机器学习的模型](azure-machine-learning-experiments.md)。

## <a name="prerequisites"></a>先决条件

- 通过 [Azure 机器学习批处理管道](/azure/machine-learning/concept-ml-pipelines)发布的 Web 服务。
- 管道必须在[管道终结点](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)下发布。
- 与 Azure Studio 实例关联的 [Azure Data Lake Gen2 存储帐户](/azure/storage/blobs/data-lake-storage-quickstart-create-account)。
- 对于具有管道的 Azure 机器学习工作区，具有针对 Azure 机器学习工作区的负责人或用户访问管理员权限。

  > [!NOTE]
  > 数据是在 Customer Insights 实例和工作流中的所选 Azure Web 服务或管道之间传输的。 将数据传输至 Azure 服务时，请确保服务已配置为按照所需的方式和位置处理数据，以符合组织数据的任何法律或法规要求。

## <a name="add-a-new-workflow"></a>添加新工作流

1. 转到 **智能** > **自定义模型** 并选择 **新工作流**。

1. 提供一个可识别的 **名称**。

   :::image type="content" source="media/new-workflowv2.png" alt-text="“新建工作流”窗格的屏幕截图。":::

1. 在 **包含 Web 服务的租户** 中，选择包含 Web 服务的组织。

1. 如果您的 Azure 机器学习订阅与 Customer Insights 在不同的租户中，请为所选组织选择使用您的凭据 **登录**。

1. 选择与您的 Web 服务相关联的 **工作区**。

1. 在 **包含您的模型的 Web 服务** 下拉列表中选择 Azure 机器学习管道。 然后选择 **下一步**。
   了解有关[使用设计器在 Azure 机器学习中发布管道](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)或使用 [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 进行发布的详细信息。

1. 从 Customer Insights 中为每个 **Web 服务输入** 选择匹配的 **实体**。 然后选择 **下一步**。
   > [!NOTE]
   > 自定义模型工作流将应用启发式方法，根据字段的名称和数据类型将 Web 服务输入字段映射到实体属性。 如果 Web 服务字段无法映射到实体，将出现错误。

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="配置工作流。":::

1. 对于 **模型输出参数**，设置以下属性：
   - 管道输出结果的 **实体名称**
   - 批处理管道的 **输出数据存储参数名称**
   - 批处理管道的 **输出路径参数名称**

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="模型输出参数窗格。":::

1. 从 **结果中的客户 ID** 中选择标识客户的匹配属性，然后选择 **保存**。

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="将结果与客户数据关联窗格。":::

   **已保存工作流** 屏幕将显示有关工作流的详细信息。 如果为 Azure 机器学习管道配置了工作流，Customer Insights 会附加到包含该管道的工作区。 Customer Insights 将在 Azure 工作区上获得 **参与者** 角色。

1. 选择 **完成**。 将显示 **自定义模型** 页面。

1. 选择工作流的垂直省略号 (&vellip;)，然后选择 **运行**。 您的工作流也会在每次[计划刷新](schedule-refresh.md)后自动运行。

## <a name="manage-an-existing-workflow"></a>管理现有工作流

转到 **智能** > **自定义模型** 查看您创建的工作流。

选择工作流查看可用操作。

- **编辑** 工作流
- **运行** 工作流
- [**删除**](#delete-a-workflow)工作流

### <a name="edit-a-workflow"></a>编辑工作流

1. 转到 **智能** > **自定义模型**。

1. 在要更新的工作流旁边，选择垂直省略号 (&vellip;)，然后选择 **编辑**。

1. 根据需要更改 **显示名称**，然后选择 **下一步**。

1. 对于每个 **Web 服务输入**，您可以根据需要从 Customer Insights 中更新匹配的 **实体**。 然后选择 **下一步**。

1. 对于 **模型输出参数**，更改以下任意内容：
   - 管道输出结果的 **实体名称**
   - 批处理管道的 **输出数据存储参数名称**
   - 批处理管道的 **输出路径参数名称**

1. 更改 **结果中的客户 ID** 中的匹配属性以识别客户。 从包含类似于客户实体的客户 ID 列的值的推理输出中选择一个属性。 如果您的数据集中没有这样的列，请选择可唯一标识该行的属性。

1. 选择 **保存**

### <a name="delete-a-workflow"></a>删除工作流

1. 转到 **智能** > **自定义模型**。

1. 在要删除的工作流旁边，选择垂直省略号 (&vellip;)，然后选择 **删除**。

1. 确认删除。

将删除您的工作流。 您创建工作流时创建的 [实体](entities.md)将保留，并且可以从 **数据** > **实体** 页查看。

## <a name="view-the-results"></a>查看结果

工作流的结果存储在为 **模型输出参数** 定义的实体名称中。 从 [**数据** > **实体** 页面](entities.md)或通过 [API 访问](apis.md)访问此数据。

### <a name="api-access"></a>API 访问

对于从自定义模型实体获取数据的特定 OData 查询，请使用以下格式：

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. 将 `<your instance id>` 替换为您的 Customer Insights 环境的 ID，该 ID 将在访问 Customer Insights 时显示在浏览器的地址栏中。

1. 将 `<custom model output entity>` 替换为您为 **模型输出参数** 提供的实体名称。

1. 将 `<guid value>` 替换为您要访问的客户的客户 ID。 此 ID 将显示在[客户配置文件页](customer-profiles.md)的 CustomerID 字段中。

## <a name="frequently-asked-questions"></a>常见问题

- 为什么在设置自定义模型工作流时看不到我的管道？
  此问题通常由于管道中的配置问题所导致。 确保[配置了输入参数](azure-machine-learning-experiments.md#dataset-configuration)，并且还配置了[输出数据存储和路径参数](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights)。

- “无法保存智能工作流”错误是什么意思？ 
  如果用户对工作区没有“负责人”或“用户访问管理员”特权，则通常会看到此错误消息。 用户需要更高级别的权限才能使 Customer Insights 能够将工作流作为服务处理，而非使用用户凭据处理工作流的后续运行。

- 我的自定义模型工作流是否支持专用终结点/专用链接？
  Customer Insights 目前不现成支持自定义模型的专用终结点，但提供了手动解决方法。 请联系客户支持了解详细信息。

## <a name="responsible-ai"></a>负责 AI

预测提供创建更好的客户体验、改进业务功能和创收流的功能。 强烈建议您在预测针对其影响的价值以及以道德方式引入的偏见之间进行权衡。 了解有关 Microsoft 如何[处理负责 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) 的详细信息。 您还可以了解特定于 Azure 机器学习的[负载机器学习的技术和流程](/azure/machine-learning/concept-responsible-ml)。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
