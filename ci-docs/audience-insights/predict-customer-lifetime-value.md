---
title: 客户生命周期值 (CLV) 预测
description: 预测未来活跃客户的潜在收入。
ms.date: 02/05/2021
ms.reviewer: wameng
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 363a46c81b5bb737d274998f9a699dc662e38d7c
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268583"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a><span data-ttu-id="2f19e-103">客户生存期值 (CLV) 预测（预览版）</span><span class="sxs-lookup"><span data-stu-id="2f19e-103">Customer lifetime value (CLV) prediction (Preview)</span></span>

<span data-ttu-id="2f19e-104">预测单个活跃客户将在定义的未来时间段内为您的公司带来的潜在价值（收入）。</span><span class="sxs-lookup"><span data-stu-id="2f19e-104">Predict potential value (revenue) that individual active customers will bring in to your business through a defined future time period.</span></span> <span data-ttu-id="2f19e-105">此功能可帮助您实现各种目标：</span><span class="sxs-lookup"><span data-stu-id="2f19e-105">This feature can help you achieve various goals:</span></span> 
- <span data-ttu-id="2f19e-106">识别高价值客户并处理此见解</span><span class="sxs-lookup"><span data-stu-id="2f19e-106">Identify high-value customers and process this insight</span></span>
- <span data-ttu-id="2f19e-107">根据潜在客户价值创建战略客户细分，以通过有针对性的销售、市场营销和支持工作开展个性化市场活动</span><span class="sxs-lookup"><span data-stu-id="2f19e-107">Create strategical customer segments based on their potential value to run personalized campaigns with targeted sales, marketing, and support efforts</span></span>
- <span data-ttu-id="2f19e-108">通过关注增加客户价值的功能来指导产品开发</span><span class="sxs-lookup"><span data-stu-id="2f19e-108">Guide product development by focusing on features tht increase customer value</span></span>
- <span data-ttu-id="2f19e-109">优化销售或营销策略并更准确地分配预算以进行客户拓展</span><span class="sxs-lookup"><span data-stu-id="2f19e-109">Optimize sales or marketing strategy and allocate budget more accurately for customer outreach</span></span>
- <span data-ttu-id="2f19e-110">通过忠诚度或奖励计划表彰和奖励高价值客户</span><span class="sxs-lookup"><span data-stu-id="2f19e-110">Recognize and reward high-value customers through loyalty or rewards programs</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2f19e-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="2f19e-111">Prerequisites</span></span>

<span data-ttu-id="2f19e-112">在开始之前，请先思考 CLV 对您的业务意味着什么。</span><span class="sxs-lookup"><span data-stu-id="2f19e-112">Before getting started, reflect what CLV means for your business.</span></span> <span data-ttu-id="2f19e-113">目前，我们支持基于交易的 CLV 预测。</span><span class="sxs-lookup"><span data-stu-id="2f19e-113">Currently, we support transaction-based CLV prediction.</span></span> <span data-ttu-id="2f19e-114">预测的客户价值基于业务交易的历史记录。</span><span class="sxs-lookup"><span data-stu-id="2f19e-114">The predicted value of a customer is based on history of business transactions.</span></span> <span data-ttu-id="2f19e-115">若要创建预测，至少需要[参与者](permissions.md)权限。</span><span class="sxs-lookup"><span data-stu-id="2f19e-115">To create the prediction, you need at least [Contributor](permissions.md) permissions.</span></span>

<span data-ttu-id="2f19e-116">由于配置和运行 CLV 模型不需要花费很多时间，因此，请考虑创建具有不同输入首选项的多个模型，并比较模型结果，以查看哪种模型方案最能够满足您的业务需要。</span><span class="sxs-lookup"><span data-stu-id="2f19e-116">Since configuring and running a CLV model doesn't take much time, consider creating several models with varying input preferences and compare model results to see which model scenario best fits your business needs.</span></span>

###  <a name="data-requirements"></a><span data-ttu-id="2f19e-117">数据要求</span><span class="sxs-lookup"><span data-stu-id="2f19e-117">Data requirements</span></span>

<span data-ttu-id="2f19e-118">必须提供以下数据，如果数据被标记为可选，建议提供该数据，以提高模型性能。</span><span class="sxs-lookup"><span data-stu-id="2f19e-118">The following data is required, and where marked optional, recommended for increased model performance.</span></span> <span data-ttu-id="2f19e-119">模型能够处理的数据越多，预测就越准确。</span><span class="sxs-lookup"><span data-stu-id="2f19e-119">The more data the model can process, the more accurate the prediction will be.</span></span> <span data-ttu-id="2f19e-120">因此，我们鼓励您引入更多客户活动数据（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="2f19e-120">Therefore, we encourage you to ingest more customer activity data, if available.</span></span>

- <span data-ttu-id="2f19e-121">客户标识符：用于将交易与单个客户匹配的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2f19e-121">Customer Identifier: Unique identifier to match transactions to an individual customer</span></span>

