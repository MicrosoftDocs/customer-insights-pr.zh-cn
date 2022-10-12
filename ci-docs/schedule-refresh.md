---
title: 计划系统刷新
description: 计划应刷新系统的时间
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610317"
---
# <a name="schedule-system-refresh"></a>计划系统刷新

计划所有[引入数据源](data-sources.md)的自动刷新。 自动刷新可帮助确保您的数据源中的更新反映在您的统一客户配置文件中。

> [!NOTE]
> 您管理的 Power Query 数据源会按其自己的计划刷新。 要计划刷新这些 Power Query 数据源，请从 **数据源** 页面配置该特定数据源的刷新设置。 将时间安排与上游数据刷新计划保持一致，以不会一次刷新所有数据。
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform 数据流刷新设置。":::

## <a name="set-system-refresh-schedule"></a>设置系统刷新计划

1. 转到 **管理员** > **系统**，然后选择 **日程安排** 选项卡。

   :::image type="content" source="media/schedule_refresh.png" alt-text="系统页的计划刷新选项卡。":::

1. 计划的刷新的默认状态为 **已关闭**。 若要启用计划的刷新，请将屏幕顶部的开关切换为 **开**。

1. 在 **每周**（默认值）和 **每日** 刷新之间选择。 如果要计划每周刷新，请选择一个或多个要运行刷新的日期。

1. 设置 **时区**，然后使用 **时间** 下拉列表来设置刷新时间。 如果要将多次刷新安排在一天内，请选择 **添加其他时间**。 您最多可以添加四个刷新。

1. 选择 **保存** 以应用您所做的更改。

[!INCLUDE [footer-include](includes/footer-banner.md)]
