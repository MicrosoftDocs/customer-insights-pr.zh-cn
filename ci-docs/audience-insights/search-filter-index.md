---
title: 搜索和筛选客户配置文件
description: 快速查找有关统一的客户配置文件的信息和筛选出指定的属性。
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405227"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="5da26-103">客户配置文件：搜索和筛选索引</span><span class="sxs-lookup"><span data-stu-id="5da26-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="5da26-104">统一客户数据的结果是一个客户配置文件实体，用于提供对总客户群的统一认识。</span><span class="sxs-lookup"><span data-stu-id="5da26-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="5da26-105">若要快速 [查找有关特定客户或客户群的信息](customer-profiles.md)，可以在 **客户** 页中配置 **搜索** 和 **筛选** 功能。</span><span class="sxs-lookup"><span data-stu-id="5da26-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="5da26-106">继续阅读以了解管理员可以如何编辑 **搜索和筛选索引** 页中的属性，用户可使用这些属性进行搜索和筛选。</span><span class="sxs-lookup"><span data-stu-id="5da26-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5da26-107">![搜索筛选器](media/search-filter.png "搜索筛选器")</span><span class="sxs-lookup"><span data-stu-id="5da26-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="5da26-108">添加字段和指定属性</span><span class="sxs-lookup"><span data-stu-id="5da26-108">Add fields and specify attributes</span></span>

<span data-ttu-id="5da26-109">如果这是您首次以管理员身份定义可搜索属性，您需要首先定义索引字段。</span><span class="sxs-lookup"><span data-stu-id="5da26-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="5da26-110">建议您选择用户在 **客户** 页中可用于搜索和筛选客户的所有属性。</span><span class="sxs-lookup"><span data-stu-id="5da26-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="5da26-111">只能指定您在数据统一过程中创建的客户配置文件实体内的已有属性。</span><span class="sxs-lookup"><span data-stu-id="5da26-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="5da26-112">打开 **客户** 页，然后选择 **搜索和筛选索引**。</span><span class="sxs-lookup"><span data-stu-id="5da26-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="5da26-113">我们根据“地图”页面上定义的以下语义类型，针对“客户”实体中的可用属性创建默认搜索索引配置。</span><span class="sxs-lookup"><span data-stu-id="5da26-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="5da26-114">人员的名、姓、中间名、全名</span><span class="sxs-lookup"><span data-stu-id="5da26-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="5da26-115">组织名称</span><span class="sxs-lookup"><span data-stu-id="5da26-115">Organization Name</span></span>
> - <span data-ttu-id="5da26-116">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="5da26-116">Email address</span></span>
> - <span data-ttu-id="5da26-117">电话号码</span><span class="sxs-lookup"><span data-stu-id="5da26-117">Phone number</span></span>
> - <span data-ttu-id="5da26-118">位置信息</span><span class="sxs-lookup"><span data-stu-id="5da26-118">Location information</span></span>

2. <span data-ttu-id="5da26-119">选择 **+ 添加** 以指定索引字段。</span><span class="sxs-lookup"><span data-stu-id="5da26-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="5da26-120">在列表中选择要作为索引字段添加的属性。</span><span class="sxs-lookup"><span data-stu-id="5da26-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="5da26-121">始终可以通过选择 **添加** 添加更多属性。</span><span class="sxs-lookup"><span data-stu-id="5da26-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="5da26-122">您还可以通过选择 **删除** 符号来删除任何选定的属性。</span><span class="sxs-lookup"><span data-stu-id="5da26-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="5da26-123">浏览已编制索引的客户字段表</span><span class="sxs-lookup"><span data-stu-id="5da26-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="5da26-124">此表中提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="5da26-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="5da26-125">**名称**：表示属性在客户配置文件实体中显示时的名称。</span><span class="sxs-lookup"><span data-stu-id="5da26-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="5da26-126">**数据类型**：指定数据类型是字符串、数字还是日期。</span><span class="sxs-lookup"><span data-stu-id="5da26-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="5da26-127">**包含在搜索中**：指定当使用 **搜索** 字段在 **客户** 页中搜索客户时，是否可使用此属性。</span><span class="sxs-lookup"><span data-stu-id="5da26-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="5da26-128">**添加筛选器**：用于定义如何将此属性用于在 **客户** 页中进行属性的控件。</span><span class="sxs-lookup"><span data-stu-id="5da26-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="5da26-129">编辑给定属性的筛选选项</span><span class="sxs-lookup"><span data-stu-id="5da26-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="5da26-130">**客户** 页中的 **筛选器** 菜单中可包含数量不定的属性级别（例如，在筛选客户时充当依据的不同年龄组）。</span><span class="sxs-lookup"><span data-stu-id="5da26-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="5da26-131">在 **搜索和筛选索引** 页中为给定属性选择 **添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="5da26-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="5da26-132">可以定义结果的数量和排列顺序。</span><span class="sxs-lookup"><span data-stu-id="5da26-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="5da26-133">将显示下面的一个窗格，具体取决于属性的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5da26-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="5da26-134">字符串类型属性：在 **字符串筛选器选项** 窗格中指定所需结果数量和结果的排列顺序策略。</span><span class="sxs-lookup"><span data-stu-id="5da26-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5da26-135">数值类型属性：指定 **数字筛选选项** 窗格中包含的时间间隔和结果的排列顺序策略。</span><span class="sxs-lookup"><span data-stu-id="5da26-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5da26-136">日期类型属性：指定 **日期筛选选项** 窗格中包含的时间间隔和结果的排列顺序策略。</span><span class="sxs-lookup"><span data-stu-id="5da26-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="5da26-137">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5da26-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="5da26-138">准备好应用设置时，选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="5da26-138">Select **Run** once you're ready to apply your settings.</span></span>
