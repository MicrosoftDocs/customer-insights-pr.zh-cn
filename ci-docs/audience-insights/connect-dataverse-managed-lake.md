---
title: 在 Microsoft Dataverse 中连接到表
description: 从 Microsoft Dataverse 托管数据湖导入数据。
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 81412ea8259e690eb839676d82ab31847854a97e
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464055"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>连接到 Microsoft Dataverse 托管数据湖中的数据

本文提供了有关 Dataverse 用户如何在 Microsoft Dataverse 托管湖中快速连接到分析实体的信息。 

> [!NOTE]
> 您必须是 Dataverse 组织的管理员才能继续查看托管湖中可用的实体列表。

## <a name="important-considerations"></a>重要考虑因素

1. 可以将联机服务（如 Azure Data Lake Storage）中存储的数据存储到 Dynamics 365 Customer Insights 中处理或存储数据之外的位置。导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心](https://www.microsoft.com/trust-center)。
2. 只有启用了[更改跟踪](/power-platform/admin/enable-change-tracking-control-data-synchronization)的 Dataverse 实体可见。 这些实体可以导出到 Dataverse 托管的数据湖并在 Customer Insights 中使用。 现成可用的 Dataverse 表默认已启用更改跟踪。 您需要为自定义表打开更改跟踪。 要检查 Dataverse 表是否启用了更改跟踪，请转到 [Power Apps](https://make.powerapps.com) > **数据** > **表**。 查找您感兴趣的表并选择它。 转到 **设置** > **高级选项**，查看 **跟踪更改** 设置。

## <a name="connect-to-a-dataverse-managed-lake"></a>连接到 Dataverse 托管湖

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择 **添加数据源**。

3. 选择 **Microsoft Dataverse**，然后选择 **下一步**。

4. 输入数据源的 **名称**，然后选择 **下一步**。 

5. 为 Dataverse 组织提供 **服务器地址**，然后选择 **登录**。

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="用户可以在其中输入 Dataverse 环境 URL 的数据引入步骤中的屏幕。":::

6. 从可用列表中选择要作为实体引入到访问群体见解中的表。    

   > [!NOTE]
   > 如果已选择某些表，则其他 Dynamics 365 应用程序（例如 Dynamics 365 Sales Insights 或 Customer Service Insights）可能会使用它们。 您不能更改此选择。 创建数据源后，这些表将可用作实体。

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="显示 Dataverse 环境中的实体列表的对话框。":::

7. 保存您的选择，以开始同步 Dataverse 中的选定表。 您将在 **数据源** 页上找到新添加的连接。 它将排队等待刷新并将实体计数显示为 0，直到同步了所有选定表为止。

仅环境中的一个数据源可以同时使用相同的 Dataverse 托管湖。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>编辑 Dataverse 托管湖数据源

您仅在创建数据源之后才编辑对实体的选择。 例如，如果其他实体被添加到 Dataverse 中，并且您也希望导入它们。    
要连接到不同的 Dataverse Data Lake，请[创建新数据源](#connect-to-a-dataverse-managed-lake)。

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择要更新的数据源旁边的省略号。

3. 从列表中选择 **编辑** 选项。

4. 从可用实体列表中选择其他实体，然后选择 **保存**。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
