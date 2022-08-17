---
title: 更新统一设置
description: 更新统一设置中的重复规则、匹配规则或统一字段。
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245583"
---
# <a name="update-the-unification-settings"></a>更新统一设置

要在创建了统一配置文件后查看或更改任何统一设置，请执行以下步骤。

1. 转到 **数据** > **统一**。

   :::image type="content" source="media/m3_unified.png" alt-text="数据统一后的“数据统一”页面的屏幕截图。":::

   > [!TIP]
   > 仅在选择多个实体时才会显示 **匹配条件** 磁贴。

1. 选择要更新的内容：
   - 用于添加实体或属性或更改属性类型的[源字段](#edit-source-fields)。
   - 用于管理重复记录规则或合并首选项的[重复记录](#manage-deduplication-rules)。
   - 用于跨两个或更多个实体更新匹配规则的[匹配条件](#manage-match-rules)。
   - 用于合并或排除字段的[统一客户字段](#manage-unified-fields)。 您也可以将相关配置文件分组到群集中。

1. 进行更改后，请选择下一个选项：

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="“数据统一”页面的屏幕截图，其中突出显示了“统一”选项。":::

   - [运行匹配条件](#run-matching-conditions)来快速评估匹配条件（删除重复项和匹配规则）的质量，而无需更新统一配置文件。 不会针对单个实体显示 **仅运行匹配条件** 选项。
   - [统一客户配置文件](#run-updates-to-the-unified-customer-profile)来运行匹配条件并更新 Unified customer profile 实体，而不影响依赖项（如扩充、客户细分或度量）。 相关流程不会运行，而是将按[刷新计划中的定义](schedule-refresh.md)进行刷新。
   - [统一客户配置文件和依赖项](#run-updates-to-the-unified-customer-profile)来运行匹配条件并更新 Unified customer profile 实体和所有依赖项（如扩充、客户细分或度量）。 所有流程都将自动重新运行。

## <a name="edit-source-fields"></a>编辑源字段

如果属性或实体已经统一，则不能删除它们。

1. 在 **源字段** 磁贴上选择 **编辑**。

   :::image type="content" source="media/m3_source_edit.png" alt-text="“源字段”页面的屏幕截图，其中显示了主键、映射和未映射字段的数量":::

   系统会显示已映射和未映射的字段数。

1. 选择 **选择实体或字段** 以添加其他属性或实体。 使用搜索或滚动查找和选择您感兴趣的属性和实体。 选择 **应用**。

1. （可选）您可以更改实体的主键、更改属性类型以及打开或关闭 **智能映射**。 有关详细信息，请参阅[为属性选择主键和语义类型](map-entities.md#select-primary-key-and-semantic-type-for-attributes)。

1. 选择 **下一步** 以更改删除重复项规则，或选择 **保存并关闭** 并返回[更新统一设置](#update-the-unification-settings)。

## <a name="manage-deduplication-rules"></a>管理删除重复项规则

1. 在 **重复记录** 磁贴上选择 **编辑**。

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="显示重复记录数的“重复记录”页面的屏幕截图" lightbox="media/m3_duplicates_edit.png":::

   系统会在 **重复项** 下显示找到的重复记录数。 **重复项已删除的记录** 列显示哪些实体有重复记录以及重复记录的百分比。

1. 如果您添加了扩充的实体，请选择 **使用已扩充实体**。 有关详细信息，请参阅[数据源扩充](data-sources-enrichment.md)。

1. 要管理删除重复规则，请选择以下任意选项：
   - **创建新规则：** 在相应实体下选择 **添加规则**。 有关详细信息，请参阅[定义删除重复规则](remove-duplicates.md#define-deduplication-rules)。
   - **更改规则条件**：选择规则，然后选择 **编辑**。 更改字段、添加或删除条件，或者添加或删除异常。
   - **预览**：选择规则，然后选择 **预览** 以查看此规则的上次运行结果。
   - **停用规则**：选择规则，然后选择 **停用** 以保留删除重复规则，同时将其从匹配流程中排除。
   - **复制规则**：选择规则，然后选择 **复制** 以创建包含修改的类似规则。
   - **删除规则**：选择规则，然后选择 **删除**。

1. 要更改合并首选项，请选择实体。 只有在创建规则后才能更改首选项。
   1. 选择 **编辑合并首选项**，并更改 **要保留的记录** 选项。
   1. 要更改实体的个别属性的合并首选项，请选择 **高级** 并进行必要的更改。

      :::image type="content" source="media/m3_adv_merge.png" alt-text="显示最新电子邮件和最完整地址的高级合并首选项的屏幕截图":::

   1. 选择 **完成**。

1. 选择 **下一步** 以更改匹配条件，或选择 **保存并关闭** 并返回[更新统一设置](#update-the-unification-settings)。

## <a name="manage-match-rules"></a>管理匹配规则

您可以重新配置和细微调整大部分匹配参数。 您无法添加或删除实体。 匹配规则不适用于单个实体。

1. 在 **匹配条件** 磁贴上选择 **编辑**。

   :::image type="content" source="media/m3_match_edit.png" alt-text="包含统计信息的“匹配规则和条件”页面的屏幕截图。" lightbox="media/m3_match_edit.png":::

   此页面显示匹配顺序和定义的规则和以下统计信息：
   - **唯一源记录** 显示上一次匹配运行中处理的单个源记录的数量。
   - **匹配的记录和非匹配记录** 突出显示处理匹配规则后保留的唯一记录数。
   - **仅匹配的记录** 只显示所有匹配对中的匹配数。

1. 若要查看所有规则的结果及其分数，请选择 **查看上次运行**。 系统将显示结果，包括备用联系人 ID。 您可以下载结果。

1. 若要查看特定规则的结果和分数，请选择规则，然后选择 **预览**。 此时会显示结果。 您可以下载结果。

1. 若要查看特定规则条件的结果，请选择规则，然后选择 **编辑**。 在“编辑”窗格上，选择条件下面的 **预览**。 您可以下载结果。

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="不匹配和匹配的记录的图形表示，包括数据列表。":::

1. 如果您添加了扩充的实体，请选择 **使用已扩充实体**。 有关详细信息，请参阅[数据源扩充](data-sources-enrichment.md)。

1. 要管理规则，请选择以下任意选项：
   - **创建新规则：** 在相应实体下选择 **添加规则**。 有关详细信息，请参阅[定义匹配对的规则](match-entities.md#define-rules-for-match-pairs)。
   - 如果定义了多个规则，请 **更改规则的顺序**：将规则拖放成想要的顺序。 有关详细信息，请参阅[指定匹配顺序](match-entities.md#specify-the-match-order)。
   - **更改规则条件**：选择规则，然后选择 **编辑**。 更改字段、添加或删除条件，或者添加或删除异常。
   - **停用规则**：选择规则，然后选择 **停用** 以保留匹配规则，同时将其从匹配流程中排除。
   - **复制规则**：选择规则，然后选择 **复制** 以创建包含修改的类似规则。
   - **删除规则**：选择规则，然后选择 **删除**。

1. 选择 **下一步** 以更改统一字段，或选择 **保存并关闭** 并返回[更新统一设置](#update-the-unification-settings)。

## <a name="manage-unified-fields"></a>管理统一字段

1. 在 **统一客户字段** 磁贴上选择 **编辑**。

    :::image type="content" source="media/m3_merge_edit.png" alt-text="统一客户字段的屏幕截图":::

1. 查看组合和排除的字段，并根据需要进行更改。 添加或编辑 CustomerID 键或将配置文件分组到群集中。 有关详细信息，请参阅[统一客户字段](merge-entities.md)。

1. 选择 **下一步** 以查看统一设置并 [更新统一配置文件和依赖项](#run-updates-to-the-unified-customer-profile)，或者选择 **保存并关闭** 并返回[更新统一设置](#update-the-unification-settings)以进行更多更改。

## <a name="run-matching-conditions"></a>运行匹配条件

运行匹配条件仅运行删除重复项和匹配规则，并更新 *Deduplication_* 和 *ConflationMatchPair* 实体。

1. 从 **数据** > **统一** 页中，选择 **仅运行匹配条件**。

   **重复记录** 和 **匹配条件** 磁贴显示 **已排队** 或 **正在刷新** 状态。

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. 匹配过程完成时，选择 **匹配条件** 磁贴上的 **编辑**。

   :::image type="content" source="media/match-KPIs.png" alt-text="包含数字和详细信息的“匹配”页上关键度量的已裁剪屏幕截图。":::

1. 要进行更改，请参阅[管理删除重复项规则](#manage-deduplication-rules)或[管理匹配规则](#manage-match-rules)。

1. 再次运行匹配过程或[运行客户配置文件更新](#run-updates-to-the-unified-customer-profile)。

## <a name="run-updates-to-the-unified-customer-profile"></a>运行统一的客户配置文件更新

1. 从 **数据** > **统一** 页中，选择：

   - **统一客户配置文件**：运行匹配条件并更新 Unified customer profile 实体，而不影响依赖项（如扩充、客户细分或度量）。 相关流程不会运行，而是将按[刷新计划中的定义](schedule-refresh.md)进行刷新。

   - **统一客户配置文件和依赖项**：运行匹配条件并更新统一配置文件和所有依赖项。 所有流程都将自动重新运行。 所有下游流程完成后，客户配置文件会反映更新的数据。

   **重复记录**、**匹配条件** 和 **统一客户字段** 磁贴将显示 **已排队** 或 **正在刷新** 状态。

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

成功运行的结果显示在 **统一** 页面中，其中显示了统一的客户配置文件的数量。
