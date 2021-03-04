---
title: 由机器学习提供支持的建议客户细分
description: 让机器学习功能帮助您根据客户属性找到感兴趣的新客户细分。
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268215"
---
# <a name="suggested-segments-preview"></a><span data-ttu-id="6ba92-103">建议的客户细分（预览版）</span><span class="sxs-lookup"><span data-stu-id="6ba92-103">Suggested segments (preview)</span></span>

<span data-ttu-id="6ba92-104">借助 AI 模型发现感兴趣的客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-104">Discover interesting segments of your customers with the help of an AI model.</span></span> <span data-ttu-id="6ba92-105">这项由机器学习提供支持的功能可根据度量或客户属性建议客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-105">This machine learning powered feature suggests segments based on measures or customer attributes.</span></span> <span data-ttu-id="6ba92-106">它可以帮助改善您的 KPI 或更好地了解属性在其他属性的上下文中的影响。</span><span class="sxs-lookup"><span data-stu-id="6ba92-106">It can help improve your KPIs or better understand the influence of attributes in context of other attributes.</span></span> 

> [!NOTE]
> <span data-ttu-id="6ba92-107">建议的客户细分功能使用自动方式来评估数据，并根据该数据做出预测，因此能够用作概要分析方法，该术语由一般数据保护条例（“GDPR”）定义。</span><span class="sxs-lookup"><span data-stu-id="6ba92-107">The suggested segments feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="6ba92-108">使用此功能处理数据时可能会受到 GDPR 或其他法律或法规的约束。</span><span class="sxs-lookup"><span data-stu-id="6ba92-108">Your use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="6ba92-109">您有责任确保在使用 Dynamics 365 Customer Insights（包括此功能）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。</span><span class="sxs-lookup"><span data-stu-id="6ba92-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including this feature, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Customer Insights 中的建议的客户细分页面，其中显示了侧窗格中的建议的详细信息。":::

## <a name="suggested-segments-to-improve-your-kpis"></a><span data-ttu-id="6ba92-111">用于改进 KPI 的建议客户细分</span><span class="sxs-lookup"><span data-stu-id="6ba92-111">Suggested segments to improve your KPIs</span></span>

<span data-ttu-id="6ba92-112">作为访问群体见解的用户，您可能具有一系列[创建的度量](measures.md)，这些度量可帮助跟踪关键绩效指标 (KPI)。</span><span class="sxs-lookup"><span data-stu-id="6ba92-112">As a user of audience insights, you likely have a series of [measures created](measures.md) that help track your Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="6ba92-113">一定要了解某些属性对此 KPI 有何影响，以创建客户细分并运行针对性强的市场活动。</span><span class="sxs-lookup"><span data-stu-id="6ba92-113">It's important to understand how certain attributes influence this KPI to create segments and run a highly targeted campaign.</span></span>   
<span data-ttu-id="6ba92-114">例如，您可以跟踪一个名为 *TotalSpendPerCustomer* 的度量。</span><span class="sxs-lookup"><span data-stu-id="6ba92-114">For example, you track a measure called *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="6ba92-115">作为一个企业，您喜欢看到此数目增加。</span><span class="sxs-lookup"><span data-stu-id="6ba92-115">As a business, you’d like to see this number grow.</span></span> <span data-ttu-id="6ba92-116">如果选择度量作为主要属性，则可以选择要评估影响力的属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-116">Choosing a measure as primary attribute, lets you select the attributes that you want to assess for influence.</span></span> <span data-ttu-id="6ba92-117">假设有 *成员资格层*、*成员资格期间* 和 *职业*。</span><span class="sxs-lookup"><span data-stu-id="6ba92-117">Let's say *membership tier*, *membership period*, and *occupation*.</span></span> <span data-ttu-id="6ba92-118">然后，Customer Insights 可以建议一个客户细分，告诉您谁是该度量的最大影响因素。</span><span class="sxs-lookup"><span data-stu-id="6ba92-118">Customer Insights can then suggest a segment that tells you who are the biggest influence of that measure.</span></span> <span data-ttu-id="6ba92-119">例如，作为 *金牌* 成员并且已与您做生意 *至少 5 年* 的 *会计人员* 是 *TotalSpendPerCustomer* 的最大影响者。</span><span class="sxs-lookup"><span data-stu-id="6ba92-119">For example, *Accountants* who are *Gold* members, and who have been with your business for *at least five years* are the biggest influencer of *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="6ba92-120">对于每个建议，您都会获得一个估计的客户细分大小。</span><span class="sxs-lookup"><span data-stu-id="6ba92-120">You’ll get an estimated segment size for every suggestion.</span></span> <span data-ttu-id="6ba92-121">您可以使用此信息为目标受众创建市场活动。</span><span class="sxs-lookup"><span data-stu-id="6ba92-121">You can use this information to create campaigns for the targeted audiences.</span></span>

