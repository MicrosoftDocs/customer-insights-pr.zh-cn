---
title: 更新客户或联系人统一设置
description: 更新客户统一设置中的重复规则、匹配规则或统一字段。
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392460"
---
# <a name="update-unification-settings"></a>更新统一设置

要在创建了统一配置文件后查看或更改任何统一设置，请执行以下步骤。

1. 转到 **数据** > **统一**。

   对于个人客户（企业对客户），**统一** 页面显示每个统一步骤的统一客户配置文件和磁贴的数量。

   :::image type="content" source="media/m3_unified.png" alt-text="数据统一后的“数据统一”页面的屏幕截图。" lightbox="media/m3_unified.png":::

   对于企业客户（企业对企业），**统一** 页面显示每个客户统一步骤的统一客户配置文件和磁贴的数量。 如果联系人已统一，将显示每个联系人统一步骤的统一联系人配置文件和磁贴的数量。 根据您要更新的内容，在 **统一客户** 或 **统一联系人（预览）** 下选择适当的磁贴。

   :::image type="content" source="media/b2b_unified.png" alt-text="客户和联系人数据统一后的“数据统一”页面的屏幕截图。" lightbox="media/b2b_unified.png":::

   > [!TIP]
   > 仅在选择多个实体时才会显示 **匹配条件** 磁贴。

