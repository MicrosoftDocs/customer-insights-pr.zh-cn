---
title: 产品建议预测示例指南
description: 使用本示例指南试用产品建议预测模型。
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129888"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="80497-103">产品建议预测（预览版）示例指南</span><span class="sxs-lookup"><span data-stu-id="80497-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="80497-104">我们将向您演示使用下面提供的示例数据的产品建议预测的端到端示例。</span><span class="sxs-lookup"><span data-stu-id="80497-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="80497-105">方案</span><span class="sxs-lookup"><span data-stu-id="80497-105">Scenario</span></span>

<span data-ttu-id="80497-106">Contoso 是一家生产高品质咖啡和咖啡机的公司，他们通过 Contoso Coffee 网站销售这些产品。</span><span class="sxs-lookup"><span data-stu-id="80497-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="80497-107">他们的目标是了解应该向定期客户推荐哪些产品。</span><span class="sxs-lookup"><span data-stu-id="80497-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="80497-108">通过了解客户更 **有可能购买** 哪些产品，可以将主要精力放在特定项目上来节省市场营销工作。</span><span class="sxs-lookup"><span data-stu-id="80497-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80497-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="80497-109">Prerequisites</span></span>

- <span data-ttu-id="80497-110">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="80497-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="80497-111">我们建议您[在新环境中](manage-environments.md)实施以下步骤。</span><span class="sxs-lookup"><span data-stu-id="80497-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="80497-112">任务 1 - 引入数据</span><span class="sxs-lookup"><span data-stu-id="80497-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="80497-113">查看[关于数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)文章。</span><span class="sxs-lookup"><span data-stu-id="80497-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="80497-114">以下信息假设您大致了解如何引入数据。</span><span class="sxs-lookup"><span data-stu-id="80497-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="80497-115">从电子商务平台中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="80497-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="80497-116">创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="80497-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="80497-117">输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。</span><span class="sxs-lookup"><span data-stu-id="80497-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="80497-118">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="80497-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="80497-119">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="80497-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="80497-120">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="80497-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="80497-121">**CreatedOn**：日期/时间/区域</span><span class="sxs-lookup"><span data-stu-id="80497-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

5. <span data-ttu-id="80497-123">在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="80497-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="80497-124">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="80497-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="80497-125">引入在线购买数据</span><span class="sxs-lookup"><span data-stu-id="80497-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="80497-126">将另一个数据集添加到相同的 **电子商务** 数据源中。</span><span class="sxs-lookup"><span data-stu-id="80497-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="80497-127">再次选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="80497-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="80497-128">输入 **在线购买** 数据的 URL https://aka.ms/ciadclassonline。</span><span class="sxs-lookup"><span data-stu-id="80497-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="80497-129">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="80497-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="80497-130">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="80497-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="80497-131">**PurchasedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="80497-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="80497-132">**TotalPrice**：货币</span><span class="sxs-lookup"><span data-stu-id="80497-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="80497-133">在侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommercePurchases**。</span><span class="sxs-lookup"><span data-stu-id="80497-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="80497-134">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="80497-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="80497-135">从忠诚度架构中引入客户数据</span><span class="sxs-lookup"><span data-stu-id="80497-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="80497-136">创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。</span><span class="sxs-lookup"><span data-stu-id="80497-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="80497-137">输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。</span><span class="sxs-lookup"><span data-stu-id="80497-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="80497-138">编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。</span><span class="sxs-lookup"><span data-stu-id="80497-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="80497-139">更新下面列出的列的数据类型：</span><span class="sxs-lookup"><span data-stu-id="80497-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="80497-140">**DateOfBirth**：日期</span><span class="sxs-lookup"><span data-stu-id="80497-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="80497-141">**RewardsPoints**：整数</span><span class="sxs-lookup"><span data-stu-id="80497-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="80497-142">**CreatedOn**：日期/时间</span><span class="sxs-lookup"><span data-stu-id="80497-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="80497-143">在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="80497-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="80497-144">**保存** 数据源。</span><span class="sxs-lookup"><span data-stu-id="80497-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="80497-145">任务 2 - 数据统一</span><span class="sxs-lookup"><span data-stu-id="80497-145">Task 2 - Data unification</span></span>

<span data-ttu-id="80497-146">在引入数据后，我们现在开始进行数据统一流程，以创建统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="80497-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="80497-147">有关详细信息，请参阅[数据统一](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="80497-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="80497-148">映射</span><span class="sxs-lookup"><span data-stu-id="80497-148">Map</span></span>