- <span data-ttu-id="2f19e-122">交易历史记录：具有以下语义数据架构的历史交易日志</span><span class="sxs-lookup"><span data-stu-id="2f19e-122">Transaction History: Historical transactions log with below semantic data schema</span></span>
    - <span data-ttu-id="2f19e-123">交易 ID：每个交易的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2f19e-123">Transaction ID: Unique identifier of each transaction</span></span>
    - <span data-ttu-id="2f19e-124">交易日期：日期（最好是每个交易的时间戳）</span><span class="sxs-lookup"><span data-stu-id="2f19e-124">Transaction date: Date, preferably a time stamp of each transaction</span></span>
    - <span data-ttu-id="2f19e-125">交易金额：每个交易的货币价值（如收入或利润）</span><span class="sxs-lookup"><span data-stu-id="2f19e-125">Transaction amount: Monetary value (for example, revenue or profit margin) of each transaction</span></span>
    - <span data-ttu-id="2f19e-126">分派给退货的标签（可选）：用于表示交易是否为退货交易的布尔值</span><span class="sxs-lookup"><span data-stu-id="2f19e-126">Label assigned to returns (optional): Boolean value signifying whether the transaction is a return</span></span> 
    - <span data-ttu-id="2f19e-127">产品 ID（可选）：交易涉及的产品的产品 ID</span><span class="sxs-lookup"><span data-stu-id="2f19e-127">Product ID (optional): Product ID of product involved in the transaction</span></span>

- <span data-ttu-id="2f19e-128">例如，其他数据（可选）</span><span class="sxs-lookup"><span data-stu-id="2f19e-128">Additional data (optional), for example</span></span>
    - <span data-ttu-id="2f19e-129">Web 活动：网站访问历史记录、电子邮件历史记录</span><span class="sxs-lookup"><span data-stu-id="2f19e-129">Web activities: website visit history, email history</span></span>
    - <span data-ttu-id="2f19e-130">忠诚度活动：忠诚度奖励积分累积和兑换历史记录</span><span class="sxs-lookup"><span data-stu-id="2f19e-130">Loyalty activities: loyalty reward points accrual and redemption history</span></span>
    - <span data-ttu-id="2f19e-131">客户服务日志、服务请求、投诉或退货历史记录</span><span class="sxs-lookup"><span data-stu-id="2f19e-131">Customer service log, service call, complaint, or return history</span></span>
- <span data-ttu-id="2f19e-132">有关客户活动的数据（可选）：</span><span class="sxs-lookup"><span data-stu-id="2f19e-132">Data about customer activities (optional):</span></span>
    - <span data-ttu-id="2f19e-133">用于区分相同类型的活动的活动标识符</span><span class="sxs-lookup"><span data-stu-id="2f19e-133">Activity identifiers to distinguish activities of the same type</span></span>
    - <span data-ttu-id="2f19e-134">用于将活动映射到客户的客户标识符</span><span class="sxs-lookup"><span data-stu-id="2f19e-134">Customer identifiers to map activities to your customers</span></span>
    - <span data-ttu-id="2f19e-135">包含活动的名称和日期的活动信息</span><span class="sxs-lookup"><span data-stu-id="2f19e-135">Activity information containing the name and date of the activity</span></span>
    - <span data-ttu-id="2f19e-136">活动的语义数据架构包括：</span><span class="sxs-lookup"><span data-stu-id="2f19e-136">The semantic data schema for activities includes:</span></span> 
        - <span data-ttu-id="2f19e-137">主键：活动的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2f19e-137">Primary key: A unique identifier for an activity</span></span>
        - <span data-ttu-id="2f19e-138">时间戳：主键所标识事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="2f19e-138">Timestamp: The date and time of the event identified by the primary key</span></span>
        - <span data-ttu-id="2f19e-139">事件（活动名称）：要使用的事件名称</span><span class="sxs-lookup"><span data-stu-id="2f19e-139">Event (activity name):  The name of event you want to use</span></span>
        - <span data-ttu-id="2f19e-140">详细信息（金额或值）：有关客户活动的详细信息</span><span class="sxs-lookup"><span data-stu-id="2f19e-140">Details (amount or value): Details about the customer activity</span></span>

## <a name="create-a-customer-lifetime-value-prediction"></a><span data-ttu-id="2f19e-141">创建客户生存期值预测</span><span class="sxs-lookup"><span data-stu-id="2f19e-141">Create a Customer Lifetime Value prediction</span></span>

1. <span data-ttu-id="2f19e-142">在访问群体见解中，转到 **智能** > **预测**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-142">In audience insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="2f19e-143">选择 **客户生存期值** 磁贴并选择 **使用模型**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-143">Select the **Customer lifetime value** tile and select **Use model**.</span></span> 

1. <span data-ttu-id="2f19e-144">在 **客户生存期值（预览版）** 窗格中，选择 **入门**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-144">In the **Customer lifetime value (preview)** pane, select **Get started**.</span></span>

1. <span data-ttu-id="2f19e-145">用于与其他模型或实体区分开来的 **为此模型命名** 和 **输出实体名称**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-145">**Name this model** and the **Output entity name** to distinguish them from other models or entities.</span></span>

