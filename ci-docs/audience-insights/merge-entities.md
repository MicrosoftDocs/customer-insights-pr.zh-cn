---
title: 在数据统一中合并实体
description: 合并实体以创建统一客户配置文件。
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494308"
---
# <a name="merge-entities"></a>合并实体

合并阶段是数据统一过程中的最后一个阶段。 其目的是协调冲突数据。 冲突数据的示例包括，在两个数据集中找到的一个客户名称在每个数据集中显示时稍微不同（“Grant Marshall”与“Grant Marshal”），或一个电话号码的格式不同（617-803-091X 与 617803091X）。 将逐个属性完成这些冲突数据点的合并。

:::image type="content" source="media/merge-fields-page.png" alt-text="数据统一进程中的合并页，其中显示带定义统一客户配置文件的合并字段的表。":::

完成 [匹配阶段](match-entities.md)之后，选择 **统一** 页中的 **合并** 磁贴开始进行合并阶段。

## <a name="review-system-recommendations"></a>查看系统建议

在 **数据** > **统一** > **合并** 中，您可以选择并排除要在统一客户配置文件实体中合并的属性。 统一客户配置文件是数据统一过程的结果。 系统会自动合并某些属性。

若要查看包括在一个自动合并属性中的属性，请在表的 **客户字段** 选项卡中选择该合并的属性。 将在合并的属性下的两个新行内显示构成这个合并的属性的属性。

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>分隔、重命名、排除和编辑合并的字段

您可以更改系统处理合并属性以生成统一客户配置文件的方法。 选择 **显示更多** 并选择要更改的内容。

:::image type="content" source="media/manage-merged-attributes.png" alt-text="显示更多下拉菜单中的选项，用于管理合并的属性。":::

有关详细信息，请参阅以下部分。

## <a name="separate-merged-fields"></a>拆分合并的字段

若要拆分合并的字段，请在表中查找属性。 拆分的字段在统一客户配置文件上显示为单个数据点。 

1. 选择合并的字段。
  
1. 选择 **显示更多** 并选择 **拆分字段**。
 
1. 确认拆分。

1. 选择 **保存** 和 **运行** 以处理更改。

## <a name="rename-merged-fields"></a>重命名合并的字段

更改合并的属性的显示名称。 您无法更改输出实体的名称。

1. 选择合并的字段。
  
1. 选择 **显示更多** 并选择 **重命名**。

1. 确认更改的显示名称。 

1. 选择 **保存** 和 **运行** 以处理更改。

## <a name="exclude-merged-fields"></a>排除合并的字段

从统一客户配置文件中排除属性。 如果字段用于其他流程（如客户细分中的流程），请从这些流程中删除此字段，然后从客户配置文件中排除此字段。 

1. 选择一个合并字段。
  
1. 选择 **显示更多** 并选择 **排除**。

1. 确认排除。

1. 选择 **保存** 和 **运行** 以处理更改。 

在 **合并** 页上，选择 **排除的字段** 以查看所有排除的字段的列表。 此窗格允许您添加回排除的字段。

## <a name="edit-a-merged-field"></a>编辑合并字段

1.  选择一个合并字段。

1.  选择 **显示更多** 并选择 **编辑**。

1.  指定如何使用以下三个选项之一组合或合并字段：
    - **重要性**：根据为参与字段指定的重要性等级确定获胜者值。 这是默认的合并选项。 选择 **上移/下移** 设置重要性排名。
    :::image type="content" source="media/importance-merge-option.png" alt-text="合并字段对话框中的重要性选项。"::: 
    - **最新**：根据最近 recency 指定获胜者值。 合并字段中每个参与实体都需要日期或数值字段，才能定义 recency。
    :::image type="content" source="media/recency-merge-option.png" alt-text="合并字段对话框中的 recency 选项。":::
    - **最早**：根据最早 recency 指定获胜者值。 合并字段中每个参与实体都需要日期或数值字段，才能定义 recency。

1.  您可以添加更多字段以参与合并过程。

1.  您可以重命名合并字段。

1. 选择 **完成** 以应用更改。

