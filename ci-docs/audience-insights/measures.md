---
title: 创建和管理度量
description: 定义度量以分析和反映业务绩效。
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654721"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="3b9db-103">定义和管理度量</span><span class="sxs-lookup"><span data-stu-id="3b9db-103">Define and manage measures</span></span>

<span data-ttu-id="3b9db-104">通过从[统一配置文件](data-unification.md)中检索相关值，度量可帮助您更好地了解客户行为和业务绩效。</span><span class="sxs-lookup"><span data-stu-id="3b9db-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="3b9db-105">例如，企业希望查看 *每个客户所花费的总费用*，以了解各个客户的购买历史记录。</span><span class="sxs-lookup"><span data-stu-id="3b9db-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="3b9db-106">或衡量 *公司的总销售额*，以了解整个业务中的聚合级别收入。</span><span class="sxs-lookup"><span data-stu-id="3b9db-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="3b9db-107">度量是使用度量生成器（具有各种运算符和简单映射选项的数据查询平台）创建的。</span><span class="sxs-lookup"><span data-stu-id="3b9db-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="3b9db-108">它允许您筛选数据、对结果进行分组、检测[实体关系路径](relationships.md)和预览输出。</span><span class="sxs-lookup"><span data-stu-id="3b9db-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="3b9db-109">使用度量生成器通过查询客户数据来规划业务活动并提取见解。</span><span class="sxs-lookup"><span data-stu-id="3b9db-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="3b9db-110">例如，创建 *每个客户所花费的总费用* 和 *每个客户的总回报* 的度量有助于确定一组花费高但回报也高的客户。</span><span class="sxs-lookup"><span data-stu-id="3b9db-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="3b9db-111">您可以[创建客户细分](segments.md)以推动后续最佳操作。</span><span class="sxs-lookup"><span data-stu-id="3b9db-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="3b9db-112">创建度量</span><span class="sxs-lookup"><span data-stu-id="3b9db-112">Create a measure</span></span>

<span data-ttu-id="3b9db-113">本节将从头开始引导您创建新度量。</span><span class="sxs-lookup"><span data-stu-id="3b9db-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="3b9db-114">您可以使用数据实体中的数据属性构建度量，这些数据实体的关系已设置为与客户实体建立连接。</span><span class="sxs-lookup"><span data-stu-id="3b9db-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="3b9db-115">在访问群体见解中，转到 **度量**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3b9db-116">选择 **新建**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-116">Select **New**.</span></span>

1. <span data-ttu-id="3b9db-117">选择 **编辑名称 **并为该度量提供** 名称**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="3b9db-118">如果您的新度量配置只有两个字段（例如，CustomerID 和一个计算），则输出将作为新列添加到系统生成的名为 Customer_Measure 的实体中。</span><span class="sxs-lookup"><span data-stu-id="3b9db-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="3b9db-119">您将可以在统一客户配置文件中查看度量的值。</span><span class="sxs-lookup"><span data-stu-id="3b9db-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="3b9db-120">其他度量将生成自己的实体。</span><span class="sxs-lookup"><span data-stu-id="3b9db-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="3b9db-121">在配置区域中，从 **选择函数** 下拉菜单中选择聚合函数。</span><span class="sxs-lookup"><span data-stu-id="3b9db-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="3b9db-122">聚合函数包括：</span><span class="sxs-lookup"><span data-stu-id="3b9db-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="3b9db-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="3b9db-123">**Sum**</span></span>
   - <span data-ttu-id="3b9db-124">**平均值**</span><span class="sxs-lookup"><span data-stu-id="3b9db-124">**Average**</span></span>
   - <span data-ttu-id="3b9db-125">**计数**</span><span class="sxs-lookup"><span data-stu-id="3b9db-125">**Count**</span></span>
   - <span data-ttu-id="3b9db-126">**唯一计数**</span><span class="sxs-lookup"><span data-stu-id="3b9db-126">**Count Unique**</span></span>
   - <span data-ttu-id="3b9db-127">**最大值**</span><span class="sxs-lookup"><span data-stu-id="3b9db-127">**Max**</span></span>
   - <span data-ttu-id="3b9db-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="3b9db-128">**Min**</span></span>
   - <span data-ttu-id="3b9db-129">**第一个**：采用数据记录的第一个值</span><span class="sxs-lookup"><span data-stu-id="3b9db-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="3b9db-130">**最后一个**：采用添加到数据记录的最后一个值</span><span class="sxs-lookup"><span data-stu-id="3b9db-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="度量计算运算符。":::