1. <span data-ttu-id="80497-149">引入数据后，将联系人从电子商务和忠诚度数据映射到常见数据类型。</span><span class="sxs-lookup"><span data-stu-id="80497-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="80497-150">转到 **数据** > **统一** > **映射**。</span><span class="sxs-lookup"><span data-stu-id="80497-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="80497-151">选择表示客户配置文件的实体 – **eCommerceContacts** 和 **loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="80497-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![统一电子商务和忠诚度数据源。](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="80497-153">选择 **ContactId** 作为 **eCommerceContacts** 的主键，选择 **LoyaltyID** 作为 **loyCustomers** 的主键。</span><span class="sxs-lookup"><span data-stu-id="80497-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![统一 LoyaltyId 作为主键。](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="80497-155">匹配项</span><span class="sxs-lookup"><span data-stu-id="80497-155">Match</span></span>

1. <span data-ttu-id="80497-156">转到 **匹配** 选项卡并选择 **设置顺序**。</span><span class="sxs-lookup"><span data-stu-id="80497-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="80497-157">在 **主要** 下拉列表中，选择 **eCommerceContacts：电子商务** 作为主要源，并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="80497-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="80497-158">在 **实体 2** 下拉列表中，选择 **loyCustomers：LoyaltyScheme**，并包括所有记录。</span><span class="sxs-lookup"><span data-stu-id="80497-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![统一匹配电子商务和忠诚度。](media/unify-match-order.png)

4. <span data-ttu-id="80497-160">选择 **创建新规则**</span><span class="sxs-lookup"><span data-stu-id="80497-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="80497-161">使用 FullName 添加您的第一个条件。</span><span class="sxs-lookup"><span data-stu-id="80497-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="80497-162">对于 eCommerceContacts，在下拉列表中选择 **全名**。</span><span class="sxs-lookup"><span data-stu-id="80497-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="80497-163">对于 loyCustomers，在下拉列表中选择 **全名**。</span><span class="sxs-lookup"><span data-stu-id="80497-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="80497-164">选择 **标准化** 下拉列表，然后选择 **类型（电话、名称、地址......）**。</span><span class="sxs-lookup"><span data-stu-id="80497-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="80497-165">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="80497-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="80497-166">为新规则输入名称 **全名、电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="80497-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="80497-167">通过选择 **添加条件** 为电子邮件地址添加第二个条件</span><span class="sxs-lookup"><span data-stu-id="80497-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="80497-168">对于实体 eCommerceContacts，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="80497-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="80497-169">对于实体 loyCustomers，在下拉列表中选择 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="80497-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="80497-170">将“标准化”留空。</span><span class="sxs-lookup"><span data-stu-id="80497-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="80497-171">设置 **精度级别**：**基本** 和 **值**：**高**。</span><span class="sxs-lookup"><span data-stu-id="80497-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![统一名称和电子邮件的匹配规则。](media/unify-match-rule.png)

7. <span data-ttu-id="80497-173">选择 **保存** 和 **运行**。</span><span class="sxs-lookup"><span data-stu-id="80497-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="80497-174">合并​​</span><span class="sxs-lookup"><span data-stu-id="80497-174">Merge</span></span>

1. <span data-ttu-id="80497-175">转到 **合并** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="80497-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="80497-176">在 **loyCustomers** 实体的 **ContactId** 上，将显示名称更改为 **ContactIdLOYALTY** 以将其与引入的其他 ID 区分开。</span><span class="sxs-lookup"><span data-stu-id="80497-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![从忠诚度 ID 中重命名 contactid。](media/unify-merge-contactid.png)

1. <span data-ttu-id="80497-178">选择 **保存** 和 **运行** 以启动合并流程。</span><span class="sxs-lookup"><span data-stu-id="80497-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="80497-179">任务 3 - 配置产品建议预测</span><span class="sxs-lookup"><span data-stu-id="80497-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="80497-180">有了统一的客户配置文件，我们现在可以运行订阅流失预测。</span><span class="sxs-lookup"><span data-stu-id="80497-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="80497-181">转到 **智能** > **预测**，选择 **产品建议**。</span><span class="sxs-lookup"><span data-stu-id="80497-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="80497-182">选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="80497-182">Select **Get started**.</span></span>

1. <span data-ttu-id="80497-183">将模型命名为 **OOB 产品建议模型预测**，将输出实体命名为 **OOBProductReendationModelPrediproduct**。</span><span class="sxs-lookup"><span data-stu-id="80497-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="80497-184">定义模型的三个条件：</span><span class="sxs-lookup"><span data-stu-id="80497-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="80497-185">**产品数量**：将此值设置为 **5**。</span><span class="sxs-lookup"><span data-stu-id="80497-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="80497-186">此设置定义要推荐给客户的产品数。</span><span class="sxs-lookup"><span data-stu-id="80497-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="80497-187">**重复预期的购买**：选择 **是** 以表示您希望将客户以前购买过的产品包含在建议中。</span><span class="sxs-lookup"><span data-stu-id="80497-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="80497-188">**回看窗口：** 至少选择 **365 天**。</span><span class="sxs-lookup"><span data-stu-id="80497-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="80497-189">此设置定义模型回溯客户活动的时长以将其用作建议输入。</span><span class="sxs-lookup"><span data-stu-id="80497-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="产品建议模型的模型首选项。":::

1. <span data-ttu-id="80497-191">选择 **必需数据**，然后针对购买历史记录选择 **添加数据**。</span><span class="sxs-lookup"><span data-stu-id="80497-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="80497-192">添加 **eCommercePurchases：电子商务** 实体，并将电子商务中的字段映射到模型所需的相应字段。</span><span class="sxs-lookup"><span data-stu-id="80497-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="80497-193">使用 **eCommerceContacts：电子商务** 加入 **eCommercePurchases：电子商务** 实体。</span><span class="sxs-lookup"><span data-stu-id="80497-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![加入电子商务实体。](media/model-purchase-join.png)

1. <span data-ttu-id="80497-195">选择 **下一步** 以设置模型计划。</span><span class="sxs-lookup"><span data-stu-id="80497-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="80497-196">在引入新数据后，需要定期对模型进行定型以学习新模式。</span><span class="sxs-lookup"><span data-stu-id="80497-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="80497-197">对于此示例，请选择 **每月**。</span><span class="sxs-lookup"><span data-stu-id="80497-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="80497-198">在查看所有详细信息后，选择 **保存并运行**。</span><span class="sxs-lookup"><span data-stu-id="80497-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="80497-199">任务 4 - 审阅模型结果和说明</span><span class="sxs-lookup"><span data-stu-id="80497-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="80497-200">让模型完成数据的训练和评分。</span><span class="sxs-lookup"><span data-stu-id="80497-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="80497-201">您现在可以审阅产品建议模型说明。</span><span class="sxs-lookup"><span data-stu-id="80497-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="80497-202">有关详细信息，请参阅[审阅预测状态和结果](predict-subscription-churn.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="80497-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="80497-203">任务 5 - 创建热销产品的客户细分</span><span class="sxs-lookup"><span data-stu-id="80497-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="80497-204">运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。</span><span class="sxs-lookup"><span data-stu-id="80497-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="80497-205">您可以基于模型创建的实体创建新的客户细分。</span><span class="sxs-lookup"><span data-stu-id="80497-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="80497-206">转到 **客户细分**。</span><span class="sxs-lookup"><span data-stu-id="80497-206">Go to **Segments**.</span></span> <span data-ttu-id="80497-207">选择 **新建**，然后选择 **创建自** > **智能**。</span><span class="sxs-lookup"><span data-stu-id="80497-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![使用模型输出创建客户细分。](media/segment-intelligence.png)

1. <span data-ttu-id="80497-209">选择 **OOBProductRecommendationModelPrediction** 终结点并定义客户细分：</span><span class="sxs-lookup"><span data-stu-id="80497-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="80497-210">字段：ProductID</span><span class="sxs-lookup"><span data-stu-id="80497-210">Field: ProductID</span></span>
   - <span data-ttu-id="80497-211">运算符：值</span><span class="sxs-lookup"><span data-stu-id="80497-211">Operator: Value</span></span>
   - <span data-ttu-id="80497-212">值：选择前三个产品 ID</span><span class="sxs-lookup"><span data-stu-id="80497-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="利用模型结果创建客户细分。":::

<span data-ttu-id="80497-214">您现在具有一个动态更新的客户细分，它确定更愿意购买这三种推荐度最高的产品的客户</span><span class="sxs-lookup"><span data-stu-id="80497-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="80497-215">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="80497-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
