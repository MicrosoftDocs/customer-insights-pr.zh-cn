---
title: 订阅流失预测示例指南
description: 使用本示例指南试用现成的订阅流失预测模型。
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269825"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="69da4-103">订阅流失预测（预览）示例指南</span><span class="sxs-lookup"><span data-stu-id="69da4-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="69da4-104">我们将向您演示使用下面提供的示例数据的订阅流失预测的端到端示例。</span><span class="sxs-lookup"><span data-stu-id="69da4-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="69da4-105">方案</span><span class="sxs-lookup"><span data-stu-id="69da4-105">Scenario</span></span>

<span data-ttu-id="69da4-106">Contoso 是一家生产优质咖啡和咖啡机的公司，它们通过 Contoso 咖啡网站销售。</span><span class="sxs-lookup"><span data-stu-id="69da4-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="69da4-107">他们最近为定期购买咖啡的客户启动了一项订阅业务。</span><span class="sxs-lookup"><span data-stu-id="69da4-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="69da4-108">他们的目标是了解哪些订阅客户可能会在接下来的几个月内取消订阅。</span><span class="sxs-lookup"><span data-stu-id="69da4-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="69da4-109">了解哪些客户 **可能会流失** 有助于他们将市场营销工作集中在留住这些客户上。</span><span class="sxs-lookup"><span data-stu-id="69da4-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69da4-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="69da4-110">Prerequisites</span></span>

- <span data-ttu-id="69da4-111">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="69da4-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="69da4-112">我们建议您[在新环境中](manage-environments.md)实施以下步骤。</span><span class="sxs-lookup"><span data-stu-id="69da4-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="69da4-113">任务 1 - 引入数据</span><span class="sxs-lookup"><span data-stu-id="69da4-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="69da4-114">查看[关于数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)文章。</span><span class="sxs-lookup"><span data-stu-id="69da4-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="69da4-115">以下信息假设您大致了解如何引入数据。</span><span class="sxs-lookup"><span data-stu-id="69da4-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="69da4-116">从电子商务平台中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="69da4-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="69da4-117">创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="69da4-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="69da4-118">输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。</span><span class="sxs-lookup"><span data-stu-id="69da4-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="69da4-119">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="69da4-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="69da4-120">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="69da4-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="69da4-121">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="69da4-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="69da4-122">**CreatedOn**：日期/时间/区域</span><span class="sxs-lookup"><span data-stu-id="69da4-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. <span data-ttu-id="69da4-124">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="69da4-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="69da4-125">保存数据源。</span><span class="sxs-lookup"><span data-stu-id="69da4-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="69da4-126">从忠诚度架构中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="69da4-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="69da4-127">创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="69da4-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="69da4-128">输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="69da4-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="69da4-129">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="69da4-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="69da4-130">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="69da4-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="69da4-131">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="69da4-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="69da4-132">**RewardsPoints**：整数</span><span class="sxs-lookup"><span data-stu-id="69da4-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="69da4-133">**CreatedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="69da4-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="69da4-134">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="69da4-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="69da4-135">保存数据源。</span><span class="sxs-lookup"><span data-stu-id="69da4-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="69da4-136">引入订阅信息</span><span class="sxs-lookup"><span data-stu-id="69da4-136">Ingest subscription information</span></span>

1. <span data-ttu-id="69da4-137">创建名为 **SubscriptionHistory** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="69da4-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="69da4-138">输入电子商务联系人的 URL https://aka.ms/ciadchurnsubscriptionhistory。</span><span class="sxs-lookup"><span data-stu-id="69da4-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="69da4-139">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="69da4-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="69da4-140">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="69da4-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="69da4-141">**SubscriptioID**：整数</span><span class="sxs-lookup"><span data-stu-id="69da4-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="69da4-142">**SubscriptionAmount**：货币</span><span class="sxs-lookup"><span data-stu-id="69da4-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="69da4-143">**SubscriptionEndDate**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="69da4-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="69da4-144">**SubscriptionStartDate**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="69da4-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="69da4-145">**TransactionDate**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="69da4-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="69da4-146">**IsRecurring**：True/False</span><span class="sxs-lookup"><span data-stu-id="69da4-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="69da4-147">**Is_auto_renew**：True/False</span><span class="sxs-lookup"><span data-stu-id="69da4-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="69da4-148">**RecurringFrequencyInMonths**：整数</span><span class="sxs-lookup"><span data-stu-id="69da4-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="69da4-149">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **SubscriptionHistory**。</span><span class="sxs-lookup"><span data-stu-id="69da4-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="69da4-150">保存数据源。</span><span class="sxs-lookup"><span data-stu-id="69da4-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="69da4-151">从网站评价中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="69da4-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="69da4-152">创建名为 **网站** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="69da4-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="69da4-153">输入电子商务联系人的 URL https://aka.ms/ciadclasswebsite。</span><span class="sxs-lookup"><span data-stu-id="69da4-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="69da4-154">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="69da4-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="69da4-155">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="69da4-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="69da4-156">**ReviewRating**：整数</span><span class="sxs-lookup"><span data-stu-id="69da4-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="69da4-157">**ReviewDate**：日期</span><span class="sxs-lookup"><span data-stu-id="69da4-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="69da4-158">在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **webReviews**。</span><span class="sxs-lookup"><span data-stu-id="69da4-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="69da4-159">任务 2 - 数据统一</span><span class="sxs-lookup"><span data-stu-id="69da4-159">Task 2 - Data unification</span></span>

