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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085519"
---
# <a name="data-sources-overview"></a><span data-ttu-id="9c267-103">数据源概述</span><span class="sxs-lookup"><span data-stu-id="9c267-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9c267-104">Dynamics 365 Customer Insights 中的访问群体见解功能可连接到各种来源的数据。</span><span class="sxs-lookup"><span data-stu-id="9c267-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="9c267-105">连接到数据源通常称为 *数据引入* 过程。</span><span class="sxs-lookup"><span data-stu-id="9c267-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="9c267-106">引入数据后，您可以[统一](data-unification.md)数据并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="9c267-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="9c267-107">添加数据源</span><span class="sxs-lookup"><span data-stu-id="9c267-107">Add a data source</span></span>

<span data-ttu-id="9c267-108">请参阅有关如何添加数据源的详细文章，如何添加具体取决于您选择的选项。</span><span class="sxs-lookup"><span data-stu-id="9c267-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="9c267-109">您可以通过以下三种主要方式添加数据源：</span><span class="sxs-lookup"><span data-stu-id="9c267-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="9c267-110">通过许多 Power Query 连接器</span><span class="sxs-lookup"><span data-stu-id="9c267-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="9c267-111">从 Common Data Model 文件夹</span><span class="sxs-lookup"><span data-stu-id="9c267-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="9c267-112">从您自己的 Common Data Service 湖</span><span class="sxs-lookup"><span data-stu-id="9c267-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="9c267-113">添加来自本地数据源的数据</span><span class="sxs-lookup"><span data-stu-id="9c267-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="9c267-114">根据 Power Platform 数据流支持从受众见解内的本地数据源中引入数据。</span><span class="sxs-lookup"><span data-stu-id="9c267-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="9c267-115">通过在设置环境时[提供 Microsoft Dataverse 环境 URL](manage-environments.md#create-an-environment-in-an-existing-organization)，可以在 Customer Insights 中启用数据流。</span><span class="sxs-lookup"><span data-stu-id="9c267-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="9c267-116">将 Dataverse 环境与 Customer Insights 关联后创建的数据源将默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。</span><span class="sxs-lookup"><span data-stu-id="9c267-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="9c267-117">数据流使用数据网关支持本地连接。</span><span class="sxs-lookup"><span data-stu-id="9c267-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="9c267-118">删除并重新创建关联 Dataverse 环境以[使用本地数据网关](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md)之前已存在的数据源。</span><span class="sxs-lookup"><span data-stu-id="9c267-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="9c267-119">现有 Power BI 或 Power Apps 环境中的数据网关将可见，您可以在 Customer Insights 中重复使用它们。</span><span class="sxs-lookup"><span data-stu-id="9c267-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="9c267-120">数据源页面显示了用于转到可以在其中查看和配置本地数据网关的 Power Platform 环境的链接。</span><span class="sxs-lookup"><span data-stu-id="9c267-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="9c267-121">查看引入的数据</span><span class="sxs-lookup"><span data-stu-id="9c267-121">Review ingested data</span></span>

