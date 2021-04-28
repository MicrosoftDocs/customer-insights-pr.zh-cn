---
title: 从 Customer Insights 导出数据
description: 管理导出以共享数据。
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896132"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="89a18-103">导出(预览版)概述</span><span class="sxs-lookup"><span data-stu-id="89a18-103">Exports (preview) overview</span></span>

<span data-ttu-id="89a18-104">**导出** 页面显示所有配置的导出。</span><span class="sxs-lookup"><span data-stu-id="89a18-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="89a18-105">导出与各种应用程序共享特定数据。</span><span class="sxs-lookup"><span data-stu-id="89a18-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="89a18-106">它们可以包括客户配置文件或实体、架构和映射详细信息。</span><span class="sxs-lookup"><span data-stu-id="89a18-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="89a18-107">每个导出都需要[由管理员设置的连接以管理身份验证和访问](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="89a18-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89a18-108">在 2021 年 3 月之前，导出自动创建了与相应服务的连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="89a18-109">导出现在需要[由管理员创建和共享的连接](connections.md)，然后才能创建它们。</span><span class="sxs-lookup"><span data-stu-id="89a18-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="89a18-110">转到 **数据** > **导出** 以查看导出页面。</span><span class="sxs-lookup"><span data-stu-id="89a18-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="89a18-111">所有用户角色都有权查看配置的导出。</span><span class="sxs-lookup"><span data-stu-id="89a18-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="89a18-112">使用命令栏中的搜索字段按其名称、连接名称或连接类型查找导出。</span><span class="sxs-lookup"><span data-stu-id="89a18-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="89a18-113">设置新导出</span><span class="sxs-lookup"><span data-stu-id="89a18-113">Set up a new export</span></span>

<span data-ttu-id="89a18-114">要设置或编辑导出，您需要有可用的连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="89a18-115">连接取决于您的[用户角色](permissions.md)：</span><span class="sxs-lookup"><span data-stu-id="89a18-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="89a18-116">管理员可以访问所有连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-116">Administrators have access to all connections.</span></span> <span data-ttu-id="89a18-117">他们还可以在设置导出时创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="89a18-118">参与者可以访问特定连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="89a18-119">他们依靠管理员来配置和共享连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="89a18-120">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="89a18-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="89a18-121">查看者只能查看现有导出，但无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="89a18-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="89a18-122">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="89a18-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="89a18-123">选择 **添加导出** 以创建新导出目标。</span><span class="sxs-lookup"><span data-stu-id="89a18-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="89a18-124">在 **设置导出** 窗格中，选择要使用的连接。</span><span class="sxs-lookup"><span data-stu-id="89a18-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="89a18-125">[连接](connections.md)由管理员管理。</span><span class="sxs-lookup"><span data-stu-id="89a18-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="89a18-126">提供所需的详细信息并选择 **保存** 以创建导出。</span><span class="sxs-lookup"><span data-stu-id="89a18-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="89a18-127">编辑导出</span><span class="sxs-lookup"><span data-stu-id="89a18-127">Edit an export</span></span>

1. <span data-ttu-id="89a18-128">选择要编辑的导出目标的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="89a18-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="89a18-129">从下拉菜单中选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="89a18-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="89a18-130">更改要更新的值，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="89a18-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="89a18-131">查看导出和导出详细信息</span><span class="sxs-lookup"><span data-stu-id="89a18-131">View Exports and export details</span></span>

<span data-ttu-id="89a18-132">创建导出目标后，它们会列在 **数据** > **导出** 中。</span><span class="sxs-lookup"><span data-stu-id="89a18-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="89a18-133">所有用户都可以看到共享的数据及其最新状态。</span><span class="sxs-lookup"><span data-stu-id="89a18-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="89a18-134">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="89a18-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="89a18-135">无编辑权限的用户应选择 **查看** 而不是 **编辑**，以查看导出详细信息。</span><span class="sxs-lookup"><span data-stu-id="89a18-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="89a18-136">此侧窗格显示此导出的设置。</span><span class="sxs-lookup"><span data-stu-id="89a18-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="89a18-137">如果没有编辑权限，您无法更改值。</span><span class="sxs-lookup"><span data-stu-id="89a18-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="89a18-138">选择 **关闭** 以返回到出口页面。</span><span class="sxs-lookup"><span data-stu-id="89a18-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="89a18-139">按需运行导出</span><span class="sxs-lookup"><span data-stu-id="89a18-139">Run exports on demand</span></span>

<span data-ttu-id="89a18-140">配置导出后，只要具有工作连接，每次进行[计划的刷新](system.md#schedule-tab)时都将运行导出。</span><span class="sxs-lookup"><span data-stu-id="89a18-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="89a18-141">要在不等待计划刷新的情况下导出数据，请转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="89a18-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="89a18-142">您有两种选择：</span><span class="sxs-lookup"><span data-stu-id="89a18-142">You have two options:</span></span>

- <span data-ttu-id="89a18-143">要运行所有导出，请在命令栏中选择 **全部运行**。</span><span class="sxs-lookup"><span data-stu-id="89a18-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="89a18-144">要运行单个导出，请选择列表项上的椭圆 (...)，然后选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="89a18-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="89a18-145">删除导出</span><span class="sxs-lookup"><span data-stu-id="89a18-145">Remove an Export</span></span>

1. <span data-ttu-id="89a18-146">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="89a18-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="89a18-147">选择要删除的导出的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="89a18-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="89a18-148">此下拉菜单中选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="89a18-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="89a18-149">选择确认屏幕中的 **删除** 确认删除。</span><span class="sxs-lookup"><span data-stu-id="89a18-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
