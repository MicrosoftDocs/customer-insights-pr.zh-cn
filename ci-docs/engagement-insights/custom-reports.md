---
title: 关于自定义报表
description: 了解如何创建自定义报表。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2540221710786dc1c84b231fbb23b9749b601cc6a2aeb78614e16002302a80a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036952"
---
# <a name="create-and-edit-custom-reports"></a>创建和编辑自定义报表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

除了现成的报表外，您还可以使用图表和表格可视化效果来构建自定义报表，以帮助您了解用户行为。 本文介绍如何使用表格和图表可视化效果来创建包含所需数据的报表。 

## <a name="create-a-custom-report"></a>创建自定义报表

1. 转到 **分析** > **自定义** 以访问自定义报表列表。

1. 选择 **新建报表** 以开始创建自定义报表。

   :::image type="content" source="media/new-custom-report.png" alt-text="新建自定义报表。":::

1. 确定您要生成的报表的类型：

    - 在命令栏中选择 **添加可视化项** 以创建默认表格可视化项。
    - 或者，从 **报表编辑器** 窗格中选择列、条形、线条、面积、饼图、甜甜圈或表格可视化效果。

1. 在 **数据** 窗格中，选择要显示的可用 **指标** 之一（例如页面视图）。 然后，添加要在可视化项上显示的 **维度**（例如，国家/地区）。 有关添加其他选项以从中进行选择的详细信息，请参阅[查看和创建指标](metrics.md)以及[查看和创建维度](dimensions.md)。

1. 在 **可视化编辑器** 窗格中选择 **设计** 以添加 **标题文本**，并设置 **位置**、**数据标签** 和 **轴**。  您也可以通过选择其他图表类型来更改可视化项。

1. 可以更改可视化项的大小和位置：
   - 选择可视化项，然后拖动其中一个角或边框以调整其大小。
   - 选择可视化项，将其移动到新位置。 您也可以使用箭头键更改位置。
1. 要添加其他可视化效果，请在命令栏中选择 **添加视觉对象**。
1. 为报表添加所需的可视化效果后，在命令栏中选择 **保存**。

1. 提供自定义报表的名称，选择 **保存** 以创建它。
 
## <a name="edit-a-custom-report"></a>编辑自定义报表

1. 转到 **分析** > **自定义** 以访问自定义报表列表。

1. 在自定义报表列表中，选择 **更多 [...]** 

1. 选择 **编辑详细信息** 以更改报表的名称。

1. 选择报表名称并使用 **添加视觉对象** 和 **编辑** 选项来添加、删除、重新定位可视化项或调整可视化项的大小。

1. 若要更改可视化项的属性，请选择 **...**，然后选择 **编辑视觉对象**。

   :::image type="content" source="media/edit-visual-control.png" alt-text="编辑自定义报表的图表属性。":::

1. 编辑报表后，选择 **保存** 以应用您所做的更改。 

## <a name="delete-a-custom-report"></a>删除自定义报表

1. 转到 **分析** > **自定义** 以访问自定义报表列表。

1. 在自定义报表列表中，选择 **...**

1. 选择 **删除** 以删除报表。

1. 确认删除以永久删除该报表。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
