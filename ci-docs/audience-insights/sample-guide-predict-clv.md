---
title: 客户生存期值预测示例指南
description: 使用此示例指南试用客户生存期值模型。
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306338"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="b8d24-103">客户生存期值 (CLV) 预测示例指南</span><span class="sxs-lookup"><span data-stu-id="b8d24-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="b8d24-104">本指南将使用示例数据逐步向您解释 Customer Insights 中的客户生存期值 (CLV) 预测端到端示例。</span><span class="sxs-lookup"><span data-stu-id="b8d24-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="b8d24-105">方案</span><span class="sxs-lookup"><span data-stu-id="b8d24-105">Scenario</span></span>

<span data-ttu-id="b8d24-106">Contoso 是一家生产高品质咖啡和咖啡机的公司。</span><span class="sxs-lookup"><span data-stu-id="b8d24-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="b8d24-107">他们通过 Contoso 咖啡网站销售产品。</span><span class="sxs-lookup"><span data-stu-id="b8d24-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="b8d24-108">公司希望了解客户在未来 12 个月内可以产生的价值（收入）。</span><span class="sxs-lookup"><span data-stu-id="b8d24-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="b8d24-109">了解客户在未来 12 个月的预期价值将有助于他们将营销工作转向高价值客户。</span><span class="sxs-lookup"><span data-stu-id="b8d24-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8d24-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="b8d24-110">Prerequisites</span></span>

- <span data-ttu-id="b8d24-111">至少具有访问群体见解中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d24-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="b8d24-112">我们建议您[在新环境中](manage-environments.md)实施以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b8d24-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="b8d24-113">任务 1 - 引入数据</span><span class="sxs-lookup"><span data-stu-id="b8d24-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="b8d24-114">查看关于[数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="b8d24-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="b8d24-115">以下信息假设您大致了解如何引入数据。</span><span class="sxs-lookup"><span data-stu-id="b8d24-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="b8d24-116">从电子商务平台中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="b8d24-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="b8d24-117">创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="b8d24-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b8d24-118">输入电子商务联系人的 URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。</span><span class="sxs-lookup"><span data-stu-id="b8d24-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="b8d24-119">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b8d24-120">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b8d24-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b8d24-121">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="b8d24-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="b8d24-122">**CreatedOn**：日期/时间/区域</span><span class="sxs-lookup"><span data-stu-id="b8d24-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. <span data-ttu-id="b8d24-124">在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="b8d24-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="b8d24-125">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="b8d24-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="b8d24-126">引入在线购买数据</span><span class="sxs-lookup"><span data-stu-id="b8d24-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="b8d24-127">将另一个数据集添加到相同的 **电子商务** 数据源中。</span><span class="sxs-lookup"><span data-stu-id="b8d24-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="b8d24-128">再次选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="b8d24-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="b8d24-129">输入 **在线购买** 数据的 URL https://aka.ms/ciadclassonline。</span><span class="sxs-lookup"><span data-stu-id="b8d24-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="b8d24-130">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b8d24-131">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b8d24-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b8d24-132">**PurchasedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="b8d24-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="b8d24-133">**TotalPrice**：货币</span><span class="sxs-lookup"><span data-stu-id="b8d24-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="b8d24-134">在侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommercePurchases**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="b8d24-135">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="b8d24-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="b8d24-136">从忠诚度架构中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="b8d24-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="b8d24-137">创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="b8d24-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b8d24-138">输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="b8d24-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="b8d24-139">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b8d24-140">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b8d24-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b8d24-141">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="b8d24-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b8d24-142">**RewardsPoints**：整数</span><span class="sxs-lookup"><span data-stu-id="b8d24-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="b8d24-143">**CreatedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="b8d24-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="b8d24-144">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="b8d24-145">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="b8d24-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="b8d24-146">从网站评价中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="b8d24-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="b8d24-147">创建名为 **网站** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="b8d24-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b8d24-148">输入电子商务联系人的 URL https://aka.ms/CI-ILT/WebReviews。</span><span class="sxs-lookup"><span data-stu-id="b8d24-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="b8d24-149">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b8d24-150">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b8d24-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b8d24-151">**ReviewRating**：十进制数</span><span class="sxs-lookup"><span data-stu-id="b8d24-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="b8d24-152">**ReviewDate**：日期</span><span class="sxs-lookup"><span data-stu-id="b8d24-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="b8d24-153">在右侧窗格上的“名称”字段中，将您的数据源从 **查询** 重命名为 **审核**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="b8d24-154">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="b8d24-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="b8d24-155">任务 2 - 数据统一</span><span class="sxs-lookup"><span data-stu-id="b8d24-155">Task 2 - Data unification</span></span>

