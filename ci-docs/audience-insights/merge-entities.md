---
title: 在数据统一中合并实体
description: 合并实体以创建统一客户配置文件。
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085565"
---
# <a name="merge-entities"></a><span data-ttu-id="614f2-103">合并实体</span><span class="sxs-lookup"><span data-stu-id="614f2-103">Merge entities</span></span>

<span data-ttu-id="614f2-104">合并阶段是数据统一过程中的最后一个阶段。</span><span class="sxs-lookup"><span data-stu-id="614f2-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="614f2-105">其目的是协调冲突数据。</span><span class="sxs-lookup"><span data-stu-id="614f2-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="614f2-106">冲突数据的示例包括，在两个数据集中找到的一个客户名称在每个数据集中显示时稍微不同（“Grant Marshall”与“Grant Marshal”），或一个电话号码的格式不同（617-803-091X 与 617803091X）。</span><span class="sxs-lookup"><span data-stu-id="614f2-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="614f2-107">将逐个属性完成这些冲突数据点的合并。</span><span class="sxs-lookup"><span data-stu-id="614f2-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="数据统一进程中的合并页，其中显示带定义统一客户配置文件的合并字段的表。":::

<span data-ttu-id="614f2-109">完成 [匹配阶段](match-entities.md)之后，选择 **统一** 页中的 **合并** 磁贴开始进行合并阶段。</span><span class="sxs-lookup"><span data-stu-id="614f2-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="614f2-110">查看系统建议</span><span class="sxs-lookup"><span data-stu-id="614f2-110">Review system recommendations</span></span>

<span data-ttu-id="614f2-111">在 **数据** > **统一** > **合并** 中，您可以选择并排除要在统一客户配置文件实体中合并的属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="614f2-112">统一客户配置文件是数据统一过程的结果。</span><span class="sxs-lookup"><span data-stu-id="614f2-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="614f2-113">系统会自动合并某些属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="614f2-114">若要查看包括在一个自动合并属性中的属性，请在表的 **客户字段** 选项卡中选择该合并的属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="614f2-115">将在合并的属性下的两个新行内显示构成这个合并的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="614f2-116">分隔、重命名、排除和编辑合并的字段</span><span class="sxs-lookup"><span data-stu-id="614f2-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="614f2-117">您可以更改系统处理合并属性以生成统一客户配置文件的方法。</span><span class="sxs-lookup"><span data-stu-id="614f2-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="614f2-118">选择 **显示更多** 并选择要更改的内容。</span><span class="sxs-lookup"><span data-stu-id="614f2-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="显示更多下拉菜单中用于管理合并属性的选项。":::

<span data-ttu-id="614f2-120">有关详细信息，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="614f2-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="614f2-121">拆分合并的字段</span><span class="sxs-lookup"><span data-stu-id="614f2-121">Separate merged fields</span></span>

<span data-ttu-id="614f2-122">若要拆分合并的字段，请在表中查找属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="614f2-123">拆分的字段在统一客户配置文件上显示为单个数据点。</span><span class="sxs-lookup"><span data-stu-id="614f2-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="614f2-124">选择合并的字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="614f2-125">选择 **显示更多** 并选择 **拆分字段**。</span><span class="sxs-lookup"><span data-stu-id="614f2-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="614f2-126">确认拆分。</span><span class="sxs-lookup"><span data-stu-id="614f2-126">Confirm the separation.</span></span>

1. <span data-ttu-id="614f2-127">选择 **保存** 和 **运行** 以处理更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="614f2-128">重命名合并的字段</span><span class="sxs-lookup"><span data-stu-id="614f2-128">Rename merged fields</span></span>

<span data-ttu-id="614f2-129">更改合并的属性的显示名称。</span><span class="sxs-lookup"><span data-stu-id="614f2-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="614f2-130">您无法更改输出实体的名称。</span><span class="sxs-lookup"><span data-stu-id="614f2-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="614f2-131">选择合并的字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="614f2-132">选择 **显示更多** 并选择 **重命名**。</span><span class="sxs-lookup"><span data-stu-id="614f2-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="614f2-133">确认更改的显示名称。</span><span class="sxs-lookup"><span data-stu-id="614f2-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="614f2-134">选择 **保存** 和 **运行** 以处理更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="614f2-135">排除合并的字段</span><span class="sxs-lookup"><span data-stu-id="614f2-135">Exclude merged fields</span></span>

