---
title: 交易流失预测
description: 预测客户是否存在不再购买您的产品或服务的风险。
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0e587739f9f4d03942d70a72de4f9378822054d
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095591"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="1a598-103">交易流失预测（预览）</span><span class="sxs-lookup"><span data-stu-id="1a598-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="1a598-104">交易流失预测可帮助预测客户是否在给定的时间范围内不再购买您的产品或服务。</span><span class="sxs-lookup"><span data-stu-id="1a598-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="1a598-105">您可以在 **智能** > **预测** 上创建新的流失预测。</span><span class="sxs-lookup"><span data-stu-id="1a598-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="1a598-106">选择 **我的预测** 以查看您已创建的其他预测。</span><span class="sxs-lookup"><span data-stu-id="1a598-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="1a598-107">请试用使用示例数据的交易流失预测的教程：[交易流失预测（预览）示例指南](sample-guide-predict-transactional-churn.md)。</span><span class="sxs-lookup"><span data-stu-id="1a598-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a598-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="1a598-108">Prerequisites</span></span>

- <span data-ttu-id="1a598-109">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="1a598-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1a598-110">具有了解流失对您的业务意味着什么所必需的商业知识。</span><span class="sxs-lookup"><span data-stu-id="1a598-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="1a598-111">我们支持基于时间的流失定义，这意味着客户在一段时间后没有进行购买就视为已流失。</span><span class="sxs-lookup"><span data-stu-id="1a598-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="1a598-112">有关您的交易/购买及其历史记录的数据：</span><span class="sxs-lookup"><span data-stu-id="1a598-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="1a598-113">用于区分交易/购买的交易标识符。</span><span class="sxs-lookup"><span data-stu-id="1a598-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="1a598-114">用于将交易匹配到客户的客户标识符。</span><span class="sxs-lookup"><span data-stu-id="1a598-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="1a598-115">交易事件日期，用于定义交易发生的日期。</span><span class="sxs-lookup"><span data-stu-id="1a598-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="1a598-116">购买/交易的语义数据架构需要以下信息：</span><span class="sxs-lookup"><span data-stu-id="1a598-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="1a598-117">**交易 ID：** 购买或交易的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1a598-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="1a598-118">**交易日期：** 购买或交易的日期。</span><span class="sxs-lookup"><span data-stu-id="1a598-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="1a598-119">**交易值：** 交易/商品的货币/数值金额。</span><span class="sxs-lookup"><span data-stu-id="1a598-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="1a598-120">（可选）**唯一产品 ID：** 购买的产品或服务的 ID（如果您的数据位于行项级别）。</span><span class="sxs-lookup"><span data-stu-id="1a598-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="1a598-121">（可选）**此交易是否有退货：** 用于确定交易是否有退货的 true/false 字段。</span><span class="sxs-lookup"><span data-stu-id="1a598-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="1a598-122">如果 **交易值** 为负值，我们还将使用此信息推断退货。</span><span class="sxs-lookup"><span data-stu-id="1a598-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="1a598-123">（可选）有关客户活动的数据：</span><span class="sxs-lookup"><span data-stu-id="1a598-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="1a598-124">用于区分相同类型的活动的活动标识符。</span><span class="sxs-lookup"><span data-stu-id="1a598-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="1a598-125">用于将活动映射到客户的客户标识符。</span><span class="sxs-lookup"><span data-stu-id="1a598-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="1a598-126">包含活动的名称和日期的活动信息。</span><span class="sxs-lookup"><span data-stu-id="1a598-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="1a598-127">客户活动的语义数据架构包括：</span><span class="sxs-lookup"><span data-stu-id="1a598-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="1a598-128">**主键：** 活动的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1a598-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="1a598-129">例如，显示客户试用了您的产品示例的网站访问或使用情况记录。</span><span class="sxs-lookup"><span data-stu-id="1a598-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="1a598-130">**时间戳：** 主键所标识事件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1a598-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="1a598-131">**事件：** 您要使用的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="1a598-132">例如，杂货店中称为“UserAction”的字段可能是供客户使用的优惠券。</span><span class="sxs-lookup"><span data-stu-id="1a598-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="1a598-133">**详细信息：** 有关事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1a598-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="1a598-134">例如，杂货店中称为“CouponValue”的字段可能是优惠券的货币值。</span><span class="sxs-lookup"><span data-stu-id="1a598-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>
- <span data-ttu-id="1a598-135">建议的数据特征：</span><span class="sxs-lookup"><span data-stu-id="1a598-135">Suggested data characteristics:</span></span>
    - <span data-ttu-id="1a598-136">足够的历史数据：交易数据至少是所选时间窗口数据的两倍。</span><span class="sxs-lookup"><span data-stu-id="1a598-136">Sufficient historical data: Transaction data for at least double the selected time window.</span></span> <span data-ttu-id="1a598-137">最好是两到三年的订阅数据。</span><span class="sxs-lookup"><span data-stu-id="1a598-137">Preferably, two to three years of subscription data.</span></span> 
    - <span data-ttu-id="1a598-138">每个客户多项购买：理想情况下，每个客户至少要进行两次交易。</span><span class="sxs-lookup"><span data-stu-id="1a598-138">Multiple purchases per customer: Ideally at least two transactions per customer.</span></span>
    - <span data-ttu-id="1a598-139">客户数量：至少 10 个客户配置文件，最好是超过 1,000 个唯一客户。</span><span class="sxs-lookup"><span data-stu-id="1a598-139">Number of customers: At least 10 customer profiles, preferably more than 1,000 unique customers.</span></span> <span data-ttu-id="1a598-140">该模型将因客户少于 10 个以及历史数据不足而失败。</span><span class="sxs-lookup"><span data-stu-id="1a598-140">The model will fail with fewer than 10 customers and insufficient historical data.</span></span>
    - <span data-ttu-id="1a598-141">数据完整性：在提供的实体的数据字段中，缺失值的不足 20%。</span><span class="sxs-lookup"><span data-stu-id="1a598-141">Data completeness: Less than 20% of missing values in the data field of the entity provided.</span></span>

