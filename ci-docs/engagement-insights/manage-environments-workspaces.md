---
title: 管理工作区和环境
description: 如何创建、重命名和删除工作区和环境。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645435"
---
# <a name="manage-environments-and-workspaces"></a>管理环境和工作区

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>概述

本主题讨论如何在创建工作区和环境后对其进行管理。 

- *工作区* 是您存储和管理事件和报表的空间。 您可以在工作区中实时查看用户活动。 创建工作区时，您可以选择要发送到工作区的数据的类型。 当前，支持 Web 数据和移动应用。 有关详细信息，请参阅[创建工作区并添加成员](create-workspace.md)。

- *环境* 是用于管理工作区和连接的空间。 有关详细信息，请参阅[创建新环境](create-new-environment.md)。

## <a name="manage-an-existing-workspace"></a>管理现有工作区

您可以在一个环境中同时维护多个工作区。 您的[角色](user-roles.md)决定了您如何在这些工作区中工作。 

 - 您必须是环境管理员或工作区管理员才能管理该工作区。
 - 作为工作区管理员，您可以重命名现有工作区或删除它们。 

:::image type="content" source="media/workspace-edit.png" alt-text="工作区管理中心。":::

### <a name="edit-a-workspace-name"></a>编辑工作区名称

1. 转到 **管理员** > **工作区**，然后选择 **设置**。

1. 在 **工作区名称** 框中，输入新名称。

1. 选择 **保存** 以应用您所做的更改。

### <a name="delete-a-workspace"></a>删除工作区

删除工作区将永久删除其所有内容、数据、设置和权限。 此操作无法撤消。

1. 转到 **管理员** > **工作区**，然后选择 **设置**。

1. 选择 **删除工作区**。 

1. 在 **删除工作区** 对话中，全部大写输入 **CONFIRM DELETE**。 

1. 选择 **删除** 以永久删除工作区。

### <a name="manage-workspace-members"></a>管理工作区成员

1. 转到 **管理员** > **工作区**，然后选择 **成员**。

1. 选择 **添加成员** 以授予访问权限并[分派角色](user-roles.md)。 目前，只有 **工作区管理员** 可用。

1. 选择 **添加成员** 以将其添加到您的工作区。

## <a name="manage-an-existing-environment"></a>管理现有环境

作为环境管理员，您可以从左侧导航窗格访问环境。 您可以配置环境设置、其他环境管理员和工作区。 选择相关选项卡以在管理中心的不同区域之间移动。

:::image type="content" source="media/environment-edit.png" alt-text="环境管理中心。":::

### <a name="rename-an-environment"></a>重命名环境

1. 转到 **管理员** > **环境**，然后选择 **设置**。

1. 更新 **环境名称** 并选择 **保存** 以应用所做的更改。

### <a name="manage-environment-members"></a>管理环境成员

1. 转到 **管理员** > **环境**，然后选择 **成员**。

1. 选择 **添加成员** 以更新成员并[分派角色](user-roles.md)。 目前，只有 **环境管理员** 可用。

1. 选择 **添加成员** 以将其添加到您的环境。

### <a name="delete-an-environment"></a>删除环境

环境管理员可以删除环境。 在删除环境之前，您必须删除其下的所有工作区。

1. 转到 **管理员** > **环境**，然后选择 **设置**。

1. 选择 **删除环境**。 

1. 在 **删除工作区** 对话中，全部大写输入 **CONFIRM DELETE**。 

1. 选择 **删除** 以永久删除环境。

## <a name="manage-connections"></a>管理连接

通过建立与访问群体见解的连接，您可以基于统一的客户配置文件在参与见解中查看报表。 

有关详细信息，请参阅[创建参与见解与访问群体见解之间的链接](integrate-audience-insights-engagement-insights.md)。

## <a name="manage-personal-data"></a>管理个人数据

为了保护客户的个人数据，您可以删除或导出最终用户身份信息。

有关详细信息，请参阅[删除和导出包含个人信息的事件数据](delete-export-personal-data.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
