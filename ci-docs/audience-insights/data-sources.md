---
title: 使用数据源引入数据
description: 了解如何从各个数据源导入数据。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887883"
---
# <a name="data-sources-overview"></a><span data-ttu-id="ed7d5-103">数据源概述</span><span class="sxs-lookup"><span data-stu-id="ed7d5-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ed7d5-104">Dynamics 365 Customer Insights 中的访问群体见解功能可连接到各种来源的数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="ed7d5-105">连接到数据源通常称为 *数据引入* 过程。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="ed7d5-106">引入数据后，您可以[统一](data-unification.md)数据并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="ed7d5-107">添加数据源</span><span class="sxs-lookup"><span data-stu-id="ed7d5-107">Add a data source</span></span>

<span data-ttu-id="ed7d5-108">请参阅有关如何添加数据源的详细文章，如何添加具体取决于您选择的选项。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="ed7d5-109">您可以通过以下三种主要方式添加数据源：</span><span class="sxs-lookup"><span data-stu-id="ed7d5-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="ed7d5-110">通过许多 Power Query 连接器</span><span class="sxs-lookup"><span data-stu-id="ed7d5-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="ed7d5-111">从 Common Data Model 文件夹</span><span class="sxs-lookup"><span data-stu-id="ed7d5-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="ed7d5-112">从您自己的 Common Data Service 湖</span><span class="sxs-lookup"><span data-stu-id="ed7d5-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="ed7d5-113">添加来自本地数据源的数据</span><span class="sxs-lookup"><span data-stu-id="ed7d5-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="ed7d5-114">根据 Power Platform 数据流支持从受众见解内的本地数据源中引入数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="ed7d5-115">通过在设置环境时[提供 Microsoft Dataverse 环境 URL](manage-environments.md#create-an-environment-in-an-existing-organization)，可以在 Customer Insights 中启用数据流。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="ed7d5-116">将 Dataverse 环境与 Customer Insights 关联后创建的数据源将默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="ed7d5-117">数据流使用数据网关支持本地连接。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="ed7d5-118">删除并重新创建关联 Dataverse 环境以使用本地数据网关之前已存在的数据源。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="ed7d5-119">现有 Power BI 或 Power Apps 环境中的数据网关将可见，您可以在 Customer Insights 中重复使用它们。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="ed7d5-120">数据源页面显示了用于转到可以在其中查看和配置本地数据网关的 Power Platform 环境的链接。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="数据源页面屏幕截图，它显示了指向 Power Platform 环境的链接。":::

## <a name="review-ingested-data"></a><span data-ttu-id="ed7d5-122">查看引入的数据</span><span class="sxs-lookup"><span data-stu-id="ed7d5-122">Review ingested data</span></span>

<span data-ttu-id="ed7d5-123">您将看到每个引入的数据源的名称、它的状态以及上次为该源刷新数据的时间。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="ed7d5-124">您可以按每一列对数据源列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed7d5-125">![已添加数据源](media/configure-data-datasource-added.png "已添加数据源")</span><span class="sxs-lookup"><span data-stu-id="ed7d5-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="ed7d5-126">状态 </span><span class="sxs-lookup"><span data-stu-id="ed7d5-126">Status</span></span>  |<span data-ttu-id="ed7d5-127">描述</span><span class="sxs-lookup"><span data-stu-id="ed7d5-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ed7d5-128">成功</span><span class="sxs-lookup"><span data-stu-id="ed7d5-128">Successful</span></span>   |<span data-ttu-id="ed7d5-129">如果 **已刷新** 列中显示时间，则数据源已成功引入。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="ed7d5-130">未开始</span><span class="sxs-lookup"><span data-stu-id="ed7d5-130">Not started</span></span>   |<span data-ttu-id="ed7d5-131">数据源尚未引入数据，或仍处于草稿模式。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="ed7d5-132">正在刷新</span><span class="sxs-lookup"><span data-stu-id="ed7d5-132">Refreshing</span></span>    |<span data-ttu-id="ed7d5-133">正在引入数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-133">Data ingestion is in progress.</span></span> <span data-ttu-id="ed7d5-134">可以通过选择 **操作** 列中的 **停止刷新** 来取消此操作。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="ed7d5-135">停止刷新数据源将把数据源恢复为上次的刷新状态。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="ed7d5-136">已失败</span><span class="sxs-lookup"><span data-stu-id="ed7d5-136">Failed</span></span>     |<span data-ttu-id="ed7d5-137">数据引入出错。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="ed7d5-138">在任意数据源的 **状态** 列中选择值以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="ed7d5-139">在 **进度详细信息** 窗格中，展开 **数据源**。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="ed7d5-140">选择 **查看详细信息** 以查看有关刷新状态的详细信息，包括错误详细信息和下游流程更新。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="ed7d5-141">加载数据可能需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-141">Loading data can take some time.</span></span> <span data-ttu-id="ed7d5-142">成功刷新后，可以从 **实体** 页查看引入的数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="ed7d5-143">有关详细信息，请参阅[实体](entities.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="ed7d5-144">刷新数据源</span><span class="sxs-lookup"><span data-stu-id="ed7d5-144">Refresh a data source</span></span>

<span data-ttu-id="ed7d5-145">数据源可以按计划自动刷新，也可以根据需要手动刷新。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="ed7d5-146">转到 **管理员** > **系统** > [**计划**](system.md#schedule-tab)以配置所有引入数据源的计划刷新。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="ed7d5-147">若要根据需要刷新数据源，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ed7d5-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="ed7d5-148">在访问群体见解中，转到 **数据** > **数据源**</span><span class="sxs-lookup"><span data-stu-id="ed7d5-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="ed7d5-149">选择要刷新的数据源旁边的垂直省略号，然后从下拉列表中选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="ed7d5-150">现在，将为数据源触发手动刷新。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="ed7d5-151">刷新数据源将更新数据源中指定的所有实体的实体架构和数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="ed7d5-152">如果要取消现有刷新，请选择 **停止刷新**，数据源将还原到上次刷新状态。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="ed7d5-153">删除数据源</span><span class="sxs-lookup"><span data-stu-id="ed7d5-153">Delete a data source</span></span>

1. <span data-ttu-id="ed7d5-154">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ed7d5-155">选择要删除的数据源旁边的垂直省略号，然后选择下拉菜单中的 **删除**。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="ed7d5-156">确认删除。</span><span class="sxs-lookup"><span data-stu-id="ed7d5-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
