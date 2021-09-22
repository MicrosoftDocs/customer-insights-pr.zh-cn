---
title: 创建和修改已优化的事件
description: 如何创建和修改已优化的事件。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034763"
---
# <a name="create-and-modify-refined-events"></a>创建和修改已优化的事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


事件是代表用户行为的数据，如网站上的活动。

- *基本* 事件记录用户查看页面（查看事件）或与内容交互（操作事件）的时间。
- *已优化的* 事件是基本事件的虚拟视图。 通过删除和添加属性，或者基于属性值筛选事件，可以定义已优化的事件。

使用已优化的事件可以缩小[导出](export-events.md)的基本事件范围，或者删除公开不需要的属性。

## <a name="create-refined-events"></a>创建细化的事件

根据基本事件创建已优化的事件有三种方法。 

1. 转到 **数据**> **事件** 并选择以下选项之一：
    - 选择 **新事件**，然后选择 **创建已优化的事件**。
    - 选择基本事件以打开详细视图，然后从顶部菜单中选择 **创建已优化的事件**。
    - 选择 **更多 [...]** 以打开基本事件的快捷菜单。 然后选择 **创建已优化的事件**。
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="用于创建已优化的事件的选项。":::

1. 在 **创建已优化的事件** 对话框中，输入以下信息：

- 如果要创建新事件，请从 **基本事件** 下拉列表中选择一个事件。
- 在 **已优化的事件显示名称** 框中输入名称。
- （可选）更新建议的 **实际名称**，但不要使用空格。

3. 选择 **创建** 以应用设置。

1. 在已优化的事件的详细视图中，选择 **添加和删除属性** 以打开 **编辑属性** 窗格。 

1. 使用复选框可以选择要显示的属性和要隐藏的属性。 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="编辑已优化的事件的属性。":::

1. 选择 **确认** 以应用您的选择。

1. 选择 **保存** 以保存配置。

## <a name="edit-refined-events"></a>编辑已优化的事件

您可以更改已优化的事件的名称和属性。

### <a name="edit-event-name"></a>编辑事件名称

1. 转到 **数据** > **事件**。 
1. 针对事件选择 **更多 [...]**，并选择 **编辑名称**。
1. 更新事件名称并选择 **重命名**。

### <a name="edit-selected-properties"></a>编辑所选属性

1. 转到 **数据** > **事件** 并选择已优化的事件以打开详细视图。
1. 选择 **添加和删除属性**。 
1. 编辑复选框选择。
1. 选择 **确认**，然后选择 **保存** 以应用更改。

有关导出事件的信息，请参阅[导出事件](export-events.md)。
[!INCLUDE[footer-include](../includes/footer-banner.md)]
