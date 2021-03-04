---
title: 匹配数据统一的实体
description: 匹配实体以创建统一客户配置文件。
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267467"
---
# <a name="match-entities"></a><span data-ttu-id="acc52-103">匹配实体</span><span class="sxs-lookup"><span data-stu-id="acc52-103">Match entities</span></span>

<span data-ttu-id="acc52-104">完成映射阶段后，可以匹配实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="acc52-105">匹配阶段指定如何将数据集合并为一个统一的客户配置文件数据集。</span><span class="sxs-lookup"><span data-stu-id="acc52-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="acc52-106">匹配阶段需要至少[两个映射的实体](map-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="acc52-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="acc52-107">指定匹配顺序</span><span class="sxs-lookup"><span data-stu-id="acc52-107">Specify the match order</span></span>

<span data-ttu-id="acc52-108">转到 **数据** > **统一** > **匹配**，并选择 **设置顺序** 以开始匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="acc52-108">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="acc52-109">每次匹配都会将两个或更多实体统一为一个实体，同时保留每个唯一客户记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="acc52-110">在下面的示例中，我们选择了三个实体：**ContactCSV: TestData** 是 **主** 实体，**WebAccountCSV: TestData** 是 **实体 2**，**CallRecordSmall: TestData** 是 **实体 3**。</span><span class="sxs-lookup"><span data-stu-id="acc52-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="acc52-111">所选内容上面的图演示如何执行匹配顺序。</span><span class="sxs-lookup"><span data-stu-id="acc52-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="acc52-112">![编辑数据匹配顺序](media/configure-data-match-order-edit-page.png "编辑数据匹配顺序")</span><span class="sxs-lookup"><span data-stu-id="acc52-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="acc52-113">**主** 实体与 **实体 2** 匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="acc52-114">第一次匹配生成的数据集与 **实体 3** 匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="acc52-115">在此示例中，我们只选择了两次匹配，但系统可以支持更多次匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acc52-116">选择作为 **主** 实体的实体将充当统一的主数据集的基础。</span><span class="sxs-lookup"><span data-stu-id="acc52-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="acc52-117">将把匹配阶段选择的其他实体添加到此实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="acc52-118">同时，这不意味着统一的实体中将包含此实体中包含的 *所有* 数据。</span><span class="sxs-lookup"><span data-stu-id="acc52-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="acc52-119">可帮助您选择实体层次结构的注意事项有两个：</span><span class="sxs-lookup"><span data-stu-id="acc52-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="acc52-120">您认为哪个实体具有有关您的客户的最完整、最可靠的数据？</span><span class="sxs-lookup"><span data-stu-id="acc52-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="acc52-121">您刚才确认的实体是否拥有其他实体也共享的属性（例如，名称、电话号码或电子邮件地址）？</span><span class="sxs-lookup"><span data-stu-id="acc52-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="acc52-122">如果没有，请选择第二个最可靠的实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="acc52-123">选择 **完成** 以保存您的匹配顺序。</span><span class="sxs-lookup"><span data-stu-id="acc52-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="acc52-124">定义第一个匹配对的规则</span><span class="sxs-lookup"><span data-stu-id="acc52-124">Define rules for your first match pair</span></span>

