---
title: 管理 Cookie 和用户同意以存储用户数据
description: 了解如何使用 Cookie 和用户同意来识别网站访问者。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036727"
---
# <a name="manage-cookies-and-user-consent"></a>管理 Cookie 和用户同意

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights 参与见解功能使用 Cookie 和本地存储 (`localStorage`) 来识别网站访问者。

Cookie 是小文件，用于存储有关用户与网站的交互的少量信息。 它们存储在 Web 浏览器中。 当用户访问用户存储 Cookie 所针对的网站时，浏览器会向服务器发送该信息，这会返回用户所特有的信息。 这是一种技术，例如，即使用户离开网站，在线购物车也可以将选定的商品保留在其中。

## <a name="user-consent"></a>用户同意

[一般数据保护条例 (GDPR)](/dynamics365/get-started/gdpr/) 是欧盟 (EU) 的一项法规，规定组织应如何处理其用户的隐私和安全性。 Cookie 通常存储或收集 GDPR 涵盖的“个人数据”，例如在线标识符。 如果您的企业雇用欧盟数据使用者并且/或者向其进行出售，则 GDPR 会影响您。 [详细了解 Microsoft 如何帮助您遵守 GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs)。

若要允许参与见解 SDK 存储 Cookie 或其他敏感信息，您必须指定您的用户是否已同意。 这发生在 SDK 初始化过程中。

如果您指示未获得用户同意，SDK 将不会存储任何数据，并且将不会发送可用于跟踪用户行为的事件。 以前存储的所有数据将从浏览器中删除。

如果未指定用户同意值，SDK 将假定用户已同意。 这意味着，如果您（作为我们的客户）未在 SDK 中指定用户同意值，则会收集数据。 但是，如果您指定用户同意值必须为“true”，则如果用户拒绝或未能提供明确同意，则不会收集数据。

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>参与见解功能中的访问者数据存储

### <a name="cookies"></a>曲奇饼

- _msei
    - 存储匿名用户 ID。 此 Cookie 在客户域中设置，在 365 天后过期。

### <a name="local-storage"></a>本地存储

参与见解功能还利用本地存储 (`localStorage`) 来跟踪非敏感数据。 此数据完全存储在浏览器本身中，不会向服务器发送任何流量。

- *EISession.Id* 
    - 存储有关持续用户会话的信息，例如会话 ID、会话启动时间以及会话到期时间。
- *EISession.Previous*
    - 在当前会话中存储以前访问的页面的 URL。
    
本地存储中的密钥不会自动过期。 SDK 将在下一个会话中重置它们。

## <a name="deleting-cookies"></a>删除 Cookie

您的客户可以通过浏览器的设置随时手动删除 Cookie 和本地存储密钥。


[!INCLUDE[footer-include](../includes/footer-banner.md)]