1. 选择要更新的内容：
   - 用于添加属性或实体或更改属性类型的[源字段](#edit-source-fields)。 要删除属性，请参阅[删除统一字段](#remove-a-unified-field)。 要删除实体，请参阅[删除统一实体](#remove-a-unified-entity)。
   - 用于管理重复记录规则或合并首选项的[重复记录](#manage-deduplication-rules)。
   - 用于跨两个或更多个实体更新匹配规则的[匹配条件](#manage-match-rules)。
   - 用于合并或排除字段的[统一客户字段](#manage-unified-fields)。 您也可以将相关配置文件分组到群集中。
   - [语义字段](#manage-semantic-fields-for-unified-contacts)用于管理统一联系人字段的语义类型。
   - [关系](#manage-contact-and-account-relationships)用于管理联系人与客户的关系。

1. 进行更改后，请选择下一个选项：

   - [运行匹配条件](#run-matching-conditions)来快速评估匹配条件（删除重复项和匹配规则）的质量，而无需更新统一配置文件。 不会针对单个实体显示 **仅运行匹配条件** 选项。
   - [统一配置文件](#run-updates-to-the-unified-profile)用于运行匹配条件并更新统一配置文件实体，而不影响依赖项（如扩充、客户细分或度量）。 相关流程不会运行，而是将按[刷新计划中的定义](schedule-refresh.md)进行刷新。
   - [统一配置文件和依赖项](#run-updates-to-the-unified-profile)用于运行匹配条件并更新统一配置文件实体，并更新所有依赖项（如扩充、客户细分或度量）。 所有流程都将自动重新运行。 在企业对企业中，统一在更新统一配置文件的客户和联系人实体上运行。

## <a name="edit-source-fields"></a>编辑源字段

1. 在 **源字段** 磁贴上选择 **编辑**。

   :::image type="content" source="media/m3_source_edit.png" alt-text="“源字段”页面的屏幕截图，其中显示了主键、映射和未映射字段的数量":::

   系统会显示已映射和未映射的字段数。

1. 要添加其他属性或实体，选择 **选择实体或字段**。

1. （可选）您可以更改实体的主键、更改属性类型以及打开或关闭 **智能映射**。 有关详细信息，请参阅[选择源字段](map-entities.md)。

1. 选择 **下一步** 以更改删除重复项规则，或选择 **保存并关闭** 并返回[更新统一设置](#update-unification-settings)。

### <a name="remove-a-unified-field"></a>删除统一字段

要删除已统一的字段，必须从任何依赖项（如客户细分、度量、扩充或关系）中删除该字段。

1. 删除字段的所有依赖项后，转到 **数据** > **统一**。

1. 在 **统一客户字段** 磁贴上选择 **编辑**。

1. 选择所有出现的字段，然后选择 **排除**。

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="显示选定字段和“排除”按钮的统一字段页面的屏幕截图":::

1. 选择 **完成** 确认，然后选择 **保存并关闭**。

   > [!TIP]
   > 如果您看到消息“无法保存统一操作。 由于下游依赖项的缘故，无法修改或删除指定的资源”，则说明字段仍在下游依赖项中使用。

1. 如果该字段用于重复记录或匹配条件的规则中，请执行以下步骤。 否则，请转到下一步。
   1. 在 **重复记录** 磁贴上选择 **编辑**。
   1. 从所有使用它的规则中删除该字段（如果有），然后选择 **下一步**。
   1. 在 **匹配条件** 页面上，从所有使用它的规则中删除该字段（如果有），然后选择 **保存并关闭**。
   1. 选择 **统一** > **统一客户配置文件和依赖项**。 等待统一完成，然后继续下一步。

1. 在 **源字段** 磁贴上选择 **编辑**。

1. 选择 **选择实体和字段**，清除每个出现的字段旁边的复选框。

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="显示已清除复选框的“选择实体和字段”对话框的屏幕截图":::

1. 选择 **应用**。

1. 选择 **保存并关闭**。

1. 选择 **统一** > **统一客户配置文件和依赖项** 更新统一配置文件。

### <a name="remove-a-unified-entity"></a>删除统一实体

要删除已统一的实体，必须从任何依赖项（如客户细分、度量、扩充或关系）中删除该实体。

1. 删除实体的所有依赖项后，转到 **数据** > **统一**。

1. 在 **统一客户字段** 磁贴上选择 **编辑**。

1. 选择实体的所有字段，然后选择 **排除**。

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="包含选定实体的所有字段的统一字段和“排除”按钮的屏幕截图":::

1. 选择 **完成** 确认，然后选择 **保存并关闭**。

   > [!TIP]
   > 如果您看到消息“无法保存统一操作。 由于下游依赖项的缘故，无法修改或删除指定的资源”，则说明实体仍在下游依赖项中使用。

1. 在 **重复记录** 磁贴上选择 **编辑**。

1. 从实体中删除所有规则（如果有），然后选择 **下一步**。

1. 在 **匹配条件** 页面上，选择实体，然后选择 **删除**。

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="选择了实体的“匹配条件”和“删除”按钮的屏幕截图":::

1. 选择 **保存并关闭**。

1. 在 **源字段** 磁贴上选择 **编辑**。

1. 选择 **选择实体和字段**，清除实体旁边的复选框。

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="已清除实体复选框的“选择实体和字段”对话框的屏幕截图":::

1. 选择 **应用**。

1. 选择 **保存并关闭**。

1. 选择 **统一** > **统一客户配置文件和依赖项** 更新统一配置文件。

## <a name="manage-deduplication-rules"></a>管理删除重复项规则

1. 在 **重复记录** 磁贴上选择 **编辑**。

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="显示重复记录数的“重复记录”页面的屏幕截图" lightbox="media/m3_duplicates_edit.png":::

   系统会在 **重复项** 下显示找到的重复记录数。 **重复项已删除的记录** 列显示哪些实体有重复记录以及重复记录的百分比。

1. 要使用扩充的实体，选择 **使用已扩充实体**。 有关详细信息，请参阅[数据源扩充](data-sources-enrichment.md)。

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

   1. 选择 **完成**。

1. 选择 **下一步** 以更改匹配条件，或选择 **保存并关闭** 并返回[更新统一设置](#update-unification-settings)。

## <a name="manage-match-rules"></a>管理匹配规则

您可以重新配置和细微调整大部分匹配参数。 您无法添加或删除实体。 匹配规则不适用于单个实体。

1. 在 **匹配条件** 磁贴上选择 **编辑**。

   :::image type="content" source="media/m3_match_edit.png" alt-text="包含统计信息的“匹配规则和条件”页面的屏幕截图。" lightbox="media/m3_match_edit.png":::

   此页面显示匹配顺序和定义的规则和以下统计信息：
   - **唯一源记录** 显示上一次匹配运行中处理的单个源记录的数量。
   - **匹配的记录和非匹配记录** 突出显示处理匹配规则后保留的唯一记录数。
   - **仅匹配的记录** 只显示所有匹配对中的匹配数。

1. 若要查看所有规则的结果及其分数，请选择 **查看上次运行**。 系统将显示结果，包括备用联系人 ID。 您可以下载结果。

1. 若要查看特定规则的结果和分数，请选择规则，然后选择 **预览**。 结果将显示。 您可以下载结果。

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

1. 选择 **下一步** 以更改统一字段，或选择 **保存并关闭** 并返回[更新统一设置](#update-unification-settings)。

## <a name="manage-unified-fields"></a>管理统一字段

1. 在 **统一客户字段** 磁贴上选择 **编辑**。

    :::image type="content" source="media/m3_merge_edit.png" alt-text="统一客户字段的屏幕截图":::

1. 查看组合和排除的字段，并根据需要进行更改。 添加或编辑 CustomerID 键或将配置文件分组到群集中。 有关详细信息，请参阅[统一客户字段](merge-entities.md)。

1. 对于客户，选择 **下一步** 查看并[更新统一配置文件和依赖项](#run-updates-to-the-unified-profile)。 或选择 **保存并关闭** 返回[更新统一设置](#update-unification-settings)进行更多更改。

   对于联系人，选择 **下一步** 管理语义字段。 或选择 **保存并关闭** 返回[更新统一设置](#update-unification-settings)进行更多更改。

## <a name="manage-semantic-fields-for-unified-contacts"></a>管理统一联系人的语义字段

1. 在 **语义字段** 磁贴上选择 **编辑**。

1. 要更改统一字段的语义类型，选择一个新类型。 有关详细信息，请参阅[定义统一联系人的语义字段](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts)。

1. 选择 **下一步** 管理客户和联系人关系，或选择 **保存并关闭** 返回[更新统一设置](#update-unification-settings)进行更多更改。

## <a name="manage-contact-and-account-relationships"></a>管理联系人和客户关系

1. 在 **关系** 磁贴上选择 **编辑**。

1. 要更改联系人和客户关系，请更改以下任何信息：

   - **联系人实体中的外键**：选择将您的联系人实体连接到客户的属性。
   - **目标客户实体**：选择与联系人关联的客户实体。

1. 选择 **下一步** 以查看统一设置并 [更新统一配置文件和依赖项](#run-updates-to-the-unified-profile)，或者选择 **保存并关闭** 并返回[更新统一设置](#update-unification-settings)以进行更多更改。

## <a name="run-matching-conditions"></a>运行匹配条件

运行匹配条件仅运行删除重复项和匹配规则，并更新 *Deduplication_* 和 *ConflationMatchPair* 实体。

1. 从 **数据** > **统一** 页中，选择 **仅运行匹配条件**。

   **重复记录** 和 **匹配条件** 磁贴显示 **已排队** 或 **正在刷新** 状态。

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. 匹配过程完成时，选择 **匹配条件** 磁贴上的 **编辑**。

   :::image type="content" source="media/match-KPIs.png" alt-text="包含数字和详细信息的“匹配”页上关键度量的已裁剪屏幕截图。":::

1. 要进行更改，请参阅[管理删除重复项规则](#manage-deduplication-rules)或[管理匹配规则](#manage-match-rules)。

1. 再次运行匹配过程或[运行配置文件更新](#run-updates-to-the-unified-profile)。

## <a name="run-updates-to-the-unified-profile"></a>运行统一配置文件更新

- 要运行匹配条件并更新统一配置文件实体 *而不* 影响依赖项（如客户卡、扩充、客户细分或度量），选择 **统一客户配置文件**。 对于客户，选择 **统一客户** > **统一配置文件**。 对于联系人，选择 **统一联系人（预览）** > **统一配置文件**。 相关流程不会运行，而是将按[刷新计划中的定义](schedule-refresh.md)进行刷新。
- 要运行匹配条件、更新统一配置文件并运行所有依赖项，选择 **统一客户配置文件和依赖项**。 所有流程都将自动重新运行。 对于客户和联系人，选择 **统一客户** > **统一配置文件和依赖项**。 将为更新统一配置文件和所有其他依赖项的客户和联系人运行匹配条件。

除了 **源字段** 之外的所有磁贴均显示 **已排队** 或 **正在刷新**。

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

成功运行的结果显示在 **统一** 页面中，其中显示了统一配置文件的数量。
