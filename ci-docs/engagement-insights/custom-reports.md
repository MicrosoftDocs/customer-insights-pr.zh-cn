---
title: 关于自定义报表
description: 了解如何创建自定义报表。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232137"
---
# <a name="create-and-edit-custom-reports"></a>创建和编辑自定义报表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

除了现成 (OOB) 报表之外，您还可以生成带有图表和表格可视化效果的自定义报表，以帮助您了解用户行为。 本文介绍如何使用表格和图表可视化效果来创建包含所需数据的报表。 有关 OOB 报表的信息，请参阅[查看报表](view-reports.md)。

## <a name="create-a-custom-report"></a>创建自定义报表

1. 转到 **分析** > **自定义** 以访问自定义报表列表。

1. 选择 **新建报表** 以开始创建自定义报表。

   :::image type="content" source="media/new-custom-report.png" alt-text="新建自定义报表。":::

1. 确定您要生成的报表的类型：

    - 在命令栏中选择 **添加可视化项** 以创建默认表格可视化项。
    - 或者，从 **报表编辑器** 窗格中选择列、条形、线条、面积、饼图、甜甜圈或表格可视化效果。

1. 在 **可视化效果编辑器** 窗格的 **数据** 部分，从 **指标** 下拉列表中选择一个可用选项（例如，页面浏览量）。 您还可以添加要显示在可视化效果中的 **维度**（例如，国家/地区）。 有关详细信息，请参阅[查看和创建指标](metrics.md)和[查看和创建维度](dimensions.md)。

   :::image type="content" source="media/page-views.png" alt-text="为您的报表选择指标。":::

1. 选择 **可视化效果编辑器** 窗格的 **设计** 部分可以添加 **标题文本** 和打开或关闭 **标题**。  您还可以通过选择另一个图表来更改可视化效果类型，如 **饼图**。

1. 要更改可视化效果的大小和位置：
   - 选择可视化项，然后拖动其中一个角或边框以调整其大小。
   - 选择可视化项，将其移动到新位置。 您也可以使用箭头键更改位置。
1. 要添加其他可视化效果，请在命令栏中选择 **添加视觉对象**。
1. 为报表添加所需的可视化效果后，在命令栏中选择 **保存**。

1. 提供自定义报表的名称，选择 **保存** 以创建它。
 
## <a name="filter-a-custom-report"></a>筛选自定义报表

您可以在自定义报表中选择期限或日期范围来关注某个值或时间段。

要选择期限，在报表视图的右上角，从报表的下拉列表中选择一个值。 您还可以选择 *固定日期范围*。

:::image type="content" source="media/filter-time-date-range.png" alt-text="按时间或日期范围筛选。":::

对于大多数报表，选择 **+ 添加条件** 可以选择维度或客户细分来筛选报表。 有关详细信息，请参阅[查看和创建客户细分](segments.md)。

## <a name="edit-a-custom-report"></a>编辑自定义报表

1. 转到 **分析** > **自定义** 以访问自定义报表列表。

1. 在自定义报表列表中，选择 **更多 [...]** 

1. 选择 **编辑名称** 可以更改报表的名称。

1. 选择报表名称并使用 **+ 添加视觉对象** 和 **编辑** 选项可以添加、删除、重新定位可视化项或调整可视化项的大小。

1. 要更改可视化效果的属性，选择该视觉对象，选择 **...**，然后选择 **编辑视觉对象**。

   :::image type="content" source="media/edit-visual-control.png" alt-text="编辑自定义报表的图表属性。":::

1. 编辑报表后，选择 **保存** 以应用您所做的更改。 

## <a name="delete-a-custom-report"></a>删除自定义报表

1. 转到 **分析** > **自定义** 以访问自定义报表列表。

1. 在自定义报表列表中，选择 **...**

1. 选择 **删除** 以删除报表。

1. 确认删除以永久删除该报表。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