1. 选择 **保存** 和 **运行** 以处理更改。 

## <a name="manually-combine-fields"></a>手动合并字段

手动指定合并的属性。 

1. 在 **合并** 页上，选择 **组合字段**。

1. 在 **合并字段的依据** 下拉列表中指定合并获胜者策略。

1. 选择要添加的字段。 选择 **添加字段** 以合并其他字段。

1. 提供 **名称** 和 **输出字段名称**。

1. 选择 **完成** 以应用更改。

1. 选择 **保存** 和 **运行** 以处理更改。 

## <a name="change-the-order-of-fields"></a>更改字段的顺序

有些实体包含的详细信息要多于其他实体包含的详细信息。 如果实体包含有关字段的最新数据，则您可以在合并值时让该实体优先于其他实体。

1. 选择合并的字段。
  
1. 选择 **显示更多** 并选择 **编辑**。

1. 在 **合并字段** 窗格中，选择 **上移/下移** 以设置顺序，或将字段拖放到所需位置。

1. 确认更改。

1. 选择 **保存** 和 **运行** 以处理更改。

## <a name="configure-customer-id-generation"></a>配置客户 ID 生成 

配置合并字段之后，可以定义如何生成 CustomerId 值，即客户配置文件唯一标识符。 数据统一过程中的合并步骤将生成客户配置文件唯一标识符。 此标识符是 *Customer* 实体中数据统一过程生成的 CustomerId。 

Customer 实体中的 CustomerId 基于非空获胜者主键第一个值的哈希。 这些密钥来自匹配和合并阶段使用的实体，并且受匹配顺序影响。因此，如果匹配顺序中的主实体内主键值改变，生成的 CustomerID 也可能改变。 因此，主键值可能并不是始终代表同一位客户。

配置稳定的客户 Id 可以避免此行为。

**配置唯一客户 ID**

1. 转到 **统一** > **合并**。

1. 在 **合并** 页上，选择 **键** 选项卡。 

1. 将鼠标光标悬停在 **CustomerId** 行上方，然后选择 **配置** 选项。
   :::image type="content" source="media/customize-stable-id.png" alt-text="用于自定义 ID 生成的控件。":::

1. 最多选择五个字段，这些字段构成唯一客户 ID，并且会更稳定。 与配置不匹配的记录使用系统配置的 ID。  

1. 选择 **完成** 并运行合并过程以应用更改。

## <a name="run-your-merge"></a>运行合并

无论您手动合并属性还是让系统合并属性，您始终都可以运行合并。 在 **合并** 页中选择 **运行** 开始执行此过程。

> [!div class="mx-imgBorder"]
> ![数据合并保存和运行。](media/configure-data-merge-save-run.png "数据合并保存和运行")

如果只想查看统一客户实体中反映的输出，请选择 **仅运行合并**。 将按[刷新计划中的定义](system.md#schedule-tab)来刷新下游流程。

选择 **运行合并和下游流程** 以用您所做的更改刷新系统。 所有流程（包括扩充、客户细分和度量）将自动重新运行。 所有下游流程都完成后，客户配置文件将反映您做出的任何更改。

若要进行更多更改并重新运行此步骤，可以取消正在进行的合并。 选择 **正在刷新...**，然后选择显示的侧边窗格中的 **取消作业**。

> [!TIP]
> 运行合并流程后，选择流程状态以打开 **任务详细信息** 窗格。 它概述了处理时间、上次处理日期以及与任务相关的所有错误和警告。 选择 **查看详细信息**，以查看哪些实体参与了匹配流程、是否成功进行了冲突解决，以及是否成功发布了更新。  
> 对于任务/流程，有[六种类型的状态](system.md#status-types)。 此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。  
> :::image type="content" source="media/process-detail-path.png" alt-text="从任务状态链接获取流程详细信息的向下钻取路径。":::

## <a name="next-step"></a>下一步

配置[活动](activities.md)、[扩充](enrichment-hub.md)或[关系](relationships.md)，以便加深对客户的了解。

如果您已经配置了活动、扩充或客户细分，系统将自动处理它们以使用最新的客户数据。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