1. <span data-ttu-id="2f19e-146">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-146">Select **Next**.</span></span>

### <a name="define-model-preferences"></a><span data-ttu-id="2f19e-147">定义模型首选项</span><span class="sxs-lookup"><span data-stu-id="2f19e-147">Define model preferences</span></span>

1. <span data-ttu-id="2f19e-148">设置 **预测时间段**，以定义要预测 CLV 的未来时长。</span><span class="sxs-lookup"><span data-stu-id="2f19e-148">Set a **Prediction time period** to define how far into the future you want to predict the CLV.</span></span>    
   <span data-ttu-id="2f19e-149">默认情况下，单位设置为月。</span><span class="sxs-lookup"><span data-stu-id="2f19e-149">By default, the unit is set as months.</span></span> <span data-ttu-id="2f19e-150">您可以将它更改为年以预测更长的未来时间。</span><span class="sxs-lookup"><span data-stu-id="2f19e-150">You can change it to years to look further in the future.</span></span>

   > [!TIP]
   > <span data-ttu-id="2f19e-151">若要准确预测所设置的时间段的 CLV，您需要具有一个相似的历史数据期间。</span><span class="sxs-lookup"><span data-stu-id="2f19e-151">To accurately predict CLV for the time period you set, you need a comparable period of historical data.</span></span> <span data-ttu-id="2f19e-152">例如，如果您希望预测未来 12 个月，则建议您至少具有 18 – 24 个月的历史数据。</span><span class="sxs-lookup"><span data-stu-id="2f19e-152">For example, if you want to predict for the next 12 months, it is recommended that you have at least 18 – 24 months of historical data.</span></span>

1. <span data-ttu-id="2f19e-153">指定 **活跃客户** 对您的业务的意义。</span><span class="sxs-lookup"><span data-stu-id="2f19e-153">Specify what **Active customers** mean for your business.</span></span> <span data-ttu-id="2f19e-154">设置期限，在该期限内，客户必须至少有一笔交易被视为处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f19e-154">Set the time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="2f19e-155">该模型将只预测活跃客户的 CLV。</span><span class="sxs-lookup"><span data-stu-id="2f19e-155">The model will only predict CLV for active customers.</span></span> 
   - <span data-ttu-id="2f19e-156">**让模型计算购买间隔（推荐）**：模型将分析您的数据，并根据过去的购买数据来确定时间段。</span><span class="sxs-lookup"><span data-stu-id="2f19e-156">**Let model calculate purchase interval (recommended)**: The model analyzes your data and determines a time period based on historical purchases.</span></span>
   - <span data-ttu-id="2f19e-157">**手动设置时隔**：如果您具有活跃客户的特定业务定义，请选择此选项并相应地设置时间段。</span><span class="sxs-lookup"><span data-stu-id="2f19e-157">**Set interval manually**: If you have a specific business definition of an active customer, choose this option and set the time period accordingly.</span></span>

