---
title: 查看数据统一
description: 查看数据统一步骤、创建统一的客户配置文件并查看结果
ms.date: 06/02/2022
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844075"
---
# <a name="review-data-unification"></a>查看数据统一

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

统一过程中的最后一步显示该过程中的步骤的摘要，并提供了一个在创建统一配置文件之前进行更改的机会。

:::image type="content" source="media/m3_review.png" alt-text="“查看和创建客户配置文件”的屏幕截图。":::

## <a name="review-the-data-unification-steps"></a>查看数据统一步骤

1. 在任何数据统一步骤中选择 **编辑** 以查看并进行任何更改。

1. 如果您对选择感到满意，请选择 **创建客户配置文件**。 在创建统一的客户配置文件时，将显示 **统一** 页面。 除了 **源字段** 之外的所有磁贴均显示 **已排队** 或 **正在刷新** 状态。

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="包含显示&quot;已排队&quot;或&quot;正在刷新&quot;的磁贴的统一页面的屏幕截图。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

统一算法需要一些时间才能完成，并且在完成之前您无法更改配置。 统一过程完成时，名为 *Customer* 的统一的客户配置文件实体将列在 **实体** 页面上的 **配置文件** 部分中。 第一次成功运行统一时，会创建统一的 *Customer* 实体。 所有后续运行均会展开该实体。

## <a name="review-the-results-of-data-unification"></a>查看数据统一的结果

统一后，**数据** > **统一** 页将显示统一的客户配置文件的数量。 统一过程中每个步骤的结果都显示在每个磁贴上。 例如，**源字段** 显示已映射属性（字段）的数量，而 **重复记录** 显示找到的重复记录数。

:::image type="content" source="media/m3_unified.png" alt-text="数据统一后的“数据统一”页面的屏幕截图。":::

> [!TIP]
> 仅在选择多个实体时才会显示 **匹配条件** 磁贴。

我们建议您查看结果，尤其是[匹配规则](data-unification-update.md#manage-match-rules)的质量，并在必要时对其进行改进。

如果需要，[更改统一设置](data-unification-update.md)，然后重新运行统一配置文件。

## <a name="next-step"></a>下一步

配置[活动](activities.md)、[扩充](enrichment-hub.md)、[关系](relationships.md)或[度量](measures.md)，以获得有关客户的更多见解。

[!INCLUDE[footer-include](includes/footer-banner.md)]