> [!NOTE]
> <span data-ttu-id="1a598-142">对于客户购买频率较高（每几周一次）的企业，建议选择较短的预测窗口和流失定义。</span><span class="sxs-lookup"><span data-stu-id="1a598-142">For a business with high customer purchase frequency (every few weeks) it's recommended to select a shorter prediction window and churn definition.</span></span> <span data-ttu-id="1a598-143">如果购买频率较低（几个月或一年一次），请选择较长的预测窗口和流失定义。</span><span class="sxs-lookup"><span data-stu-id="1a598-143">For low purchase frequency (every few months or once a year), choose a longer prediction window and churn definition.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="1a598-144">创建交易流失预测</span><span class="sxs-lookup"><span data-stu-id="1a598-144">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="1a598-145">在 Customer Insights 中，转到 **智能** > **预测**。</span><span class="sxs-lookup"><span data-stu-id="1a598-145">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="1a598-146">选择 **客户流失模型（预览）** 磁贴并选择 **使用此模型**。</span><span class="sxs-lookup"><span data-stu-id="1a598-146">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="1a598-147">在 **客户流失模型** 窗格中，选择 **交易** 并选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="1a598-147">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="显示客户流失模型窗格中的所选交易选项的屏幕截图。":::

### <a name="name-model"></a><span data-ttu-id="1a598-149">命名模型</span><span class="sxs-lookup"><span data-stu-id="1a598-149">Name model</span></span>

1. <span data-ttu-id="1a598-150">为模型提供一个名称，以区别于其他模型。</span><span class="sxs-lookup"><span data-stu-id="1a598-150">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="1a598-151">仅使用字母和数字（不使用任何空格）为输出实体提供名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-151">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="1a598-152">这是模型实体将使用的名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-152">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="1a598-153">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a598-153">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="1a598-154">定义客户流失</span><span class="sxs-lookup"><span data-stu-id="1a598-154">Define customer churn</span></span>

1. <span data-ttu-id="1a598-155">在 **确定在接下来的时间可能流失的客户** 字段中设置预测流失的时间段。</span><span class="sxs-lookup"><span data-stu-id="1a598-155">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="1a598-156">例如，预测客户在接下来的 90 天内流失的风险，以调整您的市场营销保留工作。</span><span class="sxs-lookup"><span data-stu-id="1a598-156">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="1a598-157">预测更长时间段或更短时间段的风险流失会更难解决流失风险配置文件中的因素，但这取决于您的特定业务需求。</span><span class="sxs-lookup"><span data-stu-id="1a598-157">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="1a598-158">您可以随时选择 **保存并关闭** 以将预测保存为草稿。</span><span class="sxs-lookup"><span data-stu-id="1a598-158">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="1a598-159">您可以在 **我的预测** 选项卡中查找草稿预测以继续操作。</span><span class="sxs-lookup"><span data-stu-id="1a598-159">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="1a598-160">在 **客户在以下时间段内未进行购买而流失：** 字段中输入天数以定义流失。</span><span class="sxs-lookup"><span data-stu-id="1a598-160">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="1a598-161">例如，如果客户在最近 30 天内未进行购买，针对您的业务，可能会将他们视为已流失。</span><span class="sxs-lookup"><span data-stu-id="1a598-161">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="1a598-162">选择 **下一步** 继续操作</span><span class="sxs-lookup"><span data-stu-id="1a598-162">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="1a598-163">添加所需数据</span><span class="sxs-lookup"><span data-stu-id="1a598-163">Add required data</span></span>

