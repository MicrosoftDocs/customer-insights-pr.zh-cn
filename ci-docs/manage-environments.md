---
title: 管理环境
description: 了解如何以管理员身份管理现有 Customer Insights 环境。
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304269"
---
# <a name="manage-environments"></a>管理环境

管理员可以[创建](create-environment.md)和管理环境。 他们可以更改现有环境中的一些设置。 创建环境后会确定业务、类型、区域、存储选项和 Dataverse 设置。 如果要更改这些设置，请[重置环境](#reset-an-existing-environment-preview)或[创建新的环境](create-environment.md)。

## <a name="edit-an-existing-environment"></a>编辑现有环境

编辑现有环境的详细信息，如默认环境的名称或设置。

1. 选择应用标题中的 **环境** 选择器。

1. 选择 **编辑** 图标。

   :::image type="content" source="media/edit-environment.png" alt-text="用于编辑环境设置的图标。":::

1. 在 **编辑环境** 窗格中，更新环境设置。

1. 选择 **查看并完成**，然后选择 **更新** 应用更改。

## <a name="change-the-owner-of-an-environment"></a>更改环境负责人

多个用户可以具有管理员权限，但只有一个用户是环境的负责人。 默认情况下，最初将由管理员创建环境。 作为环境的管理员，您可以将所有权分配给具有管理员权限的其他用户。

1. 选择应用标题中的 **环境** 选择器。

1. 选择 **编辑** 图标。

1. 在 **编辑环境** 窗格中，转到 **基本信息** 步骤。

1. 在 **更改环境负责人** 字段中，选择新的环境负责人。  

1. 选择 **查看并完成**，然后选择 **更新** 应用更改。

## <a name="claim-ownership-of-an-environment"></a>认领环境的所有权

如果删除或暂停了负责人的用户帐户，则环境将没有负责人。 任何管理员用户都可以认领所有权，成为新负责人。 负责管理员可以继续负责环境或[将所有权更改为其他管理员](#change-the-owner-of-an-environment)。

要认领所有权，选择在原始负责人离开组织时显示在 Customer Insights 中每个页面顶部的 **获取所有权** 按钮。

## <a name="reset-an-existing-environment-preview"></a>重置现有环境（预览）

作为环境的负责人，如果您想要删除所有配置并删除引入的数据，将环境重置为空状态。

1. 选择应用标题中的 **环境** 选择器。

1. 选择要重置的环境并选择竖省略号 (&vellip;)。

1. 选择 **重置（预览）**。

   :::image type="content" source="media/reset-environment.png" alt-text="用于重置环境的控件。":::

1. 选择是要重置整个环境、除数据源之外的所有内容，还是基于统一客户配置文件配置的任何内容。

1. 要进行确认，请输入环境名称并选择 **重置**。

## <a name="delete-an-existing-environment"></a>删除现有环境

作为环境的负责人，您可以将其删除。

> [!IMPORTANT]
> 删除环境不会删除到 Dataverse 环境的连接。 如果您计划将来将相同的 Dataverse 环境连接到新的 Customer Insights 环境，则必须[删除与 Dataverse 环境的连接](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment)。

1. 选择应用标题中的 **环境** 选择器。

1. 选择要删除的环境并选择竖省略号 (&vellip;)。 

1. 选择 **删除**。

   :::image type="content" source="media/delete-environment.png" alt-text="用于删除环境的控件。":::

1. 若要确认删除，请输入环境名称，然后选择 **删除**。

[!INCLUDE [footer-include](includes/footer-banner.md)]