<span data-ttu-id="614f2-136">从统一客户配置文件中排除属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="614f2-137">如果字段用于其他流程（如客户细分中的流程），请从这些流程中删除此字段，然后从客户配置文件中排除此字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="614f2-138">选择合并的字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="614f2-139">选择 **显示更多** 并选择 **排除**。</span><span class="sxs-lookup"><span data-stu-id="614f2-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="614f2-140">确认排除。</span><span class="sxs-lookup"><span data-stu-id="614f2-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="614f2-141">选择 **保存** 和 **运行** 以处理更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="614f2-142">在 **合并** 页上，选择 **排除的字段** 以查看所有排除的字段的列表。</span><span class="sxs-lookup"><span data-stu-id="614f2-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="614f2-143">此窗格允许您添加回排除的字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="614f2-144">手动合并字段</span><span class="sxs-lookup"><span data-stu-id="614f2-144">Manually combine fields</span></span>

<span data-ttu-id="614f2-145">手动指定合并的属性。</span><span class="sxs-lookup"><span data-stu-id="614f2-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="614f2-146">在 **合并** 页上，选择 **组合字段**。</span><span class="sxs-lookup"><span data-stu-id="614f2-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="614f2-147">提供 **名称** 和 **输出字段名称**。</span><span class="sxs-lookup"><span data-stu-id="614f2-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="614f2-148">选择要添加的字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-148">Choose a field to add.</span></span> <span data-ttu-id="614f2-149">选择 **添加字段** 以合并其他字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="614f2-150">确认排除。</span><span class="sxs-lookup"><span data-stu-id="614f2-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="614f2-151">选择 **保存** 和 **运行** 以处理更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="614f2-152">更改字段的顺序</span><span class="sxs-lookup"><span data-stu-id="614f2-152">Change the order of fields</span></span>

<span data-ttu-id="614f2-153">有些实体包含的详细信息要多于其他实体包含的详细信息。</span><span class="sxs-lookup"><span data-stu-id="614f2-153">Some entities contain more details than others.</span></span> <span data-ttu-id="614f2-154">如果实体包含有关字段的最新数据，则您可以在合并值时让该实体优先于其他实体。</span><span class="sxs-lookup"><span data-stu-id="614f2-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="614f2-155">选择合并的字段。</span><span class="sxs-lookup"><span data-stu-id="614f2-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="614f2-156">选择 **显示更多** 并选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="614f2-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="614f2-157">在 **合并字段** 窗格中，选择 **上移/下移** 以设置顺序，或将字段拖放到所需位置。</span><span class="sxs-lookup"><span data-stu-id="614f2-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="614f2-158">确认更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-158">Confirm the change.</span></span>

1. <span data-ttu-id="614f2-159">选择 **保存** 和 **运行** 以处理更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="614f2-160">运行合并</span><span class="sxs-lookup"><span data-stu-id="614f2-160">Run your merge</span></span>

<span data-ttu-id="614f2-161">无论您手动合并属性还是让系统合并属性，您始终都可以运行合并。</span><span class="sxs-lookup"><span data-stu-id="614f2-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="614f2-162">在 **合并** 页中选择 **运行** 开始执行此过程。</span><span class="sxs-lookup"><span data-stu-id="614f2-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="614f2-163">![数据合并保存和运行](media/configure-data-merge-save-run.png "数据合并保存和运行")</span><span class="sxs-lookup"><span data-stu-id="614f2-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="614f2-164">如果只想查看统一客户实体中反映的输出，请选择 **仅运行合并**。</span><span class="sxs-lookup"><span data-stu-id="614f2-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="614f2-165">将按[刷新计划中的定义](system.md#schedule-tab)来刷新下游流程。</span><span class="sxs-lookup"><span data-stu-id="614f2-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="614f2-166">选择 **运行合并和下游流程** 以用您所做的更改刷新系统。</span><span class="sxs-lookup"><span data-stu-id="614f2-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="614f2-167">所有流程（包括扩充、客户细分和度量）将自动重新运行。</span><span class="sxs-lookup"><span data-stu-id="614f2-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="614f2-168">所有下游流程都完成后，客户配置文件将反映您做出的任何更改。</span><span class="sxs-lookup"><span data-stu-id="614f2-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="614f2-169">若要进行更多更改并重新运行此步骤，可以取消正在进行的合并。</span><span class="sxs-lookup"><span data-stu-id="614f2-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="614f2-170">选择 **正在刷新...**，然后选择显示的侧边窗格中的 **取消作业**。</span><span class="sxs-lookup"><span data-stu-id="614f2-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="614f2-171">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="614f2-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="614f2-172">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="614f2-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="614f2-173">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="614f2-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="614f2-174">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="614f2-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="614f2-175">下一步</span><span class="sxs-lookup"><span data-stu-id="614f2-175">Next Step</span></span>

<span data-ttu-id="614f2-176">配置[活动](activities.md)、[扩充](enrichment-hub.md)或[关系](relationships.md)，以便加深对客户的了解。</span><span class="sxs-lookup"><span data-stu-id="614f2-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="614f2-177">如果您已经配置了活动、扩充或客户细分，系统将自动处理它们以使用最新的客户数据。</span><span class="sxs-lookup"><span data-stu-id="614f2-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
