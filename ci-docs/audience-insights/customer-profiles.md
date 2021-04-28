---
title: 查看客户配置文件
description: 获取统一客户数据的组合视图。
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896316"
---
# <a name="customer-profiles"></a><span data-ttu-id="6c936-103">客户配置文件</span><span class="sxs-lookup"><span data-stu-id="6c936-103">Customer profiles</span></span>

<span data-ttu-id="6c936-104">**客户** 页面显示客户的组合视图，基于从[所有数据源](data-sources.md)收集的配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="6c936-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="6c936-105">[创建统一的客户实体](data-unification.md)之后，客户配置文件可用。</span><span class="sxs-lookup"><span data-stu-id="6c936-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="6c936-106">确保完成数据统一过程以获得更丰富的客户视图。</span><span class="sxs-lookup"><span data-stu-id="6c936-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="6c936-107">还可以通过此页面搜索客户。</span><span class="sxs-lookup"><span data-stu-id="6c936-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="6c936-108">客户可以是个人，也可以是组织（预览）。</span><span class="sxs-lookup"><span data-stu-id="6c936-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="6c936-109">每个客户或组织配置文件通过磁贴表示。</span><span class="sxs-lookup"><span data-stu-id="6c936-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="6c936-110">选择磁贴可查看有关这个具体客户或组织的更多信息。</span><span class="sxs-lookup"><span data-stu-id="6c936-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="6c936-111">可使用页面底部的翻页控件查看更多记录。</span><span class="sxs-lookup"><span data-stu-id="6c936-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="6c936-112">![B2C 客户配置文件](media/profiles-customers.png "B2C 客户配置文件")</span><span class="sxs-lookup"><span data-stu-id="6c936-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="6c936-113">组织（预览）</span><span class="sxs-lookup"><span data-stu-id="6c936-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="6c936-114">![B2B 客户配置文件](media/profile-customers-b2b.png "B2B 客户配置文件")</span><span class="sxs-lookup"><span data-stu-id="6c936-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="6c936-115">如果在导航中选择 **客户** 后看不到磁贴，您的管理员需要在 **搜索和筛选索引** 中[定义至少一个可搜索属性](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="6c936-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="6c936-116">搜索客户</span><span class="sxs-lookup"><span data-stu-id="6c936-116">Search for customers</span></span>

<span data-ttu-id="6c936-117">通过在搜索框中输入名称或其他某个属性搜索客户。</span><span class="sxs-lookup"><span data-stu-id="6c936-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="6c936-118">只有在数据统一过程中创建的客户配置文件实体内才支持搜索。</span><span class="sxs-lookup"><span data-stu-id="6c936-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="6c936-119">作为管理员，您可以使用 **搜索和筛选索引** 页配置可搜索属性。</span><span class="sxs-lookup"><span data-stu-id="6c936-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="6c936-120">有关详细信息，请参阅[管理搜索和筛选索引](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="6c936-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="6c936-121">筛选客户</span><span class="sxs-lookup"><span data-stu-id="6c936-121">Filter customers</span></span>

<span data-ttu-id="6c936-122">可以按客户配置文件实体字段搜索客户。</span><span class="sxs-lookup"><span data-stu-id="6c936-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="6c936-123">与搜索类似，您的管理员首先需要使用 **搜索和筛选索引** 将字段定义为可搜索。</span><span class="sxs-lookup"><span data-stu-id="6c936-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="6c936-124">在 **客户** 页面上选择 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="6c936-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="6c936-125">选中要充当客户搜索依据的属性旁边的框。</span><span class="sxs-lookup"><span data-stu-id="6c936-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="6c936-126">![客户配置文件](media/profiles-customers3.png "客户配置文件")</span><span class="sxs-lookup"><span data-stu-id="6c936-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="6c936-127">通过在 **客户** 页面上选择 **清除筛选器** 来删除您的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6c936-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="6c936-128">客户详细信息页面</span><span class="sxs-lookup"><span data-stu-id="6c936-128">Customer details page</span></span>

<span data-ttu-id="6c936-129">选择任何客户磁贴以打开 **客户详细信息页面**。</span><span class="sxs-lookup"><span data-stu-id="6c936-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="6c936-130">此视图包含所选客户的统一信息。</span><span class="sxs-lookup"><span data-stu-id="6c936-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="6c936-131">客户详细信息包括:</span><span class="sxs-lookup"><span data-stu-id="6c936-131">Customer details include:</span></span>

-   <span data-ttu-id="6c936-132">**客户配置文件磁贴：** 此磁贴显示统一客户配置文件实体中的不同值。</span><span class="sxs-lookup"><span data-stu-id="6c936-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="6c936-133">这些详细信息可以包括电子邮件地址、姓名、市/县等等。</span><span class="sxs-lookup"><span data-stu-id="6c936-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="6c936-134">**潜在兴趣、潜在品牌：** 显示您是否配置了第一方扩充。</span><span class="sxs-lookup"><span data-stu-id="6c936-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="6c936-135">它表示具有与此客户类似的配置文件的客户可能具有的潜在兴趣和品牌相似性。</span><span class="sxs-lookup"><span data-stu-id="6c936-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="6c936-136">有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="6c936-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="6c936-137">**度量：** 显示您是否配置了一个或多个特定类型的度量：客户属性度量。</span><span class="sxs-lookup"><span data-stu-id="6c936-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="6c936-138">它们包括针对各个客户级别的客户的计算 KPI。</span><span class="sxs-lookup"><span data-stu-id="6c936-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="6c936-139">有关详细信息，请参阅[定义和管理度量](measures.md)。</span><span class="sxs-lookup"><span data-stu-id="6c936-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="6c936-140">**活动时间线：** 显示您是否已配置活动。</span><span class="sxs-lookup"><span data-stu-id="6c936-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="6c936-141">时间线视图包含此客户的按时间排序的活动，从最近活动开始。</span><span class="sxs-lookup"><span data-stu-id="6c936-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="6c936-142">有关详细信息，请参阅[自定义活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="6c936-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="6c936-143">选择 **返回到客户** 以返回到客户搜索页面。</span><span class="sxs-lookup"><span data-stu-id="6c936-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c936-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6c936-144">Next steps</span></span>

<span data-ttu-id="6c936-145">[添加更多数据源](data-sources.md)或[创建客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="6c936-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]