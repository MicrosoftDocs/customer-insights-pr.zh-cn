---
title: 创建新环境
description: 环境的用途以及如何创建新环境。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648106"
---
# <a name="create-a-new-environment"></a>创建新环境 

## <a name="overview"></a>概述

环境是用于管理工作区和连接的空间。 使用环境的方式取决于组织和用例。 例如，您可以创建：

- 单个环境。
- 用于测试和生产的单独环境。
- 组织中特定团队或部门的单独环境，其中包含与每个访问群体相关的事件。
- 适用于公司的其他全球分支机构的不同环境。
- 与 Customer Insights 访问群体见解功能的连接。

## <a name="create-a-new-environment"></a>创建新环境

1. 在主横幅的右侧，选择环境选取器，然后选择 **+新建**。

   :::image type="content" source="media/environment-picker.png" alt-text="选择环境选取器。":::

1. 在 **设置** 窗格中，键入 **环境名称**。

1. 根据您的计划类型选择客户 **类型**。

1. 选择 **区域** 并选择 **下一步**。 

1. 键入 **工作区名称**，这样，您可以收集特定网站或应用的数据。 有关详细信息，请参阅[创建工作区](create-workspace.md)。

1. 选择您要创建的 **工作区类型**（Web 或移动）。 

1. 选择 **显示高级设置** 启用或禁用这些可选设置：

   - 将 **未知到已知** 切换到“启用”，将 Web 事件与先前通过身份验证的用户关联。 有关详细信息，请参阅[识别以前通过身份验证的访问者的 Web 事件](unknown-to-known.md)
   - 将 **筛选机器人流量** 切换到“启用”，删除此工作区中机器人的 Web 流量。 

1. 完成后选择 **完成**。 

1. 安装代码片段开始接收数据，然后选择 **完成** 创建工作区。 有关详细信息，请参阅[开发人员资源概述](developer-resources.md)。

> [!NOTE]
> 您现在可以从 **角色** 列表中添加成员并分配他们的权限级别。 有关详细信息，请参阅[角色和权限](user-roles.md)。 

有关详细信息，请参阅[管理环境和工作区](manage-environments-workspaces.md)。

## <a name="work-with-your-new-environment"></a>使用新环境

- [创建工作区](../engagement-insights/create-workspace.md)并添加成员。
- [将代码添加到您的网站](../engagement-insights/instrument-website.md)或[移动应用](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps)。
- 查看[实时报表](../engagement-insights/view-reports.md)或创建[自定义报表](../engagement-insights/custom-reports.md)。
- 为导出[创建已优化的事件](../engagement-insights/refined-events.md)。
- [将数据导出](../engagement-insights/export-events.md)到 Data Lake Storage。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
