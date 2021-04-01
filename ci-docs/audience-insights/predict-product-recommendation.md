---
title: 产品建议预测
description: 预测客户可能会购买或与其交互的产品。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598052"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="56d89-103">产品建议预测（预览版）</span><span class="sxs-lookup"><span data-stu-id="56d89-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="56d89-104">产品建议模型可创建多组预测产品建议。</span><span class="sxs-lookup"><span data-stu-id="56d89-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="56d89-105">建议基于先前的购买行为以及具有类似购买模式的客户。</span><span class="sxs-lookup"><span data-stu-id="56d89-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="56d89-106">您可以在 **智能** > **预测** 页上创建新的产品建议预测。</span><span class="sxs-lookup"><span data-stu-id="56d89-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="56d89-107">选择 **我的预测** 以查看您已创建的其他预测。</span><span class="sxs-lookup"><span data-stu-id="56d89-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="56d89-108">产品建议可能受当地法律、法规以及客户期望的约束，未生成模型来专门考虑这些方面。</span><span class="sxs-lookup"><span data-stu-id="56d89-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="56d89-109">作为此预测功能的用户，**在将建议提供给客户之前，您必须复查这些建议**，以确保遵守了任何适用的法律或法规，并且满足了客户对具体建议内容的期望。</span><span class="sxs-lookup"><span data-stu-id="56d89-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="56d89-110">此外，此模型的输出将基于产品 ID 提供建议。</span><span class="sxs-lookup"><span data-stu-id="56d89-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="56d89-111">您的交付机制将需要获取预测的产品 ID，并将其映射到适合客户的内容，以说明本地化、图像内容以及其他业务特定的内容或行为。</span><span class="sxs-lookup"><span data-stu-id="56d89-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="56d89-112">示例指南</span><span class="sxs-lookup"><span data-stu-id="56d89-112">Sample Guide</span></span>

