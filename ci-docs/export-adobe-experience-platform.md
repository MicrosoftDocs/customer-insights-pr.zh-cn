---
title: 将客户细分导出到 Adobe Experience Platform（预览版）
description: 了解如何在 Adobe Experience Platform 中使用 Customer Insights 客户细分。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195279"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>将客户细分导出到 Adobe Experience Platform（预览版）

将针对相关访问群体的客户细分导出到 Adobe Experience Platform。

:::image type="content" source="media/AEP-flow.png" alt-text="本文中概述的步骤的流程图。":::

## <a name="prerequisites"></a>先决条件

- Adobe Experience Platform 许可证。
- Adobe Campaign Standard 许可证。
- [Azure Blob 存储帐户](/azure/storage/blobs/create-data-lake-storage-account)名称和帐户密钥。 要查找名称和密钥，请参阅[在 Azure 门户中创建存储帐户设置](/azure/storage/common/storage-account-manage)。
- [Azure Blob 存储容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="campaign-overview"></a>市场活动概述

为了更好地了解如何在 Adobe Experience Platform 中使用 Customer Insights 中的客户细分，我们来看一个虚构的示例市场活动。

假设贵公司每月为美国客户提供基于订阅的服务。 您希望确定其订阅应在未来八天内续订但尚未续订的客户。 若要留住这些客户，请使用 Adobe Experience Platform 通过电子邮件向其发送促销优惠。

在此示例中，我们希望运行一次促销电子邮件活动。 本文不涵盖多次运行活动的用例。

## <a name="identify-your-target-audience"></a>确定目标访问群体

在我们的方案中，我们假设客户的电子邮件地址在 Customer Insights 中可用，并分析他们的促销偏好以识别该客户细分的成员。

[您在 Customer Insights 中定义的客户细分](segments.md)称为 **ChurnProneCustomers**，您计划向这些客户发送电子邮件促销信息。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="一个其中创建了 ChurnProneCustomers 客户细分的客户细分页的屏幕截图。":::

您要发出的优惠电子邮件将包含客户的名、姓和订阅结束日期。 它告知客户，如果他们在订阅结束前续订其订阅，他们将获得折扣。

## <a name="export-your-target-audience"></a>导出目标访问群体

我们将配置从 Customer Insights 到 Azure Blob 存储帐户的导出。

### <a name="set-up-connection-to-azure-blob-storage"></a>设置与 Azure Blob 存储的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Blob 存储**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入要将客户细分导出到的 Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。":::

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

### <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Azure Blob 存储部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 选择您要导出的客户细分。 在这个例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> 确保导出的客户细分中的记录数量在 Adobe Campaign Standard 许可证的允许限制范围之内。

导出的数据存储在您配置的 Azure Blob 存储容器中。 将在容器中自动创建以下文件夹路径：

- 对于源实体和由系统生成的实体： 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- 导出实体的 *model.json* 位于 *%ExportDestinationName%* 级别。

  示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>在 Adobe Experience Platform 中定义经验数据模型 (XDM)

在从 Customer Insights 中导出的数据可以在 Adobe Experience Platform 中使用之前，定义体验数据模型架构并[为实时客户配置文件配置数据](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。

了解 [XDM 是什么](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，并了解[架构组合的基础知识](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。

## <a name="import-data-into-adobe-experience-platform"></a>将数据导入 Adobe Experience Platform。

将准备好的访问群体数据从 Customer Insights 导入 Adobe Experience Platform。

1. [创建 Azure Blob 存储源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。

1. 为云存储批量连接[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)，以将客户细分输出从 Customer Insights 导入到 Adobe Experience Platform 中。

## <a name="create-an-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中创建访问群体

若要发送此市场活动的电子邮件，我们将使用 Adobe Campaign Standard。

1. 使用 Adobe Experience Platform 中的数据在 Adobe Campaign Standard 中[创建访问群体](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。

1. 在 Adobe Campaign Standard 中[使用客户细分生成器](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html)基于 Adobe Experience Platform 中的数据定义访问群体。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 创建和发送电子邮件

创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中包含续签优惠的示例电子邮件。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
