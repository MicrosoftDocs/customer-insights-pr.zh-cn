---
title: 在数据统一中合并实体
description: 合并实体以创建统一客户配置文件。
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597822"
---
# <a name="merge-entities"></a>合并实体

合并阶段是数据统一过程中的最后一个阶段。 其目的是协调冲突数据。 冲突数据的示例包括，在两个数据集中找到的一个客户名称在每个数据集中显示时稍微不同（“Grant Marshall”与“Grant Marshal”），或一个电话号码的格式不同（617-803-091X 与 617803091X）。 将逐个属性完成这些冲突数据点的合并。

完成 [匹配阶段](match-entities.md)之后，选择 **统一** 页中的 **合并** 磁贴开始进行合并阶段。

## <a name="review-system-recommendations"></a>查看系统建议

在 **合并** 页中，选择和排除统一客户配置文件实体（配置过程的产物）内要合并的属性。 系统会自动合并某些属性。

### <a name="view-merged-attributes"></a>查看合并的属性

若要查看一个自动合并的属性中包含的属性，请选择这个合并的属性。 将在合并的属性下的两个新行内显示构成这个合并的属性的两个属性。

> [!div class="mx-imgBorder"]
> ![选择合并的属性](media/configure-data-merge-profile-attributes.png "选择合并的属性")

### <a name="separate-merged-attributes"></a>拆分合并的属性

若要拆分或取消合并任何自动合并的属性，请在 **配置文件属性** 表中找到该属性。

1. 选择省略号 (...) 按钮。
  
2. 在下拉列表中，选择 **拆分字段**。

### <a name="remove-merged-attributes"></a>删除合并的属性

若要从最终客户配置文件实体中排除某个属性，请在 **配置文件属性** 表中找到该属性。

1. 选择省略号 (...) 按钮。
  
2. 在下拉列表中，选择 **不合并**。

   将把该属性移到 **已从客户记录中删除** 部分。

## <a name="manually-add-a-merged-attribute"></a>手动添加合并的属性

若要添加合并的属性，请转到 **合并** 页。

1. 选择 **添加合并的属性**。

2. 提供 **名称**，以便以后在 **合并** 页中可以识别该属性。

3. （可选）提供要在统一的客户配置文件实体中显示的 **显示名称**。

4. 配置 **选择重复的属性**，以便从匹配的实体中选择要合并的属性。 也可以搜索属性。

5. 设置 **按重要性分等级**，以便将一个属性的优先级设置为高于其他属性。 例如，如果 *WebAccountCSV* 实体中包含有关 *完整名称* 属性的最精确数据，您可以通过选择 *WebAccountCSV* 将此实体的优先级设置为高于 *ContactCSV*。 结果，在提取 *完整名称* 属性的值时，*WebAccountCSV* 将移到第一优先级，而 *ContactCSV* 则移到第二优先级。

## <a name="run-your-merge"></a>运行合并

无论您手动合并属性还是让系统合并属性，您始终都可以运行合并。 在 **合并** 页中选择 **运行** 开始执行此过程。

> [!div class="mx-imgBorder"]
> ![数据合并保存和运行](media/configure-data-merge-save-run.png "数据合并保存和运行")

若要进行更多配置并重新运行步骤，可以取消正在进行的合并。 选择 **正在刷新...**，然后选择显示的侧边窗格中的 **取消作业**。

文本 **正在刷新...** 更改为 **成功** 之后，说明已完成合并，并根据您定义的策略解决了冲突。 统一配置文件实体中包含合并的属性和未合并的属性。 统一配置文件实体中不包含排除的属性。

如果这不是第一次成功运行合并，将自动重新运行所有下游流程，包括扩充、细分和度量。 重新运行了所有下游流程之后，客户配置文件将反映您进行的所有更改。

> [!TIP]
> 对于任务/流程，有[六种类型的状态](system.md#status-types)。 此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。 可以选择流程状态以查看有关整个作业的进度的详细信息。 在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。

## <a name="next-step"></a>下一步

配置[活动](activities.md)、[扩充](enrichment-microsoft-graph.md)或[关系](relationships.md)，以便加深对客户的了解。

如果您已配置了活动、扩充或关系，或者如果您定义了细分，系统将自动处理它们以使用最新的客户数据。




[!INCLUDE[footer-include](../includes/footer-banner.md)]