## <a name="understand-what-influences-a-customer-attribute"></a><span data-ttu-id="6ba92-122">了解影响客户属性的因素</span><span class="sxs-lookup"><span data-stu-id="6ba92-122">Understand what influences a customer attribute</span></span>

<span data-ttu-id="6ba92-123">您可以选择客户属性而不是度量作为主要属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-123">You can choose a customer attribute instead of a measure as the primary attribute.</span></span> <span data-ttu-id="6ba92-124">根据您选择的影响属性，AI 模型会创建一系列建议，以显示所选属性如何影响主要属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-124">Based on your choice of influencing attributes, the AI model creates a series of suggestions that show how the selected attributes influence the primary attribute.</span></span>   
<span data-ttu-id="6ba92-125">例如，您选择 *奖励成员（是/否）* 作为主要属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-125">For example, you choose *Rewards Member (Yes/No)* as the primary attribute.</span></span> <span data-ttu-id="6ba92-126">*服务期*、*职业* 和 *支持票证数* 被设置为其他影响属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-126">*Tenure*, *Occupation*, and *Number of Support Tickets* are set as other influencing attributes.</span></span> <span data-ttu-id="6ba92-127">AI 模型可能会建议客户细分，并指明大部分任期在两年以上的 IT 专业人员是奖励成员。</span><span class="sxs-lookup"><span data-stu-id="6ba92-127">The AI model could suggest segments indicating mostly IT professionals with tenure over two years are rewards members.</span></span> <span data-ttu-id="6ba92-128">另一个建议可能会强调，任期在一年以上且支持票证少于三张的会计师是奖励会员。</span><span class="sxs-lookup"><span data-stu-id="6ba92-128">Another suggestion could highlight that accountants with tenure over one year and fewer than three support tickets are rewards members.</span></span> 

## <a name="artificial-intelligence-usage"></a><span data-ttu-id="6ba92-129">人工智能的使用</span><span class="sxs-lookup"><span data-stu-id="6ba92-129">Artificial intelligence usage</span></span>

<span data-ttu-id="6ba92-130">决策树算法使用主要属性和影响属性建议感兴趣的客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-130">Using the primary attribute and influencing attributes, a decision tree algorithm suggests interesting segments.</span></span> <span data-ttu-id="6ba92-131">这些建议基于 AI 算法选择的规则或模式。</span><span class="sxs-lookup"><span data-stu-id="6ba92-131">The suggestions are based on rules or patterns that were picked up by the AI algorithm.</span></span> <span data-ttu-id="6ba92-132">系统仅将与普通人群明显不同的客户细分显示为建议。</span><span class="sxs-lookup"><span data-stu-id="6ba92-132">Only segments that significantly differ from the average population are shown as suggestions.</span></span> <span data-ttu-id="6ba92-133">系统根据所选度量或主要属性与普通人群进行比较。</span><span class="sxs-lookup"><span data-stu-id="6ba92-133">The comparison to the average population is based on the selected measure or primary attribute.</span></span>

### <a name="responsible-ai"></a><span data-ttu-id="6ba92-134">负责 AI</span><span class="sxs-lookup"><span data-stu-id="6ba92-134">Responsible AI</span></span>

