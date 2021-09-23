---
title: 开始使用 Android SDK
description: 了解如何个性化和运行 Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494264"
---
# <a name="get-started-with-the-android-sdk"></a>开始使用 Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

此教程将指导您完成使用 Dynamics 365 Customer Insights 参与见解 SDK 检测 Android 应用程序的流程。 您将在五分钟或更短时间内在门户中开始查看事件。

## <a name="configuration-options"></a>配置选项
可以将以下配置选项传递给 SDK：

- **ingestionKey**：引入密钥用于将事件发送到您的工作区。

## <a name="prerequisites"></a>先决条件

- Android Studio

- 最低 Android API 级别：16 (Jelly Bean)

- 引入密钥（有关如何获取的说明，请参阅下方）

## <a name="integrate-the-sdk-into-your-application"></a>将 SDK 集成到应用程序中
通过选择工作区，选择 Android 移动平台并下载 Android SDK 来开始流程。

- 使用左侧导航窗格中的工作区切换器来选择您的工作区。

- 如果您没有现有工作区，请选择 **新建工作区**，然后按照步骤创建[新工作区](create-workspace.md)。

- 创建工作区后，请转到 **管理** > **工作区**，然后选择 **安装指南**。 

## <a name="configure-the-sdk"></a>配置 SDK

下载 SDK 后，可以在 Android Studio 中使用它以启用和定义事件。 方法有两种。
### <a name="option-1-using-jitpack-recommended"></a>选项 1：使用 JitPack（推荐）
1. 将 JitPack 存储库添加到根 `build.gradle`：
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. 添加依赖项：
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>选项 2：使用下载链接
1. 下载[参与见解 Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip)，然后将 `eiandroidsdk-debug.aar` 文件放入 `libs` 文件夹中。

1. 打开项目级别 `build.gradle` 文件并添加以下片段：
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. 在 `manifests` 文件夹中 `AndroidManifest.xml` 文件内添加网络和 Internet 的权限。 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. 通过  `AndroidManifest.xml`文件设置参与见解 SDK 配置。 

## <a name="enable-auto-instrumentation"></a>启用自动检测
1. 从 **安装指南** 中复制 XML 片段。 `Your-Ingestion-Key` 应自动填充。

   > [!NOTE]
   > 无需替换 `${applicationId}` 部分。 它将自动填充。
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. 通过将上面的 `autoCapture` 字段设置为 `true` 或 `false`，启用或禁用 `View` 事件的自动捕获。 现在需要手动添加 `Action` 事件。

1. （可选）其他配置包括设置终结点收集器 URL。 可以在 `AndroidManifest.xml` 中的引入密钥元数据下添加它们：
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>实现自定义事件

初始化 SDK 后，您可以在 `MainActivity` 环境中处理事件及其属性。

    
Java：
```java
Analytics analytics = new Analytics();
```

Kotlin：
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>设置所有事件的属性（可选）
    
Java：
```java
analytics.setProperty("year", 2021);
```

Kotlin：
```kotlin
analytics.setProperty("year", 2021)
```

上下文事件属性支持以下类型：
- String
- 日期
- 双精度
- Long
- 布尔型
- UUID

### <a name="track-an-event"></a>跟踪事件

Java：
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin：
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>设置事件的用户详细信息（可选）

SDK 允许您定义可随每个事件一起发送的用户信息。 您可以通过在 `Analytics` 级别上调用 `setUser(user: User)` API 来指定用户信息。

Java：
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin：
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` 数据类包含以下字符串属性：

- **localId**：用户的本地 ID。
- **authId**：经过身份验证的用户 ID。
- **authType**：用于获取经过身份验证的用户 ID 的身份验证类型。
- **name**：用户的姓名。
- **email**：用户的电子邮件地址。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
