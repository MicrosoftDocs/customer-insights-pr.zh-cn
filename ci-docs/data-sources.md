---
title: 数据源概述
description: 了解如何从各种源导入或导入数据。
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245638"
---
# <a name="data-sources-overview"></a>数据源概述

Dynamics 365 Customer Insights 提供连接来从广泛的源获取数据。 连接到数据源通常称为 *数据引入* 过程。 引入数据后，您可以[统一](data-unification.md)、生成见解以及激活数据来构建个性化体验。

## <a name="add-or-edit-data-sources"></a>添加或编辑数据源

您可以将数据源附加或导入到 Customer Insights。 下面的链接提供了添加和编辑数据源的说明。

**附加数据源**

如果您在 Microsoft 的 Azure 数据服务之一中准备了数据，Customer Insights 可以轻松连接到数据源，而无需重新引入数据。 请选择以下选项之一：
- [Azure Data Lake Storage（Common Data Model 文件夹中的 csv 或 Parquet 文件）](connect-common-data-model.md)
- [Azure Synapse Analytics（湖数据库）](connect-synapse.md)
- [Microsoft Dataverse data lake](connect-dataverse-managed-lake.md)

**导入和转换**

如果您使用本地数据源、Microsoft 或第三方数据，请使用 Power Query 连接器导入和转换数据。
- [Power Query 连接器](connect-power-query.md)

## <a name="review-data-sources"></a>查看数据源

如果您的环境配置为使用 Customer Insights 存储并且您使用本地数据源，您将使用 Power Platform 数据流。 使用 Power Platform 数据流，您可以查看共享数据源和其他人管理的数据源。 **数据源** 页面分三个部分列出数据源：
- **共享**：可由所有 Customer Insights 管理员管理的数据源。 Power Platform 数据流、您自己的存储帐户以及附加到 Dataverse 托管的数据湖是共享数据源的示例。
- **由我管理**：Power Platform 数据流被创建，只由您管理。 其他 Customer Insights 管理员只能查看这些数据流，不能编辑、刷新或删除它们。
- **由其他人管理**：由其他管理员创建的 Power Platform 数据流。 您只能查看这些数据流。 其中将列出数据流的负责人，可以向其寻求帮助。
> [!NOTE]
> 其他用户可以查看和使用所有实体。 虽然数据源归创建它们的用户所有，但通过数据引入生成的实体可供 Customer Insights 的每个用户使用。

如果您的环境不使用 Power Platform 数据流，**数据源** 页面仅包含所有数据源的列表。 不显示任何部分。

## <a name="manage-existing-data-sources"></a>管理现有数据源

转到 **数据** > **数据源** 查看每个引入的数据源的名称、状态以及上次为该源刷新数据的时间。 您可以按任何列对数据源列表进行排序，或使用搜索框查找要管理的数据源。

选择数据源查看可用操作。

:::image type="content" source="media/data_sources_showmore.png" alt-text="已添加数据源。":::

- [**编辑**](#add-or-edit-data-sources)数据源更改其属性。
- [**刷新**](#refresh-data-sources)数据源以包括最新数据。
- 在统一之前 [**扩充**](data-sources-enrichment.md)数据源。
- **删除** 数据源。 仅当数据未用于任何处理（如统一、见解、激活或导出）时，才能删除数据源。

## <a name="refresh-data-sources"></a>刷新数据源

数据源可以按计划自动刷新，也可以根据需要手动刷新。 [本地数据源](connect-power-query.md#add-data-from-on-premises-data-sources)根据数据引入期间设置的数据源自己的计划刷新。 对于附加的数据源，数据引入会使用该数据源中可用的最新数据。

转到 **管理** > **系统** > [**计划**](schedule-refresh.md)配置引入的数据源的系统计划刷新。

要按需刷新数据源：

1. 转到 **数据** > **数据源**。

1. 选择要刷新的数据源，然后选择 **刷新**。 现在，将为数据源触发手动刷新。 刷新数据源将更新数据源中指定的所有实体的实体架构和数据。

1. 选择状态打开 **进度详细信息** 窗格，查看进度。 要取消作业，选择窗格底部的 **取消作业**。

[!INCLUDE [footer-include](includes/footer-banner.md)]