1. <span data-ttu-id="3b9db-132">选择 **添加属性**，以选择创建此度量所需的数据。</span><span class="sxs-lookup"><span data-stu-id="3b9db-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="3b9db-133">选择 **属性** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3b9db-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="3b9db-134">数据实体：选择包括要度量的属性的实体。</span><span class="sxs-lookup"><span data-stu-id="3b9db-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="3b9db-135">数据属性：选择要在聚合函数中用于计算度量的属性。</span><span class="sxs-lookup"><span data-stu-id="3b9db-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="3b9db-136">一次只能选择一个属性。</span><span class="sxs-lookup"><span data-stu-id="3b9db-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="3b9db-137">通过选择 **度量** 选项卡，还可以从现有度量中选择数据属性。或者，可以搜索实体或度量名称。</span><span class="sxs-lookup"><span data-stu-id="3b9db-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="3b9db-138">选择 **添加** 以将所选属性添加到度量中。</span><span class="sxs-lookup"><span data-stu-id="3b9db-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="选择一个要用于计算的属性。":::

1. <span data-ttu-id="3b9db-140">若要生成更复杂的度量，您可以添加更多属性或在度量函数中使用数学运算符。</span><span class="sxs-lookup"><span data-stu-id="3b9db-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="使用数学运算符创建复杂度量。":::

