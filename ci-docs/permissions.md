---
title: 分派用户权限
description: 了解权限和用户角色。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245408"
---
# <a name="assign-user-permissions"></a>分派用户权限

对 Customer Insights 的访问仅限于您组织中由管理员添加到应用程序的用户。管理员可以添加、编辑或删除用户。 用户可以是单个用户、组或应用程序。 用户可以具有三种类型的角色：

## <a name="viewer"></a>查看者

- 在 **主页** 和 **客户细分** 页面中浏览见解和客户细分。
- 使用 **客户** 页搜索和筛选客户配置文件。 字段必须是可搜索字段。
- 查看和浏览 **扩充** 页面。
- 使用 **实体** 页浏览和导出实体。
- 使用 **系统** 页查看系统进程的状态。
- 在 **导出** 页中查看导出。
- 安装和使用 **Power BI Customer Insights** 仪表板。

## <a name="contributor"></a>参与者

- 查看者的所有可用权限。
- 使用 **数据源** 页面加载和转换数据。
- 完成 **数据统一**，这会产生统一的客户配置文件实体。
- 定义 **关系** 和 **活动**。
- 使用 **客户细分** 页面创建客户细分。
- 使用 **度量** 页创建度量。
- 通过 **扩充** 页面管理配置和扩充客户配置文件（仅适用于第一方扩充）。
- 根据[与参与者共享的连接](connections.md#allow-contributors-to-use-a-connection-for-exports)来管理和创建导出。

## <a name="admin"></a>管理员

- 参与者的所有可用权限。
- 更改 **系统** 页面上的设置（包括工作语言），刷新系统流程的计划，并导出诊断日志。
- 更改 **安全性** 页面上的设置，包括用户、API 密钥、专用链接和密钥保管库。
- 使用 **搜索和筛选** 索引页面（通过 **客户** 页面访问）设置客户页面的搜索和筛选定义。
- 在 **连接** 页上管理连接并允许其他用户角色使用连接。
- 通过 **扩充** 页面管理配置和扩充客户配置文件（适用于所有扩充）。
- 在 **导出** 页上管理和创建导出。
- 安装和使用 **客户卡加载项**。
- 添加和使用 **Power Apps 连接器**。
- [启用 Customer Insights API 的使用](apis.md)。
- [将环境所有权分配](manage-environments.md#change-the-owner-of-an-environment)给其他管理员。

## <a name="admin-owner"></a>管理员（负责人）

- 管理员将具有所有权限。
- [重置和删除](manage-environments.md#reset-an-existing-environment-preview)环境。

## <a name="add-users"></a>添加用户

1. 转到 **管理员** > **安全性**，然后选择 **用户** 选项卡。

1. 选择 **添加用户** 以打开 **添加/编辑权限** 窗格。

1. 使用 **搜索** 字段查找要添加的 Azure Active Directory 用户或组。 选择要分配给该用户或组的 **角色**。

1. 选择 **保存**。 将与用户或组成员自动共享当前环境。 用户可以访问 Customer Insights 应用并根据其指定角色进行工作。

## <a name="view-current-permissions"></a>查看当前权限

转到 **管理员** > **安全性**，选择 **用户** 选项卡查看活动用户列表及其角色分配。 您可以按任何列对用户列表进行排序，或使用搜索框查找特定用户。

## <a name="manage-current-users"></a>管理当前用户

转到 **管理员** > **安全性**，选择 **用户** 选项卡。您可以按任何列对用户列表进行排序，或使用搜索框查找要管理的用户。

选择用户查看可用操作。

- 选择 **编辑** 编辑用户在 Customer Insights 中的角色。 选择 **保存** 确认更改。
- 选择 **删除** 删除用户对 Customer Insights 的访问权限。 选择 **删除** 以确认删除。

[!INCLUDE [footer-include](includes/footer-banner.md)]