<span data-ttu-id="acc52-125">指定匹配顺序后，您将在 **匹配** 页上看到定义的匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="acc52-126">运行匹配顺序之前，屏幕顶部的磁贴为空。</span><span class="sxs-lookup"><span data-stu-id="acc52-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="acc52-127">![定义规则](media/configure-data-match-need-rules.png "定义规则")</span><span class="sxs-lookup"><span data-stu-id="acc52-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="acc52-128">**需要规则** 警告说明尚未为匹配对定义任何匹配规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="acc52-129">匹配规则指定匹配一对特定实体时所用逻辑。</span><span class="sxs-lookup"><span data-stu-id="acc52-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="acc52-130">若要定义第一个规则，请打开 **规则定义** 窗格，方法是在匹配表 (1) 中选择相应匹配行，然后选择 **新建规则** (2)。</span><span class="sxs-lookup"><span data-stu-id="acc52-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-131">![新建规则](media/configure-data-match-new-rule2.png "新建规则")</span><span class="sxs-lookup"><span data-stu-id="acc52-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="acc52-132">在 **编辑规则** 窗格中，配置该规则的条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="acc52-133">每个条件由其中包含必需选择的两个行表示。</span><span class="sxs-lookup"><span data-stu-id="acc52-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-134">![“新建规则”窗格](media/configure-data-match-new-rule-condition.png "“新建规则”窗格")</span><span class="sxs-lookup"><span data-stu-id="acc52-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="acc52-135">实体/字段（第一项）- 第一个匹配对实体中将用于进行匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="acc52-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="acc52-136">例如，电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="acc52-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="acc52-137">选择可能对客户唯一的属性。</span><span class="sxs-lookup"><span data-stu-id="acc52-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="acc52-138">避免根据活动类型属性进行匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="acc52-139">换句话说，如果某个属性看起来是活动，则可能不太适合充当匹配条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="acc52-140">实体/字段（第二项）- 第二个匹配对实体中将用于进行匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="acc52-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="acc52-141">标准化 - **标准化方法**：可对所选属性使用大量标准化选项。</span><span class="sxs-lookup"><span data-stu-id="acc52-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="acc52-142">例如，删除标点符号或空格</span><span class="sxs-lookup"><span data-stu-id="acc52-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="acc52-143">对于组织名称标准化（预览版），您还可以选择 **类型（电话、姓名、组织）**</span><span class="sxs-lookup"><span data-stu-id="acc52-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-144">![标准化 - B2B](media/match-normalization-b2b.png "标准化 - B2B")</span><span class="sxs-lookup"><span data-stu-id="acc52-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="acc52-145">精度级别 - 将用于此条件的精度级别。</span><span class="sxs-lookup"><span data-stu-id="acc52-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="acc52-146">可以为匹配条件设置两种精度级别：**基本** 和 **自定义**。</span><span class="sxs-lookup"><span data-stu-id="acc52-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="acc52-147">基本：提供四个选项以供选择：“低”、“中”、“高”和“精确”。</span><span class="sxs-lookup"><span data-stu-id="acc52-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="acc52-148">如果选择 **精确**，则仅匹配 100% 匹配的记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="acc52-149">选择其他一种级别则匹配不是 100% 相同的记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="acc52-150">自定义：使用此滑块定义匹配记录时需要的自定义百分比，或在 **自定义** 字段中输入值。</span><span class="sxs-lookup"><span data-stu-id="acc52-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="acc52-151">系统将仅匹配把此阈值作为合并的匹配对传递的记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="acc52-152">滑块上的值介于 0 和 1 之间。</span><span class="sxs-lookup"><span data-stu-id="acc52-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="acc52-153">因此，0.64 表示 64%。</span><span class="sxs-lookup"><span data-stu-id="acc52-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="acc52-154">选择 **完成** 保存规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="acc52-155">添加多个条件</span><span class="sxs-lookup"><span data-stu-id="acc52-155">Add multiple conditions</span></span>

<span data-ttu-id="acc52-156">若要在仅当满足多个条件时才匹配实体，请添加多个通过 AND 运算符链接的条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="acc52-157">在 **编辑规则** 窗格中，选择 **添加条件**。</span><span class="sxs-lookup"><span data-stu-id="acc52-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="acc52-158">也可以通过选择现有条件旁边的删除按钮来删除条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="acc52-159">选择 **完成** 保存规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="acc52-160">添加多个规则</span><span class="sxs-lookup"><span data-stu-id="acc52-160">Add multiple rules</span></span>