1. <span data-ttu-id="3b9db-142">若要添加筛选器，请在配置区域中选择 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="3b9db-143">在 **筛选器 **窗格的** 添加属性** 部分中，选择要用于创建筛选器的属性。</span><span class="sxs-lookup"><span data-stu-id="3b9db-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="3b9db-144">设置筛选器运算符，以为每个所选属性定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="3b9db-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="3b9db-145">选择 **应用** 以将筛选器添加到度量中。</span><span class="sxs-lookup"><span data-stu-id="3b9db-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="3b9db-146">若要添加维度，请在配置区域中选择 **维度**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="3b9db-147">维度将在度量输出实体中显示为列。</span><span class="sxs-lookup"><span data-stu-id="3b9db-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="3b9db-148">选择 **编辑维度** 以添加要作为度量值分组依据的数据属性。</span><span class="sxs-lookup"><span data-stu-id="3b9db-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="3b9db-149">例如，市/县或性别。</span><span class="sxs-lookup"><span data-stu-id="3b9db-149">For example, city or gender.</span></span> <span data-ttu-id="3b9db-150">默认情况下选择了 *CustomerID *维度来创建* 客户级别的度量*。</span><span class="sxs-lookup"><span data-stu-id="3b9db-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="3b9db-151">如果要创建 *业务级别的度量*，可以删除默认维度。</span><span class="sxs-lookup"><span data-stu-id="3b9db-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="3b9db-152">选择 **完成** 以将维度添加到度量中。</span><span class="sxs-lookup"><span data-stu-id="3b9db-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="3b9db-153">如果所映射的数据实体与 *客户* 实体之间有多个路径，您必须选择其中一个标识的[实体关系路径](relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="3b9db-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="3b9db-154">根据所选路径的不同，度量结果可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="3b9db-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="3b9db-155">选择 **数据首选项**，并选择将用于标识度量的实体路径。</span><span class="sxs-lookup"><span data-stu-id="3b9db-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="3b9db-156">如果只有一个指向 *客户* 实体的路径，则不会显示此控件。</span><span class="sxs-lookup"><span data-stu-id="3b9db-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="3b9db-157">选择 **完成** 以应用您的选择。</span><span class="sxs-lookup"><span data-stu-id="3b9db-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="为度量选择实体路径。":::

1. <span data-ttu-id="3b9db-159">若要为度量添加更多计算，请选择 **新建计算**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="3b9db-160">只能在同一实体路径上使用实体进行新计算。</span><span class="sxs-lookup"><span data-stu-id="3b9db-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="3b9db-161">更多计算将在度量输出实体中显示为新列。</span><span class="sxs-lookup"><span data-stu-id="3b9db-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="3b9db-162">在计算中选择 **...** 以从度量中 **复制**、**重命名** 或 **删除** 计算。</span><span class="sxs-lookup"><span data-stu-id="3b9db-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="3b9db-163">在 **预览** 区域中，您将看到度量输出实体的数据架构，包括筛选器和维度。</span><span class="sxs-lookup"><span data-stu-id="3b9db-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="3b9db-164">预览会动态响应配置中的更改。</span><span class="sxs-lookup"><span data-stu-id="3b9db-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="3b9db-165">选择 **运行** 以计算已配置度量的结果。</span><span class="sxs-lookup"><span data-stu-id="3b9db-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="3b9db-166">如果希望保留当前配置并且稍后运行该度量，请选择 **保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="3b9db-167">转到 **度量** 以在列表中查看新创建的度量。</span><span class="sxs-lookup"><span data-stu-id="3b9db-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="3b9db-168">管理度量</span><span class="sxs-lookup"><span data-stu-id="3b9db-168">Manage your measures</span></span>

<span data-ttu-id="3b9db-169">在 [创建度量](#create-a-measure)后，您将在 **度量** 页面上看到度量的列表。</span><span class="sxs-lookup"><span data-stu-id="3b9db-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="3b9db-170">您将找到有关度量类型、创建者、创建日期、状况和状态的信息。</span><span class="sxs-lookup"><span data-stu-id="3b9db-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="3b9db-171">当您从列表中选择度量时，您可以预览输出并下载 .CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="3b9db-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="3b9db-172">若要同时刷新所有度量，请在不选择特定度量的情况下选择 **全部刷新**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3b9db-173">![用于管理单个度量的操作](media/measure-actions.png "用于管理单个度量的操作")</span><span class="sxs-lookup"><span data-stu-id="3b9db-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="3b9db-174">针对以下选项从列表中选择度量：</span><span class="sxs-lookup"><span data-stu-id="3b9db-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="3b9db-175">选择度量名称以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="3b9db-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="3b9db-176">**编辑** 度量的配置。</span><span class="sxs-lookup"><span data-stu-id="3b9db-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="3b9db-177">根据最新数据 **刷新** 度量。</span><span class="sxs-lookup"><span data-stu-id="3b9db-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="3b9db-178">**重命名** 度量。</span><span class="sxs-lookup"><span data-stu-id="3b9db-178">**Rename** the measure.</span></span>
- <span data-ttu-id="3b9db-179">**删除** 度量。</span><span class="sxs-lookup"><span data-stu-id="3b9db-179">**Delete** the measure.</span></span>
- <span data-ttu-id="3b9db-180">**激活** 或 **停用**。</span><span class="sxs-lookup"><span data-stu-id="3b9db-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="3b9db-181">停用的度量在[计划刷新](system.md#schedule-tab)期间不会刷新。</span><span class="sxs-lookup"><span data-stu-id="3b9db-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="3b9db-182">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="3b9db-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3b9db-183">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="3b9db-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3b9db-184">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3b9db-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3b9db-185">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="3b9db-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3b9db-186">下一步</span><span class="sxs-lookup"><span data-stu-id="3b9db-186">Next step</span></span>

<span data-ttu-id="3b9db-187">您可以使用现有度量创建[客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="3b9db-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]