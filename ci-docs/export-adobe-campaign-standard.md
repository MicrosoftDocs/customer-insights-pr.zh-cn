---
title: 将 Customer Insights 数据导出到 Adobe Campaign Standard
description: 了解如何在 Adobe Campaign Standard 中使用 Customer Insights 客户细分。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645830"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>在 Adobe Campaign Standard（预览版）中使用 Customer Insights 客户细分

作为 Dynamics 365 Customer Insights 用户，您可能已经创建了客户细分，以通过定位相关访问群体来提高市场营销活动的效率。 要在 Adobe Experience Platform 和 Adobe Campaign Standard 等应用程序中使用 Customer Insights 中的客户细分，您需要遵循本文中概述的几个步骤。

:::image type="content" source="media/ACS-flow.png" alt-text="本文中概述的步骤的流程图。":::

## <a name="prerequisites"></a>先决条件

-   Dynamics 365 Customer Insights 许可证
-   Adobe Campaign Standard 许可证
-   Azure Blob 存储帐户

## <a name="campaign-overview"></a>市场活动概述

为了更好地了解如何在 Adobe Experience Platform 中使用 Customer Insights 中的客户细分，我们来看一个虚构的示例市场活动。

假设贵公司每月为美国客户提供基于订阅的服务。 您希望确定其订阅应在未来八天内续订但尚未续订的客户。 若要留住这些客户，请使用 Adobe Campaign Standard 通过电子邮件向其发送促销优惠。

在此示例中，我们希望运行一次促销电子邮件活动。 本文不涵盖多次运行活动的用例。 但是，也可以将 Customer Insights 和 Adobe Campaign Standard 配置为适用于重复的市场活动场景。

## <a name="identify-your-target-audience"></a>确定目标访问群体

在我们的方案中，我们假设客户的电子邮件地址可用，并分析他们的促销偏好以识别该客户细分的成员。

[您在 Customer Insights 中定义的客户细分](segments.md)称为 **ChurnProneCustomers**，您计划向这些客户发送电子邮件促销信息。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="一个其中创建了 ChurnProneCustomers 客户细分的客户细分页的屏幕截图。":::

您要发出的优惠电子邮件将包含客户的名、姓和订阅结束日期。 它告知客户，如果他们在订阅结束前续订其订阅，他们将获得折扣。

## <a name="export-your-target-audience"></a>导出目标访问群体

### <a name="configure-a-connection"></a>配置连接

确定目标访问群体后，我们可以配置到 Azure Blob 存储帐户的导出。

1. 在 Customer Insights 中，转到 **管理** > **连接**。

1. 选择 **添加连接** 并选择 **Adobe Adobe Campaign** 以配置连接，或在 **Adobe Adobe Campaign** 磁贴中选择 **设置**。

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="配置 Adobe Campaign Standard 的磁贴。":::

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 输入要将客户细分导出到的 Azure Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。"::: 

   - 若要了解有关如何查找 Azure Blob 存储帐户名称和帐户密钥的详细信息，请参阅[管理 Azure 门户中的存储帐户设置](/azure/storage/common/storage-account-manage)。

   - 若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 选择 **保存** 以完成连接。

### <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **用于导出的连接** 字段中，从 Adobe Campaign 部分中选择连接。 如果看不到此部分名称，则没有此类型的连接可用。

1. 选择您要导出的客户细分。 在这个例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. 选择 **下一步**。

1. 现在，我们将 Customer Insights 客户细分中的 **来源** 字段映射到 Adobe Campaign Standard 配置文件架构中的 **目标** 字段名称。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 连接器的字段映射。":::

   如果要添加更多属性，请选择 **添加属性**。 目标名称可以与源字段名称不同，因此如果两个系统中的字段名称不同，您仍然可以将来自 Customer Insights 的客户细分输出映射到 Adobe Campaign Standard。

   > [!NOTE]
   > 电子邮件地址用作身份字段，但您可以使用客户配置文件中的任何其他标识符将数据映射到 Adobe Campaign Standard。

1. 选择 **保存**。

保存导出目标后，您可以在 **数据** > **导出** 上找到该导出目标。

现在，您可以[按需导出客户细分](export-destinations.md#run-exports-on-demand)。 导出也会在每次[计划刷新](system.md)时运行。

> [!NOTE]
> 确保导出的客户细分中的记录数量在 Adobe Campaign Standard 许可证的允许限制范围之内。

导出的数据存储在上面配置的 Azure Blob 存储容器中。 系统在您的容器中自动创建了以下文件夹路径：

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>配置 Adobe Campaign Standard

导出的客户细分包含您在上一步中定义导出目标时选择的列。 这些数据可用于[在 Adobe Campaign Standard 中创建配置文件](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。

若要在 Adobe Campaign Standard 中使用客户细分，需要在 Adobe Campaign Standard 中扩展配置文件方案以再添加两个字段。 了解如何在 Adobe Campaign Standard 中使用新字段[扩展配置文件资源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)。

在我们的示例中，这些字段是 *客户细分名称和客户细分日期（可选）*。

我们将使用这些字段标识 Adobe Campaign Standard 中要充当此市场活动目标的配置文件。

如果除了要导入的记录，Adobe Campaign Standard 中没有其他任何记录，可跳过此步骤。

## <a name="import-data-into-adobe-campaign-standard"></a>将数据导入到 Adobe Campaign Standard 中

现在一切就绪，我们需要将准备好的访问群体数据从 Customer Insights 导入 Adobe Campaign Standard 以创建配置文件。 了解使用工作流[如何在 Adobe Campaign Standard 中导入配置文件](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。

下图中的导入工作流已配置为每八小时运行一次，并查找导出的 Customer Insights 客户细分（Azure Blob 存储中的 .csv 文件）。 此工作流按指定的列顺序提取 .csv 文件内容。 创建此工作流是为了执行基本的错误处理和确保在 Adobe Campaign Standard 中吸入数据之前，每条记录都有一个电子邮件地址。 在更新插入 Adobe Campaign Standard 配置文件数据之前，工作流还会从文件名中提取客户细分名称。

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 用户界面中导入工作流的屏幕截图。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中检索访问群体

将数据导入到 Adobe Campaign Standard 之后，可基于 *客户细分名称* 和 *客户细分日期* 来[创建工作流](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)和[查询](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)客户，以便选择为我们的示例市场活动确定的配置文件。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 创建和发送电子邮件

创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中包含续签优惠的示例电子邮件。":::
