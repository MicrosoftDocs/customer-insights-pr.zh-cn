---
title: 统一客户字段，实现数据统一
description: 合并实体以创建统一客户配置文件。
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080944"
---
# <a name="unify-customer-fields-for-data-unification"></a>统一客户字段，实现数据统一

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

在统一过程的此步骤中，选择并排除要在统一配置文件实体中合并的属性。 例如，如果三个实体具有电子邮件数据，您可能希望保留所有三个单独的电子邮件字段，或将它们合并成统一配置文件的单个电子邮件字段。 某些属性由系统自动合并。 您可以创建稳定且唯一的客户 ID，并将相关配置文件分组到一个群集中。

:::image type="content" source="media/m3_unify.png" alt-text="数据统一进程中的合并页，其中显示带定义统一客户配置文件的合并字段的表。":::

## <a name="review-and-update-the-customer-fields"></a>查看并更新客户字段

1. 查看将在表的 **客户字段** 选项卡下统一的字段的列表。 如果合适，请进行更改。

   1. 对于任何合并字段，您可以：
      - [编辑](#edit-a-merged-field)
      - [重命名](#rename-fields)
      - [拆分](#separate-merged-fields)
      - [排除](#exclude-fields)
      - [向上或向下移动](#change-the-order-of-fields)

   1. 对于任何单个字段，您可以：
      - [合并字段](#combine-fields-manually)
      - [合并字段组](#combine-a-group-of-fields)
      - [重命名](#rename-fields)
      - [排除](#exclude-fields)
      - [向上或向下移动](#change-the-order-of-fields)

1. （可选）[生成客户 ID 配置](#configure-customer-id-generation)。

1. （可选）[将配置文件分组为家庭或群集](#group-profiles-into-households-or-clusters)。

> [!div class="nextstepaction"]
> [下一步：查看统一](review-unification.md)

### <a name="edit-a-merged-field"></a>编辑合并字段

1. 选择合并的字段并选择 **编辑**。 此时将显示“合并字段”窗格。

1. 指定如何使用以下三个选项之一组合或合并字段：
    - **重要性**：根据为参与字段指定的重要性等级确定获胜者值。 这是默认的合并选项。 选择 **上移/下移** 设置重要性排名。

      :::image type="content" source="media/importance-merge-option.png" alt-text="合并字段对话框中的重要性选项。":::

    - **最新**：根据最近 recency 指定获胜者值。 合并字段中每个参与实体都需要日期或数值字段，才能定义 recency。

      :::image type="content" source="media/recency-merge-option.png" alt-text="合并字段对话框中的 recency 选项。":::

    - **最早**：根据最早 recency 指定获胜者值。 合并字段中每个参与实体都需要日期或数值字段，才能定义 recency。

1. 您可以添加更多字段来参与合并过程。

1. 您可以重命名合并字段。

1. 选择 **完成** 以应用更改。

### <a name="rename-fields"></a>重命名字段

更改合并的字段或单独字段的显示名称。 您无法更改输出实体的名称。

1. 选择字段，然后选择 **重命名**。

1. 输入新的显示名称。

1. 选择 **完成**。

### <a name="separate-merged-fields"></a>拆分合并的字段

若要拆分合并的字段，请在表中查找属性。 拆分的字段在统一客户配置文件上显示为单个数据点。

1. 选择合并的字段，然后选择 **分隔字段**。

1. 确认拆分。

### <a name="exclude-fields"></a>排除字段

从统一的客户配置文件中排除合并的字段或单独字段。 如果字段用于其他流程（如客户细分中的流程），请从这些流程中删除此字段，然后从客户配置文件中排除此字段。

1. 选择字段并选择 **排除**。

1. 确认排除。

要查看所有已排除字段的列表，请选择 **已排除字段**。 如果需要，可以读取排除的字段。

### <a name="change-the-order-of-fields"></a>更改字段的顺序

有些实体包含的详细信息要多于其他实体包含的详细信息。 如果实体包含有关字段的最新数据，则您可以在合并值时让该实体优先于其他实体。

1. 选择字段。
  
1. 选择 **上移/下移** 以设置顺序，或将字段拖放到所需位置。

### <a name="combine-fields-manually"></a>手动合并字段

合并分离的字段以创建合并的属性。

1. 选择 **合并** > **字段**。 此时将显示“合并字段”窗格。

1. 在 **合并字段的依据** 下拉列表中指定合并获胜者策略。

1. 选择 **添加字段** 以合并更多字段。

1. 提供 **名称** 和 **输出字段名称**。

1. 选择 **完成** 以应用更改。

### <a name="combine-a-group-of-fields"></a>合并字段组

将一组字段视为单个单位。 例如，如果我们的记录包含字段“地址 1”、“地址 2”、“市/县”、“省/市/自治区”和“邮政编码”，我们不想合并到不同记录的“地址 2”中，并认为这会使我们的数据更加完整。

1. 选择 **合并** > **字段组**。

1. 在 **组排名依据** 下拉列表中指定合并获胜者策略。

1. 选择 **添加** 并选择是否要向字段添加更多字段或组。

1. 为每个合并字段提供 **名称** 和 **输出名称**。

1. 为字段组提供 **名称**。

1. 选择 **完成** 以应用更改。

## <a name="configure-customer-id-generation"></a>配置客户 ID 生成

定义如何生成客户 ID 值以及唯一的客户配置文件标识符。 数据统一过程中的统一字段步骤会生成唯一的客户配置文件标识符。 此标识符是 *Customer* 实体中数据统一过程生成的 *CustomerId*。

*CustomerId* 基于非空获胜者主键第一个值的哈希。 这些键来自数据统一中使用的实体，并受匹配顺序的影响。因此，当匹配订单的主要实体中的主键值发生变化时，生成的客户 ID 可能会发生变化。 主键值可能并不总是代表同一个客户。

配置稳定的客户 ID 可以避免此行为。

1. 选择 **键** 选项卡。

1. 将鼠标指针悬停在 **CustomerId** 行上，然后选择 **配置**。
   :::image type="content" source="media/customize-stable-id.png" alt-text="用于自定义 ID 生成的控件。":::

1. 最多选择五个字段，这些字段构成唯一客户 ID，并且会更稳定。 与配置不匹配的记录使用系统配置的 ID。  

1. 选择 **完成**。

## <a name="group-profiles-into-households-or-clusters"></a>将配置文件分组为家庭或群集

您可以定义规则以将相关配置文件分组到群集中。 目前有两种类型的群集可用 – 家庭群集和自定义群集。 如果 *Customer* 实体包含语义字段 *Person.LastName* 和 *Location.Address*，系统会自动选择具有预定义规则的家庭。 您还可以使用自己的规则和条件创建群集，类似于[匹配规则](match-entities.md#define-rules-for-match-pairs)。

1. 选择 **高级** > **创建群集**。

   :::image type="content" source="media/create-cluster.png" alt-text="创建新群集的控件。":::

1. 在 **家庭** 或 **自定义** 群集之间选择。 如果 *Customer* 实体中存在语义字段 *Person.LastName* 和 *Location.Address*，将自动选择家庭。

1. 为群集命名，然后选择 **完成**。

1. 选择 **群集** 选项卡查找您创建的群集。

1. 指定用于定义群集的规则和条件。

1. 选择 **完成**。 在统一过程完成时，将创建群集。 群集标识符将被作为新字段添加到 *Customer* 实体。

> [!div class="nextstepaction"]
> [下一步：查看统一](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
