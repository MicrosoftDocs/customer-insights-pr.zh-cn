---
title: 访问群体见解中的主页
description: 开始浏览主页上的应用。
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405210"
---
# <a name="create-a-new-environment"></a>创建新环境

## <a name="create-a-trial-environment"></a>创建试用环境

您可以在[试用注册页](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)注册试用。 

> [!NOTE]
> 试用将在 30 天后过期。

1. 选择 **注册免费试用** 选项，然后选择 **立即注册**。

1. 提供您的工作或学校电子邮件地址，告诉我们有关您个人的更多信息，然后选择 **下一步**。

1. 为您的新环境提供一个 **名称**。 

1. 选择试用类型。

1. 选择环境的 **区域**。

1. （可选）对于 Dynamics 365 组织的管理员：选择 **高级设置**，提供您组织的 URL，以使用预测功能（如客户流失）。

1. 选择 **创建**。 

环境创建后，您将看到 **演示** 环境，您可以使用它来探索使用虚构数据的应用。 您可以根据您的行业更改示例数据。 选择标题中的 **设置** 图标，然后选择 **演示设置**。 此外，您还可以更改视觉主题。 

您[切换到在注册过程中创建的环境](#change-between-environments)来使用您自己的数据。

## <a name="create-a-new-production-or-sandbox-environment"></a>创建新的生产或沙盒环境

在您的环境中，选择标题中的 **设置** 图标，然后选择 **新建环境**。

请按照步骤操作，就像[创建试用环境](#create-a-trial-environment)一样。 选择 **高级设置** 时将出现一个在您自己的 Azure Data Lake 中存储数据的额外选项。 提供您的帐户名称和帐户密钥以建立与您的 Azure Data Lake 的连接。 默认情况下，数据存储在 Customer Insights 托管的数据湖中。

> [!IMPORTANT]
> 将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输到适合该 Azure 存储帐户的地理位置并存储在其中，此位置可能与 Dynamics 365 Customer Insights 中存储数据的位置不同。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>浏览主页

您可以在以下 URL 上[访问您的 Customer Insights 环境](https://home.ci.ai.dynamics.com/)：[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/)。
**主页** 页面显示您的客户群以及用于跟踪业务状况的关键指标的概览。

> [!div class="mx-imgBorder"] 
> ![主页中的见解](media/home-page-insights.png "主页中的见解")

在 **最近客户细分** 下，您将看到基于您定义的人口统计、行为或事务属性的客户组。 [创建段](segments.md)可帮助您更好地确定业务活动的目标。

**最近度量** 显示带有[度量](measures.md)的磁贴。 度量是您定义的关键绩效指标 (KPI)。 例如，每个客户的平均客户流失可能性或平均在线支出。

**最近扩充** 部分列出最近完成的扩充运行的结果。 扩充添加有关客户群的信息。 例如，通过了解与其有相关性的兴趣和品牌。 在完成[映射](map-entities.md)、[匹配](match-entities.md)和[合并](merge-entities.md)阶段之后，可以使用[扩充](enrichment-microsoft-graph.md)功能解锁此信息。

## <a name="change-between-environments"></a>在环境之间切换

一旦设置并配置了[数据源](data-sources.md)，您就需要从演示环境切换到实时环境。 利用生产环境，您可以处理自己的客户数据。 选择页面右上角中的 **环境** 控件以更改环境。

> [!div class="mx-imgBorder"] 
> ![切换环境](media/home-page-environment-switcher.png "切换环境")

管理员可以创建和管理[多个环境](manage-environments.md)。 例如，如果您的组织在国际范围内运营，并且您需要以不同的方式隔离数据和见解，则维护多个环境可能会很有用。

## <a name="next-step"></a>下一步

若要在主页上查看您自己的见解，您首先需要[添加数据源](data-sources.md)并[统一](data-unification.md)数据以构建客户配置文件。
