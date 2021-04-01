---
title: 查看客户配置文件
description: 获取统一客户数据的组合视图。
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596856"
---
# <a name="customer-profiles"></a>客户配置文件

**客户** 页面显示客户的组合视图，基于从[所有数据源](data-sources.md)收集的配置文件数据。 [创建统一的客户实体](data-unification.md)之后，客户配置文件可用。 确保完成数据统一过程以获得更丰富的客户视图。 还可以通过此页面搜索客户。

客户可以是个人，也可以是组织（预览）。 每个客户或组织配置文件通过磁贴表示。 选择磁贴可查看有关这个具体客户或组织的更多信息。 可使用页面底部的翻页控件查看更多记录。

> [!div class="mx-imgBorder"] 
> ![B2C 客户配置文件](media/profiles-customers.png "B2C 客户配置文件")

组织（预览）
> [!div class="mx-imgBorder"] 
> ![B2B 客户配置文件](media/profile-customers-b2b.png "B2B 客户配置文件")

> [!NOTE]
> 如果在导航中选择 **客户** 后看不到磁贴，您的管理员需要在 **搜索和筛选索引** 中[定义至少一个可搜索属性](search-filter-index.md)。

## <a name="search-for-customers"></a>搜索客户

通过在搜索框中输入名称或其他某个属性搜索客户。 只有在数据统一过程中创建的客户配置文件实体内才支持搜索。

作为管理员，您可以使用 **搜索和筛选索引** 页配置可搜索属性。 有关详细信息，请参阅[管理搜索和筛选索引](search-filter-index.md)。

## <a name="filter-customers"></a>筛选客户

可以按客户配置文件实体字段搜索客户。 与搜索类似，您的管理员首先需要使用 **搜索和筛选索引** 将字段定义为可搜索。

1. 在 **客户** 页面上选择 **筛选器**。

2. 选中要充当客户搜索依据的属性旁边的框。

   > [!div class="mx-imgBorder"] 
   > ![客户配置文件](media/profiles-customers3.png "客户配置文件")

3. 通过在 **客户** 页面上选择 **清除筛选器** 来删除您的筛选器。

##  <a name="customer-details-page"></a>客户详细信息页面

选择任何客户磁贴以打开 **客户详细信息页面**。 此视图包含所选客户的统一信息。

客户详细信息包括:

-   **客户配置文件磁贴：** 此磁贴显示统一客户配置文件实体中的不同值。 这些详细信息可以包括电子邮件地址、姓名、市/县等等。 

-   **潜在兴趣、潜在品牌：** 显示您是否配置了第一方扩充。 它表示具有与此客户类似的配置文件的客户可能具有的潜在兴趣和品牌相似性。 有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)。

-   **度量：** 显示您是否配置了一个或多个特定类型的度量：客户属性度量。 它们包括针对各个客户级别的客户的计算 KPI。 有关详细信息，请参阅[定义和管理度量](measures.md)。

-   **活动时间线：** 显示您是否已配置活动。 时间线视图包含此客户的按时间排序的活动，从最近活动开始。 有关详细信息，请参阅[自定义活动](activities.md)。

选择 **返回到客户** 以返回到客户搜索页面。

## <a name="next-steps"></a>后续步骤

[添加更多数据源](data-sources.md)或[创建客户细分](segments.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]