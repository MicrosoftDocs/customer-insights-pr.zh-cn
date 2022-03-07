---
title: 管理工作区和环境
description: 如何创建、重命名和删除工作区和环境。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034031"
---
# <a name="manage-environments-and-workspaces"></a>管理环境和工作区

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>概述

工作区是您存储和管理事件和报表的空间。 您可以在工作区中实时查看用户活动。 创建工作区时，您可以选择要发送到工作区的数据的类型。 当前，支持 Web 数据和移动应用。

环境是用于管理工作区和连接的空间。 使用环境的方式取决于组织和用例。 例如，您可以创建：

-   单个环境。
-   用于测试和生产的单独环境。
-   组织中特定团队或部门的单独环境，其中包含与每个访问群体相关的事件。
-   适用于公司的其他全球分支机构的不同环境。
-   与 Customer Insights 访问群体见解功能的连接。

## <a name="choose-an-environment-and-create-a-workspace"></a>选择环境并创建工作区 

每个工作区都需要在环境中。 您可以创建预先存在的环境，也可以在您创建工作区时创建新环境。 然后您可以选择添加工作区成员并开始收集数据。

**要创建您的第一个工作区，请执行以下操作**

1. 在参与见解中，从工作区切换器中选择 **新建**。 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights 页面工作区选取器。":::

1. 从列表中选择环境或选择 **创建新环境**。

1. 在 **工作区名称** 中输入名称。 

1. 选择要创建的环境类型，具体取决于您是否要度量在网站上或移动应用中发生的情况。 

1. 您可以添加成员，然后从 **角色** 列表中分派其权限级别。 然后选择 **完成** 以创建工作区，或选择 **下一步** 以安装代码。 

1. 安装代码片段以开始接收数据，然后选择 **完成**。 

## <a name="manage-a-workspace"></a>管理工作区

您可以在一个环境中同时维护多个工作区。 您的[角色](user-roles.md)决定了您如何在这些工作区中工作。 

 - 您必须是环境管理员或工作区管理员才能管理该工作区。
 - 作为工作区管理员，您可以重命名现有工作区或删除它们。 

### <a name="edit-a-workspace-name"></a>编辑工作区名称

1. 转到 **管理员** > **工作区**，然后选择 **设置**。

1. 在 **工作区名称** 框中，输入新名称。

1. 选择 **保存** 以应用您所做的更改。

### <a name="delete-a-workspace"></a>删除工作区

删除工作区将永久删除其所有内容、数据、设置和权限。 此操作无法撤消。

1. 转到 **管理员** > **工作区**，然后选择 **设置**。

1. 选择 **删除工作区**。 

1. 在 **删除工作区** 对话框中，输入 **确认删除**。 

1. 选择 **删除** 以永久删除工作区。

### <a name="manage-workspace-members"></a>管理工作区成员

1. 转到 **管理员** > **工作区**，然后选择 **成员**。

1. 选择 **添加成员** 以授予访问权限并[分派角色](user-roles.md)。 目前，只有 **工作区管理员** 可用。

1. 如果设置 [与访问群体见解的连接](configure-connections.md)，则可以选择 **允许访问配置文件数据**，以允许成员查看基于[用户配置文件](profile-reports.md)的报表。

1. 选择 **添加成员** 以将其添加到您的工作区。

## <a name="manage-an-environment"></a>管理环境

作为环境管理员，您可以从左侧导航窗格访问环境。 您可以配置环境设置、其他环境管理员、工作区和[与访问群体见解的连接](configure-connections.md)。 选择相关选项卡以在管理中心的不同区域之间移动。

:::image type="content" source="media/New-environment.png" alt-text="环境管理中心。":::

### <a name="create-an-environment"></a>创建环境

1. 在工作区选取器中，选择 **+ 新建**。

1. 在引导式体验中，打开 **环境** 下拉菜单并选择 **创建新环境**。 

1. 提供 **环境名称**。

   :::image type="content" source="media/create-environment.png" alt-text="引导式体验中用于指定环境详细信息的步骤。":::

1. 选择 **区域** 并选择 **下一步**。 

1. 提供工作区名称并选择要创建的工作区类型。 

1.  或者，添加成员并复制代码片段以完成创建过程。

### <a name="rename-an-environment"></a>重命名环境

1. 转到 **管理员** > **环境**，然后选择 **设置**。

1. 更新 **环境名称** 并选择 **保存** 以应用所做的更改。

### <a name="manage-environment-members"></a>管理环境成员

1. 转到 **管理员** > **环境**，然后选择 **成员**。

1. 选择 **添加成员** 以更新成员并[分派角色](user-roles.md)。 目前，只有 **环境管理员** 可用。

1. 如果设置 [与访问群体见解的连接](configure-connections.md)，则可以选择 **允许访问配置文件数据**，以允许成员查看基于[用户配置文件](profile-reports.md)的报表。

1. 选择 **添加成员** 以将其添加到您的环境。

### <a name="delete-an-environment"></a>删除环境

环境管理员可以删除环境。 在删除环境之前，您必须删除其下的所有工作区。

1. 转到 **管理员** > **环境**，然后选择 **设置**。

1. 选择 **删除环境**。 

1. 在 **删除工作区** 对话框中，输入 **确认删除**。 

1. 选择 **删除** 以永久删除环境。

## <a name="manage-connections"></a>管理连接

通过建立与访问群体见解的连接，您可以基于统一的客户配置文件在参与见解中查看报表。 

有关详细信息，请参阅[配置连接](configure-connections.md)。

## <a name="manage-personal-data"></a>管理个人数据

为了保护客户的个人数据，您可以删除或导出最终用户身份信息。

有关详细信息，请参阅[删除和导出包含个人信息的事件数据](delete-export-personal-data.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
