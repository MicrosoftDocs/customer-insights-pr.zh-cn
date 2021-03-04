---
title: 现有客户细分的客户细分见解
description: 获取有关现有客户细分的见解以查看差异和共性。
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270009"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="cb7da-103">客户细分见解（预览）</span><span class="sxs-lookup"><span data-stu-id="cb7da-103">Segment insights (preview)</span></span>

<span data-ttu-id="cb7da-104">发现有关现有客户细分的其他信息和见解。</span><span class="sxs-lookup"><span data-stu-id="cb7da-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="cb7da-105">找出两个客户细分的差别或它们的共同点。</span><span class="sxs-lookup"><span data-stu-id="cb7da-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="cb7da-106">客户细分重叠</span><span class="sxs-lookup"><span data-stu-id="cb7da-106">Segment overlap</span></span>

<span data-ttu-id="cb7da-107">客户细分重叠分析显示两个或多个客户细分有多少个以及哪些客户是共有的。</span><span class="sxs-lookup"><span data-stu-id="cb7da-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="cb7da-108">例如，常见客户的客户细分与包含对您的服务或产品满意的客户的客户细分如何重叠。</span><span class="sxs-lookup"><span data-stu-id="cb7da-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="cb7da-109">您还可以分析重叠对于特定属性的变化。</span><span class="sxs-lookup"><span data-stu-id="cb7da-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="cb7da-110">运行重叠分析</span><span class="sxs-lookup"><span data-stu-id="cb7da-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="cb7da-111">转到 **客户细分**，然后选择 **见解(预览)** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb7da-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="cb7da-112">选择 **新建**，然后在 **选择见解类型** 窗格中选择 **重叠** 选项。</span><span class="sxs-lookup"><span data-stu-id="cb7da-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="cb7da-113">选择感兴趣的客户细分，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cb7da-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="cb7da-114">或者，选择一个或多个感兴趣的字段，以分析每个可能的字段值的重叠，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cb7da-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="cb7da-115">为重叠分析提供名称、可选的显示名称和说明。</span><span class="sxs-lookup"><span data-stu-id="cb7da-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="cb7da-116">选择 **保存** 开始分析。</span><span class="sxs-lookup"><span data-stu-id="cb7da-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="cb7da-117">当状态从“正在刷新”变为“成功”时，重叠分析已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="cb7da-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="cb7da-118">查看和优化重叠分析</span><span class="sxs-lookup"><span data-stu-id="cb7da-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="cb7da-119">完成分析后，在 **客户细分** > **见解(预览)** 上查找有关此见解的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb7da-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="客户细分重叠见解详细信息":::

<span data-ttu-id="cb7da-121">选择一个见解查看分析结果：</span><span class="sxs-lookup"><span data-stu-id="cb7da-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="cb7da-122">与选择进行分析的客户细分重叠的成员数。</span><span class="sxs-lookup"><span data-stu-id="cb7da-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="cb7da-123">其中一个客户细分包含但其余客户细分不包含的成员数。</span><span class="sxs-lookup"><span data-stu-id="cb7da-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="cb7da-124">如果您在配置重叠分析时选择了字段，将会在相应的选项卡中找到它们。</span><span class="sxs-lookup"><span data-stu-id="cb7da-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="cb7da-125">您可以使用筛选器下拉列表选择感兴趣的任何属性级别，底部的表将显示相应的数据。</span><span class="sxs-lookup"><span data-stu-id="cb7da-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="cb7da-126">客户细分特异点</span><span class="sxs-lookup"><span data-stu-id="cb7da-126">Segment differentiators</span></span>

<span data-ttu-id="cb7da-127">客户细分区分点可帮助您找出某个客户细分与其余客户或另一个客户细分的不同之处。</span><span class="sxs-lookup"><span data-stu-id="cb7da-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="cb7da-128">您只需要选择一个客户细分，系统就会识别配置文件属性和可区分所选客户细分的度量。</span><span class="sxs-lookup"><span data-stu-id="cb7da-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="cb7da-129">运行差异项分析</span><span class="sxs-lookup"><span data-stu-id="cb7da-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="cb7da-130">转到 **客户细分**，然后选择 **见解(预览)** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb7da-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="cb7da-131">选择 **新建**，然后在 **选择见解类型** 窗格中选择 **重叠** 选项。</span><span class="sxs-lookup"><span data-stu-id="cb7da-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="cb7da-132">将您要分析的客户细分选择为 **主要客户细分**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cb7da-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="cb7da-133">选择 **所有客户** 或 **次要客户细分** 与您的主要客户细分进行比较，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cb7da-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="cb7da-134">或者，选择一个或多个感兴趣的字段，将分析重点放在特定属性上，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cb7da-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="cb7da-135">为重叠分析提供名称、可选的显示名称和说明。</span><span class="sxs-lookup"><span data-stu-id="cb7da-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="cb7da-136">选择 **保存** 开始分析。</span><span class="sxs-lookup"><span data-stu-id="cb7da-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="cb7da-137">当状态从“正在刷新”变为“成功”时，重叠分析已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="cb7da-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="cb7da-138">查看和优化差异项分析</span><span class="sxs-lookup"><span data-stu-id="cb7da-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="cb7da-139">完成分析后，在 **客户细分** > **见解(预览)** 上查找有关此见解的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb7da-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="客户细分差异项见解详细信息":::

<span data-ttu-id="cb7da-141">选择一个见解查看分析结果。</span><span class="sxs-lookup"><span data-stu-id="cb7da-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="cb7da-142">差异项分析包含两个选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb7da-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="cb7da-143">**属性** 选项卡列出被视为区分点的配置文件属性。</span><span class="sxs-lookup"><span data-stu-id="cb7da-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="cb7da-144">**度量** 选项卡列出区分点。</span><span class="sxs-lookup"><span data-stu-id="cb7da-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="cb7da-145">每个选项卡包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="cb7da-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="cb7da-146">差异项的排名列表，按差异分数排序。</span><span class="sxs-lookup"><span data-stu-id="cb7da-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="cb7da-147">每个差异项的 **差异分数**。</span><span class="sxs-lookup"><span data-stu-id="cb7da-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="cb7da-148">差异分数表示两个客户细分之间的属性的差异程度。</span><span class="sxs-lookup"><span data-stu-id="cb7da-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="cb7da-149">差异分数越高，两个客户细分之间的属性差异就越多。</span><span class="sxs-lookup"><span data-stu-id="cb7da-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="cb7da-150">选择一个分数打开 **差异分数** 窗格，其中包含该属性的值的分布。</span><span class="sxs-lookup"><span data-stu-id="cb7da-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="cb7da-151">管理客户细分见解</span><span class="sxs-lookup"><span data-stu-id="cb7da-151">Manage segment insights</span></span>

<span data-ttu-id="cb7da-152">您可以从命令栏中对见解使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="cb7da-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="cb7da-153">**返回** 将返回见解列表</span><span class="sxs-lookup"><span data-stu-id="cb7da-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="cb7da-154">**刷新** 将再次运行分析</span><span class="sxs-lookup"><span data-stu-id="cb7da-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="cb7da-155">**删除** 将删除此见解</span><span class="sxs-lookup"><span data-stu-id="cb7da-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]