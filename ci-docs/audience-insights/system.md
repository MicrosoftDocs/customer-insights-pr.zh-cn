---
title: 访问群体见解中的系统配置
description: 了解 Dynamics 365 Customer Insights 访问群体见解功能中的系统设置。
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405224"
---
# <a name="system-configuration"></a><span data-ttu-id="929a0-103">系统配置</span><span class="sxs-lookup"><span data-stu-id="929a0-103">System configuration</span></span>

<span data-ttu-id="929a0-104">**系统** 页面包括四个选项卡：**状态**、**计划**、**关于** 和 **常规**。</span><span class="sxs-lookup"><span data-stu-id="929a0-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="929a0-105">![“系统”页面](media/system-tabs.png "“系统”页面")</span><span class="sxs-lookup"><span data-stu-id="929a0-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="929a0-106">“状态”选项卡</span><span class="sxs-lookup"><span data-stu-id="929a0-106">Status tab</span></span>

<span data-ttu-id="929a0-107">**状态** 选项卡用于跟踪数据引入、数据导出和若干重要产品流程的进度。</span><span class="sxs-lookup"><span data-stu-id="929a0-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="929a0-108">查看此选项卡上的信息以确保活动流程的完整性。</span><span class="sxs-lookup"><span data-stu-id="929a0-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="929a0-109">此选项卡包含 **数据源**、**系统进程** 和 **数据准备** 的状态表。</span><span class="sxs-lookup"><span data-stu-id="929a0-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="929a0-110">每个表都会跟踪任务及其相应实体的 **名称**、任务最近运行的 **状态**，以及 **上次更新** 的时间。</span><span class="sxs-lookup"><span data-stu-id="929a0-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="929a0-111">通过选择任务名称查看任务最近几次运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="929a0-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="929a0-112">状态类型</span><span class="sxs-lookup"><span data-stu-id="929a0-112">Status types</span></span>

<span data-ttu-id="929a0-113">对于任务，有六种类型的状态。</span><span class="sxs-lookup"><span data-stu-id="929a0-113">There are six types of status for tasks.</span></span> <span data-ttu-id="929a0-114">*匹配*、*合并*、*数据源*、*客户细分*、*度量*、*扩充*、*活动* 和 *预测* 页中还显示以下状态类型：</span><span class="sxs-lookup"><span data-stu-id="929a0-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="929a0-115">**正在处理：** 正在执行任务。</span><span class="sxs-lookup"><span data-stu-id="929a0-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="929a0-116">此状态可能会变为“成功”或“失败”。</span><span class="sxs-lookup"><span data-stu-id="929a0-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="929a0-117">**成功：** 任务已成功完成。</span><span class="sxs-lookup"><span data-stu-id="929a0-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="929a0-118">**已跳过：** 已跳过任务。</span><span class="sxs-lookup"><span data-stu-id="929a0-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="929a0-119">此任务依赖的一个或多个下游流程出现故障或已跳过。</span><span class="sxs-lookup"><span data-stu-id="929a0-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="929a0-120">**失败：** 处理任务失败。</span><span class="sxs-lookup"><span data-stu-id="929a0-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="929a0-121">**已取消：** 用户在完成之前取消了处理。</span><span class="sxs-lookup"><span data-stu-id="929a0-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="929a0-122">**已排队：** 处理已排队，将在完成所有下游任务后开始。</span><span class="sxs-lookup"><span data-stu-id="929a0-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="929a0-123">有关详细信息，请参阅[刷新策略](#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="929a0-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="929a0-124">刷新策略</span><span class="sxs-lookup"><span data-stu-id="929a0-124">Refresh policies</span></span>

<span data-ttu-id="929a0-125">此列表显示每个主要流程的刷新策略：</span><span class="sxs-lookup"><span data-stu-id="929a0-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="929a0-126">**数据源：** 根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-127">不依赖于任何其他进程。</span><span class="sxs-lookup"><span data-stu-id="929a0-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="929a0-128">匹配依赖于成功完成此流程。</span><span class="sxs-lookup"><span data-stu-id="929a0-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="929a0-129">**匹配：** 根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-130">依赖于对匹配定义中使用的数据源的处理。</span><span class="sxs-lookup"><span data-stu-id="929a0-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="929a0-131">合并依赖于成功完成此流程。</span><span class="sxs-lookup"><span data-stu-id="929a0-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="929a0-132">**合并**：根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-133">依赖于完成匹配流程。</span><span class="sxs-lookup"><span data-stu-id="929a0-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="929a0-134">细分、度量、扩充、搜索、活动、预测和数据准备依赖于成功完成此流程。</span><span class="sxs-lookup"><span data-stu-id="929a0-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="929a0-135">**细分**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-136">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="929a0-136">Depends on Merge.</span></span> <span data-ttu-id="929a0-137">见解依赖于其处理。</span><span class="sxs-lookup"><span data-stu-id="929a0-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="929a0-138">**度量**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-139">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="929a0-139">Depends on Merge.</span></span>
- <span data-ttu-id="929a0-140">**活动**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-141">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="929a0-141">Depends on Merge.</span></span>
- <span data-ttu-id="929a0-142">**扩充**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-143">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="929a0-143">Depends on Merge.</span></span>
- <span data-ttu-id="929a0-144">**搜索**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-145">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="929a0-145">Depends on Merge.</span></span>
- <span data-ttu-id="929a0-146">**数据准备**：根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-147">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="929a0-147">Depends on Merge.</span></span>
- <span data-ttu-id="929a0-148">**见解**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="929a0-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="929a0-149">依赖于“细分”。</span><span class="sxs-lookup"><span data-stu-id="929a0-149">Depends on Segments.</span></span>

