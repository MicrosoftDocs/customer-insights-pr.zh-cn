---
title: 快速入门产品简介
description: 用于设置参与见解功能的首次运行体验。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 95caaa1f67a7740328b67face00acaea65452eb0
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494446"
---
# <a name="first-run-experience"></a>首次运行体验

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解（Dynamics 365 Customer Insights 的一项功能）使您能够收集和衡量您网站上的客户行为。 本文介绍如何注册参与见解、设置工作区、向工作区添加成员以及进行更改。

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>注册以观看参与见解演示

您必须拥有一个可用的 Microsoft Azure Active Directory 用户帐户。 

1. 打开[参与见解](https://home.ci.ai.dynamics.com/app/engagement-insights)网站。 

1. 使用你的学校或工作帐户登录。

1. 选择区域，然后使用相应复选框指示您是否选择通过电子邮件来接收更新和服务。

1. 查看 **参与见解（预览版）使用条款** 和 **隐私声明**，然后选择 **浏览演示** 以接受它们。

1. 使用一组示例数据来了解产品。 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>在参与见解中设置您的第一个工作区

工作区是您存储和管理事件和报表的一种方式。

要创建您的第一个工作区，请执行以下操作

1. 在参与见解中，选择 **连接数据** 以启动向导。 

:::image type="content" source="media/banner.png" alt-text="具有连接数据按钮的 Customer Insights 页。":::

2. 选择要在新的工作区中衡量的活动类型。 目前，只有 **网站活动** 可用。 **应用活动** 和 **设备活动** 将在未来版本中可用。

1. 选择 **下一步** 以确认并创建工作区。

1. 在您的网站上添加代码片段，以开始在参与见解中接收数据。 您可以立即实施此操作，或者与您的网站管理员共享代码和说明。若要稍后查找代码片段，请转到 **管理员** > **工作区** > **安装指南**。

   > [!IMPORTANT]
   > 数据将不会显示在工作区中，除非在网站上实施了代码。

1. 选择 **完成** 以打开您的新工作区。 

## <a name="add-members-to-an-existing-workspace"></a>向现有工作区添加成员

默认情况下，仅创建该工作区的人员有权访问该工作区。 您随时都可以将组织中的其他用户添加到现有工作区中。

:::image type="content" source="media/add-members.png" alt-text="具有添加成员按钮标注的成员页面。":::

1. 转到 **管理员** > **工作区** > **成员**。

2. 选择 **添加成员**。 使用 **成员** 框可以添加组织中其他人员。 可以一次添加多个成员。

3. 选择要分派给新成员的 **角色**。 目前，可能选择 **工作区管理员**。 其他角色将在未来版本中添加。

4. 选择 **添加成员** 以进行确认。

若要从工作区中删除成员，请在 **成员** 页面上选择其名称旁边的 **...**，然后从下拉菜单中选择 **删除**。

## <a name="edit-a-workspace"></a>编辑工作区

您随时都可以编辑现有工作区的详细信息。

:::image type="content" source="media/change-workspace-settings.png" alt-text="具有工作区名称标注和说明的工作区设置页面。":::

1. 转到 **管理员** > **工作区** > **设置**。

1. 更改您的工作区的 **名称**。

1. 选择 **保存** 以应用您所做的更改。

## <a name="add-another-new-workspace"></a>添加其他新工作区

:::image type="content" source="media/workspace-switcher.png" alt-text="包含导航窗格标注和说明的 Customer Insights 页面。":::

您可以创建其他工作区来对数据进行分类。

1. 在工作区选择器中，选择 **新建工作区**。

1. 输入 **名称** 以及可选 **说明**。

1. 选择 **创建**。

## <a name="switch-between-workspaces"></a>在工作区之间切换

若要在工作区之间进行更改，请选择工作区切换器。 您也可以创建新工作区，或者选择 **Web 示例** 以查看报表并使用示例数据试用功能。 



[!INCLUDE[footer-include](../includes/footer-banner.md)]