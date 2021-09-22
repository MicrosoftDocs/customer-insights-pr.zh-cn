---
title: 将代码添加到您的网站
description: 如何添加代码片段以捕获网站上的事件。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035083"
---
# <a name="install-the-code-snippet-on-a-website"></a>在网站上安装代码片段

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

本文说明了管理员如何在网站上安装代码片段。 将脚本添加到网站后不久，您将开始在工作区中看到事件。 有关详细信息，请参阅[管理工作区和环境](manage-environments-workspaces.md)。 若要捕获移动应用中的事件，请参阅[开发人员资源概述](developer-resources.md)。


### <a name="prerequisites"></a>先决条件

* 您必须具有工作区管理员权限才能存储数据。
* 您的网站或项目必须在线托管才能发送活动数据。 服务器将不会接受从本地文件发送的数据。


## <a name="add-code-to-your-website"></a>将代码添加到您的网站
1.  转到 **管理员** > **工作区**，然后选择 **安装指南**。
1. 选择 **复制代码** 以复制代码片段。 默认情况下，您的工作区的引入密钥会嵌入到代码片段中。
:::image type="content" source="media/copy-code.png" alt-text="代码片段页面的屏幕截图。":::
3. 将复制的代码片段添加到您网站中 <head> 标记附近、其他任何脚本或 CSS 标记之前。
4.  发布更新的网站，然后等待几分钟以捕获传入的 Web 流量。
5.  要查看数据，请从导航窗格中的工作区切换器中选择您的工作区。 然后选择 **发现** 部分中的一个报表。

## <a name="configuration-options"></a>配置选项

您可以在代码片段中更改以下配置选项：

- **ingestionKey**：用于将事件发送到您的工作区的引入密钥。 您可以更改引入密钥以将事件发送到其他工作区。 每个工作区的引入密钥都是唯一的。 
- **autoCapture**：指定是否捕获页面浏览量以及网站交互。 它具有两个选项：
    - **浏览量**：设置为 *true* 可捕获页面浏览量。 页面浏览被捕获为 *浏览*[事件](glossary.md#event)，这是一种[基本事件](glossary.md#base-event)。
    - **单击**：设置为 *true* 可捕获网站上的访问者交互。 交互被捕获为 *操作*[事件](glossary.md#event)，这是一种[基本事件](glossary.md#base-event)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