<span data-ttu-id="929a0-150">选择任务的状态可查看其所属整个作业的进度详细信息。</span><span class="sxs-lookup"><span data-stu-id="929a0-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="929a0-151">上面的刷新策略可帮助了解可以执行哪些操作来解决 **已跳过** 或 **已排队** 任务。</span><span class="sxs-lookup"><span data-stu-id="929a0-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="929a0-152">“计划”选项卡</span><span class="sxs-lookup"><span data-stu-id="929a0-152">Schedule tab</span></span>

<span data-ttu-id="929a0-153">使用 **计划** 选项卡以计划所有[引入数据源](data-sources.md)的自动刷新。</span><span class="sxs-lookup"><span data-stu-id="929a0-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="929a0-154">自动刷新可帮助确保您的数据源中的更新反映在您的统一客户配置文件中。</span><span class="sxs-lookup"><span data-stu-id="929a0-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="929a0-155">在访问群体见解中，转到 **管理员** > **系统** 并选择 **计划** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="929a0-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="929a0-156">计划的刷新的默认状态为 **已关闭**。</span><span class="sxs-lookup"><span data-stu-id="929a0-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="929a0-157">若要启用计划的刷新，请将屏幕顶部的开关切换为 **开**。</span><span class="sxs-lookup"><span data-stu-id="929a0-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="929a0-158">在 **每周**（默认值）和 **每日** 刷新之间选择。</span><span class="sxs-lookup"><span data-stu-id="929a0-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="929a0-159">如果要计划每周刷新，请选择一个或多个要运行刷新的日期。</span><span class="sxs-lookup"><span data-stu-id="929a0-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="929a0-160">设置 **时区**，然后使用 **时间** 下拉列表来设置刷新时间。</span><span class="sxs-lookup"><span data-stu-id="929a0-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="929a0-161">在您完成时，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="929a0-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="929a0-162">如果要将多次刷新安排在一天内，请选择 **添加其他时间**。</span><span class="sxs-lookup"><span data-stu-id="929a0-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="929a0-163">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="929a0-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="929a0-164">“关于”选项卡</span><span class="sxs-lookup"><span data-stu-id="929a0-164">About tab</span></span>

<span data-ttu-id="929a0-165">**关于** 选项卡包含贵组织的 **显示名称**、现用 **环境 ID**、**区域** 和您的 **会话 ID**。</span><span class="sxs-lookup"><span data-stu-id="929a0-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="929a0-166">如果您有多个工作环境，应该为每个工作环境提供一个易于识别的显示名称。</span><span class="sxs-lookup"><span data-stu-id="929a0-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="929a0-167">“常规”选项卡</span><span class="sxs-lookup"><span data-stu-id="929a0-167">General tab</span></span>

<span data-ttu-id="929a0-168">**常规** 选项卡上有两个选项，即 **语言** 和 **国家/地区格式**。</span><span class="sxs-lookup"><span data-stu-id="929a0-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="929a0-169">应用[支持多种语言](supported-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="929a0-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="929a0-170">若要更改首选语言，请从下拉列表中选择 **语言**。</span><span class="sxs-lookup"><span data-stu-id="929a0-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="929a0-171">若要更改日期、时间和数字的首选格式，请使用 **国家/地区格式** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="929a0-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="929a0-172">将在此字段下显示格式预览。</span><span class="sxs-lookup"><span data-stu-id="929a0-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="929a0-173">当您选择新语言时，系统将自动推荐选择。</span><span class="sxs-lookup"><span data-stu-id="929a0-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="929a0-174">选择 **保存** 以确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="929a0-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="929a0-175">“API 使用情况”选项卡</span><span class="sxs-lookup"><span data-stu-id="929a0-175">API usage tab</span></span>

<span data-ttu-id="929a0-176">查找有关实时 API 使用情况的详细信息，并查看在给定时间范围内发生的事件。</span><span class="sxs-lookup"><span data-stu-id="929a0-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="929a0-177">有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。</span><span class="sxs-lookup"><span data-stu-id="929a0-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>