<span data-ttu-id="acc52-161">每个条件应用于一对属性，而规则表示多组条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="acc52-162">若要按不同属性集匹配实体，可以添加更多规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="acc52-163">在访问群体见解中，转到 **数据** > **统一** > **匹配**。</span><span class="sxs-lookup"><span data-stu-id="acc52-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="acc52-164">选择要更新的实体，然后选择 **添加规则**。</span><span class="sxs-lookup"><span data-stu-id="acc52-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="acc52-165">指定[定义第一个匹配对的规则](#define-rules-for-your-first-match-pair)中介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="acc52-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="acc52-166">规则顺序至关重要。</span><span class="sxs-lookup"><span data-stu-id="acc52-166">The rule order matters.</span></span> <span data-ttu-id="acc52-167">匹配算法尝试根据第一个规则进行匹配，如果在第一个规则下未找到任何匹配项，则继续根据第二个规则进行匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="acc52-168">对匹配实体定义删除重复</span><span class="sxs-lookup"><span data-stu-id="acc52-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="acc52-169">除了上述部分中所述的指定跨实体匹配规则之外，您还可以指定删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="acc52-170">*删除重复* 是一个流程。</span><span class="sxs-lookup"><span data-stu-id="acc52-170">*Deduplication* is a process.</span></span> <span data-ttu-id="acc52-171">它会识别重复记录，将它们合并到一个记录中，并将所有源记录链接到该合并的记录，其中使用合并记录的替代 ID。</span><span class="sxs-lookup"><span data-stu-id="acc52-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="acc52-172">在确定删除重复的记录后，将在跨实体匹配流程中使用该记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="acc52-173">删除重复在实体级别实施，可应用于在匹配流程中使用的每个实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="acc52-174">添加删除重复规则</span><span class="sxs-lookup"><span data-stu-id="acc52-174">Add deduplication rules</span></span>

1. <span data-ttu-id="acc52-175">在访问群体见解中，转到 **数据** > **统一** > **匹配**。</span><span class="sxs-lookup"><span data-stu-id="acc52-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="acc52-176">在 **合并重复** 部分中，选择 **设置实体**。</span><span class="sxs-lookup"><span data-stu-id="acc52-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="acc52-177">在 **合并首选项** 部分中，选择要对其应用删除重复的实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="acc52-178">指定如何合并重复记录并选择以下三个合并选项之一：</span><span class="sxs-lookup"><span data-stu-id="acc52-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="acc52-179">*最多填充*：将属性填充最多的记录标识为入选记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="acc52-180">这是默认的合并选项。</span><span class="sxs-lookup"><span data-stu-id="acc52-180">This is the default merge option.</span></span>
   - <span data-ttu-id="acc52-181">*最常使用*：根据最常使用标识入选记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="acc52-182">需要日期或数字字段以定义近期性。</span><span class="sxs-lookup"><span data-stu-id="acc52-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="acc52-183">*最不常用*：根据最不常用标识入选记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="acc52-184">需要日期或数字字段以定义近期性。</span><span class="sxs-lookup"><span data-stu-id="acc52-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-185">![删除重复规则步骤 1](media/match-selfconflation.png "删除重复规则步骤 1")</span><span class="sxs-lookup"><span data-stu-id="acc52-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="acc52-186">在选择实体并设置其合并首选项后，请选择 **创建新规则** 以在实体级别定义删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="acc52-187">**选择字段** 列出了要对元数据进行删除重复的实体中的所有可用字段。</span><span class="sxs-lookup"><span data-stu-id="acc52-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="acc52-188">以在跨实体匹配中指定的类似方式指定标准化和精度设置。</span><span class="sxs-lookup"><span data-stu-id="acc52-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="acc52-189">您可以通过选择 **添加条件** 来定义其他条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-190">![删除重复规则步骤 2](media/match-selfconflation-rules.png "删除重复规则步骤 2")</span><span class="sxs-lookup"><span data-stu-id="acc52-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="acc52-191">您可以为一个实体创建多个删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="acc52-192">现在，运行匹配流程将根据在删除重复规则中定义的条件对记录进行分组。</span><span class="sxs-lookup"><span data-stu-id="acc52-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="acc52-193">对记录进行分组后，将应用合并策略以标识入选记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="acc52-194">然后，该入选记录将与非入选记录（例如，备用 ID）一起传递给跨实体匹配，以提高匹配质量。</span><span class="sxs-lookup"><span data-stu-id="acc52-194">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="acc52-195">为始终匹配和永不匹配定义的任何自定义匹配规则将取代删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="acc52-196">如果删除重复规则确定匹配的记录，并且将某个自定义匹配规则设置为永不匹配这些记录，则将无法匹配这两个记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="acc52-197">在运行匹配流程后，您将看到删除重复统计信息。</span><span class="sxs-lookup"><span data-stu-id="acc52-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="acc52-198">指定删除重复规则不是必需的。</span><span class="sxs-lookup"><span data-stu-id="acc52-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="acc52-199">如果未配置此类规则，将应用系统定义的规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="acc52-200">它们先将主键中共享相同值组合（完全匹配）的所有记录以及匹配规则中的字段折叠到一个记录中，然后再将实体数据传递到跨实体匹配，以增强性能和系统完整性。</span><span class="sxs-lookup"><span data-stu-id="acc52-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="acc52-201">运行匹配顺序</span><span class="sxs-lookup"><span data-stu-id="acc52-201">Run your match order</span></span>

<span data-ttu-id="acc52-202">在定义匹配规则（包括跨实体匹配和删除重复规则）后，您可以运行匹配顺序。</span><span class="sxs-lookup"><span data-stu-id="acc52-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="acc52-203">在 **匹配** 页上，选择 **运行** 以启动流程。</span><span class="sxs-lookup"><span data-stu-id="acc52-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="acc52-204">匹配算法可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="acc52-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="acc52-205">匹配过程完成前，不能更改 **匹配** 页中的属性。</span><span class="sxs-lookup"><span data-stu-id="acc52-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="acc52-206">您将在 **实体** 页中找到创建的统一客户配置文件实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="acc52-207">您的统一客服实体称为 **ConflationMatchPairs : CustomerInsights**。</span><span class="sxs-lookup"><span data-stu-id="acc52-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="acc52-208">若要进行更多配置并重新运行步骤，可以取消正在进行的匹配。</span><span class="sxs-lookup"><span data-stu-id="acc52-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="acc52-209">选择文本 **正在刷新...**，然后选择显示的侧边窗格底部的 **取消作业**。</span><span class="sxs-lookup"><span data-stu-id="acc52-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="acc52-210">匹配过程完成后，文本 **正在刷新...** 将更改为 **成功**，而您又可以使用页面的所有功能。</span><span class="sxs-lookup"><span data-stu-id="acc52-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="acc52-211">第一个匹配过程将导致创建一个统一的主实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="acc52-212">后面运行的所有匹配都将导致扩展该实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="acc52-213">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="acc52-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="acc52-214">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="acc52-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="acc52-215">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="acc52-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="acc52-216">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="acc52-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="acc52-217">实体形式的删除重复输出</span><span class="sxs-lookup"><span data-stu-id="acc52-217">Deduplication output as an entity</span></span>
<span data-ttu-id="acc52-218">除了会在跨实体匹配过程中创建统一主实体之外，删除重复过程还会为匹配顺序中的每个实体生成一个新实体，以标识删除了重复数据的记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-218">In addition to the unified master entity created as part of the cross entity matching, the deduplication process also generates a new entity for every entity from the match order to identify the deduplicated records.</span></span> <span data-ttu-id="acc52-219">这些实体可以与名称为 **Deduplication_Datasource_Entity** 的 **实体** 页面内 **系统** 部分中的 **ConflationMatchPairs:CustomerInsights** 一起找到。</span><span class="sxs-lookup"><span data-stu-id="acc52-219">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_Datasource_Entity**.</span></span>

<span data-ttu-id="acc52-220">删除重复输出实体包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="acc52-220">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="acc52-221">ID/键</span><span class="sxs-lookup"><span data-stu-id="acc52-221">IDs / Keys</span></span>
  - <span data-ttu-id="acc52-222">主键字段及其备用 ID 字段。</span><span class="sxs-lookup"><span data-stu-id="acc52-222">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="acc52-223">备用 ID 字段由为一条记录标识的所有备用 ID 组成。</span><span class="sxs-lookup"><span data-stu-id="acc52-223">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="acc52-224">Deduplication_GroupId 字段显示在实体中标识的组或群集，该组或群集根据指定的删除重复字段将所有相似记录归组。</span><span class="sxs-lookup"><span data-stu-id="acc52-224">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="acc52-225">这用于系统处理目的。</span><span class="sxs-lookup"><span data-stu-id="acc52-225">This is  used for system processing purposes.</span></span> <span data-ttu-id="acc52-226">如果没有指定手动删除重复规则并且系统定义的删除重复规则适用，则您可能在重复删除输出实体中找不到此字段。</span><span class="sxs-lookup"><span data-stu-id="acc52-226">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="acc52-227">Deduplication_WinnerId：此字段包含标识的组或群集中的获胜者 ID。</span><span class="sxs-lookup"><span data-stu-id="acc52-227">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="acc52-228">如果 Deduplication_WinnerId 与记录的主键值相同，则这意味着该记录是入选记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-228">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="acc52-229">用于定义删除重复规则的字段。</span><span class="sxs-lookup"><span data-stu-id="acc52-229">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="acc52-230">“规则”和“分数”字段，分别用于表示所应用的删除重复规则以及匹配算法返回的分数。</span><span class="sxs-lookup"><span data-stu-id="acc52-230">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="acc52-231">预览和验证匹配</span><span class="sxs-lookup"><span data-stu-id="acc52-231">Review and validate your matches</span></span>

<span data-ttu-id="acc52-232">评估匹配对的质量并进行优化：</span><span class="sxs-lookup"><span data-stu-id="acc52-232">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="acc52-233">在 **匹配** 页上，您将找到两个磁贴，这些磁贴显示有关您的数据的初始见解。</span><span class="sxs-lookup"><span data-stu-id="acc52-233">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="acc52-234">**唯一客户数量**：显示系统确定的唯一配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="acc52-234">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="acc52-235">**匹配的记录数量**：显示您的所有匹配对中的匹配项数量。</span><span class="sxs-lookup"><span data-stu-id="acc52-235">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="acc52-236">在 **匹配顺序** 表中，可评估每个匹配对的结果，方法是将此匹配对实体生成的记录数量与成功匹配的记录百分比进行比较。</span><span class="sxs-lookup"><span data-stu-id="acc52-236">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="acc52-237">您将在 **匹配顺序** 表中实体的 **规则** 部分内找到规则级别上成功匹配的记录的百分比。</span><span class="sxs-lookup"><span data-stu-id="acc52-237">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="acc52-238">可通过选择规则旁边的表符号查看规则级别的所有这些记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-238">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="acc52-239">建议查看一小组记录以验证这些记录的匹配是否正确。</span><span class="sxs-lookup"><span data-stu-id="acc52-239">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="acc52-240">围绕您的条件试验不同精度阈值以确定最佳值。</span><span class="sxs-lookup"><span data-stu-id="acc52-240">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="acc52-241">选择要试验的匹配对规则的省略号 (...)，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="acc52-241">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="acc52-242">选择要试验的条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-242">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="acc52-243">每个条件由 **匹配规则** 窗格中的一行表示。</span><span class="sxs-lookup"><span data-stu-id="acc52-243">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="acc52-244">**条件预览** 页中显示的内容取决于您为条件选择的精度级别。</span><span class="sxs-lookup"><span data-stu-id="acc52-244">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="acc52-245">找到所选条件匹配的记录和不匹配的记录的数量。</span><span class="sxs-lookup"><span data-stu-id="acc52-245">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="acc52-246">深入了解不同阈值级别的效果。</span><span class="sxs-lookup"><span data-stu-id="acc52-246">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="acc52-247">可以比较各阈值级别下将匹配的记录数量，并查看各选项下的记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-247">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="acc52-248">选择每个磁贴并查看表部分中的数据。</span><span class="sxs-lookup"><span data-stu-id="acc52-248">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="acc52-249">优化匹配</span><span class="sxs-lookup"><span data-stu-id="acc52-249">Optimize your matches</span></span>

<span data-ttu-id="acc52-250">可通过重新配置部分匹配参数来提高质量：</span><span class="sxs-lookup"><span data-stu-id="acc52-250">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="acc52-251">通过选择 **编辑** 来 **更改匹配顺序**，以及更改匹配顺序字段。</span><span class="sxs-lookup"><span data-stu-id="acc52-251">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="acc52-252">![编辑数据匹配顺序](media/configure-data-match-order-edit.png "编辑数据匹配顺序")</span><span class="sxs-lookup"><span data-stu-id="acc52-252">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="acc52-253">如果定义了多个规则，**更改规则的顺序**。</span><span class="sxs-lookup"><span data-stu-id="acc52-253">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="acc52-254">可以通过在匹配规则网格中选择 **上移** 和 **下移** 选项，为匹配规则重新排序。</span><span class="sxs-lookup"><span data-stu-id="acc52-254">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="acc52-255">![更改规则顺序](media/configure-data-change-rule-order.png "更改规则顺序")</span><span class="sxs-lookup"><span data-stu-id="acc52-255">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="acc52-256">如果已经定义了匹配规则，但是希望通过修改来创建相似规则，请 **复制规则**。</span><span class="sxs-lookup"><span data-stu-id="acc52-256">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="acc52-257">方法是选择 **复制**。</span><span class="sxs-lookup"><span data-stu-id="acc52-257">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="acc52-258">![复制规则](media/configure-data-duplicate-rule.png "复制规则")</span><span class="sxs-lookup"><span data-stu-id="acc52-258">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="acc52-259">用于从匹配过程中排除匹配规则时保留匹配规则的 **停用规则**。</span><span class="sxs-lookup"><span data-stu-id="acc52-259">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="acc52-260">![停用规则](media/configure-data-deactivate-rule.png "停用规则")</span><span class="sxs-lookup"><span data-stu-id="acc52-260">![Deactivate a rule](media/configure-data-deactivate-rule.png "Deactivate a rule")</span></span>

- <span data-ttu-id="acc52-261">通过选择 **编辑** 符号 **编辑规则**。</span><span class="sxs-lookup"><span data-stu-id="acc52-261">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="acc52-262">可以应用以下更改：</span><span class="sxs-lookup"><span data-stu-id="acc52-262">You can apply the following changes:</span></span>

  - <span data-ttu-id="acc52-263">更改条件的属性：在特定条件行内选择新属性。</span><span class="sxs-lookup"><span data-stu-id="acc52-263">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="acc52-264">更改条件的阈值：调整精度滑块。</span><span class="sxs-lookup"><span data-stu-id="acc52-264">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="acc52-265">更改条件的标准化方法：更新标准化方法。</span><span class="sxs-lookup"><span data-stu-id="acc52-265">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="acc52-266">指定自定义匹配记录</span><span class="sxs-lookup"><span data-stu-id="acc52-266">Specify your custom match records</span></span>

<span data-ttu-id="acc52-267">可以指定其中包含始终应或永不应匹配的记录的条件。</span><span class="sxs-lookup"><span data-stu-id="acc52-267">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="acc52-268">可以将这些规则批量上传到匹配过程。</span><span class="sxs-lookup"><span data-stu-id="acc52-268">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="acc52-269">选择 **匹配顺序** 屏幕中的 **自定义匹配** 选项。</span><span class="sxs-lookup"><span data-stu-id="acc52-269">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-270">![创建自定义匹配](media/custom-match-create.png "创建自定义匹配")</span><span class="sxs-lookup"><span data-stu-id="acc52-270">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="acc52-271">如果未上传实体，将看到一个新的 **自定义匹配** 对话框，需要您在其中填写一些详细信息。</span><span class="sxs-lookup"><span data-stu-id="acc52-271">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="acc52-272">如果之前已经提供了这些详细信息，请跳到步骤 8。</span><span class="sxs-lookup"><span data-stu-id="acc52-272">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-273">![“新建自定义匹配”对话框](media/custom-match-new-dialog-box.png "“新建自定义匹配”对话框")</span><span class="sxs-lookup"><span data-stu-id="acc52-273">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="acc52-274">选择 **填写模板** 以获取一个模板文，用于指定始终应或永不应匹配哪些实体中的哪些记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-274">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="acc52-275">您需要分别填写两个不同文件中的“始终匹配”记录和“永不匹配”记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-275">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="acc52-276">此模板中包含用于指定实体的字段和要在自定义匹配中使用的实体主键。</span><span class="sxs-lookup"><span data-stu-id="acc52-276">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="acc52-277">例如，如果要让销售实体中的主键 12345 始终与联系人实体中的主键 34567 匹配，则需进行下面的指定：</span><span class="sxs-lookup"><span data-stu-id="acc52-277">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="acc52-278">实体 1：销售</span><span class="sxs-lookup"><span data-stu-id="acc52-278">Entity1: Sales</span></span>
    - <span data-ttu-id="acc52-279">实体 1 键：12345</span><span class="sxs-lookup"><span data-stu-id="acc52-279">Entity1Key: 12345</span></span>
    - <span data-ttu-id="acc52-280">实体 2：联系人</span><span class="sxs-lookup"><span data-stu-id="acc52-280">Entity2: Contact</span></span>
    - <span data-ttu-id="acc52-281">实体 2 键：34567</span><span class="sxs-lookup"><span data-stu-id="acc52-281">Entity2Key: 34567</span></span>

   <span data-ttu-id="acc52-282">同一个模板文件可以指定多个实体的自定义匹配记录。</span><span class="sxs-lookup"><span data-stu-id="acc52-282">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="acc52-283">如果要为实体上的删除重复操作指定自定义匹配，请提供与 Entity1 和 Entity2 相同的实体，并设置不同的主键值。</span><span class="sxs-lookup"><span data-stu-id="acc52-283">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

5. <span data-ttu-id="acc52-284">添加要应用的所有替代项之后，保存模板文件。</span><span class="sxs-lookup"><span data-stu-id="acc52-284">After adding all the overrides you want to apply, save the template file.</span></span>

6. <span data-ttu-id="acc52-285">转到 **数据** > **数据源** 并将模板文件作为新实体引入。</span><span class="sxs-lookup"><span data-stu-id="acc52-285">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="acc52-286">引入后，可以将其用于指定匹配配置。</span><span class="sxs-lookup"><span data-stu-id="acc52-286">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="acc52-287">上传文件且实体可用之后，再次选择 **自定义匹配** 选项。</span><span class="sxs-lookup"><span data-stu-id="acc52-287">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="acc52-288">将看到用于指定要包含的实体的选项。</span><span class="sxs-lookup"><span data-stu-id="acc52-288">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="acc52-289">从下拉菜单选择所需实体。</span><span class="sxs-lookup"><span data-stu-id="acc52-289">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acc52-290">![自定义匹配替代](media/custom-match-overrides.png "自定义匹配替代")</span><span class="sxs-lookup"><span data-stu-id="acc52-290">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="acc52-291">选择要用于 **始终匹配** 和 **永不匹配** 的实体，然后选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="acc52-291">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="acc52-292">在 **匹配** 页上为刚才设置的自定义匹配配置选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="acc52-292">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="acc52-293">在 **匹配** 页上选择 **运行** 与开始执行匹配过程，而自定义匹配配置将生效。</span><span class="sxs-lookup"><span data-stu-id="acc52-293">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="acc52-294">设置的配置将替代系统匹配的所有规则。</span><span class="sxs-lookup"><span data-stu-id="acc52-294">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="acc52-295">匹配完成后，可以验证 **ConflationMatchPair** 实体以确认合并匹配中是否应用了替代。</span><span class="sxs-lookup"><span data-stu-id="acc52-295">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="acc52-296">下一步</span><span class="sxs-lookup"><span data-stu-id="acc52-296">Next step</span></span>

<span data-ttu-id="acc52-297">完成至少一个匹配对的匹配过程后，可以通过浏览 [**合并**](merge-entities.md)主题解决数据中可能的冲突。</span><span class="sxs-lookup"><span data-stu-id="acc52-297">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]