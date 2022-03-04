---
title: 高级 Web SDK 方案
description: 使用 SDK 对网站进行检测时要考虑的高级方案。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227187"
---
# <a name="advanced-web-sdk-instrumentation"></a>高级 Web SDK 检测

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

本文指导您完成使用 Dynamics 365 Customer Insights 参与见解功能 SDK [检测网站](instrument-website.md)时要考虑的高级方案。

## <a name="setting-user-details-for-your-event"></a>为事件设置用户详细信息

SDK 允许您定义可随每个事件一起发送的用户信息。 您可以在名为 `user` 的属性中指定用户详细信息（此属性的预期数据为 `IUser` 对象），这类似于代码片段配置中的 `src`、`name` 和 `cfg`。

该 `IUser` 对象包含以下字符串属性：

- **localId**：用户的本地 ID。
- **authId**：经过身份验证的用户 ID。
- **authType**：用于获取经过身份验证的用户 ID 的身份验证类型。
- **name**：用户的姓名。
- **email**：用户的电子邮件地址。

以下示例显示了用于发送用户信息的代码片段。 如果看到前面有星号 * 符号的函数，请将函数替换为您的自定义实现：

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

您还可以通过调用 `setUser(user: IUser)` API 来指定用户信息。 调用 `setUser` API 后发送的遥测信息将包含用户信息。

## <a name="adding-custom-properties-for-each-event"></a>添加每个事件的自定义属性

SDK 允许您定义可随每个事件一起发送的自定义属性。 可以将自定义属性指定为包含键值对的对象（该值可以是 `string | number | boolean` 类型）。 您可以在名为 `props` 的属性（类似于代码片段配置中的 `src`、`name` 和 `cfg`）中添加对象。

以下示例显示了用于发送自定义属性的代码片段：

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

您还可以通过调用 `setProperty(name: string, value: string | number | boolean)` API 来单独指定自定义属性。

## <a name="sending-custom-events"></a>发送自定义事件

可以使用 SDK 发送自定义事件。 您必须为事件指定名称以及随事件一起发送的属性。

以下示例显示了用于跟踪自定义事件的代码片段。 "NAME" 是片段配置内 `name` 键中的值。 它也是加载 SDK 所在的窗口对象中的变量名称。

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