<span data-ttu-id="6ba92-135">利用建议的客户细分，您可以选择属性来创建新的客户细分并处理您选择的数据。</span><span class="sxs-lookup"><span data-stu-id="6ba92-135">Suggested segments lets you select attributes to create new segments and process the data you select.</span></span> <span data-ttu-id="6ba92-136">在选择属性（包括种族、性取向或性别等敏感属性）时，必须确保可以并且应该处理该数据。</span><span class="sxs-lookup"><span data-stu-id="6ba92-136">When choosing attributes, including sensitive attributes like race, sexual orientation, or gender, you must ensure that you can and should process that data.</span></span> <span data-ttu-id="6ba92-137">您有责任遵守适用于您组织的任何法律，并遵守组织的原则和隐私政策。</span><span class="sxs-lookup"><span data-stu-id="6ba92-137">You are responsible to comply with any laws applicable to your organization and adhere to your organization’s principles and privacy policies.</span></span>

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a><span data-ttu-id="6ba92-138">具有分类值和数值的主要属性的不同结果</span><span class="sxs-lookup"><span data-stu-id="6ba92-138">Different results for primary attributes with categorical and numeric values</span></span>

<span data-ttu-id="6ba92-139">如果您选择数字属性或分类属性作为主要属性，则客户细分建议会有所不同。</span><span class="sxs-lookup"><span data-stu-id="6ba92-139">Segment suggestions are different if you choose a numeric attribute or a categorical attribute as the primary attribute.</span></span> <span data-ttu-id="6ba92-140">类别属性中的值包含两个或更多个类别或类型。</span><span class="sxs-lookup"><span data-stu-id="6ba92-140">Values in a categorical attribute contain two or more categories or types.</span></span> <span data-ttu-id="6ba92-141">数值属性包含定量数据，并具有与之相关的度量意义。</span><span class="sxs-lookup"><span data-stu-id="6ba92-141">A numeric attribute contains quantitative data and has a sense of measurement associated with it.</span></span>

<span data-ttu-id="6ba92-142">如果以 *年收入* 或 *成员期间* 之类的数字属性为主要属性，那么系统会建议与所有客户相比该数字属性的平均值较高或较低的客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-142">With a numeric attribute like *annual income* or *membership period* as the primary attribute, the system suggests segments that have a higher or lower average value of the numeric attribute when compared to all customers.</span></span>

<span data-ttu-id="6ba92-143">如果以分类属性（例如 *客户满意度*）作为主要属性，则会导致所建议客户细分的属于特定类别的客户百分比与属于同一类别的所有客户的百分更高或更低。</span><span class="sxs-lookup"><span data-stu-id="6ba92-143">A categorical attribute like *customer satisfaction* as the primary attribute results in suggested segments that have a higher or lower percentage of customers belonging to a particular category when compared to the percentage of all customers belonging to that same category.</span></span> <span data-ttu-id="6ba92-144">例如，*客户满意度* 被选为主要属性，并且它包含三个类别（*低*‘、*中* 和 *高*）。</span><span class="sxs-lookup"><span data-stu-id="6ba92-144">For example, *customer satisfaction* is chosen as the primary attribute and it consists of three categories (*Low*, *Medium* and *High*).</span></span> <span data-ttu-id="6ba92-145">对于每个类别，所建议客户细分的属于该类别的客户所占百分比与属于同一类别的所有客户的比例相比将明显更高或更低。</span><span class="sxs-lookup"><span data-stu-id="6ba92-145">For each category, segments will be suggested that have a significantly higher or lower percentage of customers belonging to that category as compared to the proportion of all customers in same category.</span></span> <span data-ttu-id="6ba92-146">如果 22% 的所有客户的满意度为 *高*，那么，对于该类别，将仅建议 *高* 满意度客户比 22% 明显更高或更低的客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-146">If 22% of all customers have a *High* satisfaction, then, only segments that have a significantly higher or lower proportion of customers with a *High* satisfaction as compared to 22% will be suggested for that category.</span></span> <span data-ttu-id="6ba92-147">同样，如果其他类别（*低* 和 *中*）在统计上有意义，则会针对每个这样的类别建议客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-147">Similarly, segments will be suggested for each of the other categories (*Low* and *Medium*) if they are statistically significant.</span></span>

