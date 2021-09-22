---
title: 使用“未知到已知”识别先前经过身份验证的访问者的 Web 事件
description: 利用“未知到已知”功能，您可以将网站上的事件与之前进行了身份验证的访问者相关联。
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036772"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>识别先前经过身份验证的访问者的 Web 事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

利用参与见解功能中 **未知到已知** 功能，能够将网站上的事件与以前进行过身份验证的访问者相关联。 如果禁用了该功能，则以前访问期间进行了身份验证然后离开的访问者回来时如果未再次进行身份验证，则不会被识别。 

例如，某人上周访问了一个网站，在该网站上登录了他们的用户帐户，并浏览了产品目录。 此人在接下来的一周返回去浏览更多产品，无需登录其帐户。 使用 **未知到已知** 功能的站点负责人会知道同一个人已经返回以及他们在站点上做了什么。 这样，可以更精确地报告和分析网站活动。

## <a name="enable-unknown-to-known"></a>启用“未知到已知”

您必须是[工作区管理员](user-roles.md)才能启用此功能。 

1. 在参与见解中，转到 **管理员** > **工作区**。 
2. 选择 **设置** 选项卡。
3. 在 **未知到已知** 部分，将切换开关设置为 **已启用**。

![启用“未知到已知”](media/U2Ktoggle.png "启用“未知到已知”")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>将 JavaScript 代码添加到站点的跟踪片段

网站可以使用 [参与见解 Web SDK](advanced-SDK-implementation.md) 通过以下 JavaScript 示例捕获 **用户 authId**。 为了使 **未知到已知** 功能起作用，您需要在 JavaScript 片段中捕获 authId *并* 启用 userMapping:True，如以下示例中所示。

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
