---
title: 将代码添加到您的网站
description: 如何添加代码片段以捕获网站上的 Dynamics 365 Customer Insights 事件。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230999"
---
# <a name="install-the-web-sdk-on-a-website"></a>在网站上安装 Web SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

本文说明了管理员如何在网站上安装 Web 软件开发工具包 (SDK)。 检测网站后，您将立即开始在您的工作区中看到事件。 有关详细信息，请参阅[管理工作区和环境](manage-environments-workspaces.md)。 若要捕获移动应用中的事件，请参阅[开发人员资源概述](developer-resources.md)。


### <a name="prerequisites"></a>先决条件

* 您必须具有工作区管理员权限才能存储数据。
* 您的网站或项目必须在线托管才能发送活动数据。 服务器将不会接受从本地文件发送的数据。


## <a name="add-web-sdk-to-your-website"></a>将 Web SDK 添加到您的网站

转到 **管理员** > **工作区**，然后选择 **安装指南**。 可通过两个选项安装 Web SDK。 第一个是使用下载链接，第二个是安装节点包管理器 (NPM) 包。

### <a name="option-1-using-the-download-link"></a>选项 1：使用下载链接

1. 选择 **复制代码** 以复制代码片段。 默认情况下，您的工作区的引入密钥会嵌入到代码片段中。
  :::image type="content" source="media/copy-code.png" alt-text="代码片段页面的屏幕截图。":::

1. 将复制的代码添加到您的网站、 <head> 标记附近、其他任何脚本或 CSS 标记之前。
1. 发布更新的网站，然后等待几分钟以捕获传入的 Web 流量。
1. 要查看数据，请从导航窗格中的工作区切换器中选择您的工作区。 然后选择 **发现** 部分中的一个报表。

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>选项 2：使用 NPM 程序包（推荐用于基于 JavaScript 的 Web 应用）

1. 转到我们的 [NPM 网页](https://www.npmjs.com/package/engagementinsights-web)，按照说明安装和设置 Web SDK NPM 程序包。
1. 发布更新的网站，然后等待几分钟以捕获传入的 Web 流量。
1. 要查看数据，请从导航窗格中的工作区切换器中选择您的工作区。 然后选择 **发现** 部分中的一个报表。

## <a name="configuration-options"></a>配置选项

您可以在代码片段中更改以下配置选项：

- **ingestionKey**：用于将事件发送到您的工作区的引入密钥。 您可以更改引入密钥以将事件发送到其他工作区。 每个工作区的引入密钥都是唯一的。
- **autoCapture**：指定是否捕获页面浏览量以及网站交互。 它具有两个选项：
    - **浏览量**：设置为 *true* 可捕获页面浏览量。 页面浏览被捕获为 *浏览*[事件](glossary.md#event)，这是一种[基本事件](glossary.md#base-event)。
    - **单击**：设置为 *true* 可捕获网站上的访问者交互。 交互被捕获为 *操作*[事件](glossary.md#event)，这是一种[基本事件](glossary.md#base-event)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
