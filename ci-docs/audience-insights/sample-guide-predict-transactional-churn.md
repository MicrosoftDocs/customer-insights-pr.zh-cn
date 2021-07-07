---
title: 交易流失预测示例指南
description: 使用本示例指南试用现成的交易流失预测模型。
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306109"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="d3094-103">交易流失预测（预览）示例指南</span><span class="sxs-lookup"><span data-stu-id="d3094-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="d3094-104">本指南将向您演示使用下面提供的数据的 Customer Insights 中交易流失预测的端到端示例。</span><span class="sxs-lookup"><span data-stu-id="d3094-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="d3094-105">本指南中使用的所有数据不是真正的客户数据，而是在 Customer Insights 订阅内的 *演示* 环境中找到的 Contoso 数据集的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3094-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="d3094-106">方案</span><span class="sxs-lookup"><span data-stu-id="d3094-106">Scenario</span></span>

<span data-ttu-id="d3094-107">Contoso 是一家生产高品质咖啡和咖啡机的公司，他们通过 Contoso Coffee 网站销售这些产品。</span><span class="sxs-lookup"><span data-stu-id="d3094-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="d3094-108">它们的目标是了解通常定期购买其产品的哪些客户在接下来的 60 天内将停止成为活动客户。</span><span class="sxs-lookup"><span data-stu-id="d3094-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="d3094-109">了解哪些客户 **可能会流失** 有助于他们将市场营销工作集中在留住这些客户上。</span><span class="sxs-lookup"><span data-stu-id="d3094-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3094-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3094-110">Prerequisites</span></span>

- <span data-ttu-id="d3094-111">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d3094-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="d3094-112">我们建议您[在新环境中](manage-environments.md)实施以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d3094-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="d3094-113">任务 1 - 引入数据</span><span class="sxs-lookup"><span data-stu-id="d3094-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="d3094-114">查看[关于数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)文章。</span><span class="sxs-lookup"><span data-stu-id="d3094-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="d3094-115">以下信息假设您大致了解如何引入数据。</span><span class="sxs-lookup"><span data-stu-id="d3094-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="d3094-116">从电子商务平台中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="d3094-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="d3094-117">创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="d3094-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d3094-118">输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。</span><span class="sxs-lookup"><span data-stu-id="d3094-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="d3094-119">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="d3094-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d3094-120">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3094-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d3094-121">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="d3094-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d3094-122">**CreatedOn**：日期/时间/区域</span><span class="sxs-lookup"><span data-stu-id="d3094-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="d3094-123">![将 DoB 转换为日期](media/ecommerce-dob-date.PNG "将出生日期转换为日期")</span><span class="sxs-lookup"><span data-stu-id="d3094-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="d3094-124">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="d3094-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="d3094-125">保存数据源。</span><span class="sxs-lookup"><span data-stu-id="d3094-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="d3094-126">引入在线购买数据</span><span class="sxs-lookup"><span data-stu-id="d3094-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="d3094-127">将另一个数据集添加到相同的 **电子商务** 数据源中。</span><span class="sxs-lookup"><span data-stu-id="d3094-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="d3094-128">再次选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="d3094-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="d3094-129">输入 **在线购买** 数据的 URL https://aka.ms/ciadclassonline。</span><span class="sxs-lookup"><span data-stu-id="d3094-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="d3094-130">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="d3094-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d3094-131">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3094-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d3094-132">**PurchasedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="d3094-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="d3094-133">**TotalPrice**：货币</span><span class="sxs-lookup"><span data-stu-id="d3094-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="d3094-134">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommercePurchases**。</span><span class="sxs-lookup"><span data-stu-id="d3094-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="d3094-135">保存数据源。</span><span class="sxs-lookup"><span data-stu-id="d3094-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="d3094-136">从忠诚度架构中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="d3094-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="d3094-137">创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="d3094-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d3094-138">输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="d3094-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="d3094-139">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="d3094-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d3094-140">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3094-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d3094-141">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="d3094-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d3094-142">**RewardsPoints**：整数</span><span class="sxs-lookup"><span data-stu-id="d3094-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="d3094-143">**CreatedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="d3094-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="d3094-144">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="d3094-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="d3094-145">保存数据源。</span><span class="sxs-lookup"><span data-stu-id="d3094-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="d3094-146">任务 2 - 数据统一</span><span class="sxs-lookup"><span data-stu-id="d3094-146">Task 2 - Data unification</span></span>

