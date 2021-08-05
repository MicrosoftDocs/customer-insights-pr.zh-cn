---
title: 访问群体见解中的客户细分
description: 概述客户细分以及如何创建和管理它们。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e2080b4ad19f6f57f60da591345e80ce9083e8a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554056"
---
# <a name="segments-overview"></a>客户细分概述

通过客户细分，您可以基于人口统计、交易或行为属性对客户进行分组。 您可以使用客户细分来确定促销活动、销售活动和客户支持操作的目标，以实现您的业务目标。

与客户细分定义的筛选器匹配的客户配置文件称为客户细分的 *成员*。 某些[服务限制](service-limits.md)适用。

## <a name="create-a-new-segment"></a>新建细分

创建新客户细分的方法有多种： 

- 具有客户细分生成器的复杂客户细分：[空白客户细分](segment-builder.md#create-a-new-segment)
- 具有一个运算符的简单客户细分：[快速客户细分](segment-builder.md#quick-segments)
- 由 AI 提供支持的相似客户查找方法：[相似客户](find-similar-customer-segments.md)
- 由 AI 提供支持且基于度量或属性的建议：[为改进度量而建议的客户细分](suggested-segments.md)
- 基于活动的建议：[基于客户活动的建议客户细分](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>管理现有细分

转到 **客户细分** 页，查看并管理所有已保存的客户细分。

每个客户细分都由包含有关客户细分的其他信息的行来表示。

:::image type="content" source="media/segments-selected-segment.png" alt-text="具有选项下拉列表和可用选项的选定客户细分。":::

选择客户细分时可以使用以下操作：

- **查看** 细分详细信息，包括细分成员的成员计数趋势预览。
- **编辑** 细分以更改其属性。
- **创建客户细分的重复项**。 您可以选择立即编辑其属性或只是保存重复项。
- **刷新** 细分以包括最新数据。
- **激活** 或 **停用** 细分。 客户细分具有两种可能的状态 - 活动或停用。 这些状态在编辑客户细分时很有用。 对于停用的客户细分，存在客户细分定义，但不包含任何客户。 激活客户细分时，其状态将从“停用”变为“活动”，然后开始查找匹配客户细分定义的客户。 如果配置了 [计划刷新](system.md#schedule-tab)，停用客户细分会将 **状态** 列为 **已跳过**，指示还没有尝试刷新。 激活停用客户细分后，它将刷新，并包括在计划刷新中。
  或者，您可以使用 **激活/停用** 下拉列表中的 **以后计划** 功能指定将来的日期和时间来激活和停用特定客户细分。
- **重命名** 细分。
- 以 .CSV 文件格式 **下载** 成员列表。
- **管理导出**，以查看导出相关客户细分并进行管理。 [详细了解导出。](export-destinations.md)
- **删除** 细分。

## <a name="refresh-segments"></a>刷新细分

您可以通过选择 **客户细分** 页上的 **全部刷新** 来同时刷新所有客户细分；也可以选择一个或多个客户细分，然后从选项中选择 **刷新** 来刷新它们。 也可以在 **管理** > **系统** > **计划** 中配置定期刷新。

> [!TIP]
> 对于任务/流程，有[六种类型的状态](system.md#status-types)。 此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。 可以选择流程状态以查看有关整个作业的进度的详细信息。 在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。

## <a name="export-segments"></a>导出细分

您可以从客户细分页面或[导出页面](export-destinations.md)导出一个客户细分。 

1. 转到 **细分** 页。

1. 针对要导出的客户细分选择 **显示更多 [...]**。

1. 从操作下拉列表中，选择 **管理导出**。

1. **客户细分导出（预览版）** 页面将打开。 您可以查看按包含或不包含当前客户细分的导出分组的所有配置导出。

   1. 要将选定的客户细分添加到导出中，请在列表中选择导出，然后选择 **添加客户细分**。

   1. 要使用选定的客户细分创建新的导出，请选择 **添加导出**。 有关创建导出的更多信息，请参阅[设置新的导出](export-destinations.md#set-up-a-new-export)。

1. 选择 **返回** 以返回客户细分的主页。

## <a name="view-processing-history-and-segment-members"></a>查看处理历史记录和细分成员

可以通过查看细分的详细信息来查看有关该细分的合并数据。

在 **细分** 页上，选择要查看的细分。

此页面的上半部分中有一个趋势图，该趋势图显示成员计数的变化。 将光标悬停在数据点上方可查看特定日期的成员计数。

可以更新可视化的时间段。

> [!div class="mx-imgBorder"]
> ![客户细分时间范围。](media/segment-time-range.png "细分时间范围")

下半部分中包含细分成员列表。

> [!NOTE]
> 此列表中显示的字段基于细分的实体属性。
>
>此列表是匹配的细分成员的预览，并显示您的细分的前 100 条记录，以便您快速评估该细分和在需要时查看其定义。 若要查看所有匹配的记录，需要[导出细分](export-destinations.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