1. <span data-ttu-id="1a598-164">针对 **购买历史记录** 选择 **添加数据**，然后选择提供交易/购买历史记录信息的实体，如[先决条件](#prerequisites)中所述。</span><span class="sxs-lookup"><span data-stu-id="1a598-164">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="1a598-165">将语义字段映射到购买历史记录实体中的属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a598-165">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="1a598-166">有关字段的说明，请查看[先决条件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="1a598-166">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="映射购买实体的语义字段。":::

1. <span data-ttu-id="1a598-168">如果以下字段未填充，请配置购买历史记录实体与客户实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="1a598-168">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="1a598-169">选择 **购买历史记录实体**。</span><span class="sxs-lookup"><span data-stu-id="1a598-169">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="1a598-170">在购买历史记录实体中选择用于标识客户的 **字段**。</span><span class="sxs-lookup"><span data-stu-id="1a598-170">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="1a598-171">它需要与您的客户实体的主要客户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="1a598-171">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="1a598-172">选择与您的主要客户实体相匹配的 **客户实体**。</span><span class="sxs-lookup"><span data-stu-id="1a598-172">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="1a598-173">输入一个用于描述关系的名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-173">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="显示创建与客户的关系的购买历史记录页面。":::
   
1. <span data-ttu-id="1a598-175">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a598-175">Select **Next**.</span></span>

1. <span data-ttu-id="1a598-176">或者，针对 **客户活动** 选择 **添加数据**。</span><span class="sxs-lookup"><span data-stu-id="1a598-176">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="1a598-177">选择提供客户活动信息的实体，如先决条件中所述。</span><span class="sxs-lookup"><span data-stu-id="1a598-177">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="1a598-178">将语义字段映射到客户活动实体中的属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a598-178">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="1a598-179">有关字段的说明，请查看[先决条件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="1a598-179">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="映射交易数据的客户字段。":::

1. <span data-ttu-id="1a598-181">选择与您要配置的客户活动类型匹配的活动类型。</span><span class="sxs-lookup"><span data-stu-id="1a598-181">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="1a598-182">选择 **新建**，然后选择可用活动类型或创建新类型。</span><span class="sxs-lookup"><span data-stu-id="1a598-182">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="1a598-183">您需要配置客户活动实体与客户实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="1a598-183">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="1a598-184">在客户实体表中选择用于标识客户的字段。</span><span class="sxs-lookup"><span data-stu-id="1a598-184">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="1a598-185">可直接与客户实体的主要客户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="1a598-185">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="1a598-186">选择与您的主要客户实体相匹配的客户实体</span><span class="sxs-lookup"><span data-stu-id="1a598-186">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="1a598-187">输入一个用于描述关系的名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-187">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="1a598-188">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="1a598-188">Select **Save**.</span></span>

1. <span data-ttu-id="1a598-189">如果您有任何要包括的其他客户活动，请重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="1a598-189">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="1a598-190">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a598-190">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="1a598-191">设置计划与查看配置</span><span class="sxs-lookup"><span data-stu-id="1a598-191">Set schedule and review configuration</span></span>

1. <span data-ttu-id="1a598-192">设置频率以重新训练您的模型。</span><span class="sxs-lookup"><span data-stu-id="1a598-192">Set a frequency to retrain your model.</span></span> <span data-ttu-id="1a598-193">引入新数据时，若要更新预测的准确性，此设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="1a598-193">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="1a598-194">大多数企业每个月可以重新进行一次训练，并取得良好的预测准确度。</span><span class="sxs-lookup"><span data-stu-id="1a598-194">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="1a598-195">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a598-195">Select **Next**.</span></span>

1. <span data-ttu-id="1a598-196">查看预测的配置。</span><span class="sxs-lookup"><span data-stu-id="1a598-196">Review the configuration of the prediction.</span></span> <span data-ttu-id="1a598-197">您可以通过选择显示值下面的 **编辑** 返回到前面的步骤。</span><span class="sxs-lookup"><span data-stu-id="1a598-197">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="1a598-198">或者，您也可以从进度指示器中选择配置步骤。</span><span class="sxs-lookup"><span data-stu-id="1a598-198">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="1a598-199">如果正确配置了所有值，请选择 **保存并运行** 以开始预测过程。</span><span class="sxs-lookup"><span data-stu-id="1a598-199">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="1a598-200">在 **我的预测** 选项卡上，您可以查看预测的状态。</span><span class="sxs-lookup"><span data-stu-id="1a598-200">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="1a598-201">完成该过程可能需要几个小时，具体取决于预测中使用的数据量。</span><span class="sxs-lookup"><span data-stu-id="1a598-201">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="1a598-202">查看预测状态和结果</span><span class="sxs-lookup"><span data-stu-id="1a598-202">Review a prediction status and results</span></span>

1. <span data-ttu-id="1a598-203">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1a598-203">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1a598-204">选择要查看的预测。</span><span class="sxs-lookup"><span data-stu-id="1a598-204">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="1a598-205">**预测名称：** 创建时提供的预测的名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-205">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="1a598-206">**预测类型：** 用于预测的模型的类型</span><span class="sxs-lookup"><span data-stu-id="1a598-206">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="1a598-207">**输出实体：** 用于存储预测输出的实体的名称。</span><span class="sxs-lookup"><span data-stu-id="1a598-207">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="1a598-208">您可以在 **数据** > **实体** 中查找具有此名称的实体。</span><span class="sxs-lookup"><span data-stu-id="1a598-208">You can find an entity with this name on **Data** > **Entities**.</span></span>    
     <span data-ttu-id="1a598-209">在输出实体中，*ChurnScore* 是预测的流失概率，*IsChurn* 是基于 *ChurnScore* 的二进制标签，阈值为 0.5。</span><span class="sxs-lookup"><span data-stu-id="1a598-209">In the output entity, *ChurnScore* is the predicted probability of churn and *IsChurn* is a binary label based on *ChurnScore* with 0.5 threshold.</span></span> <span data-ttu-id="1a598-210">默认阈值可能不适合您的方案。</span><span class="sxs-lookup"><span data-stu-id="1a598-210">The default threshold might not work for your scenario.</span></span> <span data-ttu-id="1a598-211">使用首选阈值[创建新客户细分](segments.md#create-a-new-segment)。</span><span class="sxs-lookup"><span data-stu-id="1a598-211">[Create a new segment](segments.md#create-a-new-segment) with your preferred threshold.</span></span>
     <span data-ttu-id="1a598-212">并非所有客户都一定是活跃客户。</span><span class="sxs-lookup"><span data-stu-id="1a598-212">Not all customers are necessarily active customers.</span></span> <span data-ttu-id="1a598-213">他们中的一些人可能很长一段时间没有活动，根据你的流失定义被认为是已经流失。</span><span class="sxs-lookup"><span data-stu-id="1a598-213">Some of them may not have had any activity for a long time and are considered as churned already, based on you churn definition.</span></span> <span data-ttu-id="1a598-214">预测已经流失的客户的流失风险是没有用的，因为这些客户不是兴趣的受众。</span><span class="sxs-lookup"><span data-stu-id="1a598-214">Predicting the churn risk for customers who already churned isn't useful because the are not the audience of interest.</span></span>
   - <span data-ttu-id="1a598-215">**预测字段：** 仅针对某些类型的预测填充此字段，而不在流失预测中使用它。</span><span class="sxs-lookup"><span data-stu-id="1a598-215">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="1a598-216">**状态：** 预测运行的状态。</span><span class="sxs-lookup"><span data-stu-id="1a598-216">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="1a598-217">**已排队：** 预测正在等待其他流程运行。</span><span class="sxs-lookup"><span data-stu-id="1a598-217">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="1a598-218">**刷新：** 预测当前正在运行，以生成将流入输出实体的结果。</span><span class="sxs-lookup"><span data-stu-id="1a598-218">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="1a598-219">**失败：** 预测运行已失败。</span><span class="sxs-lookup"><span data-stu-id="1a598-219">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="1a598-220">有关更多详细信息，请[查看日志](manage-predictions.md#troubleshoot-a-failed-prediction)。</span><span class="sxs-lookup"><span data-stu-id="1a598-220">[Review the logs](manage-predictions.md#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="1a598-221">**已成功：** 预测已成功。</span><span class="sxs-lookup"><span data-stu-id="1a598-221">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="1a598-222">在垂直省略号下选择 **查看** 以查看预测</span><span class="sxs-lookup"><span data-stu-id="1a598-222">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="1a598-223">**已编辑：** 预测配置的更改日期。</span><span class="sxs-lookup"><span data-stu-id="1a598-223">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="1a598-224">**上次刷新**：预测刷新输出实体中的结果的日期。</span><span class="sxs-lookup"><span data-stu-id="1a598-224">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="1a598-225">选择要查看其结果的预测旁边的垂直省略号并选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="1a598-225">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="查看控件以查看预测的结果。":::   

1. <span data-ttu-id="1a598-227">结果页中有三个主要部分的数据：</span><span class="sxs-lookup"><span data-stu-id="1a598-227">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="1a598-228">**训练模型的性能：** A、B 或 C 为可能的分数。</span><span class="sxs-lookup"><span data-stu-id="1a598-228">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="1a598-229">此分数指示预测的性能，并可帮助您做出关于使用输出实体中存储的结果的决策。</span><span class="sxs-lookup"><span data-stu-id="1a598-229">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="1a598-230">根据以下规则确定分数：</span><span class="sxs-lookup"><span data-stu-id="1a598-230">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="1a598-231">**A** 当模型准确预测总预测的至少 50% 时，以及当已流失客户的准确预测百分比大于基线率至少 10% 时。</span><span class="sxs-lookup"><span data-stu-id="1a598-231">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="1a598-232">**B** 当模型准确预测总预测的至少 50% 时，以及当已流失客户的准确预测百分比大于基线最多 10% 时。</span><span class="sxs-lookup"><span data-stu-id="1a598-232">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="1a598-233">**C** 当模型准确预测总预测的不足 50% 时，或者当已流失客户的准确预测百分比小于基线时。</span><span class="sxs-lookup"><span data-stu-id="1a598-233">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="1a598-234">**基线** 使用模型的预测时间范围输入（例如一年），并且模型将通过除以 2 创建不同的时间分数，直到它达到一个月或更短的时间。</span><span class="sxs-lookup"><span data-stu-id="1a598-234">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="1a598-235">它使用这些分数为尚未在此期限内进行购买的客户创建业务规则。</span><span class="sxs-lookup"><span data-stu-id="1a598-235">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="1a598-236">这些客户将视为已流失。</span><span class="sxs-lookup"><span data-stu-id="1a598-236">These customers are considered as churned.</span></span> <span data-ttu-id="1a598-237">选择基于时间的业务规则作为基线模型，该规则可最大程度地预测可能流失的人员。</span><span class="sxs-lookup"><span data-stu-id="1a598-237">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="1a598-238">**流失的可能性（客户数量）：** 基于预测的客户流失风险的客户组。</span><span class="sxs-lookup"><span data-stu-id="1a598-238">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="1a598-239">如果您要创建具有高流失风险的客户细分，此数据可以在以后为您提供帮助。</span><span class="sxs-lookup"><span data-stu-id="1a598-239">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="1a598-240">此类客户细分有助于了解客户细分成员资格应在何处截止。</span><span class="sxs-lookup"><span data-stu-id="1a598-240">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="1a598-241">**最具影响力的因素：** 创建预测时考虑了许多因素。</span><span class="sxs-lookup"><span data-stu-id="1a598-241">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="1a598-242">每个因素都有针对模型所创建的聚合预测而计算的重要性。</span><span class="sxs-lookup"><span data-stu-id="1a598-242">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="1a598-243">您可以使用这些因素帮助验证预测结果。</span><span class="sxs-lookup"><span data-stu-id="1a598-243">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="1a598-244">或者，您也可以在以后使用该信息[创建客户细分](segments.md)，这些客户细分可能有助于影响客户流失风险。</span><span class="sxs-lookup"><span data-stu-id="1a598-244">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="manage-predictions"></a><span data-ttu-id="1a598-245">管理预测</span><span class="sxs-lookup"><span data-stu-id="1a598-245">Manage predictions</span></span>

<span data-ttu-id="1a598-246">可以对预测进行优化、排除故障、刷新或删除。</span><span class="sxs-lookup"><span data-stu-id="1a598-246">It's possible to optimize, troubleshoot, refresh, or delete predictions.</span></span> <span data-ttu-id="1a598-247">查看输入数据可用性报告，了解如何更快、更可靠地进行预测。</span><span class="sxs-lookup"><span data-stu-id="1a598-247">Review an input data usability report to find out how to make a prediction faster and more reliable.</span></span> <span data-ttu-id="1a598-248">有关详细信息，请参阅[管理预测](manage-predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="1a598-248">For more information, see [Manage predictions](manage-predictions.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
