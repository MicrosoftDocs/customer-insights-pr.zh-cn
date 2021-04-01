---
title: 将 Customer Insights 数据导出到 Adobe 体验平台
description: 了解如何在 Adobe 体验平台中使用访问群体见解客户细分。
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596258"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>在 Adobe 体验平台（预览版）中使用 Customer Insights 客户细分。

作为 Dynamics 365 Customer Insights 访问群体见解的用户，您可能创建了多个客户细分，以通过确定目标访问群体来提高市场营销活动效率。 要使用 Adobe 体验平台和应用程序（如 Adobe Campaign Standard）内访问群体见解中的客户细分，您需要执行本文中概述的几个步骤。

:::image type="content" source="media/AEP-flow.png" alt-text="本文中概述的步骤的流程图。":::

## <a name="prerequisites"></a>先决条件

-   Dynamics 365 Customer Insights 许可证
-   Adobe 体验平台许可证
-   Adobe Campaign Standard 许可证
-   Azure Blob 存储帐户

## <a name="campaign-overview"></a>市场活动概述

为了更好地了解如何使用 Adobe 体验平台内访问群体见解中的客户细分，我们来看看虚构的示例活动。

假设贵公司每月为美国客户提供基于订阅的服务。 您希望确定其订阅应在未来八天内续订但尚未续订的客户。 为了留住这些客户，您希望使用 Adobe 体验平台通过电子邮件向他们发送促销优惠。

在此示例中，我们希望运行一次促销电子邮件活动。 本文不涵盖多次运行活动的用例。

## <a name="identify-your-target-audience"></a>确定目标访问群体

在我们的情景中，我们假设客户的电子邮件地址在访问群体见解中可用，并分析了他们的促销偏好，以确定该客户细分的成员。

[您在访问群体见解中定义的客户细分](segments.md)称为 **ChurnProneCustomers**，您计划向这些客户发送电子邮件促销。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="一个其中创建了 ChurnProneCustomers 客户细分的客户细分页的屏幕截图。":::

您要发出的优惠电子邮件将包含客户的名、姓和订阅结束日期。 它告知客户，如果他们在订阅结束前续订其订阅，他们将获得折扣。

## <a name="export-your-target-audience"></a>导出目标访问群体

通过确定目标访问群体，我们可以配置从访问群体见解导出到 Azure Blob 存储帐户。

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **Azure Blob 存储** 磁贴中，选择 **设置**。

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob 存储的配置磁贴。":::

1. 为这个新的导出目的地提供 **显示名称**，然后输入您希望将该客户细分导出到的 Azure Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。"::: 

   - 若要了解有关如何查找 Azure Blob 存储账户名称和帐户密钥的详细信息，请参阅[管理 Azure 门户中的存储帐户设置](/azure/storage/common/storage-account-manage)。

   - 若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 选择 **下一步**。

1. 选择您要导出的客户细分。 在这个例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. 选择 **保存**。

保存导出目的地后，您可以在 **管理** > **导出** > **我的导出目的地** 中找到它。

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="包含导出列表和突出显示的示例客户细分的屏幕截图。":::

现在，您可以[按需导出客户细分](export-destinations.md#export-data-on-demand)。 导出也会在每次[计划刷新](system.md)时运行。

> [!NOTE]
> 确保导出的客户细分的记录数量在 Adobe Campaign Standard 许可证的允许限度内。

导出的数据存储在上面配置的 Azure Blob 存储容器中。 系统在您的容器中自动创建了以下文件夹路径：

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

导出实体的 *model.json* 位于 *%ExportDestinationName%* 级别。

示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>在 Adobe 体验平台中定义体验数据模型 (XDM) 

在 Adobe 体验平台中使用访问群体见解中的导出数据之前，您需要定义“体验数据模型”架构并[配置实时客户配置文件的数据](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。

了解 [XDM 是什么](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，并了解[架构组合的基础知识](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。

## <a name="import-data-into-adobe-experience-platform"></a>将数据导入 Adobe 体验平台

现在一切都准备好了，我们需要将访问群体见解中准备好的访问群体数据导入到 Adobe 体验平台。

首先，[创建 Azure Blob 存储源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。    

定义源连接后，为云存储批处理连接[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)，以将访问群体见解中的客户细分输出导入到 Adobe 体验平台中。

## <a name="create-an-audience-in-adobe-campaign-standard"></a>在 Adobe Campaign Standard 中创建访问群体

为了发送此市场活动的电子邮件，我们将使用 Adobe Campaign Standard。 将数据导入到 Adobe 体验平台后，我们需要使用 Adobe 体验平台中的数据在 Adobe Campaign Standard 中[创建一个访问群体](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。

了解如何在 Adobe Campaign Standard 中[使用客户细分生成器](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment)，以基于 Adobe 体验平台中的数据定义访问群体。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 创建和发送电子邮件

创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中的包含续订优惠的样本电子邮件。":::