<span data-ttu-id="b8d24-156">在引入数据后，我们现在开始进行数据统一流程，以创建统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="b8d24-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="b8d24-157">有关详细信息，请参阅[数据统一](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d24-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="b8d24-158">映射</span><span class="sxs-lookup"><span data-stu-id="b8d24-158">Map</span></span>

1. <span data-ttu-id="b8d24-159">引入数据后，将联系人从电子商务和忠诚度数据映射到常见数据类型。</span><span class="sxs-lookup"><span data-stu-id="b8d24-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="b8d24-160">转到 **数据** > **统一** > **映射**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="b8d24-161">选择表示客户配置文件的实体 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="b8d24-162">然后选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-162">Then, select **Apply**.</span></span>

   ![统一电子商务和忠诚度数据源。](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="b8d24-164">选择 **ContactId** 作为 **eCommerceContacts** 的主键，选择 **LoyaltyID** 作为 **loyCustomers** 的主键。</span><span class="sxs-lookup"><span data-stu-id="b8d24-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![统一 LoyaltyId 作为主键。](media/unify-loyaltyid.png)

1. <span data-ttu-id="b8d24-166">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="b8d24-167">匹配项</span><span class="sxs-lookup"><span data-stu-id="b8d24-167">Match</span></span>

1. <span data-ttu-id="b8d24-168">转到 **匹配** 选项卡并选择 **设置顺序**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="b8d24-169">在 **主要** 下拉列表中，选择 **eCommerceContacts : eCommerce** 作为主要源并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="b8d24-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="b8d24-170">在 **实体 2** 下拉列表中，选择 **loyCustomers : LoyaltyScheme** 并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="b8d24-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![统一匹配电子商务和忠诚度。](media/unify-match-order.png)

1. <span data-ttu-id="b8d24-172">选择 **添加规则**</span><span class="sxs-lookup"><span data-stu-id="b8d24-172">Select **Add rule**</span></span>

1. <span data-ttu-id="b8d24-173">使用 FullName 添加您的第一个条件。</span><span class="sxs-lookup"><span data-stu-id="b8d24-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="b8d24-174">对于 eCommerceContacts，在下拉列表中选择 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="b8d24-175">对于 loyCustomers，在下拉列表中选择 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="b8d24-176">选择 **标准化** 下拉菜单，然后选择 **类型（电话、姓名、地址...）**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="b8d24-177">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="b8d24-178">为新规则输入名称 **全名、电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="b8d24-179">通过选择 **添加条件** 为电子邮件地址添加第二个条件</span><span class="sxs-lookup"><span data-stu-id="b8d24-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="b8d24-180">对于实体 eCommerceContacts，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="b8d24-181">对于实体 loyCustomers，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="b8d24-182">将“标准化”留空。</span><span class="sxs-lookup"><span data-stu-id="b8d24-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="b8d24-183">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![统一名称和电子邮件的匹配规则。](media/unify-match-rule.png)

1. <span data-ttu-id="b8d24-185">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-185">Select **Done**.</span></span>

1. <span data-ttu-id="b8d24-186">选择 **保存** 和 **运行**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="b8d24-187">合并​​</span><span class="sxs-lookup"><span data-stu-id="b8d24-187">Merge</span></span>

1. <span data-ttu-id="b8d24-188">转到 **合并** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b8d24-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="b8d24-189">在 **loyCustomers** 实体的 **ContactId** 上，将显示名称更改为 **ContactIdLOYALTY** 以将其与引入的其他 ID 区分开。</span><span class="sxs-lookup"><span data-stu-id="b8d24-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![从忠诚度 ID 中重命名 contactid。](media/unify-merge-contactid.png)

1. <span data-ttu-id="b8d24-191">选择 **保存** 和 **运行合并和下游流程**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="b8d24-192">任务 3 - 配置客户生存期值预测</span><span class="sxs-lookup"><span data-stu-id="b8d24-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="b8d24-193">部署了统一客户配置文件后，我们现在可以运行客户生存期值预测。</span><span class="sxs-lookup"><span data-stu-id="b8d24-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="b8d24-194">有关详细信息步骤，请参阅[客户生存期值预测（预览版）](predict-customer-lifetime-value.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d24-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="b8d24-195">转到 **智能**  > **预测** 并选择 **客户生存期值模型**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="b8d24-196">浏览侧窗格中的信息并选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="b8d24-197">将模型命名为 **OOB 电子商务 CLV 预测**，将输出实体命名为 **OOBeCommerceCLVPrediction**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="b8d24-198">定义 CLV 模型的模型首选项：</span><span class="sxs-lookup"><span data-stu-id="b8d24-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="b8d24-199">**预测时间段**：**12 个月或 1 年**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="b8d24-200">此设置定义了未来要预测客户生存期值多久。</span><span class="sxs-lookup"><span data-stu-id="b8d24-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="b8d24-201">**活跃客户**：指定活跃客户对您业务的意义。</span><span class="sxs-lookup"><span data-stu-id="b8d24-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="b8d24-202">设置客户必须在其中至少有一笔交易才能被视为活跃客户的历史期限。</span><span class="sxs-lookup"><span data-stu-id="b8d24-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="b8d24-203">该模型将只预测活跃客户的 CLV。</span><span class="sxs-lookup"><span data-stu-id="b8d24-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="b8d24-204">在让模型根据历史交易数据计算时间段与提供特定期限之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="b8d24-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="b8d24-205">在此示例指南中，我们 **让模型计算购买间隔**，这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="b8d24-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="b8d24-206">**高价值客户**：将高价值客户定义为最高付费客户的百分位数。</span><span class="sxs-lookup"><span data-stu-id="b8d24-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="b8d24-207">该模型使用此输入提供符合您的高价值客户定义的结果。</span><span class="sxs-lookup"><span data-stu-id="b8d24-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="b8d24-208">您可以选择让模型定义高价值客户。</span><span class="sxs-lookup"><span data-stu-id="b8d24-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="b8d24-209">它使用一种启发式规则来得出此百分位数。</span><span class="sxs-lookup"><span data-stu-id="b8d24-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="b8d24-210">您还可以将高价值客户定义为将来最高付费客户的百分位数。</span><span class="sxs-lookup"><span data-stu-id="b8d24-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="b8d24-211">在此示例指南中，我们将高价值客户手动定义为 **前 30% 的主动付费客户**，并选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 模型的引导式体验中的首选项步骤。":::

1. <span data-ttu-id="b8d24-213">在 **所需数据** 步骤中，选择 **添加数据** 以提供交易历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="b8d24-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="b8d24-214">添加 **eCommercePurchases：电子商务** 实体并映射模型所需的属性：</span><span class="sxs-lookup"><span data-stu-id="b8d24-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="b8d24-215">交易 ID：eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="b8d24-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="b8d24-216">交易日期：eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="b8d24-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="b8d24-217">交易金额：eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="b8d24-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="b8d24-218">产品 ID：eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="b8d24-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="b8d24-219">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-219">Select **Next**.</span></span>

1. <span data-ttu-id="b8d24-220">在 **eCommercePurchases：电子商务** 实体与 **eCommerceContacts：电子商务** 之间建立关系。</span><span class="sxs-lookup"><span data-stu-id="b8d24-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="b8d24-221">**附加数据（可选）** 步骤允许您添加更多客户活动数据。</span><span class="sxs-lookup"><span data-stu-id="b8d24-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="b8d24-222">这些数据可以帮助获得更多关于客户与企业之间的交互的见解，这可能对 CLV 有影响。</span><span class="sxs-lookup"><span data-stu-id="b8d24-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="b8d24-223">添加关键客户交互（如 Web 日志、客户服务日志或奖励计划历史记录）可以提高预测的准确性。</span><span class="sxs-lookup"><span data-stu-id="b8d24-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="b8d24-224">选择 **添加数据** 以包含更多客户活动数据。</span><span class="sxs-lookup"><span data-stu-id="b8d24-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="b8d24-225">添加客户活动实体，将其字段名称映射到模型所需的相应字段：</span><span class="sxs-lookup"><span data-stu-id="b8d24-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="b8d24-226">客户活动实体：Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="b8d24-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="b8d24-227">主键：Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="b8d24-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="b8d24-228">时间戳：Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="b8d24-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="b8d24-229">事件（活动名称）：Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="b8d24-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="b8d24-230">详细信息（金额或价值）：Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="b8d24-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="b8d24-231">选择 **下一步** 并配置活动以及交易数据与客户数据之间的关系：</span><span class="sxs-lookup"><span data-stu-id="b8d24-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="b8d24-232">活动类型：选择现有项</span><span class="sxs-lookup"><span data-stu-id="b8d24-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="b8d24-233">活动标签：审核</span><span class="sxs-lookup"><span data-stu-id="b8d24-233">Activity label: Review</span></span>
   - <span data-ttu-id="b8d24-234">相应的标签：Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="b8d24-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="b8d24-235">客户实体：eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="b8d24-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="b8d24-236">关系：WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="b8d24-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="b8d24-237">选择 **下一步** 以设置模型计划。</span><span class="sxs-lookup"><span data-stu-id="b8d24-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="b8d24-238">当存在引入的新数据时，模型需要定期训练以学习新模式。</span><span class="sxs-lookup"><span data-stu-id="b8d24-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="b8d24-239">对于本示例，选择 **每月**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="b8d24-240">在查看所有详细信息后，选择 **保存并运行**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="b8d24-241">任务 4 - 审阅模型结果和说明</span><span class="sxs-lookup"><span data-stu-id="b8d24-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="b8d24-242">让模型完成数据的训练和评分。</span><span class="sxs-lookup"><span data-stu-id="b8d24-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="b8d24-243">接下来，您可以查看 CLV 模型的结果和解释。</span><span class="sxs-lookup"><span data-stu-id="b8d24-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="b8d24-244">有关详细信息，请参阅[审阅预测状态和结果](predict-customer-lifetime-value.md#review-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="b8d24-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="b8d24-245">任务 5 - 创建高价值客户的客户细分</span><span class="sxs-lookup"><span data-stu-id="b8d24-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="b8d24-246">运行模型可创建一个新实体，该实体列在 **数据** > **实体** 上。</span><span class="sxs-lookup"><span data-stu-id="b8d24-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="b8d24-247">您可以根据模型创建的实体创建新客户细分。</span><span class="sxs-lookup"><span data-stu-id="b8d24-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="b8d24-248">转到 **客户细分**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="b8d24-249">选择 **新建**，然后选择 **创建自** > **智能**。</span><span class="sxs-lookup"><span data-stu-id="b8d24-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![使用模型输出创建客户细分。](media/segment-intelligence.png)

1. <span data-ttu-id="b8d24-251">选择 **OOBeCommerceCLVPrediction** 实体并定义客户细分：</span><span class="sxs-lookup"><span data-stu-id="b8d24-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="b8d24-252">字段：CLVScore</span><span class="sxs-lookup"><span data-stu-id="b8d24-252">Field: CLVScore</span></span>
  - <span data-ttu-id="b8d24-253">运算符：大于</span><span class="sxs-lookup"><span data-stu-id="b8d24-253">Operator: greater than</span></span>
  - <span data-ttu-id="b8d24-254">值：1500</span><span class="sxs-lookup"><span data-stu-id="b8d24-254">Value: 1500</span></span>

1. <span data-ttu-id="b8d24-255">选择 **审核** 并 **保存** 客户细分。</span><span class="sxs-lookup"><span data-stu-id="b8d24-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="b8d24-256">您现在有一个客户细分，该客户细分可识别预计在未来 12 个月内产生超过 1500 美元收入的客户。</span><span class="sxs-lookup"><span data-stu-id="b8d24-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="b8d24-257">如果引入更多数据，将动态更新此客户细分。</span><span class="sxs-lookup"><span data-stu-id="b8d24-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="b8d24-258">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d24-258">For more information, see [Create and manage segments](segments.md).</span></span>
