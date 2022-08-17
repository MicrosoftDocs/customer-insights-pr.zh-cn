---
title: 客户细分概述
description: 概述客户细分以及如何创建和管理它们。
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246282"
---
# <a name="segments-overview"></a>客户细分概述

通过客户细分，您可以基于人口统计、交易或行为属性对客户进行分组。 您可以使用客户细分来确定促销活动、销售活动和客户支持操作的目标，以实现您的业务目标。

与客户细分定义的筛选器匹配的客户配置文件称为客户细分的 *成员*。 某些[服务限制](/dynamics365/customer-insights/service-limits)适用。

## <a name="create-a-segment"></a>创建一个客户细分

选择如何根据您的目标访问群体创建客户细分。

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

- 使用客户细分生成器的复杂客户细分：[生成您自己的客户细分](segment-builder.md)
- 具有一个运算符的简单客户细分：[快速客户细分](segment-quick.md)
- 由 AI 提供支持的相似客户查找方法：[相似客户](find-similar-customer-segments.md)
- 由 AI 提供支持且基于度量或属性的建议：[基于度量的建议客户细分](suggested-segments.md)
- 基于活动的建议：[基于客户活动的建议客户细分](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

- 使用客户细分生成器的简单或复杂客户细分：[生成您自己的客户细分](segment-builder.md)

---

## <a name="manage-existing-segments"></a>管理现有细分

转到 **客户细分** 页面查看您创建的客户细分、客户细分的状态、成员数以及上次刷新数据的时间。 您可以按任何列对客户细分列表进行排序，或使用搜索框查找要管理的客户细分。

选择客户细分可查看可用操作。

:::image type="content" source="media/segments-selected-segment.png" alt-text="具有选项下拉列表和可用选项的选定客户细分。" lightbox="media/segments-selected-segment.png":::

- [**查看**](#view-segment-details)客户细分详细信息，包括客户细分成员的成员计数趋势和预览。
- 以 .CSV 文件格式 **下载** 成员列表。
- **编辑** 细分以更改其属性。
- **创建客户细分的重复项**。 您可以选择直接编辑其属性或保存重复项。
- [**刷新**](#refresh-segments)客户细分以包括最新数据。
- **激活** 或 **停用** 细分。 停用客户细分不会在 [计划刷新](schedule-refresh.md)时刷新，会将 **状态** 列为 **已跳过**，指示还没有尝试刷新。 可用客户细分根据其类型刷新：静态或动态。
- **设为静态** 或 **设为动态** 客户细分类型。 必须手动刷新静态客户细分。 动态客户细分将在系统刷新期间自动刷新。
- 从客户细分中 [**查找类似的客户**](find-similar-customer-segments.md)。
- **重命名** 细分。
- 用于针对客户细分 [管理标记](work-with-tags-columns.md#manage-tags)的 **标记**。
- [**管理导出**](#export-segments)，以查看导出相关客户细分并进行管理。 [详细了解导出。](export-destinations.md)
- **删除** 细分。
- 用于 [自定义显示的列](work-with-tags-columns.md#customize-columns)的 **列**。
- 用于 [按标记筛选](work-with-tags-columns.md#filter-on-tags)的 **筛选器**。
- 用于按客户细分名称进行搜索的 **搜索名称**。

## <a name="view-segment-details"></a>查看客户细分详细信息

在 **客户细分** 页面上，选择一个客户细分查看处理历史记录和客户细分成员。

此页面的上半部分中有一个趋势图，该趋势图显示成员计数的变化。 将光标悬停在数据点上方可查看特定日期的成员计数。 更改可视化的时间段。

:::image type="content" source="media/segment-time-range.png" alt-text="客户细分时间范围。":::

下半部分中包含细分成员列表。

> [!NOTE]
> 此列表中显示的字段基于细分的实体属性。
>
>此列表是匹配的细分成员的预览，并显示您的细分的前 100 条记录，以便您快速评估该细分和在需要时查看其定义。 要查看所有匹配的记录，[导出客户细分](export-destinations.md)。

## <a name="refresh-segments"></a>刷新客户细分

客户细分可以按计划自动刷新，也可以根据需要手动刷新。 要手动刷新一个或多个客户细分，选择它们并选择 **刷新**。

若要 [计划自动刷新](schedule-refresh.md)，请转到 **管理** > **系统** > **计划**。 以下规则适用：

- 所有类型为 **动态** 或 **扩展** 的客户细分都将按照设定的节奏自动刷新。 刷新完成后，**状态** 会指示刷新客户细分时是否存在任何问题。 **上次刷新时间** 显示上次成功刷新的时间戳。 如果发生错误，选择错误可以查看发生的情况的详细信息。
- **静态** 类型的客户细分 *不会* 自动刷新。 **上次刷新时间** 显示上次手动运行或刷新静态客户细分的时间戳。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>导出客户细分

将客户细分导出到其他应用以进一步使用数据。 从客户细分页面或[导出页面](export-destinations.md)导出一个客户细分。

1. 转到 **客户细分** 页面，选择要导出的客户细分。

1. 选择 **管理导出**。 **客户细分导出（预览版）** 页面将打开。 查看按照是否包含当前客户细分分组的所有配置的导出。

   1. 要将选定的客户细分添加到导出中，**编辑** 相应的导出来选择相应的客户细分，然后保存。 在面向个人客户的环境中，选择列表中的导出，然后选择 **添加客户细分** 来实现相同的结果。

   1. 要使用选定的客户细分创建新的导出，请选择 **添加导出**。 有关创建导出的更多信息，请参阅[设置新的导出](export-destinations.md#set-up-a-new-export)。

1. 选择 **返回** 以返回客户细分的主页。

## <a name="track-usage-of-a-segment"></a>跟踪客户细分的使用情况

如果您在应用中使用客户细分，并且这些客户细分基于与 Customer Insights 连接的同一 Microsoft Dataverse 组织，那么您可以跟踪客户细分的使用情况。 对于 [Dynamics 365 Marketing 的客户旅程中使用的 Customer Insights 客户细分](/dynamics365/marketing/real-time-marketing-ci-profile)，系统会通知您该客户细分的使用情况。

编辑在 Customer Insights 环境或 Marketing 客户旅程中使用的客户细分时，[客户细分生成器](segment-builder.md)中的横幅会通知您依赖项。 通过直接从横幅或选择段生成器中的 **使用情况** 来检查依赖项详细信息。

**客户细分使用情况** 窗格显示有关基于 Dataverse 的应用中此客户细分的使用情况的详细信息。 对于客户旅程中使用的客户细分，您将找到一个链接来检查 Marketing 中使用此客户细分的旅程。 如果您具有访问 Marketing 应用的权限，在此查看更多详细信息。

:::image type="content" source="media/segment-usage-pane.png" alt-text="客户细分生成器中包含客户细分使用情况详细信息的侧窗格。":::

当您尝试删除跟踪的客户细分时，系统会通知您其使用情况。 如果您要删除的客户细分用于 Marketing 中的客户旅程，则该旅程将对此客户细分中的所有用户停止。 如果旅程是市场营销活动的一部分，则删除将影响该市场活动本身。 但是，尽管有警告，您仍然可以删除该客户细分。

:::image type="content" source="media/segment-usage-delete.png" alt-text="在 Dataverse 应用程序中使用客户细分时用于确认删除客户细分的对话框。":::

### <a name="supported-apps"></a>支持的应用

当前在以下基于 Dataverse 的应用中跟踪了使用情况：

- [Dynamics 365 Marketing 中的客户旅程](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
