---
title: 管理用户权限
description: 了解权限和用户角色。
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689209"
---
# <a name="user-permissions"></a>用户权限

**权限** 页面用于设置使用访问群体见解的角色和权限。

您需要有管理员权限才能查看此页面。 若要在访问群体见解中访问权限页面，请转到 **管理员** > **权限**。

有三种类型的角色：

## <a name="viewer"></a>查看者

- 在 **主页** 和 **客户细分** 页面中浏览见解和客户细分。
- 使用 **客户** 页搜索和筛选客户配置文件。 字段必须是可搜索字段。
- 查看和浏览 **扩充** 页面。
- 使用 **实体** 页浏览和导出实体。
- 使用 **系统** 页查看系统进程的状态。
- 从 **客户细分** 页面中导出客户细分。
- 安装和使用 **Power BI Customer Insights** 仪表板。

## <a name="contributor"></a>参与者

- 查看者的所有可用权限。
- 使用 **数据源** 页面加载和转换数据。
- 填写 *数据统一* 部分（**映射**、**匹配** 和 **合并**），这将生成统一的客户配置文件实体。
- 定义 **关系** 和 **活动**。
- 使用 **客户细分** 页面创建客户细分。
- 使用 **度量** 页创建度量。
- 通过 **扩充** 页面管理配置和扩充客户配置文件（仅适用于第一方扩充）。

## <a name="administrator"></a>管理员

- 参与者的所有可用权限。
- 更改 **系统** 页面上的设置（包括工作语言），并刷新系统流程的计划。
- 使用 **权限** 页面查看和添加权限。
- 使用 **搜索和筛选** 索引页面（通过 **客户** 页面访问）设置客户页面的搜索和筛选定义。
- 使用 **导出目标** 页定义 Dynamics 365 Sales 客户细分目标。
- 通过 **扩充** 页面管理配置和扩充客户配置文件（适用于所有扩充）。
- 安装和使用 **客户卡加载项**。
- 添加和使用 **Power Apps 连接器**。
- [启用 Customer Insights API 的使用](apis.md)。

## <a name="assign-roles-and-permissions"></a>分派角色和权限

1. 在访问群体见解中，转到 **管理员** > **权限**。

1. 选择 **添加用户** 以打开 **添加/编辑权限** 窗格。

1. 使用 **搜索** 字段查找要调整其权限的 Azure Active Directory 用户或组。 选择要分配给该用户或组的 **角色**。

1. 选择 **保存**。 将与您已更改其权限的用户或组成员自动共享当前环境。 用户可以访问 Customer Insights 应用并根据其指定角色进行工作。

## <a name="view-current-permissions"></a>查看当前权限

在访问群体见解中，转到 **管理员** > **权限** 以查看哪些角色分配当前处于活动状态。

- **类型** 列指定一个用户、组或应用程序。 系统支持各个用户和组。
- 角色在 **角色** 列下指定。
- 选择任意列标题可按该列的值对结果进行排序。
- 使用页面顶部的 **搜索** 字段查找特定用户。