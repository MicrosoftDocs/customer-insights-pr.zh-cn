---
title: 使用预测填写部分数据
description: 使用预测填写不完整的客户数据。
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648700"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="03420-103">使用预测填写部分数据</span><span class="sxs-lookup"><span data-stu-id="03420-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="03420-104">可通过预测轻松创建预测值，用于增强对客户的了解。</span><span class="sxs-lookup"><span data-stu-id="03420-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="03420-105">在 **智能** > **预测** 页面上，您可以选择 **我的预测** 以查看您在访问群体见解的其他部分中配置的预测，并允许您进一步自定义它们。</span><span class="sxs-lookup"><span data-stu-id="03420-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="03420-106">如果您的环境使用 Azure Data Lake Gen 2 存储，则不能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="03420-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="03420-107">预测功能使用自动化方法评估数据，并根据这些数据进行预测，因此可以用作探查方法，而该术语是一般数据保护条例 (GDPR) 定义的。</span><span class="sxs-lookup"><span data-stu-id="03420-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="03420-108">客户在使用此功能处理数据时，应该遵守 GDPR 或其他法律或法规。</span><span class="sxs-lookup"><span data-stu-id="03420-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="03420-109">您有责任确保在使用 Dynamics 365 Customer Insights（包括预测）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。</span><span class="sxs-lookup"><span data-stu-id="03420-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03420-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="03420-110">Prerequisites</span></span>

<span data-ttu-id="03420-111">若要让组织可以使用预测功能，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="03420-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="03420-112">您的组织有[在 Common Data Service 中设置](https://docs.microsoft.com/ai-builder/build-model#prerequisites)的实例，它与 Customer Insights 位于同一组织中。</span><span class="sxs-lookup"><span data-stu-id="03420-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="03420-113">您的环境将附加到 Common Data Service 实例。</span><span class="sxs-lookup"><span data-stu-id="03420-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="03420-114">如果您在 [创建新环境](manage-environments.md)，请在 **创建环境** 对话框中配置该环境，然后选择 **高级**。</span><span class="sxs-lookup"><span data-stu-id="03420-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="03420-115">如果您已经创建了环境，请转到其设置并选择 **高级**。</span><span class="sxs-lookup"><span data-stu-id="03420-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="03420-116">在任一情况下，在 **使用预测** 部分中，输入您想要将环境附加到的 Common Data Service 实例 URL。</span><span class="sxs-lookup"><span data-stu-id="03420-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="03420-117">在客户实体中创建预测</span><span class="sxs-lookup"><span data-stu-id="03420-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="03420-118">在访问群体见解中，转到 **数据** > **实体**。</span><span class="sxs-lookup"><span data-stu-id="03420-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="03420-119">选择 **客户** 实体。</span><span class="sxs-lookup"><span data-stu-id="03420-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="03420-120">在 **客户：CustomerInsights** 实体中，在 **字段** 选项卡上进行选择。</span><span class="sxs-lookup"><span data-stu-id="03420-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="03420-121">找到要预测其值的属性名，然后在 **摘要** 列中选择 **概览** 图标。</span><span class="sxs-lookup"><span data-stu-id="03420-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03420-122">![“概览”图标](media/intelligence-overviewicon.png "“概览”图标")</span><span class="sxs-lookup"><span data-stu-id="03420-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="03420-123">如果属性的缺失值比例较高，请选择 **预测缺失值** 继续进行预测。</span><span class="sxs-lookup"><span data-stu-id="03420-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03420-124">![“概览”状态，并且显示了预测缺失值按钮](media/intelligence-overviewpredictmissingvalues.png "“概览”状态，并且显示了预测缺失值按钮")</span><span class="sxs-lookup"><span data-stu-id="03420-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="03420-125">为预测的结果提供 **显示名称** 和 **输出实体名称**。</span><span class="sxs-lookup"><span data-stu-id="03420-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="03420-126">预填充的选项列表将显示可在何处将值映射到预测的类别。</span><span class="sxs-lookup"><span data-stu-id="03420-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="03420-127">在此情况下，您的类别选项只能是 0 或 1，因为它们映射到 true/false 或预测的二进制特征。</span><span class="sxs-lookup"><span data-stu-id="03420-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="03420-128">在“类别”列，请将要在最终预测中归类为“0”的字段值映射到“0”，并将要在最终预测中归类为“1”的项映射到“1”。</span><span class="sxs-lookup"><span data-stu-id="03420-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03420-129">![显示字段值映射到类别的示例](media/intelligence-categorymapping.png "显示字段值映射到类别的示例")</span><span class="sxs-lookup"><span data-stu-id="03420-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="03420-130">选择 **完成**，然后将处理预测。</span><span class="sxs-lookup"><span data-stu-id="03420-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="03420-131">处理需要一些时间，具体取决于数据的大小和复杂程度。</span><span class="sxs-lookup"><span data-stu-id="03420-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="03420-132">将根据您创建的预测的 **输出实体名称** 在新实体中提供结果。</span><span class="sxs-lookup"><span data-stu-id="03420-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="03420-133">创建细分时创建预测</span><span class="sxs-lookup"><span data-stu-id="03420-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="03420-134">创建细分时，也可以预测所选特定属性的缺失值。</span><span class="sxs-lookup"><span data-stu-id="03420-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="03420-135">特别是，当您根据统一的客户实体或客户度量实体快速创建细分时。</span><span class="sxs-lookup"><span data-stu-id="03420-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="03420-136">在此流程中，您将选择要充当细分基础的特定属性，如客户满意度或购买量。</span><span class="sxs-lookup"><span data-stu-id="03420-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="03420-137">在创建细分后，系统将建议一种方法，用于预测此属性的所有缺失值。</span><span class="sxs-lookup"><span data-stu-id="03420-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="03420-138">在访问群体见解中，转到 **客户细分** 并选择 **配置文件** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="03420-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="03420-139">选择要充当细分的创建基础的 **字段**，选择 **运算符**，然后选择 **审阅**。</span><span class="sxs-lookup"><span data-stu-id="03420-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="03420-140">为细分提供 **名称** 和 **显示名称**。</span><span class="sxs-lookup"><span data-stu-id="03420-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="03420-141">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="03420-141">Select **Save**.</span></span>

