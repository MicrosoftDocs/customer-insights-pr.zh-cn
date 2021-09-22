---
title: 运行 Web SDK 示例
description: 了解如何个性化和运行 Web SDK 示例。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036592"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>针对 Dynamics 365 Customer Insights 参与见解功能运行 Web SDK 示例

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解功能 Web SDK 库是一个 JavaScript 库，其中包含可在网站上使用的示例代码。

## <a name="prerequisites"></a>先决条件

- 安装 [Visual Studio 代码](https://code.visualstudio.com/)。
- 在 Visual Studio 代码中[安装 Live Server 扩展](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)，并熟悉如何运行 Live Server。
- 您必须拥有[引入密钥](instrument-website.md)。

## <a name="run-sample"></a>运行示例

1. [下载 Web SDK 示例](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)。

1. 对压缩文件 `ei_websdk_sample.zip` 进行解压缩。

1. 在 Visual Studio 代码中打开解压缩的文件夹。

1. 在 `ei_websdk_sample.html` 文件中，将字符串“INGESTION_KEY”替换为来自参与见解功能门户的引入密钥，将字符串“NAME”替换为您希望 SDK 实例化所使用的全局名称。 确保替换所有出现的实例。

1. 通过从状态栏中选择 **发布**，在 Visual Studio 代码中使用 Live Server 打开 `ei_websdk_sample.html` 文件。

1. 打开页面时，应自动发送视图事件。 单击页面上的任一按钮将会发送操作事件。 **跟踪事件** 按钮还将发送自定义事件。 选择 **转到必应** 按钮将在导航到必应网站之前发送操作事件。

1. 在导航到您的工作区时，查看事件流。 此工作区与在步骤 4 中输入的引入密钥相关联。


[!INCLUDE[footer-include](../includes/footer-banner.md)]