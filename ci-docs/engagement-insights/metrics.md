---
title: 查看和创建指标
description: 如何创建、编辑和删除指标。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034258"
---
# <a name="view-and-create-metrics"></a>查看和创建指标

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

指标有助于了解访客的行为。 它们聚合事件属性并衡量网络属性的统计数据和性能。  

假设您正在您的网站上进行市场营销推广。 您可以使用指标跟踪促销期间访问您的网站的唯一访客或用户的数量。 分析指标可帮助您更好地了解您的网站访问群体。 通过将[度量](custom-reports.md)与自定义报表上的[维度](dimensions.md)结合使用，您可以衡量相关行为以便了解用户。 例如，您可以将访客分成新类别和回访类别，以确定各组之间兴趣和目的的差异。

## <a name="view-metrics"></a>查看指标

参与见解包括事件属性的常用聚合作为系统指标： 

- 访问者
- 访问次数
- 页面浏览量
- 单击次数

这些系统指标基于基本事件中的现有事件属性。

1. 在左侧导航窗格中，转到 **数据**。 
1. 选择 **指标** 选项卡以查看工作区中所有指标的列表。 
   > [!NOTE]
   > 系统生成的指标是只读指标。 您不能更改或删除它们。 只能创建和编辑自定义指标。

## <a name="create-a-metric"></a>创建指标

环境和工作区管理员可以创建指标。 创建指标之前，必须将事件属性发送到工作区。 您可以基于基本事件所发送的事件属性来创建指标，或使用 Web SDK [发送自定义事件属性](advanced-SDK-implementation.md)。

1. 转到 **数据** > **指标**。
1. 选择 **新建指标**。

   :::image type="content" source="media/new-metric.png" alt-text="向事件中添加指标。":::

1. 对于格式，请选择 **整数** 或 **双精度** 数据类型。 “整数”是指一个整数。 对于“双精度”，您可以选择一到三位小数。
1. 在 **资源库** 窗格中，查找指标所基于的事件属性。
1. 选择属性旁边的 **加号 (+)** 以在公式中使用它。 您只能基于一个属性来创建公式。 
1. 选择以下聚合函数之一。 

   - 总和：所有值的算术总和 
   - 平均值：所有值的平均值
   - 计数：值的总个数
   - 非重复计数：非重复值的总个数

   定义指标后，将看到该指标最后一小时的活动预览。

1. 选择 **保存**。 
1. 输入指标的名称，然后选择 **保存**。

该度量可能需要最多 1 分钟的时间才能用于[创建自定义报表](custom-reports.md)。

## <a name="edit-a-metric"></a>编辑指标

1. 转到 **数据** > **指标**。
1. 在列表中选择指标。
1. 更改指标的定义
1. 选择 **保存**。

## <a name="change-the-name-of-a-metric"></a>更改指标的名称

1. 转到 **数据** > **指标**。
1. 针对指标选择 **更多 [...]**，然后选择 **编辑名称**。
1. 更改名称。 
1. 选择 **重命名**。

## <a name="delete-a-metric"></a>删除指标

1. 转到 **数据** > **指标**。
1. 针对指标选择 **更多 [...]**，然后选择 **删除**。

   :::image type="content" source="media/delete-metric.png" alt-text="从事件中删除指标。":::

1. 选择 **删除** 以确认删除。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
