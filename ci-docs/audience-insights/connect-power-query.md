---
title: 通过 Power Query 连接器引入数据
description: 基于 Power Query 的数据源的连接器。
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305880"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="8bd5c-103">连接到 Power Query 数据源</span><span class="sxs-lookup"><span data-stu-id="8bd5c-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="8bd5c-104">Power Query 提供大量用于插入数据的连接器。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="8bd5c-105">其中大多数连接器都受 Dynamics 365 Customer Insights 支持。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="8bd5c-106">添加基于 Power Query 连接器的数据源通常要执行下一节中概述的步骤。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="8bd5c-107">但是，根据您使用的连接器，需要不同的信息。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="8bd5c-108">有关详细信息，请参阅 [Power Query 连接器参考](/power-query/connectors/)中各个连接器的相关文档。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="8bd5c-109">创建新的数据源</span><span class="sxs-lookup"><span data-stu-id="8bd5c-109">Create a new data source</span></span>

1. <span data-ttu-id="8bd5c-110">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="8bd5c-111">选择 **添加数据源**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="8bd5c-112">选择 **导入数据** 方法，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="8bd5c-113">为数据源提供 **名称**，然后选择 **下一步** 创建数据源。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="8bd5c-114">名称准则：</span><span class="sxs-lookup"><span data-stu-id="8bd5c-114">Name guidelines:</span></span> 
   - <span data-ttu-id="8bd5c-115">以字母开头。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-115">Start with a letter.</span></span>
   - <span data-ttu-id="8bd5c-116">只能使用字母和数字。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-116">Use letters and numbers only.</span></span> <span data-ttu-id="8bd5c-117">不允许使用特殊字符和空格。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="8bd5c-118">使用 3 至 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="8bd5c-119">选择一个[可用连接器](#available-power-query-data-sources),</span><span class="sxs-lookup"><span data-stu-id="8bd5c-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="8bd5c-120">在本例中，我们选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8bd5c-121">在所选连接器的 **连接设置** 中输入所需详细信息，然后选择 **下一步** 查看数据预览。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="8bd5c-122">选择 **转换数据**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-122">Select **Transform data**.</span></span> <span data-ttu-id="8bd5c-123">在此步骤中，将向数据源添加实体。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="8bd5c-124">实体是数据集。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-124">Entities are datasets.</span></span> <span data-ttu-id="8bd5c-125">如果有其中包含多个数据集的数据库，则每个数据集有自己的实体。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="8bd5c-126">利用 **Power Query - 编辑查询** 对话框，您可以查看和优化数据。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="8bd5c-127">系统在您的所选数据源中识别出的实体在左侧窗格中显示。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8bd5c-128">![编辑查询对话框](media/data-manager-configure-edit-queries.png "编辑查询对话框")</span><span class="sxs-lookup"><span data-stu-id="8bd5c-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="8bd5c-129">还可以转换数据。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-129">You can also transform your data.</span></span> <span data-ttu-id="8bd5c-130">选择要编辑或转换的实体。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="8bd5c-131">使用 Power Query 窗口中的选项应用转换。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="8bd5c-132">每个转换在 **应用的步骤** 下列出。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="8bd5c-133">Power Query 提供了很多预建的转换选项。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="8bd5c-134">有关详细信息，请参阅 [Power Query 转换](/power-query/power-query-what-is-power-query#transformations)。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="8bd5c-135">可以通过选择 **编辑查询** 对话框中的 **获取数据** 向数据源添加更多实体。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="8bd5c-136">强烈建议进行以下转换：</span><span class="sxs-lookup"><span data-stu-id="8bd5c-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="8bd5c-137">如果您从 CSV 文件引入数据，第一行通常包含标题。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="8bd5c-138">转到 **转换表**，选择 **使用标题作为第一行**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="8bd5c-139">确保正确设置了数据类型。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="8bd5c-140">选择 Power Query 窗口底部的 **保存** 保存转换。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="8bd5c-141">保存后，您将在 **数据** > **数据源** 中找到您的数据源。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="8bd5c-142">在 **数据源** 页上，您会注意到新数据源处于 **正在刷新** 状态。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="8bd5c-143">可用 Power Query 数据源</span><span class="sxs-lookup"><span data-stu-id="8bd5c-143">Available Power Query data sources</span></span>

<span data-ttu-id="8bd5c-144">请参阅 [Power Query 连接器参考](/power-query/connectors/)，获取您可以选择用来将数据导入 Customer Insights 的连接器的最新列表。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="8bd5c-145">**Customer Insights (数据流)** 列中带有复选标记的连接器可用于创建新的基于 Power Query 的数据源。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="8bd5c-146">查看特定连接器的文档，了解有关其先决条件、限制和其他详细信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="8bd5c-147">编辑 Power Query 数据源</span><span class="sxs-lookup"><span data-stu-id="8bd5c-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="8bd5c-148">可能不能对其中一个应用的进程（如 *细分*、*匹配* 或 *合并*）正在使用的数据源进行更改。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="8bd5c-149">可以使用 **设置** 页跟踪每个活动进程的进度。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="8bd5c-150">进程完成后，可以回到 **数据源** 页进行更改。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="8bd5c-151">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8bd5c-152">选择您要更改的数据源旁边的垂直省略号，然后从下拉菜单中选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8bd5c-153">![编辑选项](media/edit-option-data-sources.png "编辑选项")</span><span class="sxs-lookup"><span data-stu-id="8bd5c-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="8bd5c-154">按照 [创建新数据源](#create-a-new-data-source)一节中所述，在 **Power Query - 编辑查询** 对话框中应用更改和转换。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="8bd5c-155">完成编辑后，在 Power Query 中选择 **保存** 保存所作的更改。</span><span class="sxs-lookup"><span data-stu-id="8bd5c-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]