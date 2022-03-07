---
title: 运行 Web SDK 示例
description: 了解如何个性化和运行 Web SDK 示例。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606183"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>针对 Dynamics 365 Customer Insights 参与见解功能运行 Web SDK 示例

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解功能 Web SDK 库是一个 JavaScript 库，其中包含可在网站上使用的示例代码。

## <a name="prerequisites"></a>先决条件

- 安装 [Visual Studio 代码](https://code.visualstudio.com/)。
- 在 Visual Studio 代码中[安装 Live Server 扩展](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)，并熟悉如何运行 Live Server。
- 您必须有一个[参与见解工作区](create-workspace.md)。

## <a name="run-sample"></a>运行示例

1. [下载 Web SDK 示例](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)。

1. 对压缩文件 `ei_websdk_sample.zip` 进行解压缩。

1. 在 Visual Studio 代码中打开解压缩的文件夹。

1. 转到您的工作区的参与见解门户。 选择 **管理员** > **工作区**，然后选择 **安装指南**。 跟随第一个选项，选择 **复制代码** 复制 JavaScript 代码片段。

1. 在 `ei_websdk_sample.html` 文件中，将刚刚复制的代码片段粘贴到此行下方：

   - <-- 在此行下方的这个位置粘贴来自参与见解门户的 JAVASCRIPT 代码片段-->

1. 通过从状态栏中选择 **发布**，在 Visual Studio 代码中使用 Live Server 打开 `ei_websdk_sample.html` 文件。

1. 打开页面时，应自动发送视图事件。 单击页面上的任一按钮将会发送操作事件。 **跟踪事件** 按钮还将发送自定义事件。 选择 **转到必应** 按钮将在导航到必应网站之前发送操作事件。

1. 在导航到您的工作区时，查看事件流。 此工作区与在步骤 4 中输入的引入密钥相关联。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
