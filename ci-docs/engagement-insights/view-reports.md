---
title: 查看数据报表
description: 使用可用的报表查看您网站上的实时活动。
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 03b0b4bab0d5d9c2ae641c85aac8174ec1668d45
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229729"
---
# <a name="view-reports"></a>查看报表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

报表是使用通过 SDK 收集的数据的数据可视化集合，可帮助您度量和了解用户行为。 Dynamics 365 Customer Insights 参与见解包括用于 Web 和移动项目的现成 (OOB) 报表。  

## <a name="web-reports"></a>Web 报表

您可以在左侧导航窗格中的 **发现** 下访问 Web 报表。

:::image type="content" source="media/report-menu.png" alt-text="显示可用报表列表的导航。":::

### <a name="real-time-usage-report"></a>实时使用情况报表

**实时使用情况** 报表概述了您网站上每分钟都会自动刷新的当前活动。 使用实时使用情况可监视市场营销活动、新闻事件和其他情况对网站流量的影响。

### <a name="key-metrics-reports"></a>关键指标报表

- **页面视图** 列出单独页面的页面视图以及选定期限的页面视图总数。

- **访问** 显示有关访问次数和访问持续时间的信息。

- **访问者** 通知您站点的新访问者和回访的唯一访问者。

### <a name="content-reports"></a>内容报表

- **链接** 显示有关单击次数和类型的信息。

- **退出页面** 列出访问者单击以退出您的站点的链接。

### <a name="traffic-sources-reports"></a>流量源报表

- **引用者** 列出将访问者引用到您的站点的域和 URL。

- **跟踪代码** 提供有关将访问者转到您的站点的链接中的跟踪代码的详细信息。

### <a name="visitor-profiles-reports"></a>访问者配置文件报表

- **设备** 列出用于访问您的站点的物理设备。

- **操作系统和浏览器** 提供对访问站点时运行的操作系统和浏览器的见解。

- **位置** 显示有关按国家、地区和市/县列出的访问者的信息。

- **语言** 列出按访问者的首选语言显示的页面视图。

## <a name="mobile-reports"></a>移动报表

移动报表按实时使用情况、应用和用户类别分组。 您可以在左侧导航窗格中的 **发现** 下访问移动报表。   

:::image type="content" source="media/mobile-reports.png" alt-text="参与见解的用户界面，显示在图表和列表中呈现数据的实时使用情况报表。":::   

### <a name="real-time-usage"></a>实时使用情况

**实时使用情况** 概述了您的移动应用中每分钟自动刷新的当前活动。 使用实时使用情况监视当前在您的应用中处于活动状态的用户和会话数以及顶部屏幕视图。

### <a name="app-reports"></a>应用报表

- **屏幕视图** 列出应用中单独屏幕的屏幕视图以及选定期限的屏幕视图总数。 您可以按屏幕名称或屏幕标题查看屏幕视图。

- **会话** 显示有关会话数和会话持续时间的信息。

- **返回频率** 按自上次会话以来的天数对会话计数进行分组。

- **用户** 显示您的移动应用中的新用户和返回用户。

- **事件** 列出从您的应用中收集的所有事件以及每个事件的总数。

### <a name="user-reports"></a>用户报表

- **应用版本** 按用户群列出使用中的移动应用的版本。

- **设备和操作系统版本** 提供对哪些设备和操作系统正在运行您的移动应用的见解。

- **位置** 显示有关按国家、地区和市/县列出的应用用户的信息。

## <a name="filter-by-time-or-date-range"></a>按时间或日期范围筛选

您可以在 Web 或移动报表中选择期限或日期范围来关注某个值或时间段。 

- 要选择期限，在报表视图的右上角，从报表的下拉列表中选择一个值。 您还可以选择 **固定日期范围**。 

  :::image type="content" source="media/filter-by-time.png" alt-text="按时间或日期范围筛选。":::   

- 对于大多数报表，在图表或列表中选择一个值来筛选报表。

> [!NOTE]
> 对实时使用情况报表禁用了时间范围选择；实时使用情况报表的时间范围为“现在”。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
