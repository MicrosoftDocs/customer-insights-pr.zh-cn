---
title: 访问群体见解中的系统配置
description: 了解 Dynamics 365 Customer Insights 访问群体见解功能中的系统设置。
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: a9c9e258da49b8f452550794539962d48b856829
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267329"
---
# <a name="system-configuration"></a><span data-ttu-id="03cd8-103">系统配置</span><span class="sxs-lookup"><span data-stu-id="03cd8-103">System configuration</span></span>

<span data-ttu-id="03cd8-104">**系统** 页包含以下选项卡：</span><span class="sxs-lookup"><span data-stu-id="03cd8-104">The **System** page includes the following tabs:</span></span>
- [<span data-ttu-id="03cd8-105">状态</span><span class="sxs-lookup"><span data-stu-id="03cd8-105">Status</span></span>](#status-tab)
- [<span data-ttu-id="03cd8-106">Schedule</span><span class="sxs-lookup"><span data-stu-id="03cd8-106">Schedule</span></span>](#schedule-tab)
- [<span data-ttu-id="03cd8-107">API 使用情况</span><span class="sxs-lookup"><span data-stu-id="03cd8-107">API usage</span></span>](#api-usage-tab)
- [<span data-ttu-id="03cd8-108">关于</span><span class="sxs-lookup"><span data-stu-id="03cd8-108">About</span></span>](#about-tab)
- [<span data-ttu-id="03cd8-109">常规</span><span class="sxs-lookup"><span data-stu-id="03cd8-109">General</span></span>](#general-tab)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03cd8-110">![“系统”页面](media/system-tabs.png "“系统”页面")</span><span class="sxs-lookup"><span data-stu-id="03cd8-110">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="03cd8-111">“状态”选项卡</span><span class="sxs-lookup"><span data-stu-id="03cd8-111">Status tab</span></span>

<span data-ttu-id="03cd8-112">使用 **状态** 选项卡，可以跟踪数据引入、数据导出和几个其他重要产品流程的进度。</span><span class="sxs-lookup"><span data-stu-id="03cd8-112">The **Status tab** lets you track the progress of data ingestion, data exports, and several other important product processes.</span></span> <span data-ttu-id="03cd8-113">查看此选项卡上的信息以确保活动流程的完整性。</span><span class="sxs-lookup"><span data-stu-id="03cd8-113">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="03cd8-114">此选项卡包括的表中具有各个流程的状态和处理信息。</span><span class="sxs-lookup"><span data-stu-id="03cd8-114">This tab includes tables with status and processing information for various processes.</span></span> <span data-ttu-id="03cd8-115">每个表都会跟踪任务及其相应实体的 **名称**、任务最近运行的 **状态**，以及 **上次更新** 的时间。</span><span class="sxs-lookup"><span data-stu-id="03cd8-115">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="03cd8-116">通过选择任务名称查看任务最近几次运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="03cd8-116">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="03cd8-117">状态类型</span><span class="sxs-lookup"><span data-stu-id="03cd8-117">Status types</span></span>

<span data-ttu-id="03cd8-118">对于任务，有六种类型的状态。</span><span class="sxs-lookup"><span data-stu-id="03cd8-118">There are six types of status for tasks.</span></span> <span data-ttu-id="03cd8-119">*匹配*、*合并*、*数据源*、*客户细分*、*度量*、*扩充*、*活动* 和 *预测* 页中还显示以下状态类型：</span><span class="sxs-lookup"><span data-stu-id="03cd8-119">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="03cd8-120">**正在处理：** 正在执行任务。</span><span class="sxs-lookup"><span data-stu-id="03cd8-120">**Processing:** Task is in progress.</span></span> <span data-ttu-id="03cd8-121">此状态可能会变为“成功”或“失败”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-121">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="03cd8-122">**成功：** 任务已成功完成。</span><span class="sxs-lookup"><span data-stu-id="03cd8-122">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="03cd8-123">**已跳过：** 已跳过任务。</span><span class="sxs-lookup"><span data-stu-id="03cd8-123">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="03cd8-124">此任务依赖的一个或多个下游流程出现故障或已跳过。</span><span class="sxs-lookup"><span data-stu-id="03cd8-124">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="03cd8-125">**失败：** 处理任务失败。</span><span class="sxs-lookup"><span data-stu-id="03cd8-125">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="03cd8-126">**已取消：** 用户在完成之前取消了处理。</span><span class="sxs-lookup"><span data-stu-id="03cd8-126">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="03cd8-127">**已排队**：处理已排队，所有上游任务完成后将开始处理。</span><span class="sxs-lookup"><span data-stu-id="03cd8-127">**Queued:** Processing is queued and will start once all the upstream tasks are completed.</span></span> <span data-ttu-id="03cd8-128">有关详细信息，请参阅[刷新策略](#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="03cd8-128">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="03cd8-129">刷新策略</span><span class="sxs-lookup"><span data-stu-id="03cd8-129">Refresh policies</span></span>

<span data-ttu-id="03cd8-130">此列表显示每个主要流程的刷新策略：</span><span class="sxs-lookup"><span data-stu-id="03cd8-130">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="03cd8-131">**数据源：** 根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-131">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-132">不依赖于任何其他进程。</span><span class="sxs-lookup"><span data-stu-id="03cd8-132">Doesn't depend on any other process.</span></span> <span data-ttu-id="03cd8-133">匹配依赖于成功完成此流程。</span><span class="sxs-lookup"><span data-stu-id="03cd8-133">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="03cd8-134">**匹配：** 根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-134">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-135">依赖于对匹配定义中使用的数据源的处理。</span><span class="sxs-lookup"><span data-stu-id="03cd8-135">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="03cd8-136">合并依赖于成功完成此流程。</span><span class="sxs-lookup"><span data-stu-id="03cd8-136">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="03cd8-137">**合并**：根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-137">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-138">依赖于完成匹配流程。</span><span class="sxs-lookup"><span data-stu-id="03cd8-138">Depends on the completion of the match process.</span></span> <span data-ttu-id="03cd8-139">细分、度量、扩充、搜索、活动、预测和数据准备依赖于成功完成此流程。</span><span class="sxs-lookup"><span data-stu-id="03cd8-139">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="03cd8-140">**细分**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-140">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-141">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-141">Depends on Merge.</span></span> <span data-ttu-id="03cd8-142">见解依赖于其处理。</span><span class="sxs-lookup"><span data-stu-id="03cd8-142">Insights depend on its processing.</span></span>
- <span data-ttu-id="03cd8-143">**度量**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-143">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-144">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-144">Depends on Merge.</span></span>
- <span data-ttu-id="03cd8-145">**活动**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-145">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-146">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-146">Depends on Merge.</span></span>
- <span data-ttu-id="03cd8-147">**扩充**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-147">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-148">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-148">Depends on Merge.</span></span>
- <span data-ttu-id="03cd8-149">**搜索**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-149">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-150">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-150">Depends on Merge.</span></span>
- <span data-ttu-id="03cd8-151">**数据准备**：根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-151">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-152">依赖于“合并”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-152">Depends on Merge.</span></span>
- <span data-ttu-id="03cd8-153">**见解**：手动（单次刷新）和根据[配置的计划](#schedule-tab)运行。</span><span class="sxs-lookup"><span data-stu-id="03cd8-153">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="03cd8-154">依赖于“细分”。</span><span class="sxs-lookup"><span data-stu-id="03cd8-154">Depends on Segments.</span></span>

<span data-ttu-id="03cd8-155">选择任务的状态可查看其所属整个作业的进度详细信息。</span><span class="sxs-lookup"><span data-stu-id="03cd8-155">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="03cd8-156">上面的刷新策略可帮助了解可以执行哪些操作来解决 **已跳过** 或 **已排队** 任务。</span><span class="sxs-lookup"><span data-stu-id="03cd8-156">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="03cd8-157">“计划”选项卡</span><span class="sxs-lookup"><span data-stu-id="03cd8-157">Schedule tab</span></span>

<span data-ttu-id="03cd8-158">使用 **计划** 选项卡以计划所有[引入数据源](data-sources.md)的自动刷新。</span><span class="sxs-lookup"><span data-stu-id="03cd8-158">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="03cd8-159">自动刷新可帮助确保您的数据源中的更新反映在您的统一客户配置文件中。</span><span class="sxs-lookup"><span data-stu-id="03cd8-159">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="03cd8-160">在访问群体见解中，转到 **管理员** > **系统** 并选择 **计划** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="03cd8-160">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="03cd8-161">计划的刷新的默认状态为 **已关闭**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-161">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="03cd8-162">若要启用计划的刷新，请将屏幕顶部的开关切换为 **开**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-162">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="03cd8-163">在 **每周**（默认值）和 **每日** 刷新之间选择。</span><span class="sxs-lookup"><span data-stu-id="03cd8-163">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="03cd8-164">如果要计划每周刷新，请选择一个或多个要运行刷新的日期。</span><span class="sxs-lookup"><span data-stu-id="03cd8-164">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="03cd8-165">设置 **时区**，然后使用 **时间** 下拉列表来设置刷新时间。</span><span class="sxs-lookup"><span data-stu-id="03cd8-165">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="03cd8-166">在您完成时，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-166">When you're finished, select **Set**.</span></span> <span data-ttu-id="03cd8-167">如果要将多次刷新安排在一天内，请选择 **添加其他时间**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-167">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="03cd8-168">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="03cd8-168">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="03cd8-169">“关于”选项卡</span><span class="sxs-lookup"><span data-stu-id="03cd8-169">About tab</span></span>

<span data-ttu-id="03cd8-170">**关于** 选项卡包含贵组织的 **显示名称**、现用 **环境 ID**、**区域** 和您的 **会话 ID**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-170">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="03cd8-171">如果您有多个工作环境，应该为每个工作环境提供一个易于识别的显示名称。</span><span class="sxs-lookup"><span data-stu-id="03cd8-171">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="03cd8-172">“常规”选项卡</span><span class="sxs-lookup"><span data-stu-id="03cd8-172">General tab</span></span>

<span data-ttu-id="03cd8-173">**常规** 选项卡上有两个选项，即 **语言** 和 **国家/地区格式**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-173">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="03cd8-174">应用[支持多种语言](supported-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="03cd8-174">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="03cd8-175">若要更改首选语言，请从下拉列表中选择 **语言**。</span><span class="sxs-lookup"><span data-stu-id="03cd8-175">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="03cd8-176">若要更改日期、时间和数字的首选格式，请使用 **国家/地区格式** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="03cd8-176">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="03cd8-177">将在此字段下显示格式预览。</span><span class="sxs-lookup"><span data-stu-id="03cd8-177">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="03cd8-178">当您选择新语言时，系统将自动推荐选择。</span><span class="sxs-lookup"><span data-stu-id="03cd8-178">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="03cd8-179">选择 **保存** 以确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="03cd8-179">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="03cd8-180">“API 使用情况”选项卡</span><span class="sxs-lookup"><span data-stu-id="03cd8-180">API usage tab</span></span>

<span data-ttu-id="03cd8-181">查找有关实时 API 使用情况的详细信息，并查看在给定的期限内发生了哪些事件。</span><span class="sxs-lookup"><span data-stu-id="03cd8-181">Find details about the real-time API usage and see which events happened in a given time frame.</span></span> <span data-ttu-id="03cd8-182">您可以在 **选择期限** 下拉菜单中选择期限。</span><span class="sxs-lookup"><span data-stu-id="03cd8-182">You choose the time frame in the **Select a time frame** drop-down menu.</span></span> 

<span data-ttu-id="03cd8-183">**API 使用情况** 包含三个部分：</span><span class="sxs-lookup"><span data-stu-id="03cd8-183">The **API usage** contains three sections:</span></span> 
- <span data-ttu-id="03cd8-184">**API 调用** - 一个显示选定期限内的 API 调用总数的图表。</span><span class="sxs-lookup"><span data-stu-id="03cd8-184">**API calls** - a chart that visualizes the aggregated number of calls to the API in the selected time frame.</span></span>

- <span data-ttu-id="03cd8-185">**数据传输** - 一个显示在选定期限内通过 API 传输的数据量的图表。</span><span class="sxs-lookup"><span data-stu-id="03cd8-185">**Data transfer** - a chart that shows the amount of data that was transferred through the API in the selected time frame.</span></span>

-  <span data-ttu-id="03cd8-186">**操作** - 一个表，其中包含每个可用 API 操作的行以及操作使用情况的详细信息。</span><span class="sxs-lookup"><span data-stu-id="03cd8-186">**Operations** - a table with rows for each available API operation and details about the usage of the operations.</span></span> <span data-ttu-id="03cd8-187">您可以选择操作名称以转到 [API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)。</span><span class="sxs-lookup"><span data-stu-id="03cd8-187">You can select an operation name to go to [the API reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

   <span data-ttu-id="03cd8-188">使用[实时数据引用](real-time-data-ingestion.md)的操作包含带有双筒望远镜符号的按钮，用于查看实时 API 使用情况。</span><span class="sxs-lookup"><span data-stu-id="03cd8-188">Operations which use [real-time data ingestion](real-time-data-ingestion.md) contain a button with a binocular symbol to view real-time API usage.</span></span> <span data-ttu-id="03cd8-189">选择该按钮以打开一个侧窗格，其中包含在当前环境中使用实时 API 的使用情况详细信息。</span><span class="sxs-lookup"><span data-stu-id="03cd8-189">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>   
   <span data-ttu-id="03cd8-190">使用 **实时 API 使用情况** 窗格中的 **分组依据** 框，以选择如何最好地呈现实时交互。</span><span class="sxs-lookup"><span data-stu-id="03cd8-190">Use the **Group by** box in the **Real-time API usage** pane to choose how to best present your real-time interactions.</span></span> <span data-ttu-id="03cd8-191">您可以按 API 方法、实体限定名称（引入的实体）、创建者（事件来源）、结果（成功或失败）或错误代码对数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="03cd8-191">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="03cd8-192">数据以历史图表和表格形式提供。</span><span class="sxs-lookup"><span data-stu-id="03cd8-192">The data is available as a history chart and as a table.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]