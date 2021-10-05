---
title: 运行 iOS SDK 示例
description: 用于了解 iOS SDK 的示例项目
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036817"
---
# <a name="run-the-ios-sdk-sample"></a>运行 iOS SDK 示例

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

此示例 iOS 项目可帮助您了解 SDK 在应用中的工作方式。 您不必编写代码。 只需添加引入密钥，即可立即在您的工作区中查看事件。

## <a name="prerequisites"></a>先决条件

- [Xcode 版本 9+](https://developer.apple.com/xcode/downloads/)
- [引入密钥](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>下载 iOS SDK 示例

1. [下载参与见解 iOS SDK 示例](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip)。
1. 对压缩文件 `ei-ios-sample.zip` 进行解压缩。
1. 在 Xcode 中打开示例应用项目。
1. 在 `EIConfig.plist` 文件中，在 **管理** > **工作区** > **安装指南** 下将字段 `ingestionKey` 中的字符串 `“YOUR-INGESTION-KEY”` 替换为参与见解中的工作区引入密钥。
1. 选择 **运行** 以开始示例项目。
1. 在您的工作区中查看事件。

[!INCLUDE[footer-include](../includes/footer-banner.md)]