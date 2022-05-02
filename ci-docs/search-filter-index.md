---
title: 搜索和筛选客户配置文件
description: 快速查找有关统一的客户配置文件的信息和筛选出指定的属性。
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645866"
---
# <a name="customer-profiles-search--filter-index"></a>客户配置文件：搜索和筛选索引

统一客户数据的结果是一个客户配置文件实体，用于提供对总客户群的统一认识。 若要快速 [查找有关特定客户或客户群的信息](customer-profiles.md)，可以在 **客户** 页中配置 **搜索** 和 **筛选** 功能。 继续阅读以了解管理员可以如何编辑 **搜索和筛选索引** 页中的属性，用户可使用这些属性进行搜索和筛选。

   :::image type="content" source="media/search-filter.png" alt-text="搜索筛选器":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>添加字段和指定属性

如果这是您首次以管理员身份定义可搜索属性，您需要首先定义索引字段。 建议您选择用户在 **客户** 页中可用于搜索和筛选客户的所有属性。 只能指定您在数据统一过程中创建的客户配置文件实体内的已有属性。

1. 打开 **客户** 页，然后选择 **搜索和筛选索引**。

2. 选择 **+ 添加** 以指定索引字段。

3. 在列表中选择要作为索引字段添加的属性。 始终可以通过选择 **添加** 添加更多属性。 您还可以通过选择 **删除** 符号来删除任何选定的属性。

## <a name="explore-the-indexed-customer-fields-table"></a>浏览已编制索引的客户字段表

此表中提供以下信息。

- **名称**：表示属性在客户配置文件实体中显示时的名称。
- **数据类型**：指定数据类型是字符串、数字还是日期。
- **包含在搜索中**：指定当使用 **搜索** 字段在 **客户** 页中搜索客户时，是否可使用此属性。
- **添加筛选器**：用于定义如何将此属性用于在 **客户** 页中进行属性的控件。

## <a name="editing-filtering-options-for-a-given-attribute"></a>编辑给定属性的筛选选项

**客户** 页中的 **筛选器** 菜单中可包含数量不定的属性级别（例如，在筛选客户时充当依据的不同年龄组）。

1. 在 **搜索和筛选索引** 页中为给定属性选择 **添加筛选器**。 可以定义结果的数量和排列顺序。 将显示下面的一个窗格，具体取决于属性的数据类型。

- 字符串类型属性：在 **字符串筛选器选项** 窗格中指定所需结果数量和结果的排列顺序策略。

- 数值类型属性：指定 **数字筛选选项** 窗格中包含的时间间隔和结果的排列顺序策略。

- 日期类型属性：指定 **日期筛选选项** 窗格中包含的时间间隔和结果的排列顺序策略。

2. 选择 **保存** 以应用您所做的更改。

3. 准备好应用设置时，选择 **运行**。 处理完更改之后，将在[客户页中的客户卡](customer-profiles.md)内找到。 

## <a name="next-steps"></a>后续步骤

检查[统一配置文件](customer-profiles.md)页面以搜索配置文件，或使用索引字段以查看所有统一配置文件的子集。


[!INCLUDE [footer-include](includes/footer-banner.md)]
