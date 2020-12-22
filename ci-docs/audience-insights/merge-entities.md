---
title: 在数据统一中合并实体
description: 合并实体以创建统一客户配置文件。
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405220"
---
# <a name="merge-entities"></a><span data-ttu-id="c7a54-103">合并实体</span><span class="sxs-lookup"><span data-stu-id="c7a54-103">Merge entities</span></span>

<span data-ttu-id="c7a54-104">合并阶段是数据统一过程中的最后一个阶段。</span><span class="sxs-lookup"><span data-stu-id="c7a54-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="c7a54-105">其目的是协调冲突数据。</span><span class="sxs-lookup"><span data-stu-id="c7a54-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="c7a54-106">冲突数据的示例包括，在两个数据集中找到的一个客户名称在每个数据集中显示时稍微不同（“Grant Marshall”与“Grant Marshal”），或一个电话号码的格式不同（617-803-091X 与 617803091X）。</span><span class="sxs-lookup"><span data-stu-id="c7a54-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="c7a54-107">将逐个属性完成这些冲突数据点的合并。</span><span class="sxs-lookup"><span data-stu-id="c7a54-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="c7a54-108">完成 [匹配阶段](match-entities.md)之后，选择 **统一** 页中的 **合并** 磁贴开始进行合并阶段。</span><span class="sxs-lookup"><span data-stu-id="c7a54-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="c7a54-109">查看系统建议</span><span class="sxs-lookup"><span data-stu-id="c7a54-109">Review system recommendations</span></span>

<span data-ttu-id="c7a54-110">在 **合并** 页中，选择和排除统一客户配置文件实体（配置过程的产物）内要合并的属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="c7a54-111">系统会自动合并某些属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="c7a54-112">查看合并的属性</span><span class="sxs-lookup"><span data-stu-id="c7a54-112">View merged attributes</span></span>

<span data-ttu-id="c7a54-113">若要查看一个自动合并的属性中包含的属性，请选择这个合并的属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="c7a54-114">将在合并的属性下的两个新行内显示构成这个合并的属性的两个属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c7a54-115">![选择合并的属性](media/configure-data-merge-profile-attributes.png "选择合并的属性")</span><span class="sxs-lookup"><span data-stu-id="c7a54-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="c7a54-116">拆分合并的属性</span><span class="sxs-lookup"><span data-stu-id="c7a54-116">Separate merged attributes</span></span>

<span data-ttu-id="c7a54-117">若要拆分或取消合并任何自动合并的属性，请在 **配置文件属性** 表中找到该属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="c7a54-118">选择省略号 (...) 按钮。</span><span class="sxs-lookup"><span data-stu-id="c7a54-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="c7a54-119">在下拉列表中，选择 **拆分字段**。</span><span class="sxs-lookup"><span data-stu-id="c7a54-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="c7a54-120">删除合并的属性</span><span class="sxs-lookup"><span data-stu-id="c7a54-120">Remove merged attributes</span></span>

<span data-ttu-id="c7a54-121">若要从最终客户配置文件实体中排除某个属性，请在 **配置文件属性** 表中找到该属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="c7a54-122">选择省略号 (...) 按钮。</span><span class="sxs-lookup"><span data-stu-id="c7a54-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="c7a54-123">在下拉列表中，选择 **不合并**。</span><span class="sxs-lookup"><span data-stu-id="c7a54-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="c7a54-124">将把该属性移到 **已从客户记录中删除** 部分。</span><span class="sxs-lookup"><span data-stu-id="c7a54-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="c7a54-125">手动添加合并的属性</span><span class="sxs-lookup"><span data-stu-id="c7a54-125">Manually add a merged attribute</span></span>

<span data-ttu-id="c7a54-126">若要添加合并的属性，请转到 **合并** 页。</span><span class="sxs-lookup"><span data-stu-id="c7a54-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="c7a54-127">选择 **添加合并的属性**。</span><span class="sxs-lookup"><span data-stu-id="c7a54-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="c7a54-128">提供 **名称**，以便以后在 **合并** 页中可以识别该属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="c7a54-129">（可选）提供要在统一的客户配置文件实体中显示的 **显示名称**。</span><span class="sxs-lookup"><span data-stu-id="c7a54-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="c7a54-130">配置 **选择重复的属性**，以便从匹配的实体中选择要合并的属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="c7a54-131">也可以搜索属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="c7a54-132">设置 **按重要性分等级**，以便将一个属性的优先级设置为高于其他属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="c7a54-133">例如，如果 *WebAccountCSV* 实体中包含有关 *完整名称* 属性的最精确数据，您可以通过选择 *WebAccountCSV* 将此实体的优先级设置为高于 *ContactCSV*。</span><span class="sxs-lookup"><span data-stu-id="c7a54-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="c7a54-134">结果，在提取 *完整名称* 属性的值时，*WebAccountCSV* 将移到第一优先级，而 *ContactCSV* 则移到第二优先级。</span><span class="sxs-lookup"><span data-stu-id="c7a54-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="c7a54-135">运行合并</span><span class="sxs-lookup"><span data-stu-id="c7a54-135">Run your merge</span></span>

<span data-ttu-id="c7a54-136">无论您手动合并属性还是让系统合并属性，您始终都可以运行合并。</span><span class="sxs-lookup"><span data-stu-id="c7a54-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="c7a54-137">在 **合并** 页中选择 **运行** 开始执行此过程。</span><span class="sxs-lookup"><span data-stu-id="c7a54-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c7a54-138">![数据合并保存和运行](media/configure-data-merge-save-run.png "数据合并保存和运行")</span><span class="sxs-lookup"><span data-stu-id="c7a54-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="c7a54-139">若要进行更多配置并重新运行步骤，可以取消正在进行的合并。</span><span class="sxs-lookup"><span data-stu-id="c7a54-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="c7a54-140">选择 **正在刷新...**，然后选择显示的侧边窗格中的 **取消作业**。</span><span class="sxs-lookup"><span data-stu-id="c7a54-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="c7a54-141">文本 **正在刷新...** 更改为 **成功** 之后，说明已完成合并，并根据您定义的策略解决了冲突。</span><span class="sxs-lookup"><span data-stu-id="c7a54-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="c7a54-142">统一配置文件实体中包含合并的属性和未合并的属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="c7a54-143">统一配置文件实体中不包含排除的属性。</span><span class="sxs-lookup"><span data-stu-id="c7a54-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="c7a54-144">如果这不是第一次成功运行合并，将自动重新运行所有下游流程，包括扩充、细分和度量。</span><span class="sxs-lookup"><span data-stu-id="c7a54-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="c7a54-145">重新运行了所有下游流程之后，客户配置文件将反映您进行的所有更改。</span><span class="sxs-lookup"><span data-stu-id="c7a54-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="c7a54-146">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="c7a54-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c7a54-147">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="c7a54-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c7a54-148">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c7a54-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c7a54-149">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="c7a54-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c7a54-150">下一步</span><span class="sxs-lookup"><span data-stu-id="c7a54-150">Next Step</span></span>

<span data-ttu-id="c7a54-151">配置[活动](activities.md)、[扩充](enrichment-microsoft-graph.md)或[关系](relationships.md)，以便加深对客户的了解。</span><span class="sxs-lookup"><span data-stu-id="c7a54-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="c7a54-152">如果您已配置了活动、扩充或关系，或者如果您定义了细分，系统将自动处理它们以使用最新的客户数据。</span><span class="sxs-lookup"><span data-stu-id="c7a54-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