<span data-ttu-id="69da4-160">引入数据后，我们现在将开始 **映射、匹配、合并** 流程以创建统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="69da4-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="69da4-161">有关详细信息，请参阅[数据统一](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="69da4-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="69da4-162">映射</span><span class="sxs-lookup"><span data-stu-id="69da4-162">Map</span></span>

1. <span data-ttu-id="69da4-163">引入数据后，将联系人从电子商务和忠诚度数据映射到常见数据类型。</span><span class="sxs-lookup"><span data-stu-id="69da4-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="69da4-164">转到 **数据** > **统一** > **映射**。</span><span class="sxs-lookup"><span data-stu-id="69da4-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="69da4-165">选择表示客户配置文件的实体 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="69da4-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="统一电子商务和忠诚度数据源。":::

1. <span data-ttu-id="69da4-167">选择 **ContactId** 作为 **eCommerceContacts** 的主键，选择 **LoyaltyID** 作为 **loyCustomers** 的主键。</span><span class="sxs-lookup"><span data-stu-id="69da4-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="统一 LoyaltyId 作为主键。":::

### <a name="match"></a><span data-ttu-id="69da4-169">匹配项</span><span class="sxs-lookup"><span data-stu-id="69da4-169">Match</span></span>

1. <span data-ttu-id="69da4-170">转到 **匹配** 选项卡并选择 **设置顺序**。</span><span class="sxs-lookup"><span data-stu-id="69da4-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="69da4-171">在 **主要** 下拉列表中，选择 **eCommerceContacts：电子商务** 作为主要源，并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="69da4-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="69da4-172">在 **实体 2** 下拉列表中，选择 **loyCustomers：LoyaltyScheme**，并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="69da4-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="统一匹配电子商务和忠诚度。":::

1. <span data-ttu-id="69da4-174">选择 **创建新规则**</span><span class="sxs-lookup"><span data-stu-id="69da4-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="69da4-175">使用 FullName 添加您的第一个条件。</span><span class="sxs-lookup"><span data-stu-id="69da4-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="69da4-176">对于 eCommerceContacts，在下拉列表中选择 **全名**。</span><span class="sxs-lookup"><span data-stu-id="69da4-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="69da4-177">对于 loyCustomers，在下拉列表中选择 **全名**。</span><span class="sxs-lookup"><span data-stu-id="69da4-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="69da4-178">选择 **标准化** 下拉列表，然后选择 **类型（电话、名称、地址......）**。</span><span class="sxs-lookup"><span data-stu-id="69da4-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="69da4-179">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="69da4-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="69da4-180">为新规则输入名称 **全名、电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="69da4-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="69da4-181">通过选择 **添加条件** 为电子邮件地址添加第二个条件</span><span class="sxs-lookup"><span data-stu-id="69da4-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="69da4-182">对于实体 eCommerceContacts，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="69da4-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="69da4-183">对于实体 loyCustomers，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="69da4-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="69da4-184">将“标准化”留空。</span><span class="sxs-lookup"><span data-stu-id="69da4-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="69da4-185">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="69da4-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="统一名称和电子邮件的匹配规则。":::

7. <span data-ttu-id="69da4-187">选择 **保存** 和 **运行**。</span><span class="sxs-lookup"><span data-stu-id="69da4-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="69da4-188">合并​​</span><span class="sxs-lookup"><span data-stu-id="69da4-188">Merge</span></span>

1. <span data-ttu-id="69da4-189">转到 **合并** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="69da4-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="69da4-190">在 **loyCustomers** 实体的 **ContactId** 上，将显示名称更改为 **ContactIdLOYALTY** 以将其与引入的其他 ID 区分开。</span><span class="sxs-lookup"><span data-stu-id="69da4-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="从忠诚度 ID 中重命名 contactid。":::

1. <span data-ttu-id="69da4-192">选择 **保存** 和 **运行** 以启动合并流程。</span><span class="sxs-lookup"><span data-stu-id="69da4-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="69da4-193">任务 3 - 配置订阅流失预测</span><span class="sxs-lookup"><span data-stu-id="69da4-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="69da4-194">有了统一的客户配置文件，我们现在可以运行订阅流失预测。</span><span class="sxs-lookup"><span data-stu-id="69da4-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="69da4-195">有关详细步骤，请参阅[订阅流失预测（预览）](predict-subscription-churn.md)文章。</span><span class="sxs-lookup"><span data-stu-id="69da4-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="69da4-196">转到 **智能** > **发现** 并选择使用 **客户流失模型**。</span><span class="sxs-lookup"><span data-stu-id="69da4-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="69da4-197">选择 **订阅** 选项，然后选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="69da4-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="69da4-198">命名模型 **OOB 订阅流失预测** 和输出实体 **OOBSubscriptionChurnPrediction**。</span><span class="sxs-lookup"><span data-stu-id="69da4-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="69da4-199">定义流失模型的两个条件：</span><span class="sxs-lookup"><span data-stu-id="69da4-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="69da4-200">**订阅结束后的天数**：**至少 60** 天。</span><span class="sxs-lookup"><span data-stu-id="69da4-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="69da4-201">如果客户在其订阅结束后的此期间内未续订订阅，他们将会视为已流失。</span><span class="sxs-lookup"><span data-stu-id="69da4-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="69da4-202">**流失定义**：**至少 93** 天。</span><span class="sxs-lookup"><span data-stu-id="69da4-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="69da4-203">模型预测哪些客户可能流失的持续时间。</span><span class="sxs-lookup"><span data-stu-id="69da4-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="69da4-204">您所查看的将来时间越长，结果的精度越低。</span><span class="sxs-lookup"><span data-stu-id="69da4-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="选择模型方法预测时间范围和流失定义。":::

