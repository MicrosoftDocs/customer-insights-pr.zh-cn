---
title: 角色和权限
description: 工作区成员的可用角色和权限的概述。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227528"
---
# <a name="roles-and-permissions"></a>角色和权限

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

工作区是您存储和管理事件和报表的地方。 有关详细信息，请参阅[创建工作区并添加成员](create-workspace.md)。 

工作区可以包含以下角色和权限：

- *成员* 角色是可以访问工作区的用户。 您可以向工作区分配成员并定义他们的角色和权限。 
- *管理员* 角色管理工作区和环境，并为其他用户配置参与见解。 
- *参与者* 角色面向不需要配置参与见解但想要创建自己的报表、漏斗图或客户细分的分析人员。

## <a name="permissions"></a>权限
  
下表确定了每个角色的权限。 

| 权限 | 环境管理员 | 工作区管理员 | 环境参与者 | 工作区参与者 | 
|--|--|--|--|--|
| 创建环境（创建者将自动成为环境管理员） | X* | X* | X* | X* |  
| 配置环境（环境成员、删除环境） | X |  |  |  |  
| 创建工作区 | X |  |  |  |  
| 配置工作区（工作区成员、删除工作区） | X | X |  |  |  
| 配置事件和已优化的事件 | X | X | |  |  
| 查看工作区事件和已优化的事件 | X | X | |  |  
| 查看工作区资源（报表、客户细分和指标）| X | X | X | X |  
| 创建自定义报表和漏斗图 | X | X | X | X |  
| 创建基本指标和维度| X | X |  |  |  
| 创建客户细分| X | X | X | X |  

*只能在预览版中创建试用环境。 

## <a name="add-members"></a>添加成员

您可以在工作区和环境中添加和删除成员。 有关详细信息，请参阅[环境和工作区](manage-environments-workspaces.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
