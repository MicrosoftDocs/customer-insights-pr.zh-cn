---
title: 产品建议预测
description: 预测客户可能会购买或与其交互的产品。
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e46e31131a2dd5235af8221eafcd2e1d1394f3d4
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906753"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="2d8fd-103">产品建议预测（预览版）</span><span class="sxs-lookup"><span data-stu-id="2d8fd-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="2d8fd-104">产品建议模型可创建多组预测产品建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="2d8fd-105">建议基于先前的购买行为以及具有类似购买模式的客户。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="2d8fd-106">您可以在 **智能** > **预测** 页上创建新的产品建议预测。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="2d8fd-107">选择 **我的预测** 以查看您已创建的其他预测。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="2d8fd-108">产品建议可能受本地法律和法规以及客户期望的约束，未专门考虑这些来生成模型。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-108">Product recommendations may be subject to local laws and regulations and customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="2d8fd-109">作为此预测功能的用户，**在将建议传送给客户之前，您必须查看这些建议**，以确保对于您可能建议内容，您遵守了任何适用的法律或法规，并且符合客户的期望 。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, and customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="2d8fd-110">此外，此模型的输出将基于产品 ID 提供建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="2d8fd-111">您的交付机制需要将预测的产品 ID 映射到相应的内容，以让客户考虑本地化、图像内容和其他特定于业务的内容或行为。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-111">Your delivery mechanism will need to map the predicted product IDs to appropriate content for your customers to account for localization, image content, and other business-specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="2d8fd-112">示例指南</span><span class="sxs-lookup"><span data-stu-id="2d8fd-112">Sample Guide</span></span>

