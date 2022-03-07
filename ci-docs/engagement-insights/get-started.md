---
title: 开始使用参与见解功能
description: 用于快速开始使用的帮助资源的概述。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405347"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>开始使用 Dynamics 365 Customer Insights 参与见解功能（公开预览版）

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解功能使您能够收集和衡量您网站上的客户行为。 它集成了访问群体见解功能，以便您可以查看丰富的实时行为分析以及客户配置文件报表。 本文中的链接可帮助您快速配置和设置您的环境。

## <a name="step-1-review-prerequisites"></a>步骤 1：查看必备条件

首先，您必须拥有一个可用的 Microsoft Azure Active Directory 用户帐户。 然后，在设置参与见解工作区之前阅读以下文章。

- 查看并同意 Microsoft 的[服务条款](terms-of-service.md)。  
- 阅读[管理 Cookie 和用户同意](user-consent-storage.md)文章。 在查看本文后，评估是否需要更新用户同意通知。 如果您以前没有“不需要”的 Cookie，您可能需要更新站点策略。
- 查看[词汇表](glossary.md)，快速了解关键术语和概念。

## <a name="step-2-explore-engagement-insights"></a>步骤 2：探索参与见解

首次访问参与见解时，您可以配置设置、查看策略和浏览产品。

1. 使用 Microsoft Azure Active Directory 用户帐户登录[参与见解功能](https://pi.dynamics.com)门户。 （此帐户可以是您的学校帐户或工作帐户。）

1. 选择区域，然后使用相应复选框指示您是否选择通过电子邮件来接收更新和服务。

1. 查看 **参与见解（预览版）使用条款** 和 **隐私声明**，然后选择 **浏览演示** 以接受它们。

1. 使用一组示例数据来了解产品。

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>步骤 3：设置工作区并向您的网站添加代码

您可以在工作区中实时查看用户活动以及存储和管理报表。 将代码添加到您的网站，以开始收集来自用户的 *事件*、活动数据。

1. [创建工作区](create-workspace.md)并添加成员。

1. [将代码添加到您的网站](instrument-website.md)或[移动应用](developer-resources.md#capture-events-from-mobile-apps)，以查看到达工作区中的用户活动。

1. 查看按浏览器、设备、操作系统、位置和语言显示活动用户的[实时报表](view-reports.md)。 您也可以创建[自定义报表](custom-reports.md)来创建自己的可视化项。
    
## <a name="step-4-export-data-to-other-channels"></a>步骤 4：将数据导出到其他渠道

您可以创建 Web 分析数据的 *已优化的事件*（虚拟视图）。 然后将数据筛选并导出到 Azure Data Lake Storage。 可将导出的数据作为数据源引入。 有关详细信息，请参阅[创建参与见解与访问群体见解之间的链接](integrate-audience-insights-engagement-insights.md)。

1. 为导出[创建已优化的事件](refined-events.md)。

1. [将数据导出](export-events.md)到 Data Lake Storage。

1. 了解如何[删除和导出包含个人信息的事件数据](delete-export-personal-data.md)。
 
## <a name="step-5-stay-connected"></a>步骤 5：保持连接

我们期待您的积极参与，并计划在开发未来版本时考虑所有相关反馈。 通过以下渠道之一共享您的反馈并报告问题：
- [社区](https://go.microsoft.com/fwlink/?linkid=2141648)
- [提供反馈](https://go.microsoft.com/fwlink/?linkid=2143222)
- [请求支持](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
