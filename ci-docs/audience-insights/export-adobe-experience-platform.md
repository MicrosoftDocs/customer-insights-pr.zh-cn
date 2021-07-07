---
title: 将 Customer Insights 数据导出到 Adobe 体验平台
description: 了解如何在 Adobe 体验平台中使用访问群体见解客户细分。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305513"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>在 Adobe 体验平台（预览版）中使用 Customer Insights 客户细分。

作为 Dynamics 365 Customer Insights 中访问群体见解的用户，您可能创建了客户细分，通过定位相关访问群体使市场营销活动更高效。 要使用 Adobe 体验平台和应用程序（如 Adobe Campaign Standard）内访问群体见解中的客户细分，您需要执行本文中概述的几个步骤。

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

### <a name="configure-a-connection"></a>配置连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Blob 存储**，或在 **Azure Blob 存储** 磁贴中选择 **设置** 以配置连接。

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob 存储的配置磁贴。"::: 

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入要将客户细分导出到的 Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。"::: 
   
    - 若要了解有关如何查找 Blob 存储帐户名称和帐户密钥的详细信息，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。
    - 若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 选择 **保存** 以完成连接。 

### <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Azure Blob 存储部分选择连接。 如果看不到此部分名称，则没有此类型的连接可用。

1. 选择您要导出的客户细分。 在这个例子中，它是 **ChurnProneCustomers**。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. 选择 **保存**。

保存导出目标后，您可以在 **数据** > **导出** 上找到该导出目标。

现在，您可以[按需导出客户细分](export-destinations.md#run-exports-on-demand)。 导出也会在每次[计划刷新](system.md)时运行。

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

若要发送此市场活动的电子邮件，我们将使用 Adobe Campaign Standard。 将数据导入到 Adobe 体验平台后，我们需要使用 Adobe 体验平台中的数据在 Adobe Campaign Standard 中[创建一个访问群体](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。


了解如何在 Adobe Campaign Standard 中[使用客户细分生成器](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html)，以基于 Adobe 体验平台中的数据定义访问群体。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>使用 Adobe Campaign Standard 创建和发送电子邮件

创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中的包含续订优惠的样本电子邮件。":::
