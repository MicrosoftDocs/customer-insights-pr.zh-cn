---
title: 查看客户配置文件
description: 查看统一客户数据，包括使用搜索和筛选器
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303772"
---
# <a name="view-customer-profiles"></a>查看客户配置文件

[创建统一的 *客户* 实体](data-unification.md)之后，客户配置文件可用。 统一客户配置文件的组合视图在 **客户** 页面上显示。 客户可以是个人或组织。

转到 **客户** 页面查看您的客户及其配置文件。 每个客户配置文件由一个磁贴表示。 使用分页控件可以获取更多记录。 此卡显示 **搜索和筛选索引** 中定义的 *客户* 实体中的字段。 每个卡中字段的顺序由系统选择。

> [!NOTE]
> 如果您选择 **客户** 时看不到磁贴，您的管理员需要在 **搜索和筛选索引** 中[定义至少一个可搜索属性](search-filter-index.md)。

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="显示结果磁贴的客户页面。":::

选择以下任一操作：
- [查看客户详细信息](#view-customer-details)
- [管理搜索和筛选索引](search-filter-index.md)（仅管理员）
- [筛选客户](#filter-customers)
- **展开卡** 或 **折叠卡** 来展开或折叠客户磁贴上显示的信息
- 按特定属性 **排序**
- [搜索客户](#search-for-customers)

  > [!NOTE]
  > 要使用搜索和筛选，管理员必须配置可搜索属性并使用搜索和筛选索引定义可筛选字段。

## <a name="search-for-customers"></a>搜索客户

通过在 **搜索客户** 中输入名称或其他某个属性搜索客户。 可搜索属性由管理员定义，来自统一的 *客户* 实体。

> [!NOTE]
> **字符串** 是搜索中包括的唯一数据类型。 在客户页面的 **搜索客户** 字段中使用它来搜索客户。

## <a name="filter-customers"></a>筛选客户

按 *客户* 实体字段筛选客户。 可筛选字段由管理员定义。

1. 在 **客户** 页上，选择 **显示筛选器**。 筛选器窗格将显示。

1. 选中要充当客户搜索依据的属性旁边的框。

1. 通过选择 **清除筛选器** 或清除所选属性旁边的复选框来删除所有筛选器。

1. 选择 **隐藏筛选器** 可以关闭筛选器窗格。

1. 要将筛选结果保存为 [客户细分](segments.md)，选择 **将筛选另存为客户细分**。
   1. 为客户细分输入名称。
   1. 选择 **保存** 保存客户细分。
   1. 选择是通过选择 **激活** 来立即运行客户细分还是 **以后** 运行。

## <a name="view-customer-details"></a>查看客户详细信息

在 **客户** 页面上，选择客户磁贴查看所选客户的详细信息。

:::image type="content" source="media/customers-details-B2C.png" alt-text="客户详细信息页面。":::

客户详细信息包括:

**客户配置文件磁贴** 显示统一 *客户* 实体的不同值。 如果字段没有所选客户资料的值，除非是地址字段，否则不会显示。 磁贴分为几个部分：

- 第一个部分显示一组预定义的字段，后跟属于搜索和筛选索引的所有字段。 所有与地址相关的字段都将合并为一行，即使资料不包含地址信息，这一行也会显示。
- **此客户的联系人** 显示在企业客户（企业对企业）环境中。 每个联系人都显示有他们的字段。 空字段会被隐藏。
- **其他字段** 显示选定客户的其余字段（除 ID 之外）。
- **ID** 列出其相应实体名称下的所有 ID。 字段按语义使用 ID 标识。

**活动时间线** 在您配置了[活动](activities.md)时显示数据。 时间线视图包含所选客户按时间顺序排序的活动，从最近的活动开始。

**见解**：

- **度量** 在您配置了[客户属性度量值](measures.md)时显示。 它们包括针对各个客户级别的客户的计算 KPI。

- **潜在兴趣、潜在品牌** 在您配置了[品牌或兴趣相似性扩充](enrichment-microsoft.md)时显示。 它表示基于与所选客户配置文件相似的其他客户的品牌的潜在兴趣和相似性。

要返回 **客户** 页面，选择 **返回到客户**。

## <a name="next-steps"></a>后续步骤

[添加更多数据源](data-sources.md)、[扩充统一配置文件](enrichment-hub.md)或[创建客户细分](segments.md)以在其他应用程序中使用统一的客户配置文件。

[!INCLUDE [footer-include](includes/footer-banner.md)]