> [!NOTE]
> <span data-ttu-id="6ba92-148">当前，我们仅支持最多具有 10 个类别的主要类别属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-148">Currently, we only support primary categorical attributes that have up to 10 categories.</span></span> <span data-ttu-id="6ba92-149">如果您要查看基于具有 10 个以上类别的主要属性的客户细分建议，建议您对某些类别进行分组，以将类别数量减少到 10 个或更少。</span><span class="sxs-lookup"><span data-stu-id="6ba92-149">If you want to see segment suggestions based on a primary attribute with more than 10 categories, we recommend to group some of the categories to reduce the number of categories to 10 or fewer.</span></span> <span data-ttu-id="6ba92-150">此限制仅适用于主要属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-150">This limitation only applies to primary attributes.</span></span> <span data-ttu-id="6ba92-151">对于影响类别属性，我们当前最多支持 100 个类别。</span><span class="sxs-lookup"><span data-stu-id="6ba92-151">For influencing categorical attributes, we currently support a maximum of 100 categories.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="6ba92-152">生成建议的客户细分</span><span class="sxs-lookup"><span data-stu-id="6ba92-152">Generate suggested segments</span></span>

1. <span data-ttu-id="6ba92-153">转到 **客户细分**。</span><span class="sxs-lookup"><span data-stu-id="6ba92-153">Go to **Segments**.</span></span>

1. <span data-ttu-id="6ba92-154">选择 **建议（预览版）** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6ba92-154">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="6ba92-155">选择 **获取新建议** 以启动引导式体验。</span><span class="sxs-lookup"><span data-stu-id="6ba92-155">Select **Get new suggestions** to start the guided experience.</span></span>

1. <span data-ttu-id="6ba92-156">选择一个度量或客户属性作为主要属性，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="6ba92-156">Choose a measure or a customer attribute as the primary attribute and select **Next**.</span></span>

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="选择主要属性以获取有关建议客户细分的建议。":::

1. <span data-ttu-id="6ba92-158">选择影响属性并选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="6ba92-158">Select the influencing attributes and select **Save**.</span></span>
   
   > [!TIP]
   > <span data-ttu-id="6ba92-159">选择多个影响属性可以提高评估它们如何影响主要属性的机率。</span><span class="sxs-lookup"><span data-stu-id="6ba92-159">Selecting multiple influencing attributes improves the chances of evaluating how they influence the primary attribute.</span></span> <span data-ttu-id="6ba92-160">不要包括对主要属性没有影响的属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-160">Don't include attributes that have no influence the primary attribute.</span></span> <span data-ttu-id="6ba92-161">例如，如果您的所有客户都来自特定国家/地区，则不要包括 *国家/地区* 属性，因为它不会对输出产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="6ba92-161">For example, if all your customers are from a specific country, don't include the *country* attribute because it won't have any impact on the output.</span></span>

1. <span data-ttu-id="6ba92-162">根据客户配置文件和所选属性的数量，可能需要花费几分钟来处理所选属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-162">Depending on the number of customer profiles and selected attributes, it can take a few minutes to process the selected attributes.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="6ba92-163">查看建议的客户细分详细信息</span><span class="sxs-lookup"><span data-stu-id="6ba92-163">View details of a suggested segment</span></span>

<span data-ttu-id="6ba92-164">AI 模型生成建议后，您将在 **客户细分** > **建议（预览版）** 中找到它们。</span><span class="sxs-lookup"><span data-stu-id="6ba92-164">Once the AI model has generated the suggestions, you'll find them listed on **Segments** > **Suggestions (preview)**.</span></span>
 
