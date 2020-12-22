---
title: 使用数据源引入数据
description: 了解如何从各个数据源导入数据。
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643942"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="5a06c-103">数据源概述</span><span class="sxs-lookup"><span data-stu-id="5a06c-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5a06c-104">Dynamics 365 Customer Insights 中的访问群体见解功能可连接到各种来源的数据。</span><span class="sxs-lookup"><span data-stu-id="5a06c-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="5a06c-105">连接到数据源通常称为 *数据引入* 过程。</span><span class="sxs-lookup"><span data-stu-id="5a06c-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="5a06c-106">引入数据后，您可以[统一](data-unification.md)数据并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="5a06c-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="5a06c-107">添加数据源</span><span class="sxs-lookup"><span data-stu-id="5a06c-107">Add a data source</span></span>

<span data-ttu-id="5a06c-108">请参阅有关如何添加数据源的详细文章，如何添加具体取决于您选择的选项。</span><span class="sxs-lookup"><span data-stu-id="5a06c-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="5a06c-109">您可以通过以下三种主要方式添加数据源：</span><span class="sxs-lookup"><span data-stu-id="5a06c-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="5a06c-110">通过许多 Power Query 连接器</span><span class="sxs-lookup"><span data-stu-id="5a06c-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="5a06c-111">从 Common Data Model 文件夹</span><span class="sxs-lookup"><span data-stu-id="5a06c-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="5a06c-112">从您自己的 Common Data Service 湖</span><span class="sxs-lookup"><span data-stu-id="5a06c-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="5a06c-113">您还不能从本地数据源添加数据。</span><span class="sxs-lookup"><span data-stu-id="5a06c-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="5a06c-114">查看引入的数据</span><span class="sxs-lookup"><span data-stu-id="5a06c-114">Review ingested data</span></span>

<span data-ttu-id="5a06c-115">您将看到每个引入的数据源的名称、它的状态以及上次为该源刷新数据的时间。</span><span class="sxs-lookup"><span data-stu-id="5a06c-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="5a06c-116">您可以按每一列对数据源列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="5a06c-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a06c-117">![已添加数据源](media/configure-data-datasource-added.png "已添加数据源")</span><span class="sxs-lookup"><span data-stu-id="5a06c-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="5a06c-118">状态 </span><span class="sxs-lookup"><span data-stu-id="5a06c-118">Status</span></span>  |<span data-ttu-id="5a06c-119">描述</span><span class="sxs-lookup"><span data-stu-id="5a06c-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5a06c-120">成功</span><span class="sxs-lookup"><span data-stu-id="5a06c-120">Successful</span></span>   |<span data-ttu-id="5a06c-121">如果 **已刷新** 列中显示时间，则数据源已成功引入。</span><span class="sxs-lookup"><span data-stu-id="5a06c-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="5a06c-122">未开始</span><span class="sxs-lookup"><span data-stu-id="5a06c-122">Not started</span></span>   |<span data-ttu-id="5a06c-123">数据源尚未引入数据，或仍处于草稿模式。</span><span class="sxs-lookup"><span data-stu-id="5a06c-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="5a06c-124">正在刷新</span><span class="sxs-lookup"><span data-stu-id="5a06c-124">Refreshing</span></span>    |<span data-ttu-id="5a06c-125">正在引入数据。</span><span class="sxs-lookup"><span data-stu-id="5a06c-125">Data ingestion is in progress.</span></span> <span data-ttu-id="5a06c-126">可以通过选择 **操作** 列中的 **停止刷新** 来取消此操作。</span><span class="sxs-lookup"><span data-stu-id="5a06c-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="5a06c-127">停止刷新数据源将把数据源恢复为上次的刷新状态。</span><span class="sxs-lookup"><span data-stu-id="5a06c-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="5a06c-128">已失败</span><span class="sxs-lookup"><span data-stu-id="5a06c-128">Failed</span></span>     |<span data-ttu-id="5a06c-129">数据引入出错。</span><span class="sxs-lookup"><span data-stu-id="5a06c-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="5a06c-130">选择 **刷新状态** 以查看有关刷新状态的更多详细信息，包括错误详细信息和下游流程更新。</span><span class="sxs-lookup"><span data-stu-id="5a06c-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="5a06c-131">加载数据可能需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="5a06c-131">Loading data can take some time.</span></span> <span data-ttu-id="5a06c-132">成功刷新后，可以从 **实体** 页查看引入的数据。</span><span class="sxs-lookup"><span data-stu-id="5a06c-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="5a06c-133">有关详细信息，请参阅[实体](entities.md)。</span><span class="sxs-lookup"><span data-stu-id="5a06c-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="5a06c-134">刷新数据源</span><span class="sxs-lookup"><span data-stu-id="5a06c-134">Refresh a data source</span></span>

<span data-ttu-id="5a06c-135">数据源可以按计划自动刷新，也可以根据需要手动刷新。</span><span class="sxs-lookup"><span data-stu-id="5a06c-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="5a06c-136">转到 **管理员** > **系统** > [**计划**](system.md#schedule-tab)以配置所有引入数据源的计划刷新。</span><span class="sxs-lookup"><span data-stu-id="5a06c-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="5a06c-137">若要根据需要刷新数据源，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a06c-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="5a06c-138">在访问群体见解中，转到 **数据** > **数据源**</span><span class="sxs-lookup"><span data-stu-id="5a06c-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="5a06c-139">选择要刷新的数据源旁边的垂直省略号，然后从下拉列表中选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="5a06c-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="5a06c-140">现在，将为数据源触发手动刷新。</span><span class="sxs-lookup"><span data-stu-id="5a06c-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="5a06c-141">刷新数据源将更新在数据源中指定的所有实体的实体架构以及数据。</span><span class="sxs-lookup"><span data-stu-id="5a06c-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="5a06c-142">如果要取消现有刷新，请选择 **停止刷新**，数据源将还原到上次刷新状态。</span><span class="sxs-lookup"><span data-stu-id="5a06c-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="5a06c-143">删除数据源</span><span class="sxs-lookup"><span data-stu-id="5a06c-143">Delete a data source</span></span>

1. <span data-ttu-id="5a06c-144">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="5a06c-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="5a06c-145">选择要删除的数据源旁边的垂直省略号，然后选择下拉菜单中的 **删除**。</span><span class="sxs-lookup"><span data-stu-id="5a06c-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="5a06c-146">确认删除。</span><span class="sxs-lookup"><span data-stu-id="5a06c-146">Confirm your deletion.</span></span>