<span data-ttu-id="d3094-147">引入数据后，我们现在将开始 **映射、匹配、合并** 流程以创建统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="d3094-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="d3094-148">有关详细信息，请参阅[数据统一](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="d3094-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="d3094-149">映射</span><span class="sxs-lookup"><span data-stu-id="d3094-149">Map</span></span>

1. <span data-ttu-id="d3094-150">引入数据后，将联系人从电子商务和忠诚度数据映射到常见数据类型。</span><span class="sxs-lookup"><span data-stu-id="d3094-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="d3094-151">转到 **数据** > **统一** > **映射**。</span><span class="sxs-lookup"><span data-stu-id="d3094-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="d3094-152">选择表示客户配置文件的实体 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="d3094-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="统一电子商务和忠诚度数据源。":::

1. <span data-ttu-id="d3094-154">选择 **ContactId** 作为 **eCommerceContacts** 的主键，选择 **LoyaltyID** 作为 **loyCustomers** 的主键。</span><span class="sxs-lookup"><span data-stu-id="d3094-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="统一 LoyaltyId 作为主键。":::

### <a name="match"></a><span data-ttu-id="d3094-156">匹配项</span><span class="sxs-lookup"><span data-stu-id="d3094-156">Match</span></span>

1. <span data-ttu-id="d3094-157">转到 **匹配** 选项卡并选择 **设置顺序**。</span><span class="sxs-lookup"><span data-stu-id="d3094-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="d3094-158">在 **主要** 下拉列表中，选择 **eCommerceContacts : eCommerce** 作为主要源并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="d3094-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="d3094-159">在 **实体 2** 下拉列表中，选择 **loyCustomers : LoyaltyScheme** 并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="d3094-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="统一匹配电子商务和忠诚度。":::

1. <span data-ttu-id="d3094-161">选择 **创建新规则**</span><span class="sxs-lookup"><span data-stu-id="d3094-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="d3094-162">使用 FullName 添加您的第一个条件。</span><span class="sxs-lookup"><span data-stu-id="d3094-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="d3094-163">对于 eCommerceContacts，在下拉列表中选择 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="d3094-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="d3094-164">对于 loyCustomers，在下拉列表中选择 **FullName**。</span><span class="sxs-lookup"><span data-stu-id="d3094-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="d3094-165">选择 **标准化** 下拉列表，然后选择 **类型（电话、名称、地址......）**。</span><span class="sxs-lookup"><span data-stu-id="d3094-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="d3094-166">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="d3094-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="d3094-167">为新规则输入名称 **全名、电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="d3094-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="d3094-168">通过选择 **添加条件** 为电子邮件地址添加第二个条件</span><span class="sxs-lookup"><span data-stu-id="d3094-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="d3094-169">对于实体 eCommerceContacts，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="d3094-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="d3094-170">对于实体 loyCustomers，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="d3094-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="d3094-171">将“标准化”留空。</span><span class="sxs-lookup"><span data-stu-id="d3094-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="d3094-172">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="d3094-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="统一名称和电子邮件的匹配规则。":::

7. <span data-ttu-id="d3094-174">选择 **保存** 和 **运行**。</span><span class="sxs-lookup"><span data-stu-id="d3094-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="d3094-175">合并​​</span><span class="sxs-lookup"><span data-stu-id="d3094-175">Merge</span></span>

1. <span data-ttu-id="d3094-176">转到 **合并** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3094-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="d3094-177">在 **loyCustomers** 实体的 **ContactId** 上，将显示名称更改为 **ContactIdLOYALTY** 以将其与引入的其他 ID 区分开。</span><span class="sxs-lookup"><span data-stu-id="d3094-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="从忠诚度 ID 中重命名 contactid。":::