<span data-ttu-id="9c267-122">您将看到每个引入的数据源的名称、它的状态以及上次为该源刷新数据的时间。</span><span class="sxs-lookup"><span data-stu-id="9c267-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="9c267-123">您可以按每一列对数据源列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="9c267-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9c267-124">![已添加数据源](media/configure-data-datasource-added.png "已添加数据源")</span><span class="sxs-lookup"><span data-stu-id="9c267-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="9c267-125">状态 </span><span class="sxs-lookup"><span data-stu-id="9c267-125">Status</span></span>  |<span data-ttu-id="9c267-126">描述</span><span class="sxs-lookup"><span data-stu-id="9c267-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9c267-127">成功</span><span class="sxs-lookup"><span data-stu-id="9c267-127">Successful</span></span>   |<span data-ttu-id="9c267-128">如果 **已刷新** 列中显示时间，则数据源已成功引入。</span><span class="sxs-lookup"><span data-stu-id="9c267-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="9c267-129">未开始</span><span class="sxs-lookup"><span data-stu-id="9c267-129">Not started</span></span>   |<span data-ttu-id="9c267-130">数据源尚未引入数据，或仍处于草稿模式。</span><span class="sxs-lookup"><span data-stu-id="9c267-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="9c267-131">正在刷新</span><span class="sxs-lookup"><span data-stu-id="9c267-131">Refreshing</span></span>    |<span data-ttu-id="9c267-132">正在引入数据。</span><span class="sxs-lookup"><span data-stu-id="9c267-132">Data ingestion is in progress.</span></span> <span data-ttu-id="9c267-133">可以通过选择 **操作** 列中的 **停止刷新** 来取消此操作。</span><span class="sxs-lookup"><span data-stu-id="9c267-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="9c267-134">停止刷新数据源将把数据源恢复为上次的刷新状态。</span><span class="sxs-lookup"><span data-stu-id="9c267-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="9c267-135">已失败</span><span class="sxs-lookup"><span data-stu-id="9c267-135">Failed</span></span>     |<span data-ttu-id="9c267-136">数据引入出错。</span><span class="sxs-lookup"><span data-stu-id="9c267-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="9c267-137">在任意数据源的 **状态** 列中选择值以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c267-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="9c267-138">在 **进度详细信息** 窗格中，展开 **数据源**。</span><span class="sxs-lookup"><span data-stu-id="9c267-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="9c267-139">选择 **查看详细信息** 以查看有关刷新状态的详细信息，包括错误详细信息和下游流程更新。</span><span class="sxs-lookup"><span data-stu-id="9c267-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="9c267-140">加载数据可能需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="9c267-140">Loading data can take some time.</span></span> <span data-ttu-id="9c267-141">成功刷新后，可以从 **实体** 页查看引入的数据。</span><span class="sxs-lookup"><span data-stu-id="9c267-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="9c267-142">有关详细信息，请参阅[实体](entities.md)。</span><span class="sxs-lookup"><span data-stu-id="9c267-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="9c267-143">刷新数据源</span><span class="sxs-lookup"><span data-stu-id="9c267-143">Refresh a data source</span></span>

<span data-ttu-id="9c267-144">数据源可以按计划自动刷新，也可以根据需要手动刷新。</span><span class="sxs-lookup"><span data-stu-id="9c267-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="9c267-145">转到 **管理员** > **系统** > [**计划**](system.md#schedule-tab)以配置所有引入数据源的计划刷新。</span><span class="sxs-lookup"><span data-stu-id="9c267-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="9c267-146">若要根据需要刷新数据源，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9c267-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="9c267-147">在访问群体见解中，转到 **数据** > **数据源**</span><span class="sxs-lookup"><span data-stu-id="9c267-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="9c267-148">选择要刷新的数据源旁边的垂直省略号，然后从下拉列表中选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="9c267-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="9c267-149">现在，将为数据源触发手动刷新。</span><span class="sxs-lookup"><span data-stu-id="9c267-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="9c267-150">刷新数据源将更新数据源中指定的所有实体的实体架构和数据。</span><span class="sxs-lookup"><span data-stu-id="9c267-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="9c267-151">如果要取消现有刷新，请选择 **停止刷新**，数据源将还原到上次刷新状态。</span><span class="sxs-lookup"><span data-stu-id="9c267-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="9c267-152">删除数据源</span><span class="sxs-lookup"><span data-stu-id="9c267-152">Delete a data source</span></span>

1. <span data-ttu-id="9c267-153">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="9c267-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9c267-154">选择要删除的数据源旁边的垂直省略号，然后选择下拉菜单中的 **删除**。</span><span class="sxs-lookup"><span data-stu-id="9c267-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="9c267-155">确认删除。</span><span class="sxs-lookup"><span data-stu-id="9c267-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
