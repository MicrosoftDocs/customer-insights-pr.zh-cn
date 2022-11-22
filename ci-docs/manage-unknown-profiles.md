---
title: 使用 Customer Insights 管理未知资料
description: 使用在 Dynamics 365 Customer Insights 中创建和管理的未知客户资料。
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776810"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>使用 Customer Insights 管理未知资料

Internet 用户往往是身份不明的用户或匿名的在线用户。 即使是最忠实的客户，如果他们没有通过不同的设备登录过，也可能会显示“未知”。 对于很多品牌，尽管客户对个性化的期望越来越高，但已知或经过身份验证的用户依然是少数派。 考虑到第三方 Cookie 的未来，基于第一方数据管理用户偏好对于实现个性化体验至关重要。

难忘的个性化取决于您对客户的了解程度，Customer Insights 可以通过跟踪所有客户帮助您做到这一点。  您不必限制或停止使用在客户旅程开始时收集的数据。 Customer Insights 允许您使用自己的数据为未知用户创建客户资料。 然后，尽管缺少联系信息，您仍可以使用该资料进一步采取行动。 将来自 Web、移动或 CRM 系统等来源的第一方数据导入 Customer Insights，以不断扩充客户资料。 当您统一更多交互时，[将 *未知* 客户转变为 *已知* 客户](unknown-to-known.md)。

## <a name="sample-scenario"></a>示例场景

假设用户使用他们的移动设备浏览您的电子商务网站。 网站向访问者分配“mobile_guest123”作为唯一标识符，您开始根据他们的在线活动收集行为活动。 例如，他们访问了哪些页面，他们在这些页面上花费了多少时间，或者他们点击了哪些链接。 您不知道他们的姓名或电子邮件地址，但这些数据可以帮助为品牌提供有关此用户的有意义的见解。 然后，您可以在用户下次访问网站时让这些见解发挥作用。 在 Customer Insights 中查询“mobile_guest123”来检索用户的客户细分列表，如“自然流量”、“移动预订客户”、“高价值客户”等，或检索资料来创建个性化的 Web 体验。 您也可以将数据导出到任何激活系统来执行相同操作。

## <a name="prerequisites"></a>先决条件

- 将第一方数据引入 Customer Insights
- 每个实体具有设置为主键的唯一 ID
- 每个具有用于个性化的主键的实体将进行统一处理
- 您网站的内容管理系统可以使用 API（用于基于与 Customer Insights 直接通信的 Web 个性化）

下表显示了如何捕获高价值 Web 事件的简化示例。

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|产品视图|
|2|09-18-2022 10:05:00|abc123|CookieID1|产品视图|
|3|09-18-2022 10:10:00|abc123|CookieID1|添加到购物车|
|4|09-21-2022 09:05:00|abc123|CookieID1|产品视图|

## <a name="data-ingestion"></a>数据引入

有关数据引入的可用选项的详细信息，请参阅[数据源概述](data-sources.md)。

## <a name="data-unification"></a>数据统一

有关统一客户配置文件的详细信息，请参阅[数据统一概述](data-unification.md)。

## <a name="get-insights"></a>获取见解

[扩充](enrichment-hub.md)您的数据，构建[度量](measures.md)，并创建[客户细分](segments.md)来进一步激活。

例如，您可以创建浏览相同产品页面但从未完成结帐的未知用户客户细分。

## <a name="activation"></a>激活

随着您在 Customer Insights 中的数据和您的见解准备就绪，您可以使用 Customer Insights 进行个性化：

1. 使用 [OData API](apis.md) 检索客户细分成员身份或客户资料。更多示例请参阅 [Customer Insights API 的 OData 查询示例](odata-examples.md)。

1. 将数据[导出](export-destinations.md)到激活系统。

示例：未知用户多次访问网站并访问各个皮鞋款式的产品页面。 借助 Customer Insights 中提供的数据，您可以将未知用户包括在对皮鞋感兴趣的客户细分中。 然后使用此客户细分告知您的网站为返回的访问者建立个性化体验。 在下次访问时，网站会识别出这些未知用户，为他们提供 10% 折扣的皮鞋优惠券。

[!INCLUDE [footer-include](includes/footer-banner.md)]