1. <span data-ttu-id="d3094-179">选择 **保存** 和 **运行** 以启动合并流程。</span><span class="sxs-lookup"><span data-stu-id="d3094-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="d3094-180">任务 3 - 配置交易流失预测</span><span class="sxs-lookup"><span data-stu-id="d3094-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="d3094-181">有了统一的客户配置文件，我们现在可以运行订阅流失预测。</span><span class="sxs-lookup"><span data-stu-id="d3094-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="d3094-182">有关详细步骤，请参阅[订阅流失预测（预览）](predict-subscription-churn.md)文章。</span><span class="sxs-lookup"><span data-stu-id="d3094-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="d3094-183">转到 **智能** > **发现** 并选择使用 **客户流失模型**。</span><span class="sxs-lookup"><span data-stu-id="d3094-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="d3094-184">选择 **交易** 选项，然后选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="d3094-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="d3094-185">命名模型 **OOB 电子商务交易流失预测** 和输出实体 **OOBeCommerceChurnPrediction**。</span><span class="sxs-lookup"><span data-stu-id="d3094-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="d3094-186">定义流失模型的两个条件：</span><span class="sxs-lookup"><span data-stu-id="d3094-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="d3094-187">**预测时间范围**：**至少 60** 天。</span><span class="sxs-lookup"><span data-stu-id="d3094-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="d3094-188">此设置定义未来您想要预测客户流失的程度。</span><span class="sxs-lookup"><span data-stu-id="d3094-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="d3094-189">**流失定义**：**至少 60** 天。</span><span class="sxs-lookup"><span data-stu-id="d3094-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="d3094-190">视为已流失的客户未进行购买的持续时间。</span><span class="sxs-lookup"><span data-stu-id="d3094-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="选择模型方法预测时间范围和流失定义。":::

1. <span data-ttu-id="d3094-192">选择 **购买历史记录（必需）**，然后针对购买历史记录选择 **添加数据**。</span><span class="sxs-lookup"><span data-stu-id="d3094-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="d3094-193">添加 **eCommercePurchases：电子商务** 实体，并将电子商务中的字段映射到模型所需的相应字段。</span><span class="sxs-lookup"><span data-stu-id="d3094-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="d3094-194">使用 **eCommerceContacts：电子商务** 加入 **eCommercePurchases：电子商务** 实体。</span><span class="sxs-lookup"><span data-stu-id="d3094-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="加入电子商务实体。":::

1. <span data-ttu-id="d3094-196">选择 **下一步** 以设置模型计划。</span><span class="sxs-lookup"><span data-stu-id="d3094-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="d3094-197">在引入新数据后，需要定期对模型进行定型以学习新模式。</span><span class="sxs-lookup"><span data-stu-id="d3094-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="d3094-198">对于此示例，请选择 **每月**。</span><span class="sxs-lookup"><span data-stu-id="d3094-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="d3094-199">在查看所有详细信息后，选择 **保存并运行**。</span><span class="sxs-lookup"><span data-stu-id="d3094-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="d3094-200">任务 4 - 审阅模型结果和说明</span><span class="sxs-lookup"><span data-stu-id="d3094-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="d3094-201">让模型完成数据的训练和评分。</span><span class="sxs-lookup"><span data-stu-id="d3094-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="d3094-202">您现在可以审阅订阅流失模型说明。</span><span class="sxs-lookup"><span data-stu-id="d3094-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="d3094-203">有关详细信息，请参阅[审阅预测状态和结果](predict-subscription-churn.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="d3094-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="d3094-204">任务 5 - 创建高流失风险客户的客户细分</span><span class="sxs-lookup"><span data-stu-id="d3094-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="d3094-205">运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。</span><span class="sxs-lookup"><span data-stu-id="d3094-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="d3094-206">您可以基于模型创建的实体创建新的客户细分。</span><span class="sxs-lookup"><span data-stu-id="d3094-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="d3094-207">转到 **客户细分**。</span><span class="sxs-lookup"><span data-stu-id="d3094-207">Go to **Segments**.</span></span> <span data-ttu-id="d3094-208">选择 **新建**，然后选择 **创建自** > **智能**。</span><span class="sxs-lookup"><span data-stu-id="d3094-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型输出创建客户细分。":::

1. <span data-ttu-id="d3094-210">选择 **OOBSubscriptionChurnPrediction** 终结点并定义客户细分：</span><span class="sxs-lookup"><span data-stu-id="d3094-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="d3094-211">字段：ChurnScore</span><span class="sxs-lookup"><span data-stu-id="d3094-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="d3094-212">运算符：大于</span><span class="sxs-lookup"><span data-stu-id="d3094-212">Operator: greater than</span></span>
   - <span data-ttu-id="d3094-213">值：0.6</span><span class="sxs-lookup"><span data-stu-id="d3094-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="设置订阅流失客户细分。":::

<span data-ttu-id="d3094-215">现在，您已具有将动态更新的客户细分，可用于确定此订阅业务的高流失风险客户。</span><span class="sxs-lookup"><span data-stu-id="d3094-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="d3094-216">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="d3094-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]