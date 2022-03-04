---
title: 创建和修改事件
description: 如何创建和修改事件。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228192"
---
# <a name="create-and-modify-events"></a>创建和修改事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

事件是代表用户行为的数据，如网站上的活动。

- *基本* 事件记录用户查看页面（查看事件）或与内容交互（操作事件）的时间。
- *已优化的* 事件是基本事件的虚拟视图。 通过删除和添加属性，或者基于属性值筛选事件，可以定义已优化的事件。

## <a name="prerequisites"></a>先决条件

要获取事件，您的网站数据首先需要连接到包含代码片段的参与见解。 有关详细信息，请参阅[在网站上安装 Web SDK](instrument-website.md)。

 :::image type="content" source="media/new-events-connect-data.png" alt-text="首先连接您的数据。":::

## <a name="create-refined-events"></a>创建已优化的事件

使用已优化的事件可以缩小[导出](export-events.md)的基本事件范围，或者删除公开不需要的属性。

> [!NOTE]
> 将 Web SDK 添加到您的网站后，您即可以查看基本事件和创建优化事件。 

要查看基本事件：

1. 在左侧导航窗格中，转到 **数据**。

1. 选择 **事件** 查看工作区中所有事件的列表。

    :::image type="content" source="media/data-events.png" alt-text="查看事件。":::

要从基本事件创建优化事件： 

1. 转到 **数据** > **事件**，选择屏幕顶部的 **+ 新建事件**。

1. 在 **新建事件** 对话中，选择 **创建优化事件**，然后选择 **下一步**。
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="新建事件向导。":::
     
1. 在 **新建事件** 对话中，输入以下信息：

   - 从 **基本事件** 下拉列表中选择一个事件。
   - 在 **已优化的事件显示名称** 框中输入名称。
   - （可选）更新建议的 **实际名称**，但不要使用空格。

1. 选择 **创建** 以应用设置。

优化事件现在已出现在您的 **事件** 列表中。

### <a name="edit-event-name"></a>编辑事件名称

您可以更改基本事件或优化事件的名称和属性。

1. 转到 **数据** > **事件**。 

1. 针对事件选择 **更多 [...]**，并选择 **编辑名称**。
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="用于创建已优化的事件的选项。":::

3. 更新事件名称并选择 **重命名**。

### <a name="view-the-details-of-a-refined-event"></a>查看优化事件的详细信息：

1. 在 **事件** 列表中，选择您的基本事件或优化事件。 

1. 选择屏幕顶部的 **添加和删除属性** 打开 **编辑属性** 窗格。 

     :::image type="content" source="media/add-remove-properties.png" alt-text="添加和删除属性。":::

1. 使用复选框可以选择要显示的属性和要隐藏的属性。 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="编辑已优化的事件的属性。":::

1. 选择 **确认** 应用您的选择，然后选择 **保存**。


### <a name="edit-selected-properties-for-a-refined-event"></a>编辑优化事件的选定属性

1. 转到 **数据** > **事件** 并选择已优化的事件以打开详细视图。
1. 选择 **添加和删除属性**。 
1. 编辑复选框选择。
1. 选择 **确认**，然后选择 **保存** 以应用更改。

有关导出事件的信息，请参阅[导出事件](export-events.md)。
[!INCLUDE[footer-include](../includes/footer-banner.md)]
