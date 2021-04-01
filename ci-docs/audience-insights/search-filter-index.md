---
title: 搜索和筛选客户配置文件
description: 快速查找有关统一的客户配置文件的信息和筛选出指定的属性。
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597132"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="f5bed-103">客户配置文件：搜索和筛选索引</span><span class="sxs-lookup"><span data-stu-id="f5bed-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="f5bed-104">统一客户数据的结果是一个客户配置文件实体，用于提供对总客户群的统一认识。</span><span class="sxs-lookup"><span data-stu-id="f5bed-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="f5bed-105">若要快速 [查找有关特定客户或客户群的信息](customer-profiles.md)，可以在 **客户** 页中配置 **搜索** 和 **筛选** 功能。</span><span class="sxs-lookup"><span data-stu-id="f5bed-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="f5bed-106">继续阅读以了解管理员可以如何编辑 **搜索和筛选索引** 页中的属性，用户可使用这些属性进行搜索和筛选。</span><span class="sxs-lookup"><span data-stu-id="f5bed-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f5bed-107">![搜索筛选器](media/search-filter.png "搜索筛选器")</span><span class="sxs-lookup"><span data-stu-id="f5bed-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="f5bed-108">添加字段和指定属性</span><span class="sxs-lookup"><span data-stu-id="f5bed-108">Add fields and specify attributes</span></span>

<span data-ttu-id="f5bed-109">如果这是您首次以管理员身份定义可搜索属性，您需要首先定义索引字段。</span><span class="sxs-lookup"><span data-stu-id="f5bed-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="f5bed-110">建议您选择用户在 **客户** 页中可用于搜索和筛选客户的所有属性。</span><span class="sxs-lookup"><span data-stu-id="f5bed-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="f5bed-111">只能指定您在数据统一过程中创建的客户配置文件实体内的已有属性。</span><span class="sxs-lookup"><span data-stu-id="f5bed-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="f5bed-112">打开 **客户** 页，然后选择 **搜索和筛选索引**。</span><span class="sxs-lookup"><span data-stu-id="f5bed-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="f5bed-113">选择 **+ 添加** 以指定索引字段。</span><span class="sxs-lookup"><span data-stu-id="f5bed-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="f5bed-114">在列表中选择要作为索引字段添加的属性。</span><span class="sxs-lookup"><span data-stu-id="f5bed-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="f5bed-115">始终可以通过选择 **添加** 添加更多属性。</span><span class="sxs-lookup"><span data-stu-id="f5bed-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="f5bed-116">您还可以通过选择 **删除** 符号来删除任何选定的属性。</span><span class="sxs-lookup"><span data-stu-id="f5bed-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="f5bed-117">浏览已编制索引的客户字段表</span><span class="sxs-lookup"><span data-stu-id="f5bed-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="f5bed-118">此表中提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="f5bed-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="f5bed-119">**名称**：表示属性在客户配置文件实体中显示时的名称。</span><span class="sxs-lookup"><span data-stu-id="f5bed-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="f5bed-120">**数据类型**：指定数据类型是字符串、数字还是日期。</span><span class="sxs-lookup"><span data-stu-id="f5bed-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="f5bed-121">**包含在搜索中**：指定当使用 **搜索** 字段在 **客户** 页中搜索客户时，是否可使用此属性。</span><span class="sxs-lookup"><span data-stu-id="f5bed-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="f5bed-122">**添加筛选器**：用于定义如何将此属性用于在 **客户** 页中进行属性的控件。</span><span class="sxs-lookup"><span data-stu-id="f5bed-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="f5bed-123">编辑给定属性的筛选选项</span><span class="sxs-lookup"><span data-stu-id="f5bed-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="f5bed-124">**客户** 页中的 **筛选器** 菜单中可包含数量不定的属性级别（例如，在筛选客户时充当依据的不同年龄组）。</span><span class="sxs-lookup"><span data-stu-id="f5bed-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="f5bed-125">在 **搜索和筛选索引** 页中为给定属性选择 **添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f5bed-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="f5bed-126">可以定义结果的数量和排列顺序。</span><span class="sxs-lookup"><span data-stu-id="f5bed-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="f5bed-127">将显示下面的一个窗格，具体取决于属性的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f5bed-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="f5bed-128">字符串类型属性：在 **字符串筛选器选项** 窗格中指定所需结果数量和结果的排列顺序策略。</span><span class="sxs-lookup"><span data-stu-id="f5bed-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="f5bed-129">数值类型属性：指定 **数字筛选选项** 窗格中包含的时间间隔和结果的排列顺序策略。</span><span class="sxs-lookup"><span data-stu-id="f5bed-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="f5bed-130">日期类型属性：指定 **日期筛选选项** 窗格中包含的时间间隔和结果的排列顺序策略。</span><span class="sxs-lookup"><span data-stu-id="f5bed-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="f5bed-131">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f5bed-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="f5bed-132">准备好应用设置时，选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="f5bed-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5bed-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f5bed-133">Next steps</span></span>

<span data-ttu-id="f5bed-134">转到 **客户** 页以搜索客户配置文件，或使用索引字段来查看所有客户配置文件的子集。</span><span class="sxs-lookup"><span data-stu-id="f5bed-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]