---
title: 管理客户配置文件的搜索和筛选索引
description: 快速查找有关统一的客户配置文件的信息和筛选出指定的属性。
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187898"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>管理客户配置文件的搜索和筛选索引

统一客户数据的结果是一个 *客户* 实体，用于提供对总客户群的统一认识。 要让用户能够快速 [查找有关特定客户或客户群的信息](customer-profiles.md)，管理员必须为 **客户** 页配置 **搜索** 和 **筛选** 功能。

   :::image type="content" source="media/search-filter.png" alt-text="搜索筛选器":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>定义可搜索属性和索引字段

如果这是您首次以管理员身份定义可搜索属性，首先定义索引字段。 建议您选择用户在 **客户** 页中可用于搜索和筛选客户的所有属性。 只能指定在数据统一过程中创建的 *客户* 实体内的已有属性。

1. 转到 **客户**，选择 **搜索和筛选索引**。

1. 选择 **+ 添加**。

1. 在列表中选择要作为索引字段添加的属性，然后单击 **应用**。

1. 要添加更多属性，选择 **添加**。 要删除所选属性，选择属性，然后选择 **删除**。

   :::image type="content" source="media/search-filter-index.png" alt-text="搜索和筛选索引页面。":::

1. 准备好应用搜索和筛选设置时，选择 **运行**。 处理完更改之后，在[客户页中的客户卡](customer-profiles.md)中查看。

## <a name="define-filtering-options-for-a-given-attribute"></a>定义给定属性的筛选选项

在 **客户** 页面上设置可用于筛选客户的字段。

1. 转到 **客户**，选择 **搜索和筛选索引**。

1. 选择一个属性并选择 **添加筛选器**。 定义结果的数量和排列顺序。 将显示下面的一个窗格，具体取决于属性的数据类型。

   - 字符串类型属性：在 **字符串筛选** 窗格中指定所需结果数量和结果的排列顺序策略。

   - 数值类型属性：指定 **数字筛选** 窗格中包含的时间间隔和结果的排列顺序策略。

   - 日期类型属性：指定 **日期筛选** 窗格中包含的时间间隔和结果的排列顺序策略。

1. 选择 **确定**。 对您要用于筛选的所有属性重复此操作。

1. 准备好应用搜索和筛选设置时，选择 **运行**。 处理完更改之后，在[客户页中的客户卡](customer-profiles.md)中查看。

## <a name="view-indexed-customer-fields"></a>查看已编制索引的客户字段

**搜索和筛选索引** 页显示以下信息：

- **名称**：表示属性在 *客户* 实体中显示时的名称。
- **数据类型**：指定数据类型是字符串、数字还是日期。
- **包含在搜索中**：指定当使用 **搜索** 字段在 **客户** 页中搜索客户时，是否可使用此属性。
- **添加筛选器**：用于定义如何将此属性用于在 **客户** 页中进行属性的控件。

## <a name="next-steps"></a>后续步骤

检查[统一配置文件](customer-profiles.md)页面以搜索配置文件，或使用索引字段以查看所有统一配置文件的子集。

[!INCLUDE [footer-include](includes/footer-banner.md)]
