---
title: 查看和创建客户细分
description: 如何创建、编辑和删除客户细分以及在何处使用客户细分。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: f6bba645a78173fb00dc75e6080f2aeda0b5a143
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623576"
---
# <a name="view-and-create-segments"></a>查看和创建客户细分

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

客户细分允许您根据特征或网站交互确定访客的子集。 利用客户细分，您可以应用筛选器并分析这些子集。 该分析可帮助检查和响应业务趋势。 

:::image type="content" source="media/segments-page.png" alt-text="显示工作区中现有客户细分列表的约会见解应用程序的屏幕截图。":::

## <a name="view-segments"></a>查看客户细分

1. 在左侧导航窗格中，转到 **数据**。 

1. 选择 **客户细分** 选项卡以查看工作区中所有客户细分的列表。 

## <a name="create-a-segment"></a>创建一个客户细分

客户细分由通过逻辑运算符连接的规则和条件组成。 条件会对选定的维度应用筛选器。 每个客户细分都可以最多使用五个维度。

下面的示例演示在一个规则中具有两个条件的细分市场。 它可以筛选浏览器为 Chrome 且操作系统为 iOS 或 Android 的任何网站事件。

:::image type="content" source="media/segment-sample.png" alt-text="规则中具有两个网站事件筛选条件的示例客户细分。":::

本节介绍如何从头开始创建 *空白客户细分*。

1. 转到 **数据** > **客户细分**。

1. 选择 **新建细分**。

1. 在 **资源库** 中，选择要作为筛选依据的属性旁边的 (+)。 当前，只能基于维度创建客户细分。

   :::image type="content" source="media/create-new-segment.png" alt-text="创建新客户细分。":::

1. 在 **规则** 部分，为所选属性选择运算符和值。 以下操作受支持：

   :::image type="content" source="media/choose-operator-segment.png" alt-text="为您的新客户细分选择运算符。":::

   - **是**：要求精确匹配以包括值。 使用 **等于** 以包括单个值，或者使用 **属于** 以包括多个值。
   - **不是**：要求精确匹配以不包括值。 使用 **等于** 以包括单个值，或者使用 **属于** 以包括多个值。
   - **开头为**：一个作为匹配值开头的字符串。
   - **结尾为**：一个作为匹配值结尾的字符串。
   - **包含**：匹配值中包含的字符串。

1. 要向组添加更多条件，可以使用逻辑运算符。 在使用设置的运算符时，会将预测属性考虑在内。
   - **AND** 运算符：细分过程中必须同时满足两个条件。 如果要为不同实体定义条件，此选项最有用。
   - **OR** 运算符：细分过程中需要满足其中一个条件。 如果要为同一个实体定义多个条件，此选项最有用。

1. 选择 **保存** 并命名客户细分。 

此客户细分将在 **客户细分** 页上列出，您可以将其应用于工作区中的所有报表和漏斗图。

## <a name="use-a-segment-in-a-report-or-funnel"></a>在报表或漏斗图中使用客户细分

您可以将客户细分应用于报表或漏斗图，以根据客户细分中的条件进行筛选。 但是，不能将客户细分应用于实时使用情况报表。

:::image type="content" source="media/segment-reports-filter.png" alt-text="具有展开的下拉菜单的页面视图报表，用于选择要应用哪些客户细分。":::

要应用客户细分，请打开报表或漏斗图。 选择 **+ 添加条件** 并选择 **按客户细分进行筛选**。 从列表中选择要应用的客户细分。 该客户细分将应用于报表。 如果图表不支持该客户细分，则会显示错误。 有关详细信息，请参阅[创建和管理漏斗图报表](funnel-reports.md)。
 
您可以将 *最多三个客户细分* 应用于报表或漏斗图。

## <a name="edit-a-segment"></a>编辑客户细分

1. 转到 **数据** > **客户细分**。
1. 选择列表中的客户细分以将其打开。 
1. 根据需要更改或添加值。
1. 选择 **保存** 以应用您所做的更改。

## <a name="change-the-name-of-a-segment"></a>更改客户细分的名称

1. 转到 **数据** > **客户细分**。
1. 在客户细分列表中，选择 **更多 [...]**。 
1. 从下拉列表中，选择 **编辑名称**。
1. 输入新名称，然后选择 **重命名**。

## <a name="delete-a-segment"></a>删除客户细分

1. 转到 **数据** > **客户细分**。
1. 在客户细分列表中，选择 **更多 [...]**。 
1. 从下拉列表中，选择 **删除**。
1. 选择 **删除** 以确认。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
