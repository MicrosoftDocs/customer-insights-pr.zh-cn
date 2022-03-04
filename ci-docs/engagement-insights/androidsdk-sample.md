---
title: Android SDK 示例
description: 用于了解 Android SDK 的示例项目
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229907"
---
# <a name="run-the-android-sdk-sample"></a>运行 Android SDK 示例

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

此示例 Android 项目可帮助您了解 SDK 在应用中的工作方式。 您不必编写代码。 只需添加引入密钥，即可立即在您的工作区中查看事件。

## <a name="prerequisites"></a>先决条件

- [Android Studio](https://developer.android.com/studio)
- [引入密钥](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>下载 Android SDK 示例

1. [下载参与见解 Android SDK 示例](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip)。
1. 对压缩文件 `ei-android-sample.zip` 进行解压缩。
1. 在 Android Studio 中打开解压缩的文件夹。
1. 在 `AndroidManifest.xml` 文件中，在 **管理** > **工作区** > **安装指南** 下将字符串 `"Your-Ingestion-Key"` 替换为参与见解中的工作区引入密钥。 

   > [!NOTE]
   > 无需替换 `${applicationId}` 部分。 它将自动填充。

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. 选择 **运行** 以开始示例项目。
1. 在您的工作区中查看事件。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
