---
title: 统一数据之前删除重复项
description: 统一过程中的第二步是选择在发现重复项时要保留的记录。
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213616"
---
# <a name="remove-duplicates-before-unifying-data"></a>统一数据之前删除重复项

统一过程中的这个可选步骤让您能够设置用于清除实体 **内** 的重复记录的规则。 删除重复项会为客户识别多个记录并选择要保留的最佳记录（基于基本合并首选项）或将记录合并为一个（基于高级合并首选项）。 源记录会通过替代 ID 链接到合并的记录。 如果未配置规则，将应用系统定义的规则。

## <a name="default-deduplication"></a>默认删除重复项

如果未添加删除重复项规则，将应用系统定义的规则。

- 将删除主键的重复项。
  对于具有相同主键的记录，将保留 **最多填充** 记录（空值最少的记录）。
- 任何跨实体匹配规则都将应用于实体。
  例如：在匹配步骤中，如果实体 A 在 *FullName* 和 *DateofBirth* 上与实体 B 匹配，实体 A 也会被 *FullName* 和 *DateofBirth* 删除重复项。 由于 *FullName* 和 *DateofBirth* 是识别实体 A 中客户的有效键，所以这些键也可用于识别实体 A 中的重复客户。

## <a name="include-enriched-entities-preview"></a>包括扩充的实体（预览版）

如果您在数据源级别扩充了实体以帮助改进统一结果，请选择它们。 有关详细信息，请参阅[数据源扩充](data-sources-enrichment.md)。

1. 在 **重复记录** 页上，选择页面顶部的 **使用扩充的实体**。

1. 从 **使用已扩充实体** 窗格中，选择一个或多个扩充的实体。

1. 选择 **完成**。

## <a name="define-deduplication-rules"></a>定义删除重复规则

1. 在 **重复记录** 页上，选择实体并选择 **添加规则** 来定义删除重复规则。

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="“显示更多”突出显示的重复记录页面的屏幕截图":::

   1. 在 **添加规则** 窗格中，输入以下信息：
      - **选择字段**：从要检查重复项的实体的可用字段列表中进行选择。 选择可能为每个客户所特有的字段。 例如，电子邮件地址，或者名称、市/县和电话号码的组合。
      - **标准化**：为所选属性从以下标准化选项中进行选择。
        - **数字**：将其他数字系统（如罗马数字）转换为阿拉伯语数字。 *VIII* 将变为 *8*。
        - **符号**：删除所有符号和特殊字符。 *Head&Shoulder* 会变为 *HeadShoulder*。
        - **文本转换为小写：将所有字符转换为小写**。 *ALL CAPS and Title Case* 将变为 *all caps and title case*。
        - **类型（电话、名称、地址、组织）**：对名称、头衔、电话号码、地址等进行标准化处理。
        - **Unicode 转变为 ASCII**：将 Unicode 表示法转换为 ASCII 字符。 */u00B2* 将变为 *2*。
        - **空白**：删除所有空格。 *Hello   World* 会变为 *HelloWorld*。
      - **精度**：设置要用于此条件的精度级别。
        - **基本**：从 *低 (30%)*、*中 (60%)*、*高 (80%)* 和 *精确 (100%)* 中选择。 选择 **精确** 以仅匹配 100% 匹配的记录。
        - **自定义**：设置记录需要匹配的百分比。 系统将只匹配传递此阈值的记录。
      - **名称**：规则的名称。

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="用于删除重复项的“添加规则”窗格的屏幕截图。":::

   1. 或者，也可以选择 **添加** > **添加条件** 向规则添加更多条件。 条件与逻辑 AND 运算符相连，因此仅在满足所有条件时才会执行。

   1. 或者，也可以选择 **添加** > **添加异常** 以[向规则中添加异常](match-entities.md#add-exceptions-to-a-rule)。 异常用于解决个别情况下的误报和漏报。

   1. 选择 **完成** 以创建规则。

1. （可选）[添加更多规则](#define-deduplication-rules)。

1. 选择实体，然后选择 **编辑合并首选项**。

1. 在 **合并首选项** 窗格中：
   1. 选择以下三个选项之一，以确定在发现重复项时要保留的记录：
      - **最多填充**：将属性字段填充最多的记录标识为入选记录。 这是默认的合并选项。
      - **最常使用**：根据最常使用标识入选记录。 需要日期或数字字段以定义近期性。
      - **最不常用**：根据最不常用标识入选记录。 需要日期或数字字段以定义近期性。
      
      在平局的情况下，获胜者记录是具有 MAX(PK) 或较大主键值的记录。
      
   1. （可选）要对实体的个别属性定义合并首选项，可以选择窗格底部的 **高级**。 例如，您可以选择保留来自不同记录的最新电子邮件和最完整地址。 展开实体以查看其所有属性并定义用于各个属性的选项。 如果您选择基于新近度的选项，您还需要指定定义新近度的日期/时间字段。

      :::image type="content" source="media/m3_adv_merge.png" alt-text="显示最近电子邮件和完整地址的高级合并首选项窗格":::

   1. 选择 **完成** 以应用合并首选项。

1. 定义删除重复规则和合并首选项后，选择 **下一步**。
  
> [!div class="nextstepaction"]
> [单个实体的下一步：统一字段](merge-entities.md)

> [!div class="nextstepaction"]
> [多个实体的下一步：匹配条件](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>实体形式的删除重复输出

删除重复过程会为每个源实体创建一个新的已删除重复项的实体。 这些实体可以与名称为 **Deduplication_DataSource_Entity** 的 **实体** 页面内 **系统** 部分中的 **ConflationMatchPairs:CustomerInsights** 一起找到。

删除重复输出实体包含以下信息：

- ID/键
  - 主键和备用 ID 字段。 备用 ID 字段由为记录标识的所有备用 ID 组成。
  - Deduplication_GroupId 字段显示在实体中标识的组或群集，该组或群集根据指定的删除重复字段将所有相似记录归组。 它用于系统处理目的。 如果没有指定手动删除重复规则并且系统定义的删除重复规则适用，则您可能在重复删除输出实体中找不到此字段。
  - Deduplication_WinnerId：此字段包含标识的组或群集中的获胜者 ID。 如果 Deduplication_WinnerId 与记录的主键值相同，则这意味着该记录是入选记录。
- 用于定义删除重复规则的字段。
- “规则”和“分数”字段，分别用于表示所应用的删除重复规则以及匹配算法返回的分数。

[!INCLUDE[footer-include](includes/footer-banner.md)]
