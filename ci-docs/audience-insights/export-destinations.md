---
title: 导出的目标
description: 导出数据和管理导出目标。
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643852"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="56f56-103">导出的目标(预览)</span><span class="sxs-lookup"><span data-stu-id="56f56-103">Export destinations (preview)</span></span>

<span data-ttu-id="56f56-104">**导出目标** 页显示您已设置的要将数据导出到的所有位置。</span><span class="sxs-lookup"><span data-stu-id="56f56-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="56f56-105">您还可以为导出添加新目标。</span><span class="sxs-lookup"><span data-stu-id="56f56-105">You can also add new destinations for export.</span></span> <span data-ttu-id="56f56-106">此外，它将显示导出当前可用选项。</span><span class="sxs-lookup"><span data-stu-id="56f56-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="56f56-107">获取简要概述、说明，并了解使用每个扩展性选项可以做什么。</span><span class="sxs-lookup"><span data-stu-id="56f56-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="56f56-108">将统一的配置文件、度量和细分导出到与您的业务相关的受支持的应用。</span><span class="sxs-lookup"><span data-stu-id="56f56-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="56f56-109">转到 **管理** > **导出目标** 来查找以下扩展性选项：</span><span class="sxs-lookup"><span data-stu-id="56f56-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="56f56-110">Dynamics 365 客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="56f56-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="56f56-111">Facebook 广告管理器连接器</span><span class="sxs-lookup"><span data-stu-id="56f56-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="56f56-112">Power Automate 连接器</span><span class="sxs-lookup"><span data-stu-id="56f56-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="56f56-113">Power Apps 连接器</span><span class="sxs-lookup"><span data-stu-id="56f56-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="56f56-114">Power BI 连接器</span><span class="sxs-lookup"><span data-stu-id="56f56-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="56f56-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="56f56-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="56f56-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="56f56-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="56f56-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="56f56-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="56f56-118">Azure Blob 存储</span><span class="sxs-lookup"><span data-stu-id="56f56-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="56f56-119">LiveRamp&reg; 连接器</span><span class="sxs-lookup"><span data-stu-id="56f56-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="56f56-120">Microsoft Teams 的机器人</span><span class="sxs-lookup"><span data-stu-id="56f56-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="56f56-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="56f56-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="56f56-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="56f56-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="56f56-123">添加新的导出目标</span><span class="sxs-lookup"><span data-stu-id="56f56-123">Add a new export destination</span></span>

<span data-ttu-id="56f56-124">若要添加导出目标，您需要具有[管理员权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="56f56-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="56f56-125">如果导出到 Microsoft 服务，假设两个服务位于同一个组织中。</span><span class="sxs-lookup"><span data-stu-id="56f56-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="56f56-126">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="56f56-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="56f56-127">切换到 **我的导出目标** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56f56-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="56f56-128">选择 **添加目标** 创建新的导出目标。</span><span class="sxs-lookup"><span data-stu-id="56f56-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="56f56-129">在 **添加目标** 窗格的下拉列表中，选择导出目标的 **类型**。</span><span class="sxs-lookup"><span data-stu-id="56f56-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="56f56-130">提供必需的详细信息，然后选择 **下一步** 创建导出目标。</span><span class="sxs-lookup"><span data-stu-id="56f56-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="56f56-131">也可以在 **发现** 选项卡中的磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="56f56-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="56f56-132">查看导出目标</span><span class="sxs-lookup"><span data-stu-id="56f56-132">View Export destinations</span></span>

<span data-ttu-id="56f56-133">创建导出目标之后，可以在 **我的导出目标** 选项卡上的表中看到这些目标。此表有三列：</span><span class="sxs-lookup"><span data-stu-id="56f56-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="56f56-134">**显示名称**：创建目标时输入的名称。</span><span class="sxs-lookup"><span data-stu-id="56f56-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="56f56-135">**类型**：创建目标时设置的导出目标类型。</span><span class="sxs-lookup"><span data-stu-id="56f56-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="56f56-136">**创建日期**：目标的创建日期。</span><span class="sxs-lookup"><span data-stu-id="56f56-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="56f56-137">编辑导出目标</span><span class="sxs-lookup"><span data-stu-id="56f56-137">Edit an export destination</span></span>

1. <span data-ttu-id="56f56-138">选择要编辑的导出目标的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="56f56-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56f56-139">![竖省略号](media/export-destinations-page-ellipsis.png "竖省略号")</span><span class="sxs-lookup"><span data-stu-id="56f56-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="56f56-140">从下拉菜单中选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="56f56-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="56f56-141">更改需要更新的值，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="56f56-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="56f56-142">根据需要导出数据</span><span class="sxs-lookup"><span data-stu-id="56f56-142">Export data on demand</span></span>

<span data-ttu-id="56f56-143">为导出目标配置连接器之后，将在每次[安排的刷新](system.md#schedule-tab)时运行导出。</span><span class="sxs-lookup"><span data-stu-id="56f56-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="56f56-144">若要导出数据但不等待安排的刷新，请转到 **管理** > **导出目标** 中的 **我的导出目标** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56f56-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="56f56-145">![竖省略号](media/export-destinations-page-ellipsis.png "竖省略号")</span><span class="sxs-lookup"><span data-stu-id="56f56-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="56f56-146">选择列表上方的 **导出** 同时运行到所有导出目标的导出。</span><span class="sxs-lookup"><span data-stu-id="56f56-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="56f56-147">选择列表项后的省略号 (...)，然后选择 **导出** 选项为单个导出目标运行导出。</span><span class="sxs-lookup"><span data-stu-id="56f56-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="56f56-148">删除导出目标</span><span class="sxs-lookup"><span data-stu-id="56f56-148">Remove an Export destination</span></span>

<span data-ttu-id="56f56-149">若要删除导出目标，请从 **导出目标** 主页开始。</span><span class="sxs-lookup"><span data-stu-id="56f56-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="56f56-150">选择要删除的导出目标的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="56f56-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56f56-151">![竖省略号](media/export-destinations-page-ellipsis.png "竖省略号")</span><span class="sxs-lookup"><span data-stu-id="56f56-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="56f56-152">此下拉菜单中选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="56f56-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="56f56-153">选择确认屏幕中的 **删除** 确认删除。</span><span class="sxs-lookup"><span data-stu-id="56f56-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