1. <span data-ttu-id="2f19e-158">定义 **高价值客户** 的百分位数，以使模型能够提供符合业务定义的结果。</span><span class="sxs-lookup"><span data-stu-id="2f19e-158">Define percentile of **High-value customer** to enable the model to provide results that fit your business definition.</span></span>
    - <span data-ttu-id="2f19e-159">**模型计算（推荐）**：该模型会分析您的数据，并根据客户的交易历史记录确定对您的业务而言什么样的客户可能是高价值客户。</span><span class="sxs-lookup"><span data-stu-id="2f19e-159">**Model calculation (recommended)**: The model analyzes your data and determines what a high value customer might be for your business based on your customers’ transaction history.</span></span> <span data-ttu-id="2f19e-160">模型使用启发式规则（受 80/20 规则或一致原则启发）来查找高价值客户的比例。</span><span class="sxs-lookup"><span data-stu-id="2f19e-160">The model uses a heuristic rule (inspired by the 80/20 rule or pareto principle) to find the proportion of high-value customers.</span></span> <span data-ttu-id="2f19e-161">历史期间内为您的业务贡献了 80% 的累积收入的那部分客户被认为是高价值客户。</span><span class="sxs-lookup"><span data-stu-id="2f19e-161">The percentage of customers that contributed to 80% cumulative revenue for your business in the historical period are considered high-value customers.</span></span> <span data-ttu-id="2f19e-162">通常，不到 30-40% 的客户将贡献 80% 的累积收入。</span><span class="sxs-lookup"><span data-stu-id="2f19e-162">Typically, less than 30-40% customers contribute to 80% cumulative revenue.</span></span> <span data-ttu-id="2f19e-163">不过，此数字可能会因您的业务和行业而异。</span><span class="sxs-lookup"><span data-stu-id="2f19e-163">However, this number might vary depending on your business and industry.</span></span>    
    - <span data-ttu-id="2f19e-164">**排名靠前的活跃客户所占百分比**：将您的业务高价值客户定义为付款最活跃客户的百分位数。</span><span class="sxs-lookup"><span data-stu-id="2f19e-164">**Percent of top active customers**: Define high-value customers for your business as a percentile of top active paying customers.</span></span> <span data-ttu-id="2f19e-165">例如，可以使用此选项将高价值客户定义为前 20% 的未来付费客户。</span><span class="sxs-lookup"><span data-stu-id="2f19e-165">For example, you can use this option to define high-value customers as top 20% of future paying customers.</span></span>

    <span data-ttu-id="2f19e-166">如果您的公司以不同方式定义高价值客户，[请告诉我们，因为我们很想知道](https://go.microsoft.com/fwlink/?linkid=2074172)。</span><span class="sxs-lookup"><span data-stu-id="2f19e-166">If your business defines high value customers in a different way, [let us know as we would love to hear](https://go.microsoft.com/fwlink/?linkid=2074172).</span></span>

1. <span data-ttu-id="2f19e-167">选择 **下一步** 以继续进行下一步。</span><span class="sxs-lookup"><span data-stu-id="2f19e-167">Select **Next** to proceed to the next step.</span></span>

### <a name="add-required-data"></a><span data-ttu-id="2f19e-168">添加所需数据</span><span class="sxs-lookup"><span data-stu-id="2f19e-168">Add required data</span></span>

1. <span data-ttu-id="2f19e-169">在 **所需数据** 步骤中，针对 **客户交易历史记录** 选择 **添加数据**，然后选择提供交易历史记录信息的实体，如[先决条件](#prerequisites)中所述。</span><span class="sxs-lookup"><span data-stu-id="2f19e-169">In the **Required data** step, select **Add data** for **Customer transaction history** and choose the entity that provides the transaction history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="2f19e-170">将语义字段映射到购买历史记录实体中的属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-170">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="用于映射所需数据的数据属性的配置步骤图像。":::
 
1. <span data-ttu-id="2f19e-172">如果以下字段未填充，请配置购买历史记录实体与 *客户* 实体之间的关系，并选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-172">If the fields below aren't populated, configure the relationship from your purchase history entity to the *Customer* entity and select **Save**.</span></span>
    1. <span data-ttu-id="2f19e-173">选择交易历史记录实体。</span><span class="sxs-lookup"><span data-stu-id="2f19e-173">Select the transaction history entity.</span></span>
    1. <span data-ttu-id="2f19e-174">在购买历史记录实体中选择用于标识客户的字段。</span><span class="sxs-lookup"><span data-stu-id="2f19e-174">Select the field that identifies a customer in the purchase history entity.</span></span> <span data-ttu-id="2f19e-175">它需要与您的客户实体的主要客户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="2f19e-175">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="2f19e-176">选择与主要客户实体匹配的实体。</span><span class="sxs-lookup"><span data-stu-id="2f19e-176">Select the entity that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="2f19e-177">输入一个用于描述关系的名称。</span><span class="sxs-lookup"><span data-stu-id="2f19e-177">Enter a name that describes the relationship.</span></span>

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="用于定义与客户实体之间的关系的配置步骤图像。":::

1. <span data-ttu-id="2f19e-179">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-179">Select **Next**.</span></span>

### <a name="add-optional-data"></a><span data-ttu-id="2f19e-180">添加可选数据</span><span class="sxs-lookup"><span data-stu-id="2f19e-180">Add optional data</span></span>

<span data-ttu-id="2f19e-181">反映关键客户交互的数据（如 Web、客户服务和事件日志）会将上下文添加到交易记录中。</span><span class="sxs-lookup"><span data-stu-id="2f19e-181">Data reflecting key customer interactions (like web, customer service, and event logs) adds context to transaction records.</span></span> <span data-ttu-id="2f19e-182">在客户活动数据中发现的更多模式可以提高预测的准确性。</span><span class="sxs-lookup"><span data-stu-id="2f19e-182">More patterns found in your customer activity data can improve the accuracy of the predictions.</span></span> 

1. <span data-ttu-id="2f19e-183">在 **其他数据（可选）** 步骤中，选择 **添加数据**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-183">In the **Additional data (optional)** step, select **Add data**.</span></span> <span data-ttu-id="2f19e-184">选择提供客户活动信息的客户活动实体，如[先决条件](#prerequisites)中所述。</span><span class="sxs-lookup"><span data-stu-id="2f19e-184">Choose the customer activity entity that provides the customer activity information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="2f19e-185">将语义字段映射到客户活动实体中的属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-185">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="用于映射其他数据的字段的配置步骤图像。":::

1. <span data-ttu-id="2f19e-187">选择与要添加的客户活动类型匹配的活动类型。</span><span class="sxs-lookup"><span data-stu-id="2f19e-187">Select an activity type that matches the type of customer activity you're adding.</span></span> <span data-ttu-id="2f19e-188">从现有活动类型中选择或添加新的活动类型。</span><span class="sxs-lookup"><span data-stu-id="2f19e-188">Choose from existing activity types or add a new activity type.</span></span>

1. <span data-ttu-id="2f19e-189">配置客户活动实体与 *客户* 实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="2f19e-189">Configure the relationship from your customer activity entity to the *Customer* entity.</span></span>
    
    1. <span data-ttu-id="2f19e-190">在客户实体表中选择用于标识客户的字段。</span><span class="sxs-lookup"><span data-stu-id="2f19e-190">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="2f19e-191">它可能直接与 *客户* 实体的主要客户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="2f19e-191">It can be directly related to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="2f19e-192">选择与您的主要 *客户* 实体相匹配的 *客户* 实体。</span><span class="sxs-lookup"><span data-stu-id="2f19e-192">Select the *Customer* entity that matches your primary *Customer* entity.</span></span>
    1. <span data-ttu-id="2f19e-193">输入一个用于描述关系的名称。</span><span class="sxs-lookup"><span data-stu-id="2f19e-193">Enter a name that describes the relationship.</span></span>

   :::image type="content" source="media/clv-additional-data.png" alt-text="配置流中用于添加其他数据并使用示例中填充的数据配置活动的步骤图像。":::

1. <span data-ttu-id="2f19e-195">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-195">Select **Save**.</span></span>    
    <span data-ttu-id="2f19e-196">如果要包括其他客户活动，请添加更多数据。</span><span class="sxs-lookup"><span data-stu-id="2f19e-196">Add more data if there are other customer activities you want to include.</span></span>

1. <span data-ttu-id="2f19e-197">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-197">Select **Next**.</span></span>

### <a name="set-update-schedule"></a><span data-ttu-id="2f19e-198">设置更新计划</span><span class="sxs-lookup"><span data-stu-id="2f19e-198">Set update schedule</span></span>

1. <span data-ttu-id="2f19e-199">在 **数据更新计划** 步骤中，选择基于最新数据重新训练模型的频率。</span><span class="sxs-lookup"><span data-stu-id="2f19e-199">In the **Data update schedule** step, choose the frequency to retrain your model based on the latest data.</span></span> <span data-ttu-id="2f19e-200">在访问群体见解中引入新数据时，若要更新预测的准确性，此设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="2f19e-200">This setting is important to update the accuracy of predictions as new data is ingested in audience insights.</span></span> <span data-ttu-id="2f19e-201">大多数企业每个月可以重新进行一次训练，并取得良好的预测准确度。</span><span class="sxs-lookup"><span data-stu-id="2f19e-201">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="2f19e-202">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-202">Select **Next**.</span></span>


### <a name="review-and-run-the-model-configuration"></a><span data-ttu-id="2f19e-203">查看并运行模型配置</span><span class="sxs-lookup"><span data-stu-id="2f19e-203">Review and run the model configuration</span></span>

1. <span data-ttu-id="2f19e-204">在 **查看模型详细信息** 步骤中，验证预测配置。</span><span class="sxs-lookup"><span data-stu-id="2f19e-204">In the **Review your model details** step, validate the configuration of the prediction.</span></span> <span data-ttu-id="2f19e-205">通过在显示的值下面选择 **编辑**，可以返回到预测配置的任意部分。</span><span class="sxs-lookup"><span data-stu-id="2f19e-205">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="2f19e-206">您还可以从进度指示器中选择一个配置步骤。</span><span class="sxs-lookup"><span data-stu-id="2f19e-206">You can also select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="2f19e-207">如果正确配置了所有值，请选择 **保存并运行** 以开始运行模型。</span><span class="sxs-lookup"><span data-stu-id="2f19e-207">If all values are configured correctly, select **Save and run** to start running the model.</span></span> <span data-ttu-id="2f19e-208">在 **我的预测** 选项卡上，您可以查看预测过程的状态。</span><span class="sxs-lookup"><span data-stu-id="2f19e-208">On the **My predictions** tab, you can see the status of the prediction process.</span></span> <span data-ttu-id="2f19e-209">完成该过程可能需要几个小时，具体取决于预测中使用的数据量。</span><span class="sxs-lookup"><span data-stu-id="2f19e-209">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-prediction-status-and-results"></a><span data-ttu-id="2f19e-210">查看预测状态和结果</span><span class="sxs-lookup"><span data-stu-id="2f19e-210">Review prediction status and results</span></span>

### <a name="review-prediction-status"></a><span data-ttu-id="2f19e-211">查看预测状态</span><span class="sxs-lookup"><span data-stu-id="2f19e-211">Review prediction status</span></span>

1.  <span data-ttu-id="2f19e-212">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f19e-212">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2.  <span data-ttu-id="2f19e-213">选择要查看的预测。</span><span class="sxs-lookup"><span data-stu-id="2f19e-213">Select the prediction you want to review.</span></span>

- <span data-ttu-id="2f19e-214">**预测名称**：创建时提供的预测的名称。</span><span class="sxs-lookup"><span data-stu-id="2f19e-214">**Prediction name**: Name of the prediction provided when creating it.</span></span>
- <span data-ttu-id="2f19e-215">**预测类型**：用于预测的模型的类型</span><span class="sxs-lookup"><span data-stu-id="2f19e-215">**Prediction type**: Type of model used for the prediction</span></span>
- <span data-ttu-id="2f19e-216">**输出实体**：用于存储预测输出的实体的名称。</span><span class="sxs-lookup"><span data-stu-id="2f19e-216">**Output entity**: Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="2f19e-217">转到 **数据** > **实体** 以查找具有此名称的实体。</span><span class="sxs-lookup"><span data-stu-id="2f19e-217">Go to **Data** > **Entities** to find the entity with this name.</span></span>
- <span data-ttu-id="2f19e-218">**预测字段**：仅针对某些类型的预测填充此字段，而不在客户生存期值预测中使用它。</span><span class="sxs-lookup"><span data-stu-id="2f19e-218">**Predicted field**: This field is populated only for some types of predictions, and isn't used in customer lifetime value prediction.</span></span>
- <span data-ttu-id="2f19e-219">**状态**：预测运行的状态。</span><span class="sxs-lookup"><span data-stu-id="2f19e-219">**Status**: Status of the prediction run.</span></span>
    - <span data-ttu-id="2f19e-220">**已排队**：预测正在等待其他流程完成。</span><span class="sxs-lookup"><span data-stu-id="2f19e-220">**Queued**: Prediction is waiting for other processes to complete.</span></span>
    - <span data-ttu-id="2f19e-221">**刷新**：预测当前正在运行，以创建将流入输出实体的结果。</span><span class="sxs-lookup"><span data-stu-id="2f19e-221">**Refreshing**: Prediction is currently running to create results that will flow into the output entity.</span></span>
    - <span data-ttu-id="2f19e-222">**失败**：预测运行已失败。</span><span class="sxs-lookup"><span data-stu-id="2f19e-222">**Failed**: Prediction run has failed.</span></span> <span data-ttu-id="2f19e-223">有关更多详细信息，请[查看日志](#troubleshoot-a-failed-prediction)。</span><span class="sxs-lookup"><span data-stu-id="2f19e-223">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
    - <span data-ttu-id="2f19e-224">**已成功**：预测已成功。</span><span class="sxs-lookup"><span data-stu-id="2f19e-224">**Succeeded**: Prediction has succeeded.</span></span> <span data-ttu-id="2f19e-225">选择垂直省略号下面的 **视图**，以查看预测结果。</span><span class="sxs-lookup"><span data-stu-id="2f19e-225">Select **View** under the vertical ellipses to review the prediction results.</span></span>
- <span data-ttu-id="2f19e-226">**已编辑**：预测配置的更改日期。</span><span class="sxs-lookup"><span data-stu-id="2f19e-226">**Edited**: The date the configuration for the prediction was changed.</span></span>
- <span data-ttu-id="2f19e-227">**上次刷新**：预测刷新输出实体中的结果的日期。</span><span class="sxs-lookup"><span data-stu-id="2f19e-227">**Last refreshed**: The date the prediction refreshed results in the output entity.</span></span>


### <a name="review-prediction-results"></a><span data-ttu-id="2f19e-228">查看预测结果</span><span class="sxs-lookup"><span data-stu-id="2f19e-228">Review prediction results</span></span>

1. <span data-ttu-id="2f19e-229">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f19e-229">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="2f19e-230">选择要查看其结果的预测。</span><span class="sxs-lookup"><span data-stu-id="2f19e-230">Select the prediction you want to review results for.</span></span>

<span data-ttu-id="2f19e-231">结果页中有三个主要部分的数据。</span><span class="sxs-lookup"><span data-stu-id="2f19e-231">There are three primary sections of data within the results page.</span></span>

- <span data-ttu-id="2f19e-232">**训练模型性能**：A、B 或 C 是可能的等级。</span><span class="sxs-lookup"><span data-stu-id="2f19e-232">**Training model performance**: A, B, or C are possible grades.</span></span> <span data-ttu-id="2f19e-233">该等级表示预测的性能，可以帮助您做出决定来使用存储在输出实体中的结果。</span><span class="sxs-lookup"><span data-stu-id="2f19e-233">This grade indicates the performance of the prediction and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="2f19e-234">选择 **了解此分数** 以更好地了解基础模型性能指标，以及如何推导最终模型性能等级。</span><span class="sxs-lookup"><span data-stu-id="2f19e-234">Select **Learn about this score** to better understand the underlying model performance metrics and how the final model performance grade was derived.</span></span>
  
  :::image type="content" source="media/clv-model-score.png" alt-text="包含等级 A 的模型分数信息框的图像。":::

  <span data-ttu-id="2f19e-236">使用在配置预测时提供的高价值客户的定义，系统评估了与基线模型相比，AI 模型在预测高价值客户方面的性能。</span><span class="sxs-lookup"><span data-stu-id="2f19e-236">Using the definition of high value customers provided while configuring the prediction, the system assess how the AI model performed in predicting the high value customers as compared to a baseline model.</span></span>    

  <span data-ttu-id="2f19e-237">等级是根据以下规则确定的：</span><span class="sxs-lookup"><span data-stu-id="2f19e-237">Grades are determined based on the following rules:</span></span>
  - <span data-ttu-id="2f19e-238">当模型比基线模型准确预测的高价值客户至少多 5% 时，等级为 A。</span><span class="sxs-lookup"><span data-stu-id="2f19e-238">A when the model accurately predicted at least 5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="2f19e-239">当模型比基线模型准确预测的高价值客户多 0-5% 时，等级为 B。</span><span class="sxs-lookup"><span data-stu-id="2f19e-239">B when the model accurately predicted between 0-5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="2f19e-240">当模型比基线模型准确预测的高价值客户少时，等级为 C。</span><span class="sxs-lookup"><span data-stu-id="2f19e-240">C when the model accurately predicted fewer high-value customers as compared to the baseline model.</span></span>

  <span data-ttu-id="2f19e-241">**模型评级** 窗格显示有关 AI 模型性能和基线模型的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f19e-241">The **Model rating** pane shows further details about the AI model performance and the baseline model.</span></span> <span data-ttu-id="2f19e-242">基准模型使用非基于 AI 的方法，主要根据客户过去的购买情况来计算客户生存期值。</span><span class="sxs-lookup"><span data-stu-id="2f19e-242">The baseline model uses a non-AI based approach to calculate customer lifetime value based primarily on historical purchases made by customers.</span></span>     
  <span data-ttu-id="2f19e-243">基线模型计算 CLV 所使用的标准公式：</span><span class="sxs-lookup"><span data-stu-id="2f19e-243">The standard formula used to calculate CLV by the baseline model:</span></span>    

  <span data-ttu-id="2f19e-244">*每个客户的 CLV = 客户在活跃客户窗口中每月平均购买的商品 \* CLV 预测期内的月数 \* 所有客户的总体留存率*</span><span class="sxs-lookup"><span data-stu-id="2f19e-244">*CLV for each customer = Average monthly purchase made by the customer in the active customer window \* Number of months in the CLV prediction period \* Overall retention rate of all customers*</span></span>

  <span data-ttu-id="2f19e-245">将按照两个模型绩效指标将 AI 模型与基线模型进行比较。</span><span class="sxs-lookup"><span data-stu-id="2f19e-245">The AI model is compared to the baseline model based on two model performance metrics.</span></span>
  
  - <span data-ttu-id="2f19e-246">**预测高价值客户的成功率**</span><span class="sxs-lookup"><span data-stu-id="2f19e-246">**Success rate in predicting high-value customers**</span></span>

  <span data-ttu-id="2f19e-247">查看使用 AI 模型与基线模型相比在预测高价值客户方面的差别。</span><span class="sxs-lookup"><span data-stu-id="2f19e-247">See the difference in predicting high-value customers using the AI model compared to the baseline model.</span></span> <span data-ttu-id="2f19e-248">例如，84% 的成功率意味着在训练数据内的所有高价值客户中，AI 模型能够准确地捕获 84%。</span><span class="sxs-lookup"><span data-stu-id="2f19e-248">For example, 84% success rate means that out of all the high-value customers in the training data, the AI model was able to accurately capture 84%.</span></span> <span data-ttu-id="2f19e-249">然后，我们将此成功率与基线模型的成功率进行比较，以报告相对变化。</span><span class="sxs-lookup"><span data-stu-id="2f19e-249">We then compare this success rate with the success rate of the baseline model to report the relative change.</span></span> <span data-ttu-id="2f19e-250">此值用于为模型分配等级。</span><span class="sxs-lookup"><span data-stu-id="2f19e-250">This value is used to assign a grade to the model.</span></span>

  - <span data-ttu-id="2f19e-251">**错误指标**</span><span class="sxs-lookup"><span data-stu-id="2f19e-251">**Error metrics**</span></span>
    
  <span data-ttu-id="2f19e-252">另一个指标允许您查看模型预测未来值出错方面的总体性能。</span><span class="sxs-lookup"><span data-stu-id="2f19e-252">Another metric lets you review the overall performance of the model in terms of error in predicting future values.</span></span> <span data-ttu-id="2f19e-253">我们使用总体均方根误差 (RMSE) 指标来评估此误差。</span><span class="sxs-lookup"><span data-stu-id="2f19e-253">We use the overall Root Mean Squared Error (RMSE) metric to assess this error.</span></span> <span data-ttu-id="2f19e-254">RMSE 是一种衡量模型在预测定量数据方面的误差的标准方法。</span><span class="sxs-lookup"><span data-stu-id="2f19e-254">RMSE is a standard way to measure the error of a model in predicting quantitative data.</span></span> <span data-ttu-id="2f19e-255">将 AI 模型的 RMSE 与基线模型的 RMSE 进行比较，并报告相对差异。</span><span class="sxs-lookup"><span data-stu-id="2f19e-255">The AI model’s RMSE is compared to the RMSE of the baseline model and the relative difference is reported.</span></span>

  <span data-ttu-id="2f19e-256">AI 模型会根据客户为您的公司带来的价值，对客户的准确排名进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="2f19e-256">The AI model prioritizes the accurate ranking of customers according to the value they bring to your business.</span></span> <span data-ttu-id="2f19e-257">因此，仅使用预测高价值客户的成功率来得出最终模型等级。</span><span class="sxs-lookup"><span data-stu-id="2f19e-257">So only the success rate of predicting high-value customers is used to derive the final model grade.</span></span> <span data-ttu-id="2f19e-258">RMSE 指标对异常值敏感。</span><span class="sxs-lookup"><span data-stu-id="2f19e-258">The RMSE metric is sensitive to outliers.</span></span> <span data-ttu-id="2f19e-259">在您的小部分客户购买价值极高的情况下，总体 RMSE 指标可能无法全面反映模型的性能。</span><span class="sxs-lookup"><span data-stu-id="2f19e-259">In scenarios where you have a small percentage of customers with extraordinarily high purchase values, the overall RMSE metric might not give the full picture of the model performance.</span></span>   

- <span data-ttu-id="2f19e-260">**各百分位的客户值**：使用您对高价值客户的定义，根据客户的 CLV 预测将客户分为低价值组和高价值组，并在图表中显示。</span><span class="sxs-lookup"><span data-stu-id="2f19e-260">**Value of customers by percentile**: Using your definition of high-value customers, customers are grouped into low-value and high-value, based on their CLV predictions, and shown in a chart.</span></span> <span data-ttu-id="2f19e-261">通过将鼠标悬停在直方图中的条形上，您可以查看每个组中的客户数量以及该组的平均 CLV。</span><span class="sxs-lookup"><span data-stu-id="2f19e-261">By hovering over the bars in the histogram, you can see the number of customers in each group and the average CLV of that group.</span></span> <span data-ttu-id="2f19e-262">如果您想根据他们的 CLV 预测来[创建客户细分](segments.md)，那么此数据可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="2f19e-262">This data can help if you want to [create segments of customers](segments.md) based on their CLV predictions.</span></span>

- <span data-ttu-id="2f19e-263">**最具影响力的因素**：基于提供给 AI 模型的输入数据创建 CLV 预测时，会考虑各种因素。</span><span class="sxs-lookup"><span data-stu-id="2f19e-263">**Most influential factors**: Various factors are considered when creating your CLV prediction based on the input data provided to the AI model.</span></span> <span data-ttu-id="2f19e-264">系统针对模型创建的汇总预测计算了每个因素的重要性。</span><span class="sxs-lookup"><span data-stu-id="2f19e-264">Each of the factors has their importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="2f19e-265">您可以使用这些因素帮助验证预测结果。</span><span class="sxs-lookup"><span data-stu-id="2f19e-265">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="2f19e-266">这些因素还提供了有关最有影响力的因素的更多见解，这些因素有助于预测所有客户的 CLV。</span><span class="sxs-lookup"><span data-stu-id="2f19e-266">These factors also provide more insight about the most influential factors that contributed towards predicting CLV across all your customers.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="2f19e-267">刷新预测</span><span class="sxs-lookup"><span data-stu-id="2f19e-267">Refresh a prediction</span></span>

<span data-ttu-id="2f19e-268">预测会按照设置中配置的相同[数据刷新计划](system.md#schedule-tab)自动刷新。</span><span class="sxs-lookup"><span data-stu-id="2f19e-268">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="2f19e-269">您也可以手动刷新它们。</span><span class="sxs-lookup"><span data-stu-id="2f19e-269">You can refresh them manually too.</span></span>

1. <span data-ttu-id="2f19e-270">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f19e-270">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="2f19e-271">选择要刷新的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="2f19e-271">Select the vertical ellipses next to the prediction you want to refresh.</span></span>
3. <span data-ttu-id="2f19e-272">选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-272">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="2f19e-273">删除预测</span><span class="sxs-lookup"><span data-stu-id="2f19e-273">Delete a prediction</span></span>

<span data-ttu-id="2f19e-274">删除预测还会删除其输出实体。</span><span class="sxs-lookup"><span data-stu-id="2f19e-274">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="2f19e-275">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f19e-275">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="2f19e-276">选择要删除的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="2f19e-276">Select the vertical ellipses next to the prediction you want to delete.</span></span>
3. <span data-ttu-id="2f19e-277">选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-277">Select **Delete**.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="2f19e-278">解决失败的预测</span><span class="sxs-lookup"><span data-stu-id="2f19e-278">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="2f19e-279">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f19e-279">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="2f19e-280">选择要查看其错误日志的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="2f19e-280">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>
3. <span data-ttu-id="2f19e-281">选择 **日志**。</span><span class="sxs-lookup"><span data-stu-id="2f19e-281">Select **Logs**.</span></span>
4. <span data-ttu-id="2f19e-282">查看所有错误。</span><span class="sxs-lookup"><span data-stu-id="2f19e-282">Review all the errors.</span></span> <span data-ttu-id="2f19e-283">可能会出现几种类型的错误，这些类型描述了导致错误的原因。</span><span class="sxs-lookup"><span data-stu-id="2f19e-283">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="2f19e-284">例如，数据不足而无法准确预测的错误通常可通过向访问群体见解加载更多数据来解决。</span><span class="sxs-lookup"><span data-stu-id="2f19e-284">For example, an error that there's not enough data to accurately predict is typically resolved by loading more data into audience insights.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]