---
title: 开始使用参与见解功能
description: 用于快速开始使用的帮助资源的概述。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623666"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>开始使用 Dynamics 365 Customer Insights 参与见解功能（公开预览版）

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解功能使您能够收集和衡量您网站上的客户行为。 它集成了访问群体见解功能，以便您可以查看丰富的实时行为分析以及客户配置文件报表。 本文中的链接可帮助您快速配置和设置您的环境。

## <a name="step-1-review-prerequisites"></a>步骤 1：查看必备条件

首先，您必须拥有一个可用的 Microsoft Azure Active Directory (AAD) 用户帐户。 然后，在设置参与见解工作区之前阅读以下文章。

- 查看并同意 Microsoft 的[服务条款](terms-of-service.md)。  
- 阅读[管理 Cookie 和用户同意](user-consent-storage.md)文章。 之后，评估是否需要更新您的用户同意通知。 如果您以前没有“不需要”的 Cookie，您可能需要更新站点策略。
- 查看[词汇表](glossary.md)，快速了解关键术语和概念。

## <a name="step-2-explore-engagement-insights"></a>步骤 2：探索参与见解

首次访问参与见解时，可以配置设置，查看策略，以及探索功能。

1. 使用您的 Microsoft AAD 用户（学校或工作）帐户登录[参与见解功能门户](https://home.ci.ai.dynamics.com/app/engagement-insights)。

1. 选择您的区域，然后选中是否要选择加入接收电子邮件更新和优惠的框。

1. 查看参与见解（预览）**使用条款** 和 **隐私声明**，然后选择 **浏览演示** 接受这些设置。

1. 使用一组示例数据来了解产品。

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>步骤 3：设置工作区和创建报表

工作区用于实时查看用户活动，以及存储和管理报表。 将代码添加到您的网站，以开始收集来自用户的 *事件*、活动数据。

1. [创建工作区](create-workspace.md)并添加成员。

1. 将代码添加到您的[网站](instrument-website.md)或[移动应用](developer-resources.md#capture-events-from-mobile-apps)，以查看到达工作区中的用户活动。

1. 查看按浏览器、设备、操作系统、位置和语言显示活动用户的[实时报表](view-reports.md)。 您也可以创建[自定义报表](custom-reports.md)来创建自己的可视化项。

1. 创建[维度](dimensions.md)可按新用户和返回用户对访问者进行排序，创建[指标](metrics.md)可帮助更好地了解用户行为，创建[客户细分](segments.md)可根据特征或网站交互识别访问者子集。
    
## <a name="step-4-export-data-to-other-channels"></a>步骤 4：将数据导出到其他渠道

您可以创建 Web 分析数据的 *已优化的事件*（虚拟视图）。 然后将数据筛选并导出到 Azure Data Lake Storage。 可将导出的数据作为数据源引入。

1. 为导出[创建已优化的事件](refined-events.md)。

1. [将数据导出](export-events.md)到 Azure Data Lake Storage。

1. [创建访问群体见解与参与见解之间的链接](integrate-audience-insights-engagement-insights.md)，以便在这两种功能之间共享数据。

1. 使用 **未知到已知** 功能[识别先前通过身份验证的用户的 Web 事件](unknown-to-known.md)。

1. 了解如何[删除和导出包含个人信息的事件数据](delete-export-personal-data.md)。

## <a name="step-5-create-and-manage-funnel-reports"></a>步骤 5：创建和管理漏斗图报表

漏斗图报表通过您的网站或移动设备收集有关客户旅程期间执行的步骤的信息。 除了创建开箱即用的配置文件报表和自定义报表之外，您还可以创建漏斗图报表来确定客户在进行购买之前所使用的路径。 

1. [创建漏斗图报表](funnel-reports.md)为决策提供信息并确定优化和流程改进的领域。

1. 使用参与见解 [Android SDK](get-started-android.md) 或 [iOS SDK](get-started-ios.md) 检测您的移动应用后，即可创建跨渠道漏斗图报表。

1. 使用[漏斗图见解](funnel-reports.md#funnel-insights)深入了解有关漏斗图报表中的步骤的客户行为。
 
## <a name="step-6-stay-connected"></a>步骤 6：保持连接

我们感谢您的积极参与， 并将在开发将来的版本时注意所有相关反馈。 通过以下渠道之一共享您的反馈并报告问题：
- [社区](https://go.microsoft.com/fwlink/?linkid=2141648)
- [提供反馈](https://go.microsoft.com/fwlink/?linkid=2143222)
- [请求支持](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