<span data-ttu-id="6ba92-165">选择一个建议的客户细分以查看该建议的详细信息，包括平均值和客户细分成员数量的比较。</span><span class="sxs-lookup"><span data-stu-id="6ba92-165">Select a suggested segment to review the details of that suggestion including a comparison of the average value and the number of segment members.</span></span> <span data-ttu-id="6ba92-166">您还可以查看 AI 模型为建议所选客户细分而学习的属性值或规则。</span><span class="sxs-lookup"><span data-stu-id="6ba92-166">You can also review the attribute values or rules that the AI model learned to suggest the selected segment.</span></span>

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="6ba92-167">将建议另存为客户细分</span><span class="sxs-lookup"><span data-stu-id="6ba92-167">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="6ba92-168">转到 **客户细分** > **建议（预览版）**。</span><span class="sxs-lookup"><span data-stu-id="6ba92-168">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="6ba92-169">选择要保存的客户细分。</span><span class="sxs-lookup"><span data-stu-id="6ba92-169">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="6ba92-170">在侧窗格中，选择 **另存为客户细分**。</span><span class="sxs-lookup"><span data-stu-id="6ba92-170">In the side pane, select **Save as segment**.</span></span> 

1. <span data-ttu-id="6ba92-171">保存客户细分后，它将会显示在 **所有客户细分** 选项卡上。现在可以[像其他任何客户细分一样对其进行刷新、编辑或删除](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="6ba92-171">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed, edited, or deleted like any other segment](segments.md).</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="6ba92-172">刷新或编辑一组建议</span><span class="sxs-lookup"><span data-stu-id="6ba92-172">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="6ba92-173">转到 **客户细分** > **建议（预览版）**。</span><span class="sxs-lookup"><span data-stu-id="6ba92-173">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="6ba92-174">选择 **刷新建议** 以刷新建议，同时保留配置的属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-174">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="6ba92-175">或者选择 **编辑属性** 来修改配置的属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-175">Or select **Edit attributes** to modify the configured attributes.</span></span> <span data-ttu-id="6ba92-176">系统将重新运行 AI 模型，根据最新数据生成客户细分建议，并替换当前建议。</span><span class="sxs-lookup"><span data-stu-id="6ba92-176">The system will rerun the AI model, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

## <a name="limitations"></a><span data-ttu-id="6ba92-177">限制</span><span class="sxs-lookup"><span data-stu-id="6ba92-177">Limitations</span></span>

1. <span data-ttu-id="6ba92-178">估计的客户细分大小不匹配：如果您选择的主属性包含空值，则会影响客户细分建议中估计的客户细分大小。</span><span class="sxs-lookup"><span data-stu-id="6ba92-178">Estimated segment size mismatch: If you choose a primary attribute that contains empty values, it can affect the estimated segment size in the segment suggestions.</span></span> <span data-ttu-id="6ba92-179">保存此类客户细分时，实际客户细分大小可能与原始估计值不同。</span><span class="sxs-lookup"><span data-stu-id="6ba92-179">When saving such segment, the actual segment size can be different to the original estimation.</span></span>
 
2. <span data-ttu-id="6ba92-180">布尔类型主要属性不起作用：当前，我们仅支持字符串和数值类型的数据作为主要属性。</span><span class="sxs-lookup"><span data-stu-id="6ba92-180">Boolean type primary attributes don't work: Currently, we only support string and numeric types of data as the primary attribute.</span></span>

3. <span data-ttu-id="6ba92-181">建议的客户细分还不够明确：请记住，所选属性和这些属性的值分布会影响结果。</span><span class="sxs-lookup"><span data-stu-id="6ba92-181">Suggested segments aren't distinct enough: Keep in mind that the selected attributes and the distribution of values of those attributes influences the results.</span></span> <span data-ttu-id="6ba92-182">您可以更改影响属性，甚至可以更改主要属性，以获得不同的结果。</span><span class="sxs-lookup"><span data-stu-id="6ba92-182">You can change your influencing attributes or even your primary attribute to get different results.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]