1. <span data-ttu-id="69da4-206">选择 **添加必需数据**，然后针对订阅历史记录选择 **添加数据**。</span><span class="sxs-lookup"><span data-stu-id="69da4-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="69da4-207">添加 **订阅：SubscriptionHistory** 实体，并将电子商务中的字段映射到模型所需的相应字段。</span><span class="sxs-lookup"><span data-stu-id="69da4-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="69da4-208">使用 **eCommerceContacts：电子商务** 加入 **订阅：SubscriptionHistory** 实体，命名关系 **eCommerceSubscription**。</span><span class="sxs-lookup"><span data-stu-id="69da4-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="加入电子商务实体。":::

1. <span data-ttu-id="69da4-210">在客户活动下，添加 **webReviews：网站** 实体，并将 webReviews 中的字段映射到模型所需的相应字段。</span><span class="sxs-lookup"><span data-stu-id="69da4-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="69da4-211">主键：ReviewId</span><span class="sxs-lookup"><span data-stu-id="69da4-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="69da4-212">时间戳：ReviewDate</span><span class="sxs-lookup"><span data-stu-id="69da4-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="69da4-213">事件：ReviewRating</span><span class="sxs-lookup"><span data-stu-id="69da4-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="69da4-214">为网站评价配置活动。</span><span class="sxs-lookup"><span data-stu-id="69da4-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="69da4-215">选择活动 **评价** 并使用 **eCommerceContacts：电子商务** 加入 **webReviews：网站** 实体。</span><span class="sxs-lookup"><span data-stu-id="69da4-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="69da4-216">选择 **下一步** 以设置模型计划。</span><span class="sxs-lookup"><span data-stu-id="69da4-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="69da4-217">在引入新数据后，需要定期对模型进行定型以学习新模式。</span><span class="sxs-lookup"><span data-stu-id="69da4-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="69da4-218">对于此示例，请选择 **每月**。</span><span class="sxs-lookup"><span data-stu-id="69da4-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="69da4-219">在查看所有详细信息后，选择 **保存并运行**。</span><span class="sxs-lookup"><span data-stu-id="69da4-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="69da4-220">任务 4 - 审阅模型结果和说明</span><span class="sxs-lookup"><span data-stu-id="69da4-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="69da4-221">让模型完成数据的训练和评分。</span><span class="sxs-lookup"><span data-stu-id="69da4-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="69da4-222">您现在可以审阅订阅流失模型说明。</span><span class="sxs-lookup"><span data-stu-id="69da4-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="69da4-223">有关详细信息，请参阅[审阅预测状态和结果](predict-subscription-churn.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="69da4-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="69da4-224">任务 5 - 创建高流失风险客户的客户细分</span><span class="sxs-lookup"><span data-stu-id="69da4-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="69da4-225">运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。</span><span class="sxs-lookup"><span data-stu-id="69da4-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="69da4-226">您可以基于模型创建的实体创建新的客户细分。</span><span class="sxs-lookup"><span data-stu-id="69da4-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="69da4-227">转到 **客户细分**。</span><span class="sxs-lookup"><span data-stu-id="69da4-227">Go to **Segments**.</span></span> <span data-ttu-id="69da4-228">选择 **新建**，然后选择 **创建自** > **智能**。</span><span class="sxs-lookup"><span data-stu-id="69da4-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型输出创建客户细分。":::

1. <span data-ttu-id="69da4-230">选择 **OOBSubscriptionChurnPrediction** 终结点并定义客户细分：</span><span class="sxs-lookup"><span data-stu-id="69da4-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="69da4-231">字段：ChurnScore</span><span class="sxs-lookup"><span data-stu-id="69da4-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="69da4-232">运算符：大于</span><span class="sxs-lookup"><span data-stu-id="69da4-232">Operator: greater than</span></span>
   - <span data-ttu-id="69da4-233">值：0.6</span><span class="sxs-lookup"><span data-stu-id="69da4-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="设置订阅流失客户细分。":::

<span data-ttu-id="69da4-235">现在，您已具有将动态更新的客户细分，可用于确定此订阅业务的高流失风险客户。</span><span class="sxs-lookup"><span data-stu-id="69da4-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="69da4-236">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="69da4-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]