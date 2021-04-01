---
title: Power Apps 连接器
description: 与 Power Apps 和 Power Automate 连接。
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598144"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="34efe-103">Microsoft Power Apps 连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="34efe-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="34efe-104">使用 Power Apps 将统一客户配置文件导入到个性化的应用中。</span><span class="sxs-lookup"><span data-stu-id="34efe-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="34efe-105">连接 Power Apps 和 Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="34efe-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="34efe-106">Customer Insights 是 [Power Apps 中众多数据源](/powerapps/maker/canvas-apps/working-with-data-sources)之一。</span><span class="sxs-lookup"><span data-stu-id="34efe-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="34efe-107">请参阅 Power Apps 文档了解如何[向应用添加数据连接](/powerapps/maker/canvas-apps/add-data-connection)。</span><span class="sxs-lookup"><span data-stu-id="34efe-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="34efe-108">我们建议您另外回顾一下 [Power Apps 如何使用代理来处理画布应用中的大型数据集](/powerapps/maker/canvas-apps/delegation-overview)。</span><span class="sxs-lookup"><span data-stu-id="34efe-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="34efe-109">可用实体</span><span class="sxs-lookup"><span data-stu-id="34efe-109">Available entities</span></span>

<span data-ttu-id="34efe-110">将 Customer Insights 作为数据连接添加之后，可以在 Power Apps 中选择以下实体：</span><span class="sxs-lookup"><span data-stu-id="34efe-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="34efe-111">客户：如果要使用[统一客户配置文件](customer-profiles.md)中的数据。</span><span class="sxs-lookup"><span data-stu-id="34efe-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="34efe-112">UnifiedActivity：在应用中显示[活动时间线](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="34efe-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="34efe-113">限制</span><span class="sxs-lookup"><span data-stu-id="34efe-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="34efe-114">可检索实体</span><span class="sxs-lookup"><span data-stu-id="34efe-114">Retrievable entities</span></span>

<span data-ttu-id="34efe-115">您只能通过 Power Apps 连接器检索 **客户**、**统一活动** 和 **客户细分** 实体。</span><span class="sxs-lookup"><span data-stu-id="34efe-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="34efe-116">之所以显示其他实体，是因为基础连接器通过 Power Automate 中的触发器支持它们。</span><span class="sxs-lookup"><span data-stu-id="34efe-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="34efe-117">代理</span><span class="sxs-lookup"><span data-stu-id="34efe-117">Delegation</span></span>

<span data-ttu-id="34efe-118">委派适用于“客户”实体和“统一活动”实体。</span><span class="sxs-lookup"><span data-stu-id="34efe-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="34efe-119">**客户** 实体的委派：若要针对此实体使用委派，需要在[搜索和筛选索引](search-filter-index.md)中对字段编制索引。</span><span class="sxs-lookup"><span data-stu-id="34efe-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="34efe-120">**统一活动** 实体的委派：此实体的委派仅适用于字段 **ActivityId** 和 **CustomerId**。</span><span class="sxs-lookup"><span data-stu-id="34efe-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="34efe-121">有关委派的详细信息，请参阅 [Power Apps 可委派函数和操作](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)。</span><span class="sxs-lookup"><span data-stu-id="34efe-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="34efe-122">示例库控件</span><span class="sxs-lookup"><span data-stu-id="34efe-122">Example gallery control</span></span>

<span data-ttu-id="34efe-123">例如，您可以将客户配置文件添加到[库控件](/powerapps/maker/canvas-apps/add-gallery)。</span><span class="sxs-lookup"><span data-stu-id="34efe-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="34efe-124">请向正在构建的应用添加一个 **库** 控件。</span><span class="sxs-lookup"><span data-stu-id="34efe-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="34efe-125">![添加库元素](media/connector-powerapps9.png "添加库元素")</span><span class="sxs-lookup"><span data-stu-id="34efe-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="34efe-126">选择 **客户** 充当项的数据源。</span><span class="sxs-lookup"><span data-stu-id="34efe-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="34efe-127">![选择数据源](media/choose-datasource-powerapps.png "选择数据源")</span><span class="sxs-lookup"><span data-stu-id="34efe-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="34efe-128">可以更改右侧的数据面板以选择在库中显示客户实体的哪个字段。</span><span class="sxs-lookup"><span data-stu-id="34efe-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="34efe-129">如果要在库中显示所选客户的任何字段，请填写标签的“文本”属性：**{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="34efe-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="34efe-130">示例：Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="34efe-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="34efe-131">若要显示客户的统一时间线，请添加一个库元素，然后添加项属性：**Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="34efe-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="34efe-132">示例：Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="34efe-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]