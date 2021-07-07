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
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306246"
---
# <a name="segments-overview"></a><span data-ttu-id="7046a-103">客户细分概述</span><span class="sxs-lookup"><span data-stu-id="7046a-103">Segments overview</span></span>

<span data-ttu-id="7046a-104">通过客户细分，您可以基于人口统计、交易或行为属性对客户进行分组。</span><span class="sxs-lookup"><span data-stu-id="7046a-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="7046a-105">您可以使用客户细分来确定促销活动、销售活动和客户支持操作的目标，以实现您的业务目标。</span><span class="sxs-lookup"><span data-stu-id="7046a-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="7046a-106">与客户细分定义的筛选器匹配的客户配置文件称为客户细分的 *成员*。</span><span class="sxs-lookup"><span data-stu-id="7046a-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="7046a-107">某些[服务限制](service-limits.md)适用。</span><span class="sxs-lookup"><span data-stu-id="7046a-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="7046a-108">新建细分</span><span class="sxs-lookup"><span data-stu-id="7046a-108">Create a new segment</span></span>

<span data-ttu-id="7046a-109">创建新客户细分的方法有多种：</span><span class="sxs-lookup"><span data-stu-id="7046a-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="7046a-110">具有客户细分生成器的复杂客户细分：[空白客户细分](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="7046a-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="7046a-111">具有一个运算符的简单客户细分：[快速客户细分](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="7046a-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="7046a-112">由 AI 提供支持的相似客户查找方法：[相似客户](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="7046a-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="7046a-113">由 AI 提供支持且基于度量或属性的建议：[为改进度量而建议的客户细分](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="7046a-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="7046a-114">基于活动的建议：[基于客户活动的建议客户细分](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="7046a-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="7046a-115">管理现有细分</span><span class="sxs-lookup"><span data-stu-id="7046a-115">Manage existing segments</span></span>

<span data-ttu-id="7046a-116">转到 **客户细分** 页，查看并管理所有已保存的客户细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="7046a-117">每个客户细分都由包含有关客户细分的其他信息的行来表示。</span><span class="sxs-lookup"><span data-stu-id="7046a-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="具有选项下拉列表和可用选项的选定客户细分。":::

<span data-ttu-id="7046a-119">选择客户细分时可以使用以下操作：</span><span class="sxs-lookup"><span data-stu-id="7046a-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="7046a-120">**查看** 细分详细信息，包括细分成员的成员计数趋势预览。</span><span class="sxs-lookup"><span data-stu-id="7046a-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="7046a-121">**编辑** 细分以更改其属性。</span><span class="sxs-lookup"><span data-stu-id="7046a-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="7046a-122">**创建客户细分的重复项**。</span><span class="sxs-lookup"><span data-stu-id="7046a-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="7046a-123">您可以选择立即编辑其属性或只是保存重复项。</span><span class="sxs-lookup"><span data-stu-id="7046a-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="7046a-124">**刷新** 细分以包括最新数据。</span><span class="sxs-lookup"><span data-stu-id="7046a-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="7046a-125">**激活** 或 **停用** 细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="7046a-126">客户细分具有两种可能的状态 - 活动或停用。</span><span class="sxs-lookup"><span data-stu-id="7046a-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="7046a-127">这些状态在编辑客户细分时很有用。</span><span class="sxs-lookup"><span data-stu-id="7046a-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="7046a-128">对于停用的客户细分，存在客户细分定义，但不包含任何客户。</span><span class="sxs-lookup"><span data-stu-id="7046a-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="7046a-129">激活客户细分时，其状态将从“停用”变为“活动”，然后开始查找匹配客户细分定义的客户。</span><span class="sxs-lookup"><span data-stu-id="7046a-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="7046a-130">如果配置了 [计划刷新](system.md#schedule-tab)，停用客户细分会将 **状态** 列为 **已跳过**，指示还没有尝试刷新。</span><span class="sxs-lookup"><span data-stu-id="7046a-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="7046a-131">激活停用客户细分后，它将刷新，并包括在计划刷新中。</span><span class="sxs-lookup"><span data-stu-id="7046a-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="7046a-132">或者，您可以使用 **激活/停用** 下拉列表中的 **以后计划** 功能指定将来的日期和时间来激活和停用特定客户细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="7046a-133">**重命名** 细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-133">**Rename** the segment.</span></span>
- <span data-ttu-id="7046a-134">以 .CSV 文件格式 **下载** 成员列表。</span><span class="sxs-lookup"><span data-stu-id="7046a-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="7046a-135">**管理导出**，以查看导出相关客户细分并进行管理。</span><span class="sxs-lookup"><span data-stu-id="7046a-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="7046a-136">详细了解导出。</span><span class="sxs-lookup"><span data-stu-id="7046a-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="7046a-137">**删除** 细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="7046a-138">刷新细分</span><span class="sxs-lookup"><span data-stu-id="7046a-138">Refresh segments</span></span>

<span data-ttu-id="7046a-139">您可以通过选择 **客户细分** 页上的 **全部刷新** 来同时刷新所有客户细分；也可以选择一个或多个客户细分，然后从选项中选择 **刷新** 来刷新它们。</span><span class="sxs-lookup"><span data-stu-id="7046a-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="7046a-140">也可以在 **管理** > **系统** > **计划** 中配置定期刷新。</span><span class="sxs-lookup"><span data-stu-id="7046a-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="7046a-141">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="7046a-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7046a-142">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="7046a-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7046a-143">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7046a-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7046a-144">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="7046a-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="7046a-145">导出细分</span><span class="sxs-lookup"><span data-stu-id="7046a-145">Export segments</span></span>

<span data-ttu-id="7046a-146">您可以从客户细分页面或[导出页面](export-destinations.md)导出一个客户细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="7046a-147">转到 **细分** 页。</span><span class="sxs-lookup"><span data-stu-id="7046a-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="7046a-148">针对要导出的客户细分选择 **显示更多 [...]**。</span><span class="sxs-lookup"><span data-stu-id="7046a-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="7046a-149">从操作下拉列表中，选择 **管理导出**。</span><span class="sxs-lookup"><span data-stu-id="7046a-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="7046a-150">**客户细分导出（预览版）** 页面将打开。</span><span class="sxs-lookup"><span data-stu-id="7046a-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="7046a-151">您可以查看按包含或不包含当前客户细分的导出分组的所有配置导出。</span><span class="sxs-lookup"><span data-stu-id="7046a-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="7046a-152">要将选定的客户细分添加到导出中，请在列表中选择导出，然后选择 **添加客户细分**。</span><span class="sxs-lookup"><span data-stu-id="7046a-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="7046a-153">要使用选定的客户细分创建新的导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="7046a-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="7046a-154">有关创建导出的更多信息，请参阅[设置新的导出](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="7046a-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7046a-155">选择 **返回** 以返回客户细分的主页。</span><span class="sxs-lookup"><span data-stu-id="7046a-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="7046a-156">查看处理历史记录和细分成员</span><span class="sxs-lookup"><span data-stu-id="7046a-156">View processing history and segment members</span></span>

<span data-ttu-id="7046a-157">可以通过查看细分的详细信息来查看有关该细分的合并数据。</span><span class="sxs-lookup"><span data-stu-id="7046a-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="7046a-158">在 **细分** 页上，选择要查看的细分。</span><span class="sxs-lookup"><span data-stu-id="7046a-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="7046a-159">此页面的上半部分中有一个趋势图，该趋势图显示成员计数的变化。</span><span class="sxs-lookup"><span data-stu-id="7046a-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="7046a-160">将光标悬停在数据点上方可查看特定日期的成员计数。</span><span class="sxs-lookup"><span data-stu-id="7046a-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="7046a-161">可以更新可视化的时间段。</span><span class="sxs-lookup"><span data-stu-id="7046a-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7046a-162">![细分时间范围](media/segment-time-range.png "细分时间范围")</span><span class="sxs-lookup"><span data-stu-id="7046a-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="7046a-163">下半部分中包含细分成员列表。</span><span class="sxs-lookup"><span data-stu-id="7046a-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="7046a-164">此列表中显示的字段基于细分的实体属性。</span><span class="sxs-lookup"><span data-stu-id="7046a-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="7046a-165">此列表是匹配的细分成员的预览，并显示您的细分的前 100 条记录，以便您快速评估该细分和在需要时查看其定义。</span><span class="sxs-lookup"><span data-stu-id="7046a-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="7046a-166">若要查看所有匹配的记录，需要[导出细分](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="7046a-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
