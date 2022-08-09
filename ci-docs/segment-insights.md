---
title: 客户细分见解（预览）
description: 获取有关现有客户细分的见解以查看差异和共性。
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170992"
---
# <a name="segment-insights-preview"></a>客户细分见解（预览）

发现有关现有客户细分的其他信息和见解。 找出两个客户细分的差别或它们的共同点。

## <a name="segment-overlap"></a>客户细分重叠

客户细分重叠分析显示两个或多个客户细分有多少个以及哪些客户是共有的。 例如，常见客户的客户细分与包含对您的服务或产品满意的客户的客户细分如何重叠。
您还可以分析重叠对于特定属性的变化。

### <a name="run-an-overlap-analysis"></a>运行重叠分析

1. 转到 **客户细分**，然后选择 **见解(预览)** 选项卡。

1. 选择 **新建**，然后在 **选择见解类型** 窗格中选择 **重叠** 选项。

1. 选择感兴趣的客户细分，然后选择 **下一步**。

1. 或者，选择一个或多个感兴趣的字段，以分析每个可能的字段值的重叠，然后选择 **下一步**。

1. 为重叠分析提供名称、可选的显示名称和说明。

1. 选择 **保存** 开始分析。 当状态从“正在刷新”变为“成功”时，重叠分析已准备就绪。

### <a name="view-and-optimize-an-overlap-analysis"></a>查看和优化重叠分析

1. 完成分析后，在 **客户细分** > **见解(预览)** 上查找有关此见解的详细信息。

   :::image type="content" source="media/segment-overlap.png" alt-text="客户细分重叠见解详细信息。":::

1. 选择一个见解查看分析结果：

   - 与选择进行分析的客户细分重叠的成员数。
   - 其中一个客户细分包含但其余客户细分不包含的成员数。
   - 如果您在配置重叠分析时选择了字段，将会在相应的选项卡中找到它们。 您可以使用筛选器下拉列表选择意向的任何属性级别，底部的表将显示相应的数据。

## <a name="segment-differentiators"></a>客户细分特异点

客户细分区分点可帮助您找出某个客户细分与其余客户或另一个客户细分的不同之处。 选择一个客户细分，系统会识别配置文件属性和可区分所选客户细分的度量。

### <a name="run-a-differentiator-analysis"></a>运行差异项分析

1. 转到 **客户细分**，然后选择 **见解(预览)** 选项卡。

1. 选择 **新建**，然后在 **选择见解类型** 窗格中选择 **特异点** 选项。

1. 将您要分析的客户细分选择为 **主要客户细分**，然后选择 **下一步**。

1. 选择 **所有客户** 或 **次要客户细分** 与您的主要客户细分进行比较，然后选择 **下一步**。

1. 或者，选择一个或多个感兴趣的字段，将分析重点放在特定属性上，然后选择 **下一步**。

1. 为特异点分析提供名称、可选的显示名称和说明。

1. 选择 **保存** 开始分析。 当状态从“正在刷新”变为“成功”时，特异点分析已准备就绪。

### <a name="view-and-optimize-a-differentiators-analysis"></a>查看和优化差异项分析

1. 完成分析后，转到 **客户细分** > **见解(预览)**。

   :::image type="content" source="media/segment-differentiators.png" alt-text="客户细分差异项见解详细信息。":::

1. 选择一个见解查看分析结果。 差异项分析包含两个选项卡。 **属性** 选项卡列出被视为区分点的配置文件属性。 **度量** 选项卡列出区分点。 每个选项卡包含以下详细信息：

   - 差异项的排名列表，按差异分数排序。
   - 每个差异项的 **差异分数**。 差异分数表示两个客户细分之间的属性的差异程度。 差异分数越高，两个客户细分之间的属性差异就越多。 选择一个分数打开 **差异分数** 窗格，其中包含该属性的值的分布。

## <a name="manage-segment-insights"></a>管理客户细分见解

转到 **客户细分** > **见解(预览)** 查看您的客户细分见解并进行管理。 选择客户细分见解可查看可用操作。

- **查看** 见解分析
- **编辑** 见解以更改其属性
- **刷新** 见解将再次运行分析
- **重命名** 见解
- **删除** 见解

[!INCLUDE [footer-include](includes/footer-banner.md)]