<span data-ttu-id="2d8fd-113">如果您有兴趣尝试此功能，但因没有数据而无法完成以下要求，则可以[创建一个示例实现](sample-guide-predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d8fd-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="2d8fd-114">Prerequisites</span></span>

- <span data-ttu-id="2d8fd-115">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="2d8fd-116">用于了解业务中不同类型的产品以及客户与其的交互方式的业务知识。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="2d8fd-117">我们支持推荐客户先前购买的产品或推荐新产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>

- <span data-ttu-id="2d8fd-118">有关交易、购买及其历史记录的数据：</span><span class="sxs-lookup"><span data-stu-id="2d8fd-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="2d8fd-119">用于区分交易或购买的交易标识符。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="2d8fd-120">用于将交易映射到客户的客户标识符。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="2d8fd-121">交易事件日期，用于指定交易发生的日期。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="2d8fd-122">交易的产品 ID 信息。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-122">Product ID information for the transaction.</span></span>
    - <span data-ttu-id="2d8fd-123">（可选）用于使用产品筛选器的产品目录数据实体。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-123">(Optional) A product catalog data entity to use a product filter.</span></span>
    - <span data-ttu-id="2d8fd-124">（可选）交易是否为退货交易。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-124">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="2d8fd-125">语义数据架构需要以下信息：</span><span class="sxs-lookup"><span data-stu-id="2d8fd-125">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="2d8fd-126">**交易 ID：** 购买或交易的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-126">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="2d8fd-127">**交易日期**：购买或交易的日期。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-127">**Transaction date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="2d8fd-128">**交易值：** 购买或交易的数值。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-128">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="2d8fd-129">**唯一产品 ID：** 购买的产品或服务的 ID（如果您的数据位于行项级别）。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-129">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="2d8fd-130">（可选）**购买或退货：** 其中值 *true* 确定交易是退货交易的布尔字段。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-130">(Optional) **Purchase or return:** A boolean field where the value *true* identifies that a transaction was a return.</span></span> <span data-ttu-id="2d8fd-131">如果模型未提供购买或退货数据，并且 **交易值** 为负值，我们还将使用此信息推断退货。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-131">If the Purchase or Return data is not provided the model and the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="2d8fd-132">建议的数据特征：</span><span class="sxs-lookup"><span data-stu-id="2d8fd-132">Suggested data characteristics:</span></span>
    - <span data-ttu-id="2d8fd-133">足够的历史数据：至少一年的交易数据，最好两到三年，以包含一定的季节性。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-133">Sufficient historical data: At least one year of transactional data, preferably two to three years to include some seasonality.</span></span>
    - <span data-ttu-id="2d8fd-134">每个客户多项购买：每个客户 ID 有三个或更多个交易</span><span class="sxs-lookup"><span data-stu-id="2d8fd-134">Multiple purchases per customer: Three or more transactions per Customer ID</span></span>
    - <span data-ttu-id="2d8fd-135">客户数量：至少 100 个客户，最好是超过 10,000 个客户。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-135">Number of customers: At least 100 customers, preferably more than 10,000 customers.</span></span> <span data-ttu-id="2d8fd-136">如果客户少于 100 个，则此模型将失败。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-136">The model will fail with fewer than 100 customers.</span></span>

> [!NOTE]
> - <span data-ttu-id="2d8fd-137">该模型需要客户的交易历史记录。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-137">The model requires the transaction history of your customers.</span></span> <span data-ttu-id="2d8fd-138">交易的定义非常灵活。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-138">The definition of a transaction is quite flexible.</span></span> <span data-ttu-id="2d8fd-139">介绍用户与产品交互的任何数据都可以用作输入。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-139">Any data that describes a user-product interaction can work as an input.</span></span> <span data-ttu-id="2d8fd-140">例如，购买产品、上课或参加活动。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-140">For example, purchasing a product, taking a class, or attending an event.</span></span>
> - <span data-ttu-id="2d8fd-141">当前只能配置一个交易历史记录实体。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-141">Only one transaction history entity can be configured currently.</span></span> <span data-ttu-id="2d8fd-142">如果有多个购买实体，请在数据引入之前在 Power Query 中合并它们。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-142">If there are multiple purchase entities, union them in Power Query before data ingestion.</span></span>
> - <span data-ttu-id="2d8fd-143">如果订单和订单详细信息是不同的实体，则先加入它们，然后再在模型中使用。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-143">If order and order details are different entities, join them before using in the model.</span></span> <span data-ttu-id="2d8fd-144">该模型仅不适用于实体中的订单 ID 或收货 ID。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-144">The model doesn't work with only an order ID or receipt ID in an entity.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="2d8fd-145">创建产品建议预测</span><span class="sxs-lookup"><span data-stu-id="2d8fd-145">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="2d8fd-146">在 Customer Insights 中，转到 **智能** > **预测**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-146">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="2d8fd-147">选择 **产品建议模型（预览版）** 磁贴并选择 **使用此模型**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-147">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d8fd-148">![具有“使用此模型”按钮的“产品建议”模型磁贴](media/product-recommendation-usethismodel.PNG "具有“使用此模型”按钮的“产品建议”模型磁贴")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-148">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="2d8fd-149">查看有关模型要求的信息。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-149">Review the information about the model requirements.</span></span> <span data-ttu-id="2d8fd-150">如果您具有所需数据，请选择 **入门**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-150">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="2d8fd-151">命名模型</span><span class="sxs-lookup"><span data-stu-id="2d8fd-151">Name model</span></span>

1. <span data-ttu-id="2d8fd-152">为模型提供一个名称，以区别于其他模型。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-152">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="2d8fd-153">只能使用字母和数字为输出实体输入名称，不能使用任何空格。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-153">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="2d8fd-154">这是模型实体将使用的名称。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-154">That's the name that the model entity will use.</span></span> <span data-ttu-id="2d8fd-155">然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-155">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="2d8fd-156">定义产品建议配置</span><span class="sxs-lookup"><span data-stu-id="2d8fd-156">Define product recommendation configuration</span></span>

1. <span data-ttu-id="2d8fd-157">设置要推荐给客户的 **产品数量**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-157">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="2d8fd-158">此值取决于您的交付方法填充数据的方式。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-158">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="2d8fd-159">如果可以推荐三个产品，请相应地设置此值。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-159">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="2d8fd-160">您可以随时选择 **保存并关闭** 以将预测保存为草稿。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-160">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="2d8fd-161">您将在 **我的预测** 选项卡中找到草稿预测。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-161">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="2d8fd-162">选择是否想要 **建议客户最近购买的产品**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-162">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="2d8fd-163">如果您选择了 *不* 推荐最近购买的产品，请设置 **回看窗口**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-163">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="2d8fd-164">此设置指定模型在再次向用户推荐产品之前考虑的期限。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-164">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="2d8fd-165">例如，指示客户每两年购买一次便携式计算机。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-165">For example, indicate a customer purchases a laptop every two years.</span></span> <span data-ttu-id="2d8fd-166">此窗口将查看最近两年的购买历史记录，如果找到一个项目，将会从建议中筛选该项目。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-166">This window will look at the purchase history for the last two years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="2d8fd-167">选择 **下一个**</span><span class="sxs-lookup"><span data-stu-id="2d8fd-167">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="2d8fd-168">添加所需数据</span><span class="sxs-lookup"><span data-stu-id="2d8fd-168">Add required data</span></span>

1. <span data-ttu-id="2d8fd-169">针对 **客户交易历史记录** 选择 **添加数据**，然后选择提供交易/购买历史记录信息的实体，如[先决条件](#prerequisites)中所述。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-169">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="2d8fd-170">将语义字段映射到购买历史记录实体中的属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-170">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="2d8fd-171">有关字段的说明，请查看[先决条件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-171">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d8fd-172">![定义实体关系](media/product-recommendation-purchasehistorymapping.PNG "购买历史记录页面显示了语义属性，这些语义属性已映射到所选购买历史记录实体中的字段")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-172">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="2d8fd-173">如果字段未填充，请配置购买历史记录实体与 *客户* 实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-173">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="2d8fd-174">选择 **购买历史记录实体**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-174">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="2d8fd-175">在购买历史记录实体中选择用于标识客户的 **字段**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-175">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="2d8fd-176">它需要与您的 *客户* 实体的主要客户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-176">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="2d8fd-177">选择与您的主要客户实体相匹配的 **客户实体**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-177">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="2d8fd-178">输入一个用于描述关系的名称。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-178">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="2d8fd-179">![显示创建与客户的关系的购买历史记录页面](media/model-purchase-join.png "显示创建与客户的关系的购买历史记录页面")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-179">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="2d8fd-180">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-180">Select **Save**.</span></span>

1. <span data-ttu-id="2d8fd-181">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-181">Select **Next**.</span></span>

### <a name="configure-product-filters"></a><span data-ttu-id="2d8fd-182">配置产品筛选器</span><span class="sxs-lookup"><span data-stu-id="2d8fd-182">Configure product filters</span></span>

<span data-ttu-id="2d8fd-183">有时，只有某些产品对您建立的预测类型有益或适用。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-183">Sometimes, only certain products are beneficial or appropriate for the type of prediction you build.</span></span> <span data-ttu-id="2d8fd-184">利用产品筛选器，您能够识别一部分具有特定特征的产品，以便推荐给客户。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-184">Product filters let you identify a subset of products with specific characteristics to recommend to your customers.</span></span> <span data-ttu-id="2d8fd-185">该模型将使用所有可用的产品来学习模式，但仅使用与输出中的产品筛选器匹配的产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-185">The model will use all the products available to learn patterns but only use the products matching the product filter in its output.</span></span>

1. <span data-ttu-id="2d8fd-186">在 **添加产品信息** 步骤中，添加包含每个产品的信息的产品目录。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-186">In the **Add product information** step, add your product catalog with information for each product.</span></span> <span data-ttu-id="2d8fd-187">映射所需的信息，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-187">Map the information required in select **Next**.</span></span>

3. <span data-ttu-id="2d8fd-188">在 **产品筛选器** 步骤中，在以下选项之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-188">In the **Product filters** step, choose between the following options.</span></span>

   * <span data-ttu-id="2d8fd-189">**无筛选器**：在产品建议预测中使用所有产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-189">**No filters**: Use all products in the product recommendation prediction.</span></span>

   * <span data-ttu-id="2d8fd-190">**定义特定产品筛选器**：在产品建议预测中使用特定产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-190">**Define specific product filters**: Use specific products in the product recommendation prediction.</span></span>

1. <span data-ttu-id="2d8fd-191">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-191">Select **Next**.</span></span>

1. <span data-ttu-id="2d8fd-192">如果选择定义产品筛选器，则需要立即进行定义。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-192">If you choose to define a product filter, you need to define it now.</span></span> <span data-ttu-id="2d8fd-193">在 **产品目录属性** 窗格中，从 *产品目录实体* 中选择要包括在筛选器中的属性。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-193">In the **Product catalog attributes** pane, select the attributes from your *Product Catalog entity* that you want include in the filter.</span></span>

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="侧窗格显示产品目录实体中要为产品筛选器选择的属性。":::

1. <span data-ttu-id="2d8fd-195">选择是想让产品筛选器使用 **与** 还是**或**连接器以逻辑方式组合从产品目录中选择的属性。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-195">Choose if you want the product filter to use **and** or\*\* connectors to logically combine your selection of attributes from product catalog.</span></span>
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="与逻辑“与”连接器组合的产品筛选器的示例配置。":::

1. <span data-ttu-id="2d8fd-197">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-197">Select **Next**.</span></span>

### <a name="set-update-schedule-and-review-configuration"></a><span data-ttu-id="2d8fd-198">设置更新计划并查看配置</span><span class="sxs-lookup"><span data-stu-id="2d8fd-198">Set update schedule and review configuration</span></span>

1. <span data-ttu-id="2d8fd-199">设置频率以重新训练您的模型。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-199">Set a frequency to retrain your model.</span></span> <span data-ttu-id="2d8fd-200">在将新数据导入到 Customer Insights 中后，此设置对于更新预测的准确度很重要。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-200">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="2d8fd-201">大多数企业每个月可以重新进行一次训练，并取得良好的预测准确度。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-201">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="2d8fd-202">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-202">Select **Next**.</span></span>

1. <span data-ttu-id="2d8fd-203">查看配置。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-203">Review the configuration.</span></span> <span data-ttu-id="2d8fd-204">通过在显示的值下面选择 **编辑**，可以返回到预测配置的任意部分。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-204">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="2d8fd-205">或者，您也可以从进度指示器中选择配置步骤。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-205">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="2d8fd-206">如果正确配置了所有值，请选择 **保存并运行** 以开始预测过程。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-206">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="2d8fd-207">在 **我的预测** 选项卡上，您可以查看预测的状态。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-207">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="2d8fd-208">完成该过程可能需要几个小时，具体取决于预测中使用的数据量。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-208">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="2d8fd-209">查看预测状态和结果</span><span class="sxs-lookup"><span data-stu-id="2d8fd-209">Review a prediction status and results</span></span>

1. <span data-ttu-id="2d8fd-210">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-210">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d8fd-211">![“我的预测”页面视图](media/product-recommendation-mypredictions.PNG "“我的预测”页面视图")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-211">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="2d8fd-212">选择要查看的预测。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-212">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="2d8fd-213">**预测名称：** 创建预测时提供的预测名称。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-213">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="2d8fd-214">**预测类型：** 用于预测的模型类型</span><span class="sxs-lookup"><span data-stu-id="2d8fd-214">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="2d8fd-215">**输出实体：** 用于存储预测输出的实体的名称。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-215">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="2d8fd-216">您可以在 **数据** > **实体** 中查找具有此名称的实体。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-216">You can find an entity with this name on **Data** > **Entities**.</span></span>    
      <span data-ttu-id="2d8fd-217">输出实体中的 *分数* 是建议的定量度量。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-217">*Score* in the output entity is a quantitative measure of the recommendation.</span></span> <span data-ttu-id="2d8fd-218">该模型推荐得分较高的产品，而不推荐得分较低的产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-218">The model recommends products with a higher score over products with a lower score.</span></span>
   - <span data-ttu-id="2d8fd-219">**预测字段**：仅针对某些类型的预测填充此字段，并且在“产品建议”预测中不使用该字段。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-219">**Predicted field:** This field is populated only for some types of predictions, and isn't used in Product Recommendation prediction.</span></span>
   - <span data-ttu-id="2d8fd-220">**状态：** 预测运行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-220">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="2d8fd-221">**已排队：** 预测当前正在等待其他流程运行。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-221">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="2d8fd-222">**刷新：** 预测当前运行到“评分”处理阶段以生成将流入输出实体的结果。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-222">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="2d8fd-223">**失败：** 预测已失败。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-223">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="2d8fd-224">选择 **日志** 以了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-224">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="2d8fd-225">**已成功：** 预测已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-225">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="2d8fd-226">在垂直省略号下选择 **查看** 以查看预测</span><span class="sxs-lookup"><span data-stu-id="2d8fd-226">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="2d8fd-227">**已编辑：** 预测配置的更改日期。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-227">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="2d8fd-228">**上次刷新**：预测刷新输出实体中的结果的日期。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-228">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="2d8fd-229">选择要查看其结果的预测旁边的垂直省略号并选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-229">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d8fd-230">![预测的垂直省略号菜单中的选项视图，包括编辑、刷新、查看、日志和删除](media/product-recommendation-verticalellipses.PNG "预测的垂直省略号菜单中的选项视图，包括编辑、刷新、查看、日志和删除")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-230">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="2d8fd-231">结果页面中有五个主要数据部分：</span><span class="sxs-lookup"><span data-stu-id="2d8fd-231">There are five primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="2d8fd-232">**训练模型的性能：** A、B 或 C 为可能的分数。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-232">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="2d8fd-233">此分数指示预测的性能，并可帮助您做出关于使用输出实体中存储的结果的决策。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-233">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="2d8fd-234">根据以下规则确定分数：</span><span class="sxs-lookup"><span data-stu-id="2d8fd-234">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="2d8fd-235">**A** 如果“成功 @ K”指标至少比基线高 10%，则该模型将被视为 **A** 质量。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-235">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="2d8fd-236">**B** 如果“成功 @ K”指标比基线高 0% 到 10%，则该模型将被视为 **B** 质量。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-236">**B** The model will be considered **B** quality if the "Success @ K" metric is 0% to 10% more than the baseline.</span></span>
            - <span data-ttu-id="2d8fd-237">**C** 如果“成功 @ K”指标低于基线，则该模型将被视为 **C** 质量。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-237">**C** The model will be considered **C** quality if the "Success @ K" metric is less than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="2d8fd-238">![模型性能结果视图](media/product-recommendation-modelperformance.PNG "模型性能结果视图")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-238">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="2d8fd-239">**基线**：该模型按照所有客户的购买数量来获取推荐度最高的产品，并使用该模型标识的学习规则为客户创建一组建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-239">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="2d8fd-240">然后，将预测结果与按购买该产品的客户数量所计算出的前几个产品进行比较。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-240">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="2d8fd-241">如果客户的推荐产品中至少有一种产品（在购买量最高的产品中也出现过），则将推荐的产品视为基线的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-241">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="2d8fd-242">如果在总共 100 个客户中有 10 个客户购买了推荐的产品，则基线将是 10%。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-242">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="2d8fd-243">**成功 @ K：** 使用交易时间段的验证集，为所有客户创建建议，并将其与交易验证集进行比较。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-243">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="2d8fd-244">例如，在 12 个月期间，第 12 个月可以保留为数据验证集。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-244">For example, in a 12-month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="2d8fd-245">如果模型根据从前 11 个月中了解到的信息，预测您将在第 12 个月内至少购买一件商品，则客户将增加“成功 @ K”指标。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-245">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="2d8fd-246">**推荐最多的产品(带计数)：** 为客户预测的前 5 种产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-246">**Most suggested products (with tally):** The top five products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="2d8fd-247">![该图显示了推荐度最高的前 5 种产品](media/product-recommendation-topproducts.PNG "该图显示了推荐度最高的前 5 种产品")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-247">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="2d8fd-248">**关键建议因素**：模型使用客户的交易历史记录提供产品建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-248">**Key recommendation factors:** The model uses the customers' transaction history to make product recommendations.</span></span> <span data-ttu-id="2d8fd-249">它根据过去的购买活动了解模式，并找到客户与产品之间的相似之处。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-249">It learns patterns based on past purchases and finds similarities between customers and products.</span></span> <span data-ttu-id="2d8fd-250">然后利用这些相似之处来生成产品建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-250">These similarities are then utilized to generate product recommendations.</span></span>
    <span data-ttu-id="2d8fd-251">下列因素会影响模型生成的产品建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-251">The following are the factors that could influence a product recommendation generated by the model.</span></span> 
        - <span data-ttu-id="2d8fd-252">**过去的交易**：模型利用过去的购买模式生成产品建议。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-252">**Past transactions**: Purchase patterns in the past were utilized by the model to generate product recommendations.</span></span> <span data-ttu-id="2d8fd-253">例如，如果用户最近购买了 _Surface Book 3_ 和 _Surface Pen_，则模型可能会推荐 _Surface 弧形鼠标_。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-253">For example, the model can recommend a _Surface Arc Mouse_ if someone recently purchased a _Surface Book 3_ and a _Surface Pen_.</span></span> <span data-ttu-id="2d8fd-254">模型了解到，过去许多客户在购买了 _Surface Book 3_ 和 _Surface Pen_ 之后购买了 _Surface 弧形鼠标_。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-254">The model learned that historically, many customers had purchased a _Surface Arc Mouse_ after purchasing a _Surface Book 3_ and a _Surface Pen_.</span></span>
        - <span data-ttu-id="2d8fd-255">**客户相似性**：过去，推荐的产品是由其他具有类似购买方式的客户购买的。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-255">**Customer similarity**: A recommended product was historically purchased by other customers who show similar purchase patterns.</span></span> <span data-ttu-id="2d8fd-256">例如，向 John 推荐了 _Surface Headphones 2_，因为 Jennifer 和 Brad 最近购买了 _Surface Headphones 2_。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-256">For example, John was recommended _Surface Headphones 2_ because Jennifer and Brad recently purchased _Surface Headphones 2_.</span></span> <span data-ttu-id="2d8fd-257">模型认为 John 与 Brad 类似，因为他们过去具有类似的购买模式。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-257">The model believes John is similar to Jennifer and Brad because they have historically had similar purchase patterns.</span></span>
        - <span data-ttu-id="2d8fd-258">**产品相似性**：推荐的产品类似于之前客户购买的其他产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-258">**Product similarity**: A recommended product is similar to other products that the customer had previously purchased.</span></span> <span data-ttu-id="2d8fd-259">该模型认为，如果两个产品是一起购买的，或由相似客户购买，则它们是相似的。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-259">The model considers two products to be similar if they were bought together or by similar customers.</span></span> <span data-ttu-id="2d8fd-260">例如，某人获得了关于 _USB 存储驱动器_ 的建议，因为他们以前购买了 _USB-C 转 USB 适配器_，并且模型根据历史购买模式认为 _USB 存储驱动器_ 与 _USB-C 转 USB 适配器_ 类似。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-260">For example, someone gets a recommendation for a _USB Storage Drive_ because they previously purchased a _USB-C to USB Adapter_ and the model believes that _USB Storage Drive_ is similar to _USB-C to USB Adapter_ based on historical purchase patterns.</span></span>

        <span data-ttu-id="2d8fd-261">每个产品建议都受上述一个或多个因素影响。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-261">Every product recommendation is influenced by one or more of these factors.</span></span> <span data-ttu-id="2d8fd-262">图表中直观显示了每个影响因素起作用的建议的百分比。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-262">The percentage of recommendations where each influencing factor played a role is visualized in a chart.</span></span> <span data-ttu-id="2d8fd-263">在下面的示例中，100% 的建议受过去的交易影响，60% 的建议受客户相似度影响，22% 的建议受产品相似性影响。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-263">In the following example, 100% of the recommendations were influenced by past transactions, 60% by customer similarity and 22% by product similarity.</span></span> <span data-ttu-id="2d8fd-264">将鼠标悬停在图表中的条形图上，即可查看影响因素所占的确切百分比。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-264">Hover over the bars in the chart to see the exact percentage where the influencing factors contributed.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="2d8fd-265">![关键建议因素](media/product-recommendation-keyrecommendationfactors.png "模型为生成产品建议所了解的关键建议因素")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-265">![Key recommendation factors](media/product-recommendation-keyrecommendationfactors.png "Key recommendation factors learned by the model to generate product recommendations")</span></span>
       
     
   1. <span data-ttu-id="2d8fd-266">**数据统计信息**：概述了模型考虑的交易数、客户数和产品数。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-266">**Data statistics**: Gives an overview of the number of transactions, customers, and products the model considered.</span></span> <span data-ttu-id="2d8fd-267">它基于用于了解模式和生成产品建议的输入数据。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-267">It's based on the input data that was used to learn patterns and generate product recommendations.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="2d8fd-268">![数据统计信息](media/product-recommendation-datastatistics.png "有关模型为了解模式所使用的外发数据的相关数据统计信息")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-268">![Data statistics](media/product-recommendation-datastatistics.png "Data statistics around inout data used by the model to learn patterns")</span></span>

      <span data-ttu-id="2d8fd-269">本节显示了模型了解模式和生成产品建议所使用的数据点周围的统计信息。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-269">This section shows stats around the data points that were used by the model to learn patterns and generate product recommendations.</span></span> <span data-ttu-id="2d8fd-270">在模型配置中配置的筛选将应用于模型生成的输出。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-270">Filtering, as configured in the model configuration, will apply on the output generated by the model.</span></span> <span data-ttu-id="2d8fd-271">但是，模型会利用所有可用的数据来了解模式。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-271">However, the model uses all available data to learn patterns.</span></span> <span data-ttu-id="2d8fd-272">因此，如果您在模型配置中使用产品筛选，则本节将显示模型为了解模式所分析的产品总数，该总数可能与符合定义的筛选标准的产品数不同。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-272">Therefore, if you use product filtering in the model configuration, this section will show the total number of products that the model analyzed to learn patterns, which might differ from the number of products that match the defined filtering criteria.</span></span>

   1. <span data-ttu-id="2d8fd-273">**高置信度产品建议：** 向您的客户提供的建议示例，模型认为客户可能会购买这些建议的产品。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-273">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>    
      <span data-ttu-id="2d8fd-274">如果添加了产品目录，则产品 ID 将替换为产品名称。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-274">If a product catalog is added, the product IDs get replaced with product names.</span></span> <span data-ttu-id="2d8fd-275">产品名称提供有关预测的更可操作和直观的信息。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-275">Product names provide a more actionable and intuitive information about the predictions.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="2d8fd-276">![该列表显示了适用于部分个别客户的高置信度建议](media/product-recommendation-highconfidence.PNG "该列表显示了适用于部分个别客户的高置信度建议")</span><span class="sxs-lookup"><span data-stu-id="2d8fd-276">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="2d8fd-277">修复失败的预测</span><span class="sxs-lookup"><span data-stu-id="2d8fd-277">Fix a failed prediction</span></span>

1. <span data-ttu-id="2d8fd-278">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-278">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="2d8fd-279">选择要查看其错误日志的预测并选择 **日志**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-279">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="2d8fd-280">查看所有错误。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-280">Review all the errors.</span></span> <span data-ttu-id="2d8fd-281">可能会出现几种类型的错误，这些类型描述了导致错误的原因。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-281">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="2d8fd-282">例如，通过将更多数据加载到 Customer Insights 中，通常可以解决数据不足以准确进行预测的错误。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-282">For example, an error that there's not enough data to accurately predict is typically resolved by loading more data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="2d8fd-283">刷新预测</span><span class="sxs-lookup"><span data-stu-id="2d8fd-283">Refresh a prediction</span></span>

<span data-ttu-id="2d8fd-284">预测会按照设置中配置的相同[数据刷新计划](system.md#schedule-tab)自动刷新。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-284">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="2d8fd-285">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-285">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="2d8fd-286">选择要刷新的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-286">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="2d8fd-287">选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-287">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="2d8fd-288">删除预测</span><span class="sxs-lookup"><span data-stu-id="2d8fd-288">Delete a prediction</span></span>

<span data-ttu-id="2d8fd-289">删除预测还将删除其输出实体。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-289">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="2d8fd-290">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-290">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="2d8fd-291">选择要删除的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-291">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="2d8fd-292">选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="2d8fd-292">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
