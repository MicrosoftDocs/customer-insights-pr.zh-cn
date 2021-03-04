---
title: 管理用户权限
description: 了解权限和用户角色。
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f7fcecdea8dc49666dd5c45bf4109c205993f326
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268399"
---
# <a name="user-permissions"></a><span data-ttu-id="62e9a-103">用户权限</span><span class="sxs-lookup"><span data-stu-id="62e9a-103">User permissions</span></span>

<span data-ttu-id="62e9a-104">**权限** 页面用于设置使用访问群体见解的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="62e9a-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="62e9a-105">您需要有管理员权限才能查看此页面。</span><span class="sxs-lookup"><span data-stu-id="62e9a-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="62e9a-106">若要在访问群体见解中访问权限页面，请转到 **管理员** > **权限**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="62e9a-107">有三种类型的角色：</span><span class="sxs-lookup"><span data-stu-id="62e9a-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="62e9a-108">查看者</span><span class="sxs-lookup"><span data-stu-id="62e9a-108">Viewer</span></span>

- <span data-ttu-id="62e9a-109">在 **主页** 和 **客户细分** 页面中浏览见解和客户细分。</span><span class="sxs-lookup"><span data-stu-id="62e9a-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="62e9a-110">使用 **客户** 页搜索和筛选客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="62e9a-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="62e9a-111">字段必须是可搜索字段。</span><span class="sxs-lookup"><span data-stu-id="62e9a-111">Fields must be searchable.</span></span>
- <span data-ttu-id="62e9a-112">查看和浏览 **扩充** 页面。</span><span class="sxs-lookup"><span data-stu-id="62e9a-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="62e9a-113">使用 **实体** 页浏览和导出实体。</span><span class="sxs-lookup"><span data-stu-id="62e9a-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="62e9a-114">使用 **系统** 页查看系统进程的状态。</span><span class="sxs-lookup"><span data-stu-id="62e9a-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="62e9a-115">从 **客户细分** 页面中导出客户细分。</span><span class="sxs-lookup"><span data-stu-id="62e9a-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="62e9a-116">安装和使用 **Power BI Customer Insights** 仪表板。</span><span class="sxs-lookup"><span data-stu-id="62e9a-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="62e9a-117">参与者</span><span class="sxs-lookup"><span data-stu-id="62e9a-117">Contributor</span></span>

- <span data-ttu-id="62e9a-118">查看者的所有可用权限。</span><span class="sxs-lookup"><span data-stu-id="62e9a-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="62e9a-119">使用 **数据源** 页面加载和转换数据。</span><span class="sxs-lookup"><span data-stu-id="62e9a-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="62e9a-120">填写 *数据统一* 部分（**映射**、**匹配** 和 **合并**），这将生成统一的客户配置文件实体。</span><span class="sxs-lookup"><span data-stu-id="62e9a-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="62e9a-121">定义 **关系** 和 **活动**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="62e9a-122">使用 **客户细分** 页面创建客户细分。</span><span class="sxs-lookup"><span data-stu-id="62e9a-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="62e9a-123">使用 **度量** 页创建度量。</span><span class="sxs-lookup"><span data-stu-id="62e9a-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="62e9a-124">通过 **扩充** 页面管理配置和扩充客户配置文件（仅适用于第一方扩充）。</span><span class="sxs-lookup"><span data-stu-id="62e9a-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="62e9a-125">管理员</span><span class="sxs-lookup"><span data-stu-id="62e9a-125">Administrator</span></span>

- <span data-ttu-id="62e9a-126">参与者的所有可用权限。</span><span class="sxs-lookup"><span data-stu-id="62e9a-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="62e9a-127">更改 **系统** 页面上的设置（包括工作语言），并刷新系统流程的计划。</span><span class="sxs-lookup"><span data-stu-id="62e9a-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="62e9a-128">使用 **权限** 页面查看和添加权限。</span><span class="sxs-lookup"><span data-stu-id="62e9a-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="62e9a-129">使用 **搜索和筛选** 索引页面（通过 **客户** 页面访问）设置客户页面的搜索和筛选定义。</span><span class="sxs-lookup"><span data-stu-id="62e9a-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="62e9a-130">使用 **导出目标** 页定义 Dynamics 365 Sales 客户细分目标。</span><span class="sxs-lookup"><span data-stu-id="62e9a-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="62e9a-131">通过 **扩充** 页面管理配置和扩充客户配置文件（适用于所有扩充）。</span><span class="sxs-lookup"><span data-stu-id="62e9a-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="62e9a-132">安装和使用 **客户卡加载项**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="62e9a-133">添加和使用 **Power Apps 连接器**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="62e9a-134">[启用 Customer Insights API 的使用](apis.md)。</span><span class="sxs-lookup"><span data-stu-id="62e9a-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="62e9a-135">分派角色和权限</span><span class="sxs-lookup"><span data-stu-id="62e9a-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="62e9a-136">在访问群体见解中，转到 **管理员** > **权限**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="62e9a-137">选择 **添加用户** 以打开 **添加/编辑权限** 窗格。</span><span class="sxs-lookup"><span data-stu-id="62e9a-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="62e9a-138">使用 **搜索** 字段查找要调整其权限的 Azure Active Directory 用户或组。</span><span class="sxs-lookup"><span data-stu-id="62e9a-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="62e9a-139">选择要分配给该用户或组的 **角色**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="62e9a-140">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="62e9a-140">Select **Save**.</span></span> <span data-ttu-id="62e9a-141">将与您已更改其权限的用户或组成员自动共享当前环境。</span><span class="sxs-lookup"><span data-stu-id="62e9a-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="62e9a-142">用户可以访问 Customer Insights 应用并根据其指定角色进行工作。</span><span class="sxs-lookup"><span data-stu-id="62e9a-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="62e9a-143">查看当前权限</span><span class="sxs-lookup"><span data-stu-id="62e9a-143">View current permissions</span></span>

<span data-ttu-id="62e9a-144">在访问群体见解中，转到 **管理员** > **权限** 以查看哪些角色分配当前处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="62e9a-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="62e9a-145">**类型** 列指定一个用户、组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="62e9a-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="62e9a-146">系统支持各个用户和组。</span><span class="sxs-lookup"><span data-stu-id="62e9a-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="62e9a-147">角色在 **角色** 列下指定。</span><span class="sxs-lookup"><span data-stu-id="62e9a-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="62e9a-148">选择任意列标题可按该列的值对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="62e9a-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="62e9a-149">使用页面顶部的 **搜索** 字段查找特定用户。</span><span class="sxs-lookup"><span data-stu-id="62e9a-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]