5. <span data-ttu-id="03420-142">如果您创建的细分在源字段中的数据不完整，可以选择预测缺失值。</span><span class="sxs-lookup"><span data-stu-id="03420-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03420-143">![“预测”按钮](media/segments-predictoption.png "“预测”按钮")</span><span class="sxs-lookup"><span data-stu-id="03420-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="03420-144">为预测的结果提供 **显示名称** 和 **输出实体名称**。</span><span class="sxs-lookup"><span data-stu-id="03420-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="03420-145">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="03420-145">Select **Done**.</span></span> <span data-ttu-id="03420-146">您的预测将很快在使用您为 **输出实体名称** 提供的名称的新实体中生成。</span><span class="sxs-lookup"><span data-stu-id="03420-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="03420-147">查看预测</span><span class="sxs-lookup"><span data-stu-id="03420-147">View a prediction</span></span>

1. <span data-ttu-id="03420-148">在访问群体见解中，转到 **智能** > **预测** > **我的预测**。</span><span class="sxs-lookup"><span data-stu-id="03420-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="03420-149">选择要查看的预测。</span><span class="sxs-lookup"><span data-stu-id="03420-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="03420-150">选择 **操作** 列中的省略号，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="03420-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="03420-151">将在预测的视图中看到一些数据点。</span><span class="sxs-lookup"><span data-stu-id="03420-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03420-152">![“预测”页面](media/intelligence-predictionsviewpage.png "“预测”页面")</span><span class="sxs-lookup"><span data-stu-id="03420-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="03420-153">**预测值** 显示您在“字段值到类别映射”阶段创建的映射。</span><span class="sxs-lookup"><span data-stu-id="03420-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="03420-154">这些是您的数据集中已映射到特定类别的值。</span><span class="sxs-lookup"><span data-stu-id="03420-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="03420-155">-**主要影响因素** 是数据集内最有可能影响正在映射到特定类别的字段值的预测置信度的因素。</span><span class="sxs-lookup"><span data-stu-id="03420-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="03420-156">**性能** 指示预测的表现。</span><span class="sxs-lookup"><span data-stu-id="03420-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="03420-157">选择此链接可了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="03420-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="03420-158">**预览** 显示预测的输出数据集和预测值的可能性，也称为置信度（0 是不确定，1 是确定）的示例。</span><span class="sxs-lookup"><span data-stu-id="03420-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="03420-159">更新预测</span><span class="sxs-lookup"><span data-stu-id="03420-159">Update a prediction</span></span>

