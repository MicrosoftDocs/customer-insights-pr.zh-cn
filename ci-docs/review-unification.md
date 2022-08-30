---
title: 查看数据统一
description: 查看数据统一步骤、创建统一的客户配置文件并查看结果
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303956"
---
# <a name="review-data-unification"></a>查看数据统一

查看更改摘要、创建统一配置文件并查看结果。

## <a name="review-and-create-customer-profiles"></a>查看和创建客户配置文件

统一过程中的最后一步显示该过程中的步骤的摘要，并提供了一个在创建统一配置文件之前进行更改的机会。

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="“查看和创建客户配置文件”的屏幕截图。":::

1. 在任何数据统一步骤中选择 **编辑** 以查看并进行任何更改。

1. 如果您对选择感到满意，请选择 **创建客户配置文件**（或为企业对企业 **创建客户配置文件**）。 在创建统一的客户配置文件时，将显示 **统一** 页面。

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="包含显示&quot;已排队&quot;或&quot;正在刷新&quot;的磁贴的统一页面的屏幕截图。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

统一算法需要一些时间才能完成，并且在完成之前您无法更改配置。

## <a name="view-the-results-of-data-unification"></a>查看数据统一的结果

统一后，**数据** > **统一** 页将显示统一的客户配置文件的数量（或企业对企业的客户配置文件）。 统一过程中每个步骤的结果都显示在每个磁贴上。 例如，**源字段** 显示已映射属性（字段）的数量，而 **重复记录** 显示找到的重复记录数。

:::image type="content" source="media/m3_unified.png" alt-text="数据统一后的“数据统一”页面的屏幕截图。":::

> [!TIP]
> 仅在选择多个实体时才会显示 **匹配条件** 磁贴。

我们建议您查看结果，尤其是[匹配规则](data-unification-update.md#manage-match-rules)的质量，并在必要时对其进行改进。

如果需要，[更改统一设置](data-unification-update.md)，然后重新运行统一配置文件。

### <a name="verify-output-entities-from-data-unification"></a>验证数据统一的输出实体

转到 **数据** > **实体** 验证输出实体。

名为 *客户* 的统一客户配置文件实体显示在 **配置文件** 部分。 第一次成功运行统一时，会创建统一的 *Customer* 实体。 所有后续运行均会展开该实体。

重复数据删除和合并实体将创建并显示在 **系统** 部分。 将为每个源实体创建一个已删除重复项的实体，名称为 **Deduplication_DataSource_Entity**。 **ConflationMatchPairs** 实体包含有关跨实体匹配的信息。

删除重复输出实体包含以下信息：
- ID/键
  - 主键和备用 ID 字段。 备用 ID 字段由为记录标识的所有备用 ID 组成。
  - Deduplication_GroupId 字段显示在实体中标识的组或群集，该组或群集根据指定的删除重复字段将所有相似记录归组。 它用于系统处理目的。 如果没有指定手动删除重复规则并且系统定义的删除重复规则适用，则您可能在重复删除输出实体中找不到此字段。
  - Deduplication_WinnerId：此字段包含标识的组或群集中的获胜者 ID。 如果 Deduplication_WinnerId 与记录的主键值相同，则这意味着该记录是入选记录。
- 用于定义删除重复规则的字段。
- “规则”和“分数”字段，分别用于表示所应用的删除重复规则以及匹配算法返回的分数。

## <a name="next-step"></a>下一步

- 对于企业对企业，可选择执行[联系人统一](data-unification-contacts.md)。

- 对于企业对客户，配置[活动](activities.md)、[扩充](enrichment-hub.md)、[关系](relationships.md)或[度量](measures.md)，以获得有关客户的更多见解。

[!INCLUDE[footer-include](includes/footer-banner.md)]
