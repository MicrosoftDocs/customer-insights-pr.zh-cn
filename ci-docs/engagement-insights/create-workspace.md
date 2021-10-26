---
title: 创建新工作区
description: 工作区的用途以及如何创建新工作区。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645299"
---
# <a name="create-a-new-workspace-and-add-members"></a>创建新工作区并添加成员

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

工作区是您可以实时查看用户活动以更好地了解访问群体的一种方式。 您可以在其中存储和管理事件和报表。

创建工作区时，您可以选择要关注的数据的类型。 您随时都可以将其他用户或成员添加到现有工作区中。 

## <a name="create-a-new-workspace"></a>创建新工作区

创建工作区的过程包括设置 *环境* 以组织您的工作区。 环境是可包含一个或多个工作区的空间。 您可以利用环境来管理您的工作区以及与 Customer Insights 和访问群体见解功能的连接。

1. 从工作区切换器中选择 **新建**。

   :::image type="content" source="media/new-workspace.png" alt-text="包含导航窗格标注和说明的 Customer Insights 页面。":::

1. 在 **工作区** 窗格中，输入 **工作区名称**。

   :::image type="content" source="media/workspace-name.png" alt-text="键入工作区名称。":::

1. 选择您要衡量的平台类型（Web 或移动）。

1. 选择 **显示高级设置** 启用或禁用这些可选设置：

   - 将 **未知到已知** 切换到“启用”，将 Web 事件与先前通过身份验证的用户关联。 有关详细信息，请参阅[识别以前通过身份验证的访问者的 Web 事件](unknown-to-known.md)
   - 将 **筛选机器人流量** 切换到“启用”，删除此工作区中机器人的 Web 流量。 

1. 完成后选择 **完成**。 

1. 安装代码片段开始接收数据，然后选择 **完成** 创建工作区。 有关详细信息，请参阅[开发人员资源概述](developer-resources.md)。

> [!NOTE]
> 您现在可以从 **角色** 列表中添加成员并分配他们的权限级别。 有关详细信息，请参阅[角色和权限](user-roles.md)。 

有关详细信息，请参阅[管理环境和工作区](manage-environments-workspaces.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
