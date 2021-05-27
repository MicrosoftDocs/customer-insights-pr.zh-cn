---
title: 从 Customer Insights 导出数据
description: 管理导出以共享数据。
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016603"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e28a4-103">导出(预览版)概述</span><span class="sxs-lookup"><span data-stu-id="e28a4-103">Exports (preview) overview</span></span>

<span data-ttu-id="e28a4-104">**导出** 页面显示所有配置的导出。</span><span class="sxs-lookup"><span data-stu-id="e28a4-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e28a4-105">导出与各种应用程序共享特定数据。</span><span class="sxs-lookup"><span data-stu-id="e28a4-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e28a4-106">它们可以包括客户配置文件或实体、架构和映射详细信息。</span><span class="sxs-lookup"><span data-stu-id="e28a4-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e28a4-107">每个导出都需要[由管理员设置的连接以管理身份验证和访问](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="e28a4-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e28a4-108">转到 **数据** > **导出** 以查看导出页面。</span><span class="sxs-lookup"><span data-stu-id="e28a4-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e28a4-109">所有用户角色都有权查看配置的导出。</span><span class="sxs-lookup"><span data-stu-id="e28a4-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e28a4-110">使用命令栏中的搜索字段按其名称、连接名称或连接类型查找导出。</span><span class="sxs-lookup"><span data-stu-id="e28a4-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e28a4-111">设置新导出</span><span class="sxs-lookup"><span data-stu-id="e28a4-111">Set up a new export</span></span>

<span data-ttu-id="e28a4-112">要设置或编辑导出，您需要有可用的连接。</span><span class="sxs-lookup"><span data-stu-id="e28a4-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e28a4-113">连接取决于您的[用户角色](permissions.md)：</span><span class="sxs-lookup"><span data-stu-id="e28a4-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e28a4-114">管理员可以访问所有连接。</span><span class="sxs-lookup"><span data-stu-id="e28a4-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e28a4-115">他们还可以在设置导出时创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="e28a4-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e28a4-116">参与者可以访问特定连接。</span><span class="sxs-lookup"><span data-stu-id="e28a4-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e28a4-117">他们依靠管理员来配置和共享连接。</span><span class="sxs-lookup"><span data-stu-id="e28a4-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e28a4-118">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="e28a4-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e28a4-119">查看者只能查看现有导出，但无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="e28a4-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="e28a4-120">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e28a4-121">选择 **添加导出** 以创建新导出目标。</span><span class="sxs-lookup"><span data-stu-id="e28a4-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="e28a4-122">在 **设置导出** 窗格中，选择要使用的连接。</span><span class="sxs-lookup"><span data-stu-id="e28a4-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e28a4-123">[连接](connections.md)由管理员管理。</span><span class="sxs-lookup"><span data-stu-id="e28a4-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e28a4-124">提供所需的详细信息并选择 **保存** 以创建导出。</span><span class="sxs-lookup"><span data-stu-id="e28a4-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e28a4-125">编辑导出</span><span class="sxs-lookup"><span data-stu-id="e28a4-125">Edit an export</span></span>

1. <span data-ttu-id="e28a4-126">选择要编辑的导出目标的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="e28a4-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="e28a4-127">从下拉菜单中选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="e28a4-128">更改要更新的值，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e28a4-129">查看导出和导出详细信息</span><span class="sxs-lookup"><span data-stu-id="e28a4-129">View Exports and export details</span></span>

<span data-ttu-id="e28a4-130">创建导出目标后，它们会列在 **数据** > **导出** 中。</span><span class="sxs-lookup"><span data-stu-id="e28a4-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e28a4-131">所有用户都可以看到共享的数据及其最新状态。</span><span class="sxs-lookup"><span data-stu-id="e28a4-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e28a4-132">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e28a4-133">无编辑权限的用户应选择 **查看** 而不是 **编辑**，以查看导出详细信息。</span><span class="sxs-lookup"><span data-stu-id="e28a4-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e28a4-134">此侧窗格显示此导出的设置。</span><span class="sxs-lookup"><span data-stu-id="e28a4-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="e28a4-135">如果没有编辑权限，您无法更改值。</span><span class="sxs-lookup"><span data-stu-id="e28a4-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e28a4-136">选择 **关闭** 以返回到出口页面。</span><span class="sxs-lookup"><span data-stu-id="e28a4-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="e28a4-137">按需运行导出</span><span class="sxs-lookup"><span data-stu-id="e28a4-137">Run exports on demand</span></span>

<span data-ttu-id="e28a4-138">配置导出后，只要具有工作连接，每次进行[计划的刷新](system.md#schedule-tab)时都将运行导出。</span><span class="sxs-lookup"><span data-stu-id="e28a4-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="e28a4-139">要在不等待计划刷新的情况下导出数据，请转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="e28a4-140">您有两种选择：</span><span class="sxs-lookup"><span data-stu-id="e28a4-140">You have two options:</span></span>

- <span data-ttu-id="e28a4-141">要运行所有导出，请在命令栏中选择 **全部运行**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="e28a4-142">要运行单个导出，请选择列表项上的椭圆 (...)，然后选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="e28a4-143">删除导出</span><span class="sxs-lookup"><span data-stu-id="e28a4-143">Remove an Export</span></span>

1. <span data-ttu-id="e28a4-144">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e28a4-145">选择要删除的导出的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="e28a4-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="e28a4-146">此下拉菜单中选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="e28a4-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="e28a4-147">选择确认屏幕中的 **删除** 确认删除。</span><span class="sxs-lookup"><span data-stu-id="e28a4-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