<span data-ttu-id="56d89-113">如果您有兴趣尝试此功能，但因没有数据而无法完成以下要求，则可以[创建一个示例实现](sample-guide-predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="56d89-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56d89-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="56d89-114">Prerequisites</span></span>

- <span data-ttu-id="56d89-115">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="56d89-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="56d89-116">用于了解业务中不同类型的产品以及客户与其的交互方式的业务知识。</span><span class="sxs-lookup"><span data-stu-id="56d89-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="56d89-117">我们支持推荐客户先前购买的产品或推荐新产品。</span><span class="sxs-lookup"><span data-stu-id="56d89-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="56d89-118">有关交易、购买及其历史记录的数据：</span><span class="sxs-lookup"><span data-stu-id="56d89-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="56d89-119">用于区分交易或购买的交易标识符。</span><span class="sxs-lookup"><span data-stu-id="56d89-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="56d89-120">用于将交易映射到客户的客户标识符。</span><span class="sxs-lookup"><span data-stu-id="56d89-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="56d89-121">交易事件日期，用于指定交易发生的日期。</span><span class="sxs-lookup"><span data-stu-id="56d89-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="56d89-122">（可选）交易的产品 ID 信息。</span><span class="sxs-lookup"><span data-stu-id="56d89-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="56d89-123">（可选）交易是否为退货交易。</span><span class="sxs-lookup"><span data-stu-id="56d89-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="56d89-124">语义数据架构需要以下信息：</span><span class="sxs-lookup"><span data-stu-id="56d89-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="56d89-125">**交易 ID：** 购买或交易的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="56d89-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="56d89-126">**交易日期：** 购买或交易的日期。</span><span class="sxs-lookup"><span data-stu-id="56d89-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="56d89-127">**交易值：** 购买或交易的数值。</span><span class="sxs-lookup"><span data-stu-id="56d89-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="56d89-128">**唯一产品 ID：** 购买的产品或服务的 ID（如果您的数据位于行项级别）。</span><span class="sxs-lookup"><span data-stu-id="56d89-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="56d89-129">（可选）**购买或退货：** 用于确定交易是否为退货的 true/false 字段。</span><span class="sxs-lookup"><span data-stu-id="56d89-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="56d89-130">如果 **交易值** 为负值，我们还将使用此信息推断退货。</span><span class="sxs-lookup"><span data-stu-id="56d89-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="56d89-131">创建产品建议预测</span><span class="sxs-lookup"><span data-stu-id="56d89-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="56d89-132">在 Customer Insights 中，转到 **智能** > **预测**。</span><span class="sxs-lookup"><span data-stu-id="56d89-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="56d89-133">选择 **产品建议模型（预览版）** 磁贴并选择 **使用此模型**。</span><span class="sxs-lookup"><span data-stu-id="56d89-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56d89-134">![具有“使用此模型”按钮的“产品建议”模型磁贴](media/product-recommendation-usethismodel.PNG "具有“使用此模型”按钮的“产品建议”模型磁贴")</span><span class="sxs-lookup"><span data-stu-id="56d89-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="56d89-135">查看有关模型要求的信息。</span><span class="sxs-lookup"><span data-stu-id="56d89-135">Review the information about the model requirements.</span></span> <span data-ttu-id="56d89-136">如果您具有所需数据，请选择 **入门**。</span><span class="sxs-lookup"><span data-stu-id="56d89-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="56d89-137">命名模型</span><span class="sxs-lookup"><span data-stu-id="56d89-137">Name model</span></span>

1. <span data-ttu-id="56d89-138">为模型提供一个名称，以区别于其他模型。</span><span class="sxs-lookup"><span data-stu-id="56d89-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="56d89-139">只能使用字母和数字为输出实体输入名称，不能使用任何空格。</span><span class="sxs-lookup"><span data-stu-id="56d89-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="56d89-140">这是模型实体将使用的名称。</span><span class="sxs-lookup"><span data-stu-id="56d89-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="56d89-141">然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="56d89-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="56d89-142">定义产品建议配置</span><span class="sxs-lookup"><span data-stu-id="56d89-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="56d89-143">设置要推荐给客户的 **产品数量**。</span><span class="sxs-lookup"><span data-stu-id="56d89-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="56d89-144">此值取决于您的交付方法填充数据的方式。</span><span class="sxs-lookup"><span data-stu-id="56d89-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="56d89-145">如果可以推荐三个产品，请相应地设置此值。</span><span class="sxs-lookup"><span data-stu-id="56d89-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="56d89-146">您可以随时选择 **保存并关闭** 以将预测保存为草稿。</span><span class="sxs-lookup"><span data-stu-id="56d89-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="56d89-147">您将在 **我的预测** 选项卡中找到草稿预测。</span><span class="sxs-lookup"><span data-stu-id="56d89-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="56d89-148">选择是否想要 **建议客户最近购买的产品**。</span><span class="sxs-lookup"><span data-stu-id="56d89-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="56d89-149">如果您选择了 *不* 推荐最近购买的产品，请设置 **回看窗口**。</span><span class="sxs-lookup"><span data-stu-id="56d89-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="56d89-150">此设置指定模型在再次向用户推荐产品之前考虑的期限。</span><span class="sxs-lookup"><span data-stu-id="56d89-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="56d89-151">例如，指示客户每 2 年购买一次便携式计算机。</span><span class="sxs-lookup"><span data-stu-id="56d89-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="56d89-152">此窗口将查看过去 2 年的购买历史记录，如果找到一项，将会从建议中筛选此项。</span><span class="sxs-lookup"><span data-stu-id="56d89-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="56d89-153">选择 **下一个**</span><span class="sxs-lookup"><span data-stu-id="56d89-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="56d89-154">添加所需数据</span><span class="sxs-lookup"><span data-stu-id="56d89-154">Add required data</span></span>

1. <span data-ttu-id="56d89-155">针对 **客户交易历史记录** 选择 **添加数据**，然后选择提供交易/购买历史记录信息的实体，如[先决条件](#prerequisites)中所述。</span><span class="sxs-lookup"><span data-stu-id="56d89-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="56d89-156">将语义字段映射到购买历史记录实体中的属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="56d89-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="56d89-157">有关字段的说明，请查看[先决条件](#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="56d89-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56d89-158">![定义实体关系](media/product-recommendation-purchasehistorymapping.PNG "购买历史记录页面显示了语义属性，这些语义属性已映射到所选购买历史记录实体中的字段")</span><span class="sxs-lookup"><span data-stu-id="56d89-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="56d89-159">如果字段未填充，请配置购买历史记录实体与 *客户* 实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="56d89-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="56d89-160">选择 **购买历史记录实体**。</span><span class="sxs-lookup"><span data-stu-id="56d89-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="56d89-161">在购买历史记录实体中选择用于标识客户的 **字段**。</span><span class="sxs-lookup"><span data-stu-id="56d89-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="56d89-162">它需要与您的 *客户* 实体的主要客户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="56d89-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="56d89-163">选择与您的主要客户实体相匹配的 **客户实体**。</span><span class="sxs-lookup"><span data-stu-id="56d89-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="56d89-164">输入一个用于描述关系的名称。</span><span class="sxs-lookup"><span data-stu-id="56d89-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="56d89-165">![显示创建与客户的关系的购买历史记录页面](media/model-purchase-join.png "显示创建与客户的关系的购买历史记录页面")</span><span class="sxs-lookup"><span data-stu-id="56d89-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="56d89-166">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="56d89-166">Select **Save**.</span></span>

1. <span data-ttu-id="56d89-167">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="56d89-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="56d89-168">设置计划与查看配置</span><span class="sxs-lookup"><span data-stu-id="56d89-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="56d89-169">设置频率以重新训练您的模型。</span><span class="sxs-lookup"><span data-stu-id="56d89-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="56d89-170">在将新数据导入到 Customer Insights 中后，此设置对于更新预测的准确度很重要。</span><span class="sxs-lookup"><span data-stu-id="56d89-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="56d89-171">大多数企业每个月可以重新进行一次训练，并取得良好的预测准确度。</span><span class="sxs-lookup"><span data-stu-id="56d89-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="56d89-172">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="56d89-172">Select **Next**.</span></span>

1. <span data-ttu-id="56d89-173">查看配置。</span><span class="sxs-lookup"><span data-stu-id="56d89-173">Review the configuration.</span></span> <span data-ttu-id="56d89-174">通过在显示的值下面选择 **编辑**，可以返回到预测配置的任意部分。</span><span class="sxs-lookup"><span data-stu-id="56d89-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="56d89-175">或者，您也可以从进度指示器中选择配置步骤。</span><span class="sxs-lookup"><span data-stu-id="56d89-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="56d89-176">如果正确配置了所有值，请选择 **保存并运行** 以开始预测过程。</span><span class="sxs-lookup"><span data-stu-id="56d89-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="56d89-177">在 **我的预测** 选项卡上，您可以查看预测的状态。</span><span class="sxs-lookup"><span data-stu-id="56d89-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="56d89-178">完成该过程可能需要几个小时，具体取决于预测中使用的数据量。</span><span class="sxs-lookup"><span data-stu-id="56d89-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="56d89-179">查看预测状态和结果</span><span class="sxs-lookup"><span data-stu-id="56d89-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="56d89-180">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d89-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56d89-181">![“我的预测”页面视图](media/product-recommendation-mypredictions.PNG "“我的预测”页面视图")</span><span class="sxs-lookup"><span data-stu-id="56d89-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="56d89-182">选择要查看的预测。</span><span class="sxs-lookup"><span data-stu-id="56d89-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="56d89-183">**预测名称：** 创建预测时提供的预测名称。</span><span class="sxs-lookup"><span data-stu-id="56d89-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="56d89-184">**预测类型：** 用于预测的模型类型</span><span class="sxs-lookup"><span data-stu-id="56d89-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="56d89-185">**输出实体：** 用于存储预测输出的实体的名称。</span><span class="sxs-lookup"><span data-stu-id="56d89-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="56d89-186">您可以在 **数据** > **实体** 中查找具有此名称的实体。</span><span class="sxs-lookup"><span data-stu-id="56d89-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="56d89-187">**预测字段：** 仅针对某些类型的预测填充此字段，而不在流失预测中使用它。</span><span class="sxs-lookup"><span data-stu-id="56d89-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="56d89-188">**状态：** 预测运行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="56d89-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="56d89-189">**已排队：** 预测当前正在等待其他流程运行。</span><span class="sxs-lookup"><span data-stu-id="56d89-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="56d89-190">**刷新：** 预测当前运行到“评分”处理阶段以生成将流入输出实体的结果。</span><span class="sxs-lookup"><span data-stu-id="56d89-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="56d89-191">**失败：** 预测已失败。</span><span class="sxs-lookup"><span data-stu-id="56d89-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="56d89-192">选择 **日志** 以了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="56d89-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="56d89-193">**已成功：** 预测已成功完成。</span><span class="sxs-lookup"><span data-stu-id="56d89-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="56d89-194">在垂直省略号下选择 **查看** 以查看预测</span><span class="sxs-lookup"><span data-stu-id="56d89-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="56d89-195">**已编辑：** 预测配置的更改日期。</span><span class="sxs-lookup"><span data-stu-id="56d89-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="56d89-196">**上次刷新**：预测刷新输出实体中的结果的日期。</span><span class="sxs-lookup"><span data-stu-id="56d89-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="56d89-197">选择要查看其结果的预测旁边的垂直省略号并选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="56d89-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="56d89-198">![预测的垂直省略号菜单中的选项视图，包括编辑、刷新、查看、日志和删除](media/product-recommendation-verticalellipses.PNG "预测的垂直省略号菜单中的选项视图，包括编辑、刷新、查看、日志和删除")</span><span class="sxs-lookup"><span data-stu-id="56d89-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="56d89-199">结果页中有三个主要部分的数据：</span><span class="sxs-lookup"><span data-stu-id="56d89-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="56d89-200">**训练模型的性能：** A、B 或 C 为可能的分数。</span><span class="sxs-lookup"><span data-stu-id="56d89-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="56d89-201">此分数指示预测的性能，并可帮助您做出关于使用输出实体中存储的结果的决策。</span><span class="sxs-lookup"><span data-stu-id="56d89-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="56d89-202">根据以下规则确定分数：</span><span class="sxs-lookup"><span data-stu-id="56d89-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="56d89-203">**A** 如果“成功 @ K”指标至少比基线高 10%，则该模型将被视为 **A** 质量。</span><span class="sxs-lookup"><span data-stu-id="56d89-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="56d89-204">**B** 如果“成功 @ K”指标比基线高 0 到 10%，则该模型将被视为 **B** 质量。</span><span class="sxs-lookup"><span data-stu-id="56d89-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="56d89-205">**C** 如果“成功 @ K”指标比基线低，则该模型将被视为 **C** 质量。</span><span class="sxs-lookup"><span data-stu-id="56d89-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="56d89-206">![模型性能结果视图](media/product-recommendation-modelperformance.PNG "模型性能结果视图")</span><span class="sxs-lookup"><span data-stu-id="56d89-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="56d89-207">**基线**：该模型按照所有客户的购买数量来获取推荐度最高的产品，并使用该模型标识的学习规则为客户创建一组建议。</span><span class="sxs-lookup"><span data-stu-id="56d89-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="56d89-208">然后，将预测结果与按购买该产品的客户数量所计算出的前几个产品进行比较。</span><span class="sxs-lookup"><span data-stu-id="56d89-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="56d89-209">如果客户的推荐产品中至少有一种产品（在购买量最高的产品中也出现过），则将推荐的产品视为基线的一部分。</span><span class="sxs-lookup"><span data-stu-id="56d89-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="56d89-210">如果在总共 100 个客户中有 10 个客户购买了推荐的产品，则基线将是 10%。</span><span class="sxs-lookup"><span data-stu-id="56d89-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="56d89-211">**成功 @ K：** 使用交易时间段的验证集，为所有客户创建建议，并将其与交易验证集进行比较。</span><span class="sxs-lookup"><span data-stu-id="56d89-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="56d89-212">例如，在 12 个月期间，第 12 个月可以保留为数据验证集。</span><span class="sxs-lookup"><span data-stu-id="56d89-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="56d89-213">如果模型根据从前 11 个月中了解到的信息，预测您将在第 12 个月内至少购买一件商品，则客户将增加“成功 @ K”指标。</span><span class="sxs-lookup"><span data-stu-id="56d89-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="56d89-214">**推荐最多的产品(带计数)**：为客户预测的前 5 种产品。</span><span class="sxs-lookup"><span data-stu-id="56d89-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="56d89-215">![该图显示了推荐度最高的前 5 种产品](media/product-recommendation-topproducts.PNG "该图显示了推荐度最高的前 5 种产品")</span><span class="sxs-lookup"><span data-stu-id="56d89-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="56d89-216">**高置信度产品建议：** 向您的客户提供的建议示例，模型认为客户可能会购买这些建议的产品。</span><span class="sxs-lookup"><span data-stu-id="56d89-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="56d89-217">![该列表显示了适用于部分个别客户的高置信度建议](media/product-recommendation-highconfidence.PNG "该列表显示了适用于部分个别客户的高置信度建议")</span><span class="sxs-lookup"><span data-stu-id="56d89-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="56d89-218">修复失败的预测</span><span class="sxs-lookup"><span data-stu-id="56d89-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="56d89-219">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d89-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="56d89-220">选择要查看其错误日志的预测并选择 **日志**。</span><span class="sxs-lookup"><span data-stu-id="56d89-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="56d89-221">查看所有错误。</span><span class="sxs-lookup"><span data-stu-id="56d89-221">Review all the errors.</span></span> <span data-ttu-id="56d89-222">可能会出现几种类型的错误，这些类型描述了导致错误的原因。</span><span class="sxs-lookup"><span data-stu-id="56d89-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="56d89-223">例如，因数据不足而无法准确预测的错误通常通过将其他数据加载到 Customer Insights 中来解决。</span><span class="sxs-lookup"><span data-stu-id="56d89-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="56d89-224">刷新预测</span><span class="sxs-lookup"><span data-stu-id="56d89-224">Refresh a prediction</span></span>

<span data-ttu-id="56d89-225">预测会按照设置中配置的相同[数据刷新计划](system.md#schedule-tab)自动刷新。</span><span class="sxs-lookup"><span data-stu-id="56d89-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="56d89-226">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d89-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="56d89-227">选择要刷新的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="56d89-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="56d89-228">选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="56d89-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="56d89-229">删除预测</span><span class="sxs-lookup"><span data-stu-id="56d89-229">Delete a prediction</span></span>

<span data-ttu-id="56d89-230">删除预测还将删除其输出实体。</span><span class="sxs-lookup"><span data-stu-id="56d89-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="56d89-231">在 **智能** > **预测** 上转到 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56d89-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="56d89-232">选择要删除的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="56d89-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="56d89-233">选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="56d89-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]