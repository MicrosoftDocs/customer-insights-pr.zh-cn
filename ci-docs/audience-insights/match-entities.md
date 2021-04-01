---
title: 匹配数据统一的实体
description: 匹配实体以创建统一客户配置文件。
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb84c44aa530346a73ba720106734d705a45f23
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595553"
---
# <a name="match-entities"></a><span data-ttu-id="99868-103">匹配实体</span><span class="sxs-lookup"><span data-stu-id="99868-103">Match entities</span></span>

<span data-ttu-id="99868-104">匹配阶段指定如何将数据集合并为一个统一的客户配置文件数据集。</span><span class="sxs-lookup"><span data-stu-id="99868-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="99868-105">在数据统一过程中完成[映射步骤](map-entities.md)后，就可以匹配实体了。</span><span class="sxs-lookup"><span data-stu-id="99868-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="99868-106">匹配阶段需要至少两个映射的实体。</span><span class="sxs-lookup"><span data-stu-id="99868-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="99868-107">匹配页由三个部分组成：</span><span class="sxs-lookup"><span data-stu-id="99868-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="99868-108">对匹配记录数进行汇总的关键指标</span><span class="sxs-lookup"><span data-stu-id="99868-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="99868-109">跨实体匹配的匹配顺序和规则</span><span class="sxs-lookup"><span data-stu-id="99868-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="99868-110">匹配实体的删除重复规则</span><span class="sxs-lookup"><span data-stu-id="99868-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="99868-111">指定匹配顺序</span><span class="sxs-lookup"><span data-stu-id="99868-111">Specify the match order</span></span>

<span data-ttu-id="99868-112">转到 **数据** > **统一** > **匹配**，并选择 **设置顺序** 以开始匹配阶段。</span><span class="sxs-lookup"><span data-stu-id="99868-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="99868-113">每个匹配将两个或多个实体统一为一个合并实体。</span><span class="sxs-lookup"><span data-stu-id="99868-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="99868-114">同时，它将保留唯一的客户记录。</span><span class="sxs-lookup"><span data-stu-id="99868-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="99868-115">例如，我们选择了以下两个实体：**eCommerce:eCommerceContacts**（作为主要实体）和 **LoyaltyScheme:loyCustomers**（作为第二个实体）。</span><span class="sxs-lookup"><span data-stu-id="99868-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="99868-116">实体的顺序指定了系统尝试匹配记录的顺序。</span><span class="sxs-lookup"><span data-stu-id="99868-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="数据统一过程的“统一”区域中“匹配”页的屏幕截图。":::
  
<span data-ttu-id="99868-118">主要实体 *eCommerce:eCommerceContacts* 与下一个实体 *LoyaltyScheme:loyCustomers* 匹配。</span><span class="sxs-lookup"><span data-stu-id="99868-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="99868-119">如果您有两个以上的实体，则将第一个匹配步骤产生的数据集与以下实体进行匹配。</span><span class="sxs-lookup"><span data-stu-id="99868-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99868-120">选择作为主实体的实体将充当统一配置文件数据集的基础。</span><span class="sxs-lookup"><span data-stu-id="99868-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="99868-121">将把匹配阶段选择的其他实体添加到此实体。</span><span class="sxs-lookup"><span data-stu-id="99868-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="99868-122">这并不意味着统一实体将包括此实体中包含的 *所有* 数据。</span><span class="sxs-lookup"><span data-stu-id="99868-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="99868-123">可帮助您选择实体层次结构的注意事项有两个：</span><span class="sxs-lookup"><span data-stu-id="99868-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="99868-124">选择具有最完整、最可靠的客户配置文件数据的实体作为主要实体。</span><span class="sxs-lookup"><span data-stu-id="99868-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="99868-125">选择与其他实体一样具有多个属性（如名称、电话号码或电子邮件地址）的实体作为主要实体。</span><span class="sxs-lookup"><span data-stu-id="99868-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="99868-126">指定匹配顺序后，在 **数据** > **统一** > **匹配** 上的 **匹配记录详细信息** 部分中，您将会看到定义的匹配对。</span><span class="sxs-lookup"><span data-stu-id="99868-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="99868-127">在匹配过程完成之前，关键指标将为空。</span><span class="sxs-lookup"><span data-stu-id="99868-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="99868-128">定义匹配对的规则</span><span class="sxs-lookup"><span data-stu-id="99868-128">Define rules for match pairs</span></span>

