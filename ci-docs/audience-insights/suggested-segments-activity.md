---
title: 基于活动的建议客户细分。
description: 让机器学习功能根据客户活动帮助您查找新客户细分和感兴趣的客户细分。
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034053"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="0a1f5-103">基于活动数据的建议客户细分（预览版）</span><span class="sxs-lookup"><span data-stu-id="0a1f5-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="0a1f5-104">根据引入到 Customer Insights 的客户活动数据发现感兴趣的客户细分。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="0a1f5-105">活动数据的示例包括交易、支持通话持续时间、购买或退货。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="0a1f5-106">为了建议客户细分，将分析活动数据以了解最近情况、频率和货币值（或持续时间）。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="0a1f5-107">或者，您可以生成[建议的客户细分以改进度量或更好地了解是什么对属性产生了影响](suggested-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="建议的客户细分选项卡，显示了基于活动和基于属性的客户细分的客户细分建议。":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="0a1f5-109">按活动对客户分类</span><span class="sxs-lookup"><span data-stu-id="0a1f5-109">Categorize customers by activity</span></span>

<span data-ttu-id="0a1f5-110">通过 Customer Insights 中可用的[活动数据](activities.md)，我们可以生成表示客户组的建议：</span><span class="sxs-lookup"><span data-stu-id="0a1f5-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="0a1f5-111">最活跃的客户</span><span class="sxs-lookup"><span data-stu-id="0a1f5-111">most active customers</span></span> 
- <span data-ttu-id="0a1f5-112">购买最多的客户</span><span class="sxs-lookup"><span data-stu-id="0a1f5-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="0a1f5-113">创造收入最多的客户</span><span class="sxs-lookup"><span data-stu-id="0a1f5-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="0a1f5-114">最近没有活动的客户</span><span class="sxs-lookup"><span data-stu-id="0a1f5-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="0a1f5-115">经常与您的公司交互的客户</span><span class="sxs-lookup"><span data-stu-id="0a1f5-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="0a1f5-116">如果您有零售业务，您可以找出哪些客户创造的收入最高并奖励他们优惠券。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="0a1f5-117">或者，您可以识别临时客户并提议他们加入奖励计划，以便他们更频繁地访问您的公司。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="0a1f5-118">如果您任职于提供公共医疗保健服务的医疗保健公司，并且您的目标是最大程度地减少单个患者的费用。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="0a1f5-119">这样做的一个方法可能是在尽可能少的访问中提供最佳护理来减少重复访问。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="0a1f5-120">在这种情况下，您的目标就是保持访问频率较低，并将患者经常性成本降到最低。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="0a1f5-121">或者，您可以确定约会频繁且经常性成本高的患者的客户细分，并分析这些情况以改善个人治疗。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="0a1f5-122">所需数据</span><span class="sxs-lookup"><span data-stu-id="0a1f5-122">Required data</span></span>

<span data-ttu-id="0a1f5-123">系统根据选定的输入数据生成建议。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="0a1f5-124">客户配置文件：特定客户细分的所有客户或成员。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="0a1f5-125">时间段：上个月、去年或任何自定义期限。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="0a1f5-126">活动类型：购买、零售交易、联机交易、客户支持案例、订阅等。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="0a1f5-127">Customer Insights 中包含活动数据的实体：UnifiedActivity 实体或特定活动的实体。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="0a1f5-128">要包含的维度：最近数据、频率或货币维度，具体取决于业务要求。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="0a1f5-129">生成建议的客户细分</span><span class="sxs-lookup"><span data-stu-id="0a1f5-129">Generate suggested segments</span></span>

1. <span data-ttu-id="0a1f5-130">转到 **客户细分**。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="0a1f5-131">选择 **建议（预览版）** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="0a1f5-132">选择 **查找新建议** 并选择 **查看或预计客户行为**。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="0a1f5-133">选择 **开始** 以运行引导式体验。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="基于活动的建议细分的配置向导的第一步。":::

1. <span data-ttu-id="0a1f5-135">提供所需的输入数据并选择 **下一步** 继续。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="0a1f5-136">选择客户：包括所有客户或特定客户细分。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="0a1f5-137">选择活动：选择活动类型和描述该活动的实体。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="0a1f5-138">首选项：设置要考虑的时间段和建议的因素，并映射属性。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="0a1f5-139">检查您的输入并选择 **运行** 以运行模型并生成建议。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="0a1f5-140">根据客户配置文件和所选活动的数量，可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="0a1f5-141">在生成建议后，可以按您最感兴趣的维度或值筛选建议。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="0a1f5-142">查看建议的客户细分详细信息</span><span class="sxs-lookup"><span data-stu-id="0a1f5-142">View details of a suggested segment</span></span>

<span data-ttu-id="0a1f5-143">生成建议之后，在 **基于活动的建议** 部分中，您将会发现 **客户细分** > **建议（预览）** 中列出了这些建议。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="展开的侧窗格，其中显示了建议的客户细分的详细数据。":::

<span data-ttu-id="0a1f5-145">针对建议的客户细分选择 **查看建议**，以查看该客户细分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="0a1f5-146">侧窗格提供了与目标组比较的每个维度范围等详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="0a1f5-147">它还突出显示该客户细分中潜在成员的数量以及占总客户数的对应百分比。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="0a1f5-148">如果要将建议保留为客户细分，请选择 **创建客户细分**。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="0a1f5-149">将建议另存为客户细分</span><span class="sxs-lookup"><span data-stu-id="0a1f5-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="0a1f5-150">转到 **客户细分** > **建议（预览版）**。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="0a1f5-151">选择要保存的客户细分。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="0a1f5-152">在侧窗格中，选择 **创建客户细分**。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="0a1f5-153">保存客户细分后，它将显示在 **所有客户细分** 选项卡上的客户细分列表中。可以[像刷新或删除任何其他客户细分那样刷新或删除](segments.md)该客户细分。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="0a1f5-154">您无法编辑客户细分详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-154">You can't edit the segment details.</span></span> <span data-ttu-id="0a1f5-155">但是，您可以更改建议的输入条件并生成不同的建议。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="0a1f5-156">刷新或编辑一组建议</span><span class="sxs-lookup"><span data-stu-id="0a1f5-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="0a1f5-157">转到 **客户细分** > **建议（预览版）**，在 **基于活动的建议** 部分中查找客户细分。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="0a1f5-158">选择 **刷新建议** 以刷新建议，同时保留配置的属性。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="0a1f5-159">或者选择 **编辑建议** 以修改配置的属性。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="0a1f5-160">系统将重新运行该流程，根据最新数据生成客户细分建议，并替换当前的建议。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
