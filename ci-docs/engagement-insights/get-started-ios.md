---
title: 开始使用 iOS SDK
description: 了解如何个性化和运行 iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 879a71175a2e7d44a54d25fd8efb9f12927cea5a
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977495"
---
# <a name="get-started-with-the-ios-sdk"></a>开始使用 iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

此教程将指导您完成使用 Dynamics 365 Customer Insights 参与见解 SDK 检测 iOS 应用程序。 您将在五分钟或更短时间内在门户中开始查看事件。

## <a name="configuration-options"></a>配置选项

以下配置选项可以通过提供的 `EIConfig.plist` 文件传递给 SDK：

- **ingestionKey**：用于将事件发送到您的项目的引入密钥。
- **autocollectAction**：用于启用或禁用操作事件的自动检测的布尔值。
- **autocollectView**：用于启用或禁用视图事件的自动检测的布尔值。
- **endpointUrl**：事件所指向的终结点 URL。

## <a name="prerequisites"></a>先决条件

- Xcode 版本 9+
- iOS 版本 8.2+
- 引入密钥（参阅下面的说明获取）

## <a name="integrate-the-sdk-into-your-application"></a>将 SDK 集成到应用程序中

通过选择要进行工作的工作区，选择 iOS 移动平台并下载 SDK 来开始流程。

- 使用左侧导航窗格中的工作区切换器来选择您的工作区。

- 如果您没有现有工作区，请选择 **新建工作区**，然后按照步骤创建[新工作区](create-workspace.md)。

- 创建工作区后，请转到 **管理** > **工作区**，然后选择 **安装指南**。

## <a name="configure-the-sdk"></a>配置 SDK

下载 SDK 后，可以在 Xcode 中使用它以启用和定义事件。 方法有两种

### <a name="option-1-using-cocoapods-recommended"></a>选项 1：使用 CocoaPods（推荐）
CocoaPods 是 Swift 和 Objective-C Cocoa 项目的依赖项管理器。 使用它可以更轻松地集成适用于 iOS 的参与见解 SDK。 CocoaPods 还可以用于升级到最新的参与见解 SDK 版本。 下面了解如何使用 CocoaPods 将参与见解 SDK 集成到 Xcode 项目中。 

1. 安装 CocoaPods。 

1. 在项目的跟目录中创建一个新文件 Podfile，然后向其添加以下子句。将 YOUR_TARGET_PROJECT_NAME 替换为您的 Xcode 项目名称。 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
上面的 pod 配置中同时包含 SDK 的调试版本和发行版本。 选择最适合您的项目的版本。

1. 执行以下命令安装 pod： `pod install --repo-update `

### <a name="option-2-using-download-link"></a>选项 2：使用下载链接

1. 下载[参与见解 iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip)，然后将 `EIObjC.xcframework` 文件放入 `Frameworks` 文件夹中。

1. 如果 `Frameworks` 文件夹不存在，在项目文件夹中创建一个。

## <a name="enable-auto-instrumentation"></a>启用自动检测
 
您可以轻松启用自动检测，而无需编码。 当项目运行时，它将使用配置的引入密钥自动跟踪 `view` 和 `action` 事件。 

1. 对于以下字段，更新提供的 `EIConfig.plist` 文件并将其包括在您的项目目录文件夹中：
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. 然后，在 Xcode 中将 `EIConfig.plist` 文件添加到您的项目。 



若要禁用自动检测，请在您的项目目录文件夹中包括的 `EIConfig.plist` 文件中更新以下字段。 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>实现自定义事件

1. 在 Xcode 中打开您的项目，然后导航到 **常规** 设置。 
1. 在“框架、库和嵌入内容”部分中将 `EIObjC.xcframework` 添加到项目。

1. 使用以下片段在 AppDelegate.m 中导入标头文件:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. 从application: didFinishLaunchingWithOptions 中初始化参与见解 SDK。
1. 从 **安装指南** 中复制 XML 片段。

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. 跟踪事件：

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>设置事件的用户详细信息

SDK 允许您定义可随每个事件一起发送的用户信息。 您可以通过在 SDK 级别上调用 `setUser:(nonnull EIUser *)user` API 来指定用户信息。

在 `Analytics` 级别上指定用户详细信息意味着所有遥测都具有此信息。 但是，如果您通过在 EIEvent 对象上调用 `setUser:(nonnull EIUser *)user` API 来指定事件级别，仅该特定事件将包含信息。

`EIUser` 数据类包含以下 NSString 属性：

- **localId**：用户的本地 ID。
- **authId**：经过身份验证的用户 ID。
- **authType**：用于获取经过身份验证的用户 ID 的身份验证类型。
- **name**：用户的姓名。
- **email**：用户的电子邮件地址。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