<span data-ttu-id="99868-129">匹配规则指定匹配一对特定实体时所用逻辑。</span><span class="sxs-lookup"><span data-stu-id="99868-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="99868-130">实体名称旁边的 **需要规则** 警告表示没有为匹配对定义匹配规则。</span><span class="sxs-lookup"><span data-stu-id="99868-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="“匹配的记录详细信息”部分的屏幕截图，其中突出显示了用于添加规则的控件。":::

1. <span data-ttu-id="99868-132">在 **匹配的记录详细信息** 部分中的实体下面选择 **添加规则** 以定义匹配规则。</span><span class="sxs-lookup"><span data-stu-id="99868-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="99868-133">在 **创建规则** 窗格中，配置规则的条件。</span><span class="sxs-lookup"><span data-stu-id="99868-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="添加了条件的已开启匹配规则的屏幕截图。":::

   - <span data-ttu-id="99868-135">**实体/字段（第一行）**：选择相关实体和属性，以指定客户可能特有的记录属性。</span><span class="sxs-lookup"><span data-stu-id="99868-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="99868-136">例如，电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="99868-136">For example, a phone number or email address.</span></span> <span data-ttu-id="99868-137">避免按活动-类型属性进行匹配。</span><span class="sxs-lookup"><span data-stu-id="99868-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="99868-138">例如，购买 ID 可能在其他记录类型中找不到匹配项。</span><span class="sxs-lookup"><span data-stu-id="99868-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="99868-139">**实体/字段（第二行）**：选择与第一行中指定的实体属性相关的属性。</span><span class="sxs-lookup"><span data-stu-id="99868-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="99868-140">**标准化**：为所选属性从以下标准化选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="99868-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="99868-141">空白：删除所有空格。</span><span class="sxs-lookup"><span data-stu-id="99868-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="99868-142">*Hello   World* 会变为 *HelloWorld*。</span><span class="sxs-lookup"><span data-stu-id="99868-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="99868-143">符号：删除所有符号和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="99868-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="99868-144">*Head&Shoulder* 会变为 *HeadShoulder*。</span><span class="sxs-lookup"><span data-stu-id="99868-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="99868-145">文本转换为小写：将所有字符转换为小写。</span><span class="sxs-lookup"><span data-stu-id="99868-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="99868-146">*ALL CAPS and Title Case* 将变为 *all caps and title case*。</span><span class="sxs-lookup"><span data-stu-id="99868-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="99868-147">Unicode 转变为 ASCII：将 Unicode 表示法转换为 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="99868-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="99868-148">*/u00B2* 将变为 *2*。</span><span class="sxs-lookup"><span data-stu-id="99868-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="99868-149">数字：将其他数字系统（如罗马数字）转换为阿拉伯语数字。</span><span class="sxs-lookup"><span data-stu-id="99868-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="99868-150">*VIII* 将变为 *8*。</span><span class="sxs-lookup"><span data-stu-id="99868-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="99868-151">语义类型：对名称、职称、电话号码、地址等进行标准化处理。</span><span class="sxs-lookup"><span data-stu-id="99868-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="99868-152">**精度**：设置要用于此条件的精度级别。</span><span class="sxs-lookup"><span data-stu-id="99868-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="99868-153">**基本**：从 *低*、*中*、*高* 和 *精确* 中选择。</span><span class="sxs-lookup"><span data-stu-id="99868-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="99868-154">如果选择 **精确**，则仅匹配 100% 匹配的记录。</span><span class="sxs-lookup"><span data-stu-id="99868-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="99868-155">选择其他一种级别则匹配不是 100% 相同的记录。</span><span class="sxs-lookup"><span data-stu-id="99868-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="99868-156">**自定义**：设置记录需要匹配的百分比。</span><span class="sxs-lookup"><span data-stu-id="99868-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="99868-157">系统将只匹配传递此阈值的记录。</span><span class="sxs-lookup"><span data-stu-id="99868-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="99868-158">为规则提供 **名称**。</span><span class="sxs-lookup"><span data-stu-id="99868-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="99868-159">[添加更多条件](#add-conditions-to-a-rule)或选择 **完成** 以最终确定该规则。</span><span class="sxs-lookup"><span data-stu-id="99868-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="99868-160">（可选）[添加更多规则](#add-rules-to-a-match-pair)。</span><span class="sxs-lookup"><span data-stu-id="99868-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="99868-161">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="99868-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="99868-162">向规则添加条件</span><span class="sxs-lookup"><span data-stu-id="99868-162">Add conditions to a rule</span></span>

<span data-ttu-id="99868-163">要仅在属性满足多个条件时才匹配实体，请向匹配规则中添加更多条件。</span><span class="sxs-lookup"><span data-stu-id="99868-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="99868-164">条件与逻辑 AND 运算符相连，因此仅在满足所有条件时才会执行。</span><span class="sxs-lookup"><span data-stu-id="99868-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="99868-165">转到 **数据** > **统一** > **匹配**，并对要向其添加条件的规则选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="99868-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="99868-166">在 **编辑规则** 窗格中，选择 **添加条件**。</span><span class="sxs-lookup"><span data-stu-id="99868-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="99868-167">选择 **完成** 保存规则。</span><span class="sxs-lookup"><span data-stu-id="99868-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="99868-168">向匹配对中添加规则</span><span class="sxs-lookup"><span data-stu-id="99868-168">Add rules to a match pair</span></span>

<span data-ttu-id="99868-169">匹配规则表示条件集。</span><span class="sxs-lookup"><span data-stu-id="99868-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="99868-170">要根据多个属性按条件匹配实体，请添加更多规则</span><span class="sxs-lookup"><span data-stu-id="99868-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="99868-171">转到 **数据** > **统一** > **匹配**，并对要向其添加规则的实体选择 **添加规则**。</span><span class="sxs-lookup"><span data-stu-id="99868-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="99868-172">按照[定义匹配对的规则](#define-rules-for-match-pairs)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="99868-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="99868-173">规则的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="99868-173">The order of rules matters.</span></span> <span data-ttu-id="99868-174">匹配算法会尝试基于您的第一个规则进行匹配，并且仅在第一个规则没有找到匹配项时才会继续应用第二个规则。</span><span class="sxs-lookup"><span data-stu-id="99868-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="99868-175">对匹配实体定义删除重复</span><span class="sxs-lookup"><span data-stu-id="99868-175">Define deduplication on a match entity</span></span>

<span data-ttu-id="99868-176">除了[跨实体匹配规则](#define-rules-for-match-pairs)外，您还可以指定删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="99868-176">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="99868-177">*删除重复* 是匹配记录时的另一个过程。</span><span class="sxs-lookup"><span data-stu-id="99868-177">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="99868-178">它标识重复记录，并将它们合并成一个记录。</span><span class="sxs-lookup"><span data-stu-id="99868-178">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="99868-179">源记录会通过替代 ID 链接到合并的记录。</span><span class="sxs-lookup"><span data-stu-id="99868-179">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="99868-180">然后，将在跨实体匹配流程中使用经过删除重复的记录。</span><span class="sxs-lookup"><span data-stu-id="99868-180">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="99868-181">删除重复将对各个实体执行，并且可以配置有匹配对中使用的每个实体。</span><span class="sxs-lookup"><span data-stu-id="99868-181">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="99868-182">指定删除重复规则不是必需的。</span><span class="sxs-lookup"><span data-stu-id="99868-182">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="99868-183">如果未配置此类规则，将应用系统定义的规则。</span><span class="sxs-lookup"><span data-stu-id="99868-183">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="99868-184">它们会将所有记录合并为单个记录，然后将实体数据传递给跨实体匹配以提高性能。</span><span class="sxs-lookup"><span data-stu-id="99868-184">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="99868-185">添加删除重复规则</span><span class="sxs-lookup"><span data-stu-id="99868-185">Add deduplication rules</span></span>

1. <span data-ttu-id="99868-186">转到 **数据** > **统一** > **匹配**。</span><span class="sxs-lookup"><span data-stu-id="99868-186">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="99868-187">在 **合并重复** 部分中，选择 **设置实体**。</span><span class="sxs-lookup"><span data-stu-id="99868-187">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="99868-188">如果已创建删除重复规则，请选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="99868-188">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="99868-189">在 **合并首选项** 窗格中，选择要对其运行删除重复的实体。</span><span class="sxs-lookup"><span data-stu-id="99868-189">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="99868-190">指定如何合并重复记录并选择以下三个选项之一：</span><span class="sxs-lookup"><span data-stu-id="99868-190">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="99868-191">**最多填充**：将属性字段填充最多的记录标识为入选记录。</span><span class="sxs-lookup"><span data-stu-id="99868-191">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="99868-192">这是默认的合并选项。</span><span class="sxs-lookup"><span data-stu-id="99868-192">It's the default merge option.</span></span>
   - <span data-ttu-id="99868-193">**最常使用**：根据最常使用标识入选记录。</span><span class="sxs-lookup"><span data-stu-id="99868-193">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="99868-194">需要日期或数字字段以定义近期性。</span><span class="sxs-lookup"><span data-stu-id="99868-194">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="99868-195">**最不常用**：根据最不常用标识入选记录。</span><span class="sxs-lookup"><span data-stu-id="99868-195">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="99868-196">需要日期或数字字段以定义近期性。</span><span class="sxs-lookup"><span data-stu-id="99868-196">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99868-197">![删除重复规则步骤 1](media/match-selfconflation.png "删除重复规则步骤 1")</span><span class="sxs-lookup"><span data-stu-id="99868-197">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="99868-198">在选择实体并设置其合并首选项后，请选择 **添加规则** 以在实体级别定义删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="99868-198">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="99868-199">**选择字段** 将列出该实体的所有可用字段。</span><span class="sxs-lookup"><span data-stu-id="99868-199">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="99868-200">选择要检查重复项的字段。</span><span class="sxs-lookup"><span data-stu-id="99868-200">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="99868-201">选择可能为每个客户所特有的字段。</span><span class="sxs-lookup"><span data-stu-id="99868-201">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="99868-202">例如，电子邮件地址，或者名称、市/县和电话号码的组合。</span><span class="sxs-lookup"><span data-stu-id="99868-202">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="99868-203">指定标准化和精度设置。</span><span class="sxs-lookup"><span data-stu-id="99868-203">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="99868-204">通过选择 **添加条件** 来定义其他条件。</span><span class="sxs-lookup"><span data-stu-id="99868-204">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99868-205">![删除重复规则步骤 2](media/match-selfconflation-rules.png "删除重复规则步骤 2")</span><span class="sxs-lookup"><span data-stu-id="99868-205">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="99868-206">您可以为一个实体创建多个删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="99868-206">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="99868-207">现在，运行匹配流程将根据在删除重复规则中定义的条件对记录进行分组。</span><span class="sxs-lookup"><span data-stu-id="99868-207">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="99868-208">对记录进行分组后，将应用合并策略以标识入选记录。</span><span class="sxs-lookup"><span data-stu-id="99868-208">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="99868-209">然后，该入选记录将与非入选记录（例如，备用 ID）一起传递给跨实体匹配，以提高匹配质量。</span><span class="sxs-lookup"><span data-stu-id="99868-209">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="99868-210">任何定义的自定义匹配规则都将覆盖删除重复规则。</span><span class="sxs-lookup"><span data-stu-id="99868-210">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="99868-211">如果删除重复规则确定匹配的记录，并且将某个自定义匹配规则设置为永不匹配这些记录，则将无法匹配这两个记录。</span><span class="sxs-lookup"><span data-stu-id="99868-211">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="99868-212">在[运行匹配流程](#run-the-match-process)后，您将在重要指标磁贴中看到删除重复统计信息。</span><span class="sxs-lookup"><span data-stu-id="99868-212">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="99868-213">实体形式的删除重复输出</span><span class="sxs-lookup"><span data-stu-id="99868-213">Deduplication output as an entity</span></span>

<span data-ttu-id="99868-214">删除重复过程会为匹配对中每个实体创建一个新实体，以标识删除了重复数据的记录。</span><span class="sxs-lookup"><span data-stu-id="99868-214">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="99868-215">这些实体可以与名称为 **Deduplication_DataSource_Entity** 的 **实体** 页面内 **系统** 部分中的 **ConflationMatchPairs:CustomerInsights** 一起找到。</span><span class="sxs-lookup"><span data-stu-id="99868-215">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="99868-216">删除重复输出实体包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="99868-216">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="99868-217">ID/键</span><span class="sxs-lookup"><span data-stu-id="99868-217">IDs / Keys</span></span>
  - <span data-ttu-id="99868-218">主键字段及其备用 ID 字段。</span><span class="sxs-lookup"><span data-stu-id="99868-218">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="99868-219">备用 ID 字段由为一条记录标识的所有备用 ID 组成。</span><span class="sxs-lookup"><span data-stu-id="99868-219">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="99868-220">Deduplication_GroupId 字段显示在实体中标识的组或群集，该组或群集根据指定的删除重复字段将所有相似记录归组。</span><span class="sxs-lookup"><span data-stu-id="99868-220">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="99868-221">它用于系统处理目的。</span><span class="sxs-lookup"><span data-stu-id="99868-221">It's used for system processing purposes.</span></span> <span data-ttu-id="99868-222">如果没有指定手动删除重复规则并且系统定义的删除重复规则适用，则您可能在重复删除输出实体中找不到此字段。</span><span class="sxs-lookup"><span data-stu-id="99868-222">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="99868-223">Deduplication_WinnerId：此字段包含标识的组或群集中的获胜者 ID。</span><span class="sxs-lookup"><span data-stu-id="99868-223">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="99868-224">如果 Deduplication_WinnerId 与记录的主键值相同，则这意味着该记录是入选记录。</span><span class="sxs-lookup"><span data-stu-id="99868-224">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="99868-225">用于定义删除重复规则的字段。</span><span class="sxs-lookup"><span data-stu-id="99868-225">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="99868-226">“规则”和“分数”字段，分别用于表示所应用的删除重复规则以及匹配算法返回的分数。</span><span class="sxs-lookup"><span data-stu-id="99868-226">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="99868-227">运行匹配流程</span><span class="sxs-lookup"><span data-stu-id="99868-227">Run the match process</span></span>

<span data-ttu-id="99868-228">利用配置的匹配规则（包括跨实体匹配和删除重复规则），您可以运行匹配流程。</span><span class="sxs-lookup"><span data-stu-id="99868-228">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="99868-229">转到 **数据** > **统一** > **匹配**，并选择 **运行** 以开始此流程。</span><span class="sxs-lookup"><span data-stu-id="99868-229">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="99868-230">匹配算法需要一些时间才能完成，而且您直到匹配算法完成后才能更改配置。</span><span class="sxs-lookup"><span data-stu-id="99868-230">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="99868-231">要进行更改，您可以取消运行。</span><span class="sxs-lookup"><span data-stu-id="99868-231">To make changes, you can cancel the run.</span></span> <span data-ttu-id="99868-232">选择该作业的状态，然后选择 **进度详细信息** 窗格上的 **取消作业**。</span><span class="sxs-lookup"><span data-stu-id="99868-232">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="99868-233">您可以在 **实体** 页上查找成功运行的结果，统一客户配置文件实体。</span><span class="sxs-lookup"><span data-stu-id="99868-233">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="99868-234">统一客户实体在 **配置文件** 部分中称为 **客户**。</span><span class="sxs-lookup"><span data-stu-id="99868-234">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="99868-235">第一次成功运行匹配可创建统一的 *客户* 实体。</span><span class="sxs-lookup"><span data-stu-id="99868-235">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="99868-236">所有后续匹配运行都将展开该实体。</span><span class="sxs-lookup"><span data-stu-id="99868-236">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="99868-237">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="99868-237">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="99868-238">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="99868-238">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="99868-239">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="99868-239">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="99868-240">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="99868-240">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="99868-241">预览和验证匹配</span><span class="sxs-lookup"><span data-stu-id="99868-241">Review and validate your matches</span></span>

<span data-ttu-id="99868-242">转到 **数据** > **统一** > **匹配**，以评估匹配对的质量并在必要时进行优化。</span><span class="sxs-lookup"><span data-stu-id="99868-242">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="99868-243">页面顶部的磁贴显示关键指标，并汇总匹配的记录和重复项的数量。</span><span class="sxs-lookup"><span data-stu-id="99868-243">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="包含数字和详细信息的“匹配”页上关键度量的已裁剪屏幕截图。":::

- <span data-ttu-id="99868-245">**唯一源记录** 显示上一次匹配运行中处理的单个源记录的数量。</span><span class="sxs-lookup"><span data-stu-id="99868-245">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="99868-246">**匹配的记录和非匹配记录** 突出显示处理匹配规则后保留的唯一记录数。</span><span class="sxs-lookup"><span data-stu-id="99868-246">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="99868-247">**仅匹配的记录** 只显示所有匹配对中的匹配数。</span><span class="sxs-lookup"><span data-stu-id="99868-247">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="99868-248">您可以在 **匹配的记录详细信息** 表中评估每个匹配对及其规则的结果。</span><span class="sxs-lookup"><span data-stu-id="99868-248">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="99868-249">将来自匹配对的记录数与成功匹配的记录的百分比进行比较。</span><span class="sxs-lookup"><span data-stu-id="99868-249">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="99868-250">查看匹配对的规则，以在规则级别查看成功匹配记录的百分比。</span><span class="sxs-lookup"><span data-stu-id="99868-250">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="99868-251">选择省略号 (...)，然后选择 **匹配预览**，以在规则级别查看所有这些记录。</span><span class="sxs-lookup"><span data-stu-id="99868-251">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="99868-252">建议您查看一些记录，以验证它们是否匹配。</span><span class="sxs-lookup"><span data-stu-id="99868-252">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="99868-253">尝试不同的条件精度阈值以查找最佳值。</span><span class="sxs-lookup"><span data-stu-id="99868-253">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="99868-254">选择要试用的规则的相应省略号 (...) 并选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="99868-254">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="99868-255">在要修改的条件中更改精度值。</span><span class="sxs-lookup"><span data-stu-id="99868-255">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="99868-256">选择 **预览**，以便查看所选条件的匹配和非匹配记录的数量。</span><span class="sxs-lookup"><span data-stu-id="99868-256">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="99868-257">管理匹配规则</span><span class="sxs-lookup"><span data-stu-id="99868-257">Manage match rules</span></span>

<span data-ttu-id="99868-258">您可以重新配置和细微调整大部分匹配参数。</span><span class="sxs-lookup"><span data-stu-id="99868-258">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="包含匹配规则选项的下拉菜单的屏幕截图。":::

- <span data-ttu-id="99868-260">如果定义了多个规则，**更改规则的顺序**。</span><span class="sxs-lookup"><span data-stu-id="99868-260">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="99868-261">您可以通过选择 **上移** 和 **下移** 选项或者通过拖放来对匹配规则重新排序。</span><span class="sxs-lookup"><span data-stu-id="99868-261">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="99868-262">通过选择 **编辑** 来 **更改规则条件** 并选择不同的字段。</span><span class="sxs-lookup"><span data-stu-id="99868-262">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="99868-263">用于从匹配过程中排除匹配规则时保留匹配规则的 **停用规则**。</span><span class="sxs-lookup"><span data-stu-id="99868-263">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="99868-264">**复制规则**：如果已定义匹配规则并且希望创建包含修改的类似规则，请选择 **复制**。</span><span class="sxs-lookup"><span data-stu-id="99868-264">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="99868-265">通过选择 **删除** 符号来 **删除规则**。</span><span class="sxs-lookup"><span data-stu-id="99868-265">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="99868-266">指定自定义匹配条件</span><span class="sxs-lookup"><span data-stu-id="99868-266">Specify custom match conditions</span></span>

<span data-ttu-id="99868-267">可以指定其中包含始终应或永不应匹配的记录的条件。</span><span class="sxs-lookup"><span data-stu-id="99868-267">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="99868-268">可以上载这些规则来替代标准匹配过程。</span><span class="sxs-lookup"><span data-stu-id="99868-268">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="99868-269">例如，如果记录中有 John Doe I 和 John Doe II，则系统可能会将它们作为一个人进行匹配。</span><span class="sxs-lookup"><span data-stu-id="99868-269">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="99868-270">通过自定义匹配规则，您可以指定其配置文件指不同的人员。</span><span class="sxs-lookup"><span data-stu-id="99868-270">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="99868-271">转到 **数据** > **统一** > **匹配**，并在 **匹配的记录详细信息** 部分中选择 **自定义匹配**。</span><span class="sxs-lookup"><span data-stu-id="99868-271">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="匹配规则部分的屏幕截图，其中突出显示了“自定义匹配”控件。":::

1. <span data-ttu-id="99868-273">如果未设置自定义匹配规则，将会看到包含更多详细信息的新 **自定义匹配** 窗格。</span><span class="sxs-lookup"><span data-stu-id="99868-273">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="99868-274">选择 **填写模板** 以获取一个模板文，用于指定始终应或永不应匹配哪些实体中的哪些记录。</span><span class="sxs-lookup"><span data-stu-id="99868-274">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="99868-275">您需要分别填写两个不同文件中的“始终匹配”记录和“永不匹配”记录。</span><span class="sxs-lookup"><span data-stu-id="99868-275">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="99868-276">此模板中包含用于指定实体的字段和要在自定义匹配中使用的实体主键。</span><span class="sxs-lookup"><span data-stu-id="99868-276">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="99868-277">例如，如果您希望 *销售* 实体中的主键 *12345* 始终与 *联系人* 实体中的主键 *34567* 匹配，则填写以下模板：</span><span class="sxs-lookup"><span data-stu-id="99868-277">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="99868-278">实体 1：销售</span><span class="sxs-lookup"><span data-stu-id="99868-278">Entity1: Sales</span></span>
    - <span data-ttu-id="99868-279">实体 1 键：12345</span><span class="sxs-lookup"><span data-stu-id="99868-279">Entity1Key: 12345</span></span>
    - <span data-ttu-id="99868-280">实体 2：联系人</span><span class="sxs-lookup"><span data-stu-id="99868-280">Entity2: Contact</span></span>
    - <span data-ttu-id="99868-281">实体 2 键：34567</span><span class="sxs-lookup"><span data-stu-id="99868-281">Entity2Key: 34567</span></span>

   <span data-ttu-id="99868-282">同一个模板文件可以指定多个实体的自定义匹配记录。</span><span class="sxs-lookup"><span data-stu-id="99868-282">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="99868-283">如果要为实体上的删除重复操作指定自定义匹配，请提供与 Entity1 和 Entity2 相同的实体，并设置不同的主键值。</span><span class="sxs-lookup"><span data-stu-id="99868-283">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="99868-284">添加要应用的所有替代项之后，保存模板文件。</span><span class="sxs-lookup"><span data-stu-id="99868-284">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="99868-285">转到 **数据** > **数据源** 并将模板文件作为新实体引入。</span><span class="sxs-lookup"><span data-stu-id="99868-285">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="99868-286">引入后，可以将其用于指定匹配配置。</span><span class="sxs-lookup"><span data-stu-id="99868-286">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="99868-287">上传文件且实体可用之后，再次选择 **自定义匹配** 选项。</span><span class="sxs-lookup"><span data-stu-id="99868-287">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="99868-288">将看到用于指定要包含的实体的选项。</span><span class="sxs-lookup"><span data-stu-id="99868-288">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="99868-289">从下拉菜单选择所需实体。</span><span class="sxs-lookup"><span data-stu-id="99868-289">Select the required entities from the drop-down menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="用于选择自定义匹配方案替代的对话框的屏幕截图。":::

1. <span data-ttu-id="99868-291">选择要用于 **始终匹配** 和 **永不匹配** 的实体，然后选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="99868-291">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="99868-292">选择 **匹配** 页上的 **保存** 以应用自定义匹配配置。</span><span class="sxs-lookup"><span data-stu-id="99868-292">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="99868-293">选择 **匹配** 页上的 **运行** 以开始匹配流程。</span><span class="sxs-lookup"><span data-stu-id="99868-293">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="99868-294">自定义匹配配置会替代其他指定的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="99868-294">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="99868-295">转到 **数据** > **实体**，并查看 **ConflationMatchPair** 实体，以确认应用了替代。</span><span class="sxs-lookup"><span data-stu-id="99868-295">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="99868-296">下一步</span><span class="sxs-lookup"><span data-stu-id="99868-296">Next step</span></span>

<span data-ttu-id="99868-297">完成至少一个匹配对的匹配过程后，可以通过浏览 [**合并**](merge-entities.md)主题解决数据中可能的冲突。</span><span class="sxs-lookup"><span data-stu-id="99868-297">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