1. <span data-ttu-id="03420-160">在访问群体见解中，转到 **智能** > **预测** > **我的预测**。</span><span class="sxs-lookup"><span data-stu-id="03420-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="03420-161">选择要更新的预测，然后选择 **更新** 图标。</span><span class="sxs-lookup"><span data-stu-id="03420-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="03420-162">将计划处理预测。</span><span class="sxs-lookup"><span data-stu-id="03420-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="03420-163">可以在 **预测** 页的 **更新时间** 列中查看其上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="03420-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="03420-164">编辑预测</span><span class="sxs-lookup"><span data-stu-id="03420-164">Edit a prediction</span></span>

<span data-ttu-id="03420-165">创建预测之后，可以在 AI Builder 中自定义模型以提高模型的效率。</span><span class="sxs-lookup"><span data-stu-id="03420-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="03420-166">在访问群体见解中，转到 **智能** > **预测** > **我的预测**。</span><span class="sxs-lookup"><span data-stu-id="03420-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="03420-167">选择要编辑的预测。</span><span class="sxs-lookup"><span data-stu-id="03420-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="03420-168">选择 **操作** 列中的省略号，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="03420-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="03420-169">选择 **在 AI Builder 中自定义**。</span><span class="sxs-lookup"><span data-stu-id="03420-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="03420-170">在 AI Builder 中更新模型。</span><span class="sxs-lookup"><span data-stu-id="03420-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="03420-171">[了解有关在 AI Builder 中管理模型的详细信息](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models)。</span><span class="sxs-lookup"><span data-stu-id="03420-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="03420-172">下次运行预测将使用您已创建的更新后模型。</span><span class="sxs-lookup"><span data-stu-id="03420-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="03420-173">在 AI Builder 中创建的新模型不会显示在访问群体见解中，除非已从上面列出的体验中创建该模型。</span><span class="sxs-lookup"><span data-stu-id="03420-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="03420-174">删除预测</span><span class="sxs-lookup"><span data-stu-id="03420-174">Remove a prediction</span></span>

1. <span data-ttu-id="03420-175">在访问群体见解中，转到 **智能** > **预测** > **我的预测**。</span><span class="sxs-lookup"><span data-stu-id="03420-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="03420-176">选择要删除的预测。</span><span class="sxs-lookup"><span data-stu-id="03420-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="03420-177">选择 **操作** 列中的省略号，然后选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="03420-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="03420-178">确认删除。</span><span class="sxs-lookup"><span data-stu-id="03420-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="03420-179">疑难解答​​</span><span class="sxs-lookup"><span data-stu-id="03420-179">Troubleshooting</span></span>

<span data-ttu-id="03420-180">如果因为错误无法完成附加 Common Data Service 流程，可尝试手动完成此流程。</span><span class="sxs-lookup"><span data-stu-id="03420-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="03420-181">附加流程中可能发生两种已知问题。</span><span class="sxs-lookup"><span data-stu-id="03420-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="03420-182">未安装客户卡加载项解决方案。</span><span class="sxs-lookup"><span data-stu-id="03420-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="03420-183">按照说明[安装和配置解决方案](customer-card-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="03420-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="03420-184">未授予应用权限。</span><span class="sxs-lookup"><span data-stu-id="03420-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="03420-185">转至 [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="03420-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="03420-186">选择 **环境**。</span><span class="sxs-lookup"><span data-stu-id="03420-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="03420-187">选择要向其添加权限的环境旁边的省略号，然后选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="03420-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="03420-188">展开 **用户 + 权限**，然后选择 **用户**。</span><span class="sxs-lookup"><span data-stu-id="03420-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="03420-189">选择 **+ 新建**，然后选择 **用户**。</span><span class="sxs-lookup"><span data-stu-id="03420-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="03420-190">选择 **应用程序用户**（如果尚未选择），然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="03420-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="03420-191">**用户名：**cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="03420-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="03420-192">**应用程序 ID：** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="03420-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="03420-193">**名：** Customer</span><span class="sxs-lookup"><span data-stu-id="03420-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="03420-194">**姓：** Insights</span><span class="sxs-lookup"><span data-stu-id="03420-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="03420-195">**主要电子邮件**：cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="03420-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="03420-196">选择 **保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="03420-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="03420-197">选择您刚创建的用户。</span><span class="sxs-lookup"><span data-stu-id="03420-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="03420-198">选择顶部菜单栏中的 **管理角色**。</span><span class="sxs-lookup"><span data-stu-id="03420-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="03420-199">选择 **系统管理员**，然后选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="03420-199">Select **System Administrator**, then select **OK**.</span></span>
