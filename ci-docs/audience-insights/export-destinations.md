---
title: 从 Customer Insights 导出数据
description: 管理导出以共享数据。
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305467"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="a13e3-103">导出(预览版)概述</span><span class="sxs-lookup"><span data-stu-id="a13e3-103">Exports (preview) overview</span></span>

<span data-ttu-id="a13e3-104">**导出** 页面显示所有配置的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="a13e3-105">导出与各种应用程序共享特定数据。</span><span class="sxs-lookup"><span data-stu-id="a13e3-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="a13e3-106">它们可以包括客户配置文件或实体、架构和映射详细信息。</span><span class="sxs-lookup"><span data-stu-id="a13e3-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="a13e3-107">每个导出都需要[由管理员设置的连接以管理身份验证和访问](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="a13e3-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="a13e3-108">转到 **数据** > **导出** 以查看导出页面。</span><span class="sxs-lookup"><span data-stu-id="a13e3-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="a13e3-109">所有用户角色都可以查看已配置的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-109">All user roles can view configured exports.</span></span> <span data-ttu-id="a13e3-110">使用命令栏中的搜索字段以按名称、连接名称或连接类型查找导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="a13e3-111">设置新导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-111">Set up a new export</span></span>

<span data-ttu-id="a13e3-112">要设置或编辑导出，您需要有可用的连接。</span><span class="sxs-lookup"><span data-stu-id="a13e3-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="a13e3-113">连接取决于您的[用户角色](permissions.md)：</span><span class="sxs-lookup"><span data-stu-id="a13e3-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="a13e3-114">管理员可以访问所有连接。</span><span class="sxs-lookup"><span data-stu-id="a13e3-114">Administrators have access to all connections.</span></span> <span data-ttu-id="a13e3-115">他们还可以在设置导出时创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="a13e3-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="a13e3-116">参与者可以访问特定连接。</span><span class="sxs-lookup"><span data-stu-id="a13e3-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="a13e3-117">他们依靠管理员来配置和共享连接。</span><span class="sxs-lookup"><span data-stu-id="a13e3-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="a13e3-118">导出列表会在 **您的权限** 列中向参与者显示他们是可以编辑导出还是只能查看导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="a13e3-119">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="a13e3-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="a13e3-120">查看者只能查看现有导出，但无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="a13e3-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="a13e3-121">定义新导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-121">Define a new export</span></span>

1. <span data-ttu-id="a13e3-122">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a13e3-123">选择 **添加导出** 以创建新导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="a13e3-124">在 **设置导出** 窗格中，选择要使用的连接。</span><span class="sxs-lookup"><span data-stu-id="a13e3-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="a13e3-125">[连接](connections.md)由管理员管理。</span><span class="sxs-lookup"><span data-stu-id="a13e3-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="a13e3-126">提供所需的详细信息并选择 **保存** 以创建导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="a13e3-127">基于现有导出定义新导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="a13e3-128">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a13e3-129">在导出列表中，选择要重复的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="a13e3-130">在命令栏中选择 **创建重复项**，以打开包含所选导出详细信息的 **设置导出** 窗格。</span><span class="sxs-lookup"><span data-stu-id="a13e3-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="a13e3-131">查看并调整导出，并选择 **保存** 以创建新导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="a13e3-132">编辑导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-132">Edit an export</span></span>

1. <span data-ttu-id="a13e3-133">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a13e3-134">在导出列表中，选择要编辑的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="a13e3-135">在命令栏中选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="a13e3-136">更改要更新的值，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="a13e3-137">查看导出和导出详细信息</span><span class="sxs-lookup"><span data-stu-id="a13e3-137">View exports and export details</span></span>

<span data-ttu-id="a13e3-138">创建导出目标后，它们会列在 **数据** > **导出** 中。</span><span class="sxs-lookup"><span data-stu-id="a13e3-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="a13e3-139">所有用户都可以看到共享的数据及其最新状态。</span><span class="sxs-lookup"><span data-stu-id="a13e3-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="a13e3-140">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a13e3-141">没有编辑权限的用户可以选择 **查看**（而不是 **编辑**）来查看导出详细信息。</span><span class="sxs-lookup"><span data-stu-id="a13e3-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="a13e3-142">侧窗格显示了导出的配置。</span><span class="sxs-lookup"><span data-stu-id="a13e3-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="a13e3-143">如果没有编辑权限，您无法更改值。</span><span class="sxs-lookup"><span data-stu-id="a13e3-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="a13e3-144">选择 **关闭** 以返回到出口页面。</span><span class="sxs-lookup"><span data-stu-id="a13e3-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="a13e3-145">计划并运行导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-145">Schedule and run exports</span></span>

<span data-ttu-id="a13e3-146">您配置的每个导出都有一个刷新计划。</span><span class="sxs-lookup"><span data-stu-id="a13e3-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="a13e3-147">在刷新期间，系统会查找要包括在导出中的新数据或已更新数据。</span><span class="sxs-lookup"><span data-stu-id="a13e3-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="a13e3-148">默认情况下，导出在每个[计划系统刷新](system.md#schedule-tab)过程中运行。</span><span class="sxs-lookup"><span data-stu-id="a13e3-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a13e3-149">您可以自定义刷新计划或将其关闭以手动运行导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="a13e3-150">导出计划取决于您的环境状态。</span><span class="sxs-lookup"><span data-stu-id="a13e3-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="a13e3-151">如果在应启动计划导出时正在进行有关[依赖项](system.md#refresh-policies)的更新，系统将首先完成更新，然后运行导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="a13e3-152">可以在 **刷新时间** 列中查看最后刷新导出的时间。</span><span class="sxs-lookup"><span data-stu-id="a13e3-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="a13e3-153">计划导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-153">Schedule exports</span></span>

<span data-ttu-id="a13e3-154">您可以同时定义个别导出或多个导出的自定义刷新计划。</span><span class="sxs-lookup"><span data-stu-id="a13e3-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="a13e3-155">当前定义的计划列在导出列表的 **计划** 列中。</span><span class="sxs-lookup"><span data-stu-id="a13e3-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="a13e3-156">更改计划的权限与[编辑和定义导出](export-destinations.md#set-up-a-new-export)的权限相同。</span><span class="sxs-lookup"><span data-stu-id="a13e3-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="a13e3-157">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a13e3-158">选择要计划的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="a13e3-159">在命令栏中选择 **计划**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="a13e3-160">在 **计划导出** 窗格中，将 **计划运行时间** 设置为 **打开**，以自动运行导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="a13e3-161">将其设置为 **关闭** 可以手动刷新它。</span><span class="sxs-lookup"><span data-stu-id="a13e3-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="a13e3-162">对于自动刷新的导出，请选择 **定期** 值并指定其详细信息。</span><span class="sxs-lookup"><span data-stu-id="a13e3-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="a13e3-163">定义的时间适用于所有定期实例。</span><span class="sxs-lookup"><span data-stu-id="a13e3-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="a13e3-164">这是导出应该开始刷新的时间。</span><span class="sxs-lookup"><span data-stu-id="a13e3-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="a13e3-165">通过选择 **保存** 来应用并激活您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a13e3-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="a13e3-166">在编辑多个导出的计划时，需要在 **保留或替代计划** 下面进行选择：</span><span class="sxs-lookup"><span data-stu-id="a13e3-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="a13e3-167">**保留单个计划**：为选定导出保留先前定义的计划，并仅禁用或启用它们。</span><span class="sxs-lookup"><span data-stu-id="a13e3-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="a13e3-168">**为所有选定的导出定义新计划**：替代选定导出的现有计划。</span><span class="sxs-lookup"><span data-stu-id="a13e3-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="a13e3-169">按需运行导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-169">Run exports on demand</span></span>

<span data-ttu-id="a13e3-170">要在不等待计划刷新的情况下导出数据，请转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="a13e3-171">要运行所有导出，请在命令栏中选择 **全部运行**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="a13e3-172">此操作将只运行具有活动计划的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="a13e3-173">要运行单个导出，请在列表中选择该导出，然后在命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="a13e3-174">这是没有活动计划时运行导出的方式。</span><span class="sxs-lookup"><span data-stu-id="a13e3-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="a13e3-175">删除导出</span><span class="sxs-lookup"><span data-stu-id="a13e3-175">Remove an Export</span></span>

1. <span data-ttu-id="a13e3-176">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a13e3-177">选择要删除的导出。</span><span class="sxs-lookup"><span data-stu-id="a13e3-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="a13e3-178">在命令栏中选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="a13e3-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="a13e3-179">选择确认屏幕中的 **删除** 确认删除。</span><span class="sxs-lookup"><span data-stu-id="a13e3-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
