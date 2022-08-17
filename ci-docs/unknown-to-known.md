---
title: 使用有关已知和未知用户的数据个性化您的体验
description: 当您知道他们的身份时，合并有关以前未知用户的信息。
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224284"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>使用有关已知和未知用户的数据个性化您的体验

管理客户数据并不是一个新的挑战，但随着用户浏览品牌提供的各种数字渠道，它变得越来越困难。 如果未登录，在一个渠道中已知（经过身份验证）的用户在另一个渠道中将变为未知（未经过身份验证）。 问题通常是未经过身份验证（未知）的用户没有公用 ID。 它可用于关联有意义的配置文件属性并生成统一的客户配置文件。 Customer Insights 通过从源系统上的跟踪方法引入数据来帮助解决此问题。 合并未知和已知配置文件可为组织提供最新配置文件及其历史交易、行为和人口统计数据的完整视图。 它甚至更进了一步，提供身份解析，允许您跨多个渠道统一客户活动，包括您的网站、店内购买、会员计划等。

## <a name="sample-scenario"></a>示例方案

我们考虑一个咖啡连锁店，它拥有广泛的客户群，他们在商店购买咖啡和食品并在线订购产品。 通常，在线访问者在浏览产品时没有经过身份验证，使他们成为“未知用户”。 如果用户未知，咖啡连锁店很难提供个性化的优惠和体验。 另一方面，客户可以通过加入会员系统登录他们的帐户，成为公司的“已知用户”，从而提供更个性化的体验。 Customer Insights 可以帮助咖啡连锁店了解已知和以前未知的用户。

使用 Customer Insights，公司可以在用户登录、成为已知用户后，将客户配置文件与来自未经过身份验证（未知）会话的活动数据合并。 咖啡连锁店可以使用内置连接器将来自其他数据源的数据引入 Customer Insights，以合并来自各种渠道的客户的身份。

## <a name="prerequisites"></a>先决条件

- 已收集 Web 数据，其中包含所有访问者的“访问者 ID”。
- Web 数据包含已登录访问者的“经过身份验证的用户 ID”。 这些 ID 已与会员系统链接。
- 诸如“产品视图”和“结帐”之类的高价值事件数据已定义并包含在源数据中，带有事件的时间戳和事件 ID。

下表显示了如何捕获高价值 Web 事件的简化示例。

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|产品视图|
|2|07-23-2022 10:05:00|abc123|707|会员登录|
|3|07-23-2022 10:10:00|abc123|707|签出|
|4|07-23-2022 10:20:00|xyz789|--|产品视图|

## <a name="data-ingestion"></a>数据引入

有关客户的数据可以来自您的网站，作为事件数据，这些数据可以存储在您自己的内部或第三方数据分析服务中。 如果网站具有与身份验证服务集成的身份验证流程，Web 数据将包含已知和未知用户。 例如，要求用户提供完整详细信息以完成购买交易的电子商务系统。 或需要身份验证来确认奖励折扣的有效接收者的会员系统。

上面示例中的事件数据包含已知和未知用户的不同配置文件 ID。 在事件 1 和 4 中，用户未知，而在事件 2 和 3 中，ID 为 abc123 的用户注册了会员计划。

:::image type="content" source="media/website-data-source.png" alt-text="包括 Contoso 网站的数据源。":::

有关数据引入的可用选项的详细信息，请参阅[数据源概述](data-sources.md)。

## <a name="data-unification"></a>数据统一

将未知身份与已知身份融合有助于实现基于用户行为的个性化，而不管其配置文件状态（已知或未知）如何。 所有用户的个性化内容可帮助客户快速获知他们当时感兴趣的最相关的产品或服务。

由于我们数据中的一些用户是已知的，我们可以使用 Customer Insights 将该数据与用户的配置文件合并。 有关统一客户配置文件的详细信息，请参阅[数据统一概述](data-unification.md)。

1. 从 Web 数据实体中选择源字段。 使用存储在您的 Web 数据中的配置文件数据，并选择代表具有人口统计数据的 ID 的字段。

   :::image type="content" source="media/website-source-fields.png" alt-text="Web 数据源的源字段。":::

1. 添加规则以合并重复记录。 对于 Web 数据，选择填充最全的数据。

1. 配置匹配规则和条件。 此示例中的 Web 配置文件事件数据将在 ID 上与来自其他包含客户信息的数据源的配置文件进行匹配。 将 ID 上的精确匹配规则设置为具有相应主键或 ID 匹配的每个其他配置文件实体的单独规则。 在示例中，Web 事件配置文件数据用作最后一个匹配实体，以首先合并其他配置文件数据。
   1. 不选中 **包括所有记录** 会为已知用户创建统一的配置文件，并包括他们对应的未知用户 ID。 当您有兴趣查看已知用户的过去行为活动时，这会很有帮助。
   1. 选中 **包括所有记录** 会为未知用户创建单独的配置文件记录。 未知用户将获得一个唯一的客户 ID。 将来，当已知配置文件与 Web 事件配置文件数据相关联时，也可以查看新的已知用户的旅程并将其用于基于过去未知行为数据进行个性化。

:::image type="content" source="media/website-match-rule.png" alt-text="网站数据源实体的匹配规则。":::

## <a name="get-insights"></a>获取见解

如果为未知和已知用户创建客户配置文件，高价值 Web 事件数据可用作[活动](activities.md)。 这些活动可用于创建更多见解。 例如，六个月前访问过网站的客户（当时他们还是未知用户）或没有会员 ID 的客户从未完成结帐。

:::image type="content" source="media/website-known-unknown.png" alt-text="显示已知和未知客户的客户页面的屏幕截图。":::

[扩充](enrichment-hub.md)您的数据，构建[度量](measures.md)，并创建[客户细分](segments.md)来进一步激活。

例如，您可以创建查看某些产品但从未完成结帐的已知用户客户细分。

有关详细信息，请参阅[客户细分概述](segments.md)。

## <a name="activate-insights"></a>激活见解

有多种方法可以导出数据，然后根据基本见解采取行动。

有关详细信息，请参阅[导出概述](export-destinations.md)。
