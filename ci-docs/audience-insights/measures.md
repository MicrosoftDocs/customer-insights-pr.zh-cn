---
title: 创建和管理度量
description: 定义度量以分析和反映业务绩效。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304778"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="5b731-103">定义和管理度量</span><span class="sxs-lookup"><span data-stu-id="5b731-103">Define and manage measures</span></span>

<span data-ttu-id="5b731-104">措施有助于您更好地了解客户行为和业务绩效。</span><span class="sxs-lookup"><span data-stu-id="5b731-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="5b731-105">他们从[统一配置文件](data-unification.md)中查看相关值。</span><span class="sxs-lookup"><span data-stu-id="5b731-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="5b731-106">例如，企业希望查看 *每个客户的总支出* 以了解单独客户的购买历史记录，或度量 *公司的总销售额* 以了解整个企业的聚合级别收入。</span><span class="sxs-lookup"><span data-stu-id="5b731-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="5b731-107">度量是使用度量生成器（具有各种运算符和简单映射选项的数据查询平台）创建的。</span><span class="sxs-lookup"><span data-stu-id="5b731-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="5b731-108">它允许您筛选数据、对结果进行分组、检测[实体关系路径](relationships.md)和预览输出。</span><span class="sxs-lookup"><span data-stu-id="5b731-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="5b731-109">使用度量生成器通过查询客户数据来规划业务活动并提取见解。</span><span class="sxs-lookup"><span data-stu-id="5b731-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="5b731-110">例如，创建 *每个客户所花费的总费用* 和 *每个客户的总回报* 的度量有助于确定一组花费高但回报也高的客户。</span><span class="sxs-lookup"><span data-stu-id="5b731-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="5b731-111">您可以[创建客户细分](segments.md)以推动后续最佳操作。</span><span class="sxs-lookup"><span data-stu-id="5b731-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="5b731-112">从头开始创建自己的度量</span><span class="sxs-lookup"><span data-stu-id="5b731-112">Build your own measure from scratch</span></span>

<span data-ttu-id="5b731-113">本节将从头开始引导您创建新度量。</span><span class="sxs-lookup"><span data-stu-id="5b731-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="5b731-114">您可以使用数据实体中的数据属性构建度量，这些数据实体的关系已设置为与客户实体建立连接。</span><span class="sxs-lookup"><span data-stu-id="5b731-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="5b731-115">在访问群体见解中，转到 **度量**。</span><span class="sxs-lookup"><span data-stu-id="5b731-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="5b731-116">选择 **新建** 并选择 **创建自己的内容**。</span><span class="sxs-lookup"><span data-stu-id="5b731-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="5b731-117">选择 **编辑名称 **并为该度量提供** 名称**。</span><span class="sxs-lookup"><span data-stu-id="5b731-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="5b731-118">如果您的新度量配置只有两个字段（例如 CustomerID 和一个计算），则输出将作为新列添加到系统生成的名为 Customer_Measure 的实体中。</span><span class="sxs-lookup"><span data-stu-id="5b731-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="5b731-119">您将可以在统一客户配置文件中查看度量的值。</span><span class="sxs-lookup"><span data-stu-id="5b731-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="5b731-120">其他度量将生成自己的实体。</span><span class="sxs-lookup"><span data-stu-id="5b731-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="5b731-121">在配置区域中，从 **选择函数** 下拉菜单中选择聚合函数。</span><span class="sxs-lookup"><span data-stu-id="5b731-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="5b731-122">聚合函数包括：</span><span class="sxs-lookup"><span data-stu-id="5b731-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="5b731-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="5b731-123">**Sum**</span></span>
   - <span data-ttu-id="5b731-124">**平均值**</span><span class="sxs-lookup"><span data-stu-id="5b731-124">**Average**</span></span>
   - <span data-ttu-id="5b731-125">**计数**</span><span class="sxs-lookup"><span data-stu-id="5b731-125">**Count**</span></span>
   - <span data-ttu-id="5b731-126">**唯一计数**</span><span class="sxs-lookup"><span data-stu-id="5b731-126">**Count Unique**</span></span>
   - <span data-ttu-id="5b731-127">**最大值**</span><span class="sxs-lookup"><span data-stu-id="5b731-127">**Max**</span></span>
   - <span data-ttu-id="5b731-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="5b731-128">**Min**</span></span>
   - <span data-ttu-id="5b731-129">**第一个**：采用数据记录的第一个值</span><span class="sxs-lookup"><span data-stu-id="5b731-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="5b731-130">**最后一个**：采用添加到数据记录的最后一个值</span><span class="sxs-lookup"><span data-stu-id="5b731-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="度量计算运算符。":::

1. <span data-ttu-id="5b731-132">选择 **添加属性**，以选择创建此度量所需的数据。</span><span class="sxs-lookup"><span data-stu-id="5b731-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="5b731-133">选择 **属性** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5b731-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="5b731-134">数据实体：选择包括要度量的属性的实体。</span><span class="sxs-lookup"><span data-stu-id="5b731-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="5b731-135">数据属性：选择要在聚合函数中用于计算度量的属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="5b731-136">一次只能选择一个属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="5b731-137">通过选择 **度量** 选项卡，还可以从现有度量中选择数据属性。或者，可以搜索实体或度量名称。</span><span class="sxs-lookup"><span data-stu-id="5b731-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="5b731-138">选择 **添加** 以将所选属性添加到度量中。</span><span class="sxs-lookup"><span data-stu-id="5b731-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="选择一个要用于计算的属性。":::

1. <span data-ttu-id="5b731-140">若要生成更复杂的度量，您可以添加更多属性或在度量函数中使用数学运算符。</span><span class="sxs-lookup"><span data-stu-id="5b731-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="使用数学运算符创建复杂度量。":::

1. <span data-ttu-id="5b731-142">若要添加筛选器，请在配置区域中选择 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="5b731-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="5b731-143">在 **筛选器** 窗格的 **添加属性** 部分中，选择要用于创建筛选器的属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="5b731-144">设置筛选器运算符，以为每个所选属性定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="5b731-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="5b731-145">选择 **应用** 以将筛选器添加到度量中。</span><span class="sxs-lookup"><span data-stu-id="5b731-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="5b731-146">若要添加维度，请在配置区域中选择 **维度**。</span><span class="sxs-lookup"><span data-stu-id="5b731-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="5b731-147">维度将在度量输出实体中显示为列。</span><span class="sxs-lookup"><span data-stu-id="5b731-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="5b731-148">选择 **编辑维度** 以添加要作为度量值分组依据的数据属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="5b731-149">例如，市/县或性别。</span><span class="sxs-lookup"><span data-stu-id="5b731-149">For example, city or gender.</span></span> <span data-ttu-id="5b731-150">默认情况下选择了 *CustomerID *维度来创建* 客户级别的度量*。</span><span class="sxs-lookup"><span data-stu-id="5b731-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="5b731-151">如果要创建 *业务级别的度量*，可以删除默认维度。</span><span class="sxs-lookup"><span data-stu-id="5b731-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="5b731-152">选择 **完成** 以将维度添加到度量中。</span><span class="sxs-lookup"><span data-stu-id="5b731-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="5b731-153">如果您的数据中有需要替换为整数的值（例如，将 *null* 替换为 *0*），请选择 **规则**。</span><span class="sxs-lookup"><span data-stu-id="5b731-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="5b731-154">配置规则并确保您只选择整数作为替换值。</span><span class="sxs-lookup"><span data-stu-id="5b731-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="5b731-155">如果所映射的数据实体与 *客户* 实体之间有多个路径，您必须选择其中一个标识的[实体关系路径](relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="5b731-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="5b731-156">根据所选路径的不同，度量结果可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="5b731-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="5b731-157">选择 **数据首选项**，并选择将用于标识度量的实体路径。</span><span class="sxs-lookup"><span data-stu-id="5b731-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="5b731-158">如果只有一个指向 *客户* 实体的路径，则不会显示此控件。</span><span class="sxs-lookup"><span data-stu-id="5b731-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="5b731-159">选择 **完成** 以应用您的选择。</span><span class="sxs-lookup"><span data-stu-id="5b731-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="为度量选择实体路径。":::

1. <span data-ttu-id="5b731-161">若要为度量添加更多计算，请选择 **新建计算**。</span><span class="sxs-lookup"><span data-stu-id="5b731-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="5b731-162">只能在同一实体路径上使用实体进行新计算。</span><span class="sxs-lookup"><span data-stu-id="5b731-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="5b731-163">更多计算将在度量输出实体中显示为新列。</span><span class="sxs-lookup"><span data-stu-id="5b731-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="5b731-164">在计算中选择 **...** 以从度量中 **复制**、**重命名** 或 **删除** 计算。</span><span class="sxs-lookup"><span data-stu-id="5b731-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="5b731-165">在 **预览** 区域中，您将看到度量输出实体的数据架构，包括筛选器和维度。</span><span class="sxs-lookup"><span data-stu-id="5b731-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="5b731-166">预览会动态响应配置中的更改。</span><span class="sxs-lookup"><span data-stu-id="5b731-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="5b731-167">选择 **运行** 以计算已配置度量的结果。</span><span class="sxs-lookup"><span data-stu-id="5b731-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="5b731-168">如果希望保留当前配置并且稍后运行该度量，请选择 **保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="5b731-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="5b731-169">转到 **度量** 以在列表中查看新创建的度量。</span><span class="sxs-lookup"><span data-stu-id="5b731-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="5b731-170">使用模板生成量度</span><span class="sxs-lookup"><span data-stu-id="5b731-170">Use a template to build a measure</span></span>

<span data-ttu-id="5b731-171">您可以使用常用度量的预定义模板来创建它们。</span><span class="sxs-lookup"><span data-stu-id="5b731-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="5b731-172">模板的详细描述和引导式体验可帮助您高效创建度量。</span><span class="sxs-lookup"><span data-stu-id="5b731-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="5b731-173">模板建立在 *统一活动* 实体的映射数据的基础上。</span><span class="sxs-lookup"><span data-stu-id="5b731-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="5b731-174">因此，在从模板创建量度之前，请确保已配置[客户活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="5b731-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="5b731-175">可用的度量模板：</span><span class="sxs-lookup"><span data-stu-id="5b731-175">Available measure templates:</span></span> 
- <span data-ttu-id="5b731-176">平均交易值(ATV)</span><span class="sxs-lookup"><span data-stu-id="5b731-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="5b731-177">总交易值</span><span class="sxs-lookup"><span data-stu-id="5b731-177">Total transaction value</span></span>
- <span data-ttu-id="5b731-178">平均每日收入</span><span class="sxs-lookup"><span data-stu-id="5b731-178">Average daily revenue</span></span>
- <span data-ttu-id="5b731-179">平均每年收入</span><span class="sxs-lookup"><span data-stu-id="5b731-179">Average yearly revenue</span></span>
- <span data-ttu-id="5b731-180">交易计数</span><span class="sxs-lookup"><span data-stu-id="5b731-180">Transaction count</span></span>
- <span data-ttu-id="5b731-181">获得的忠诚度分数</span><span class="sxs-lookup"><span data-stu-id="5b731-181">Loyalty points earned</span></span>
- <span data-ttu-id="5b731-182">兑现的忠诚度分数</span><span class="sxs-lookup"><span data-stu-id="5b731-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="5b731-183">忠诚度分数余额</span><span class="sxs-lookup"><span data-stu-id="5b731-183">Loyalty points balance</span></span>
- <span data-ttu-id="5b731-184">可用的客户生存期跨度</span><span class="sxs-lookup"><span data-stu-id="5b731-184">Active customer lifespan</span></span>
- <span data-ttu-id="5b731-185">忠诚度成员资格持续时间</span><span class="sxs-lookup"><span data-stu-id="5b731-185">Loyalty membership duration</span></span>
- <span data-ttu-id="5b731-186">自最后一次购买以来的时间</span><span class="sxs-lookup"><span data-stu-id="5b731-186">Time since last purchase</span></span>

<span data-ttu-id="5b731-187">以下程序概述了使用模板构建新度量的步骤。</span><span class="sxs-lookup"><span data-stu-id="5b731-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="5b731-188">在访问群体见解中，转到 **度量**。</span><span class="sxs-lookup"><span data-stu-id="5b731-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="5b731-189">选择 **新建**，然后选择 **选择模板**。</span><span class="sxs-lookup"><span data-stu-id="5b731-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="在创建新度量并在模板上突出显示时的下拉菜单的屏幕截图。":::

1. <span data-ttu-id="5b731-191">查找适合您的需求的模板并选择 **选择模板**。</span><span class="sxs-lookup"><span data-stu-id="5b731-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="5b731-192">查看所需数据，如果所有数据都到位，请选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="5b731-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="5b731-193">在 **编辑名称** 窗格中，为您的度量和输出实体设置名称。</span><span class="sxs-lookup"><span data-stu-id="5b731-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="5b731-194">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="5b731-194">Select **Done**.</span></span>

1. <span data-ttu-id="5b731-195">在 **设置时间段** 部分中，定义要使用的数据的期限。</span><span class="sxs-lookup"><span data-stu-id="5b731-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="5b731-196">选择是希望新度量通过选择 **所有时间** 覆盖整个数据集，还是希望该度量重点关注 **特定时间段**。</span><span class="sxs-lookup"><span data-stu-id="5b731-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="从模板中配置量度时显示时间段部分的屏幕截图。":::

1. <span data-ttu-id="5b731-198">在下一节中，选择 **添加数据** 来选择活动，并从 *统一活动* 实体中映射相应的数据。</span><span class="sxs-lookup"><span data-stu-id="5b731-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="5b731-199">第 1 步，共 2 步：在 **活动类型** 下，选择要使用的实体类型。</span><span class="sxs-lookup"><span data-stu-id="5b731-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="5b731-200">对于 **活动**，请选择要映射的实体。</span><span class="sxs-lookup"><span data-stu-id="5b731-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="5b731-201">第 2 步，共 2 步：针对公式所要求的组件从 *统一活动* 实体中选择属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="5b731-202">例如，对于平均交易价值，它是代表交易值的属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="5b731-203">对于 **活动时间戳**，请从表示活动日期和时间的统一活动实体中选择属性。</span><span class="sxs-lookup"><span data-stu-id="5b731-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="5b731-204">数据映射成功后，您可以看到状态为 **完成**，并且可以看到映射活动和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="5b731-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="已完成的度量模板配置的屏幕截图。":::

1. <span data-ttu-id="5b731-206">现在，您可以选择 **运行** 来计算度量结果。</span><span class="sxs-lookup"><span data-stu-id="5b731-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="5b731-207">要稍后进行改进，请选择 **保存草稿**。</span><span class="sxs-lookup"><span data-stu-id="5b731-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="5b731-208">管理度量</span><span class="sxs-lookup"><span data-stu-id="5b731-208">Manage your measures</span></span>

<span data-ttu-id="5b731-209">您可以在 **度量** 页面上找到度量列表。</span><span class="sxs-lookup"><span data-stu-id="5b731-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="5b731-210">您将找到有关度量类型、创建者、创建日期、状况和状态的信息。</span><span class="sxs-lookup"><span data-stu-id="5b731-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="5b731-211">当您从列表中选择度量时，您可以预览输出并下载 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="5b731-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="5b731-212">若要同时刷新所有度量，请在不选择特定度量的情况下选择 **全部刷新**。</span><span class="sxs-lookup"><span data-stu-id="5b731-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5b731-213">![用于管理单个度量的操作。](media/measure-actions.png "用于管理单个度量的操作。")</span><span class="sxs-lookup"><span data-stu-id="5b731-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="5b731-214">针对以下选项从列表中选择度量：</span><span class="sxs-lookup"><span data-stu-id="5b731-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="5b731-215">选择度量名称以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b731-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="5b731-216">**编辑** 度量的配置。</span><span class="sxs-lookup"><span data-stu-id="5b731-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="5b731-217">根据最新数据 **刷新** 度量。</span><span class="sxs-lookup"><span data-stu-id="5b731-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="5b731-218">**重命名** 度量。</span><span class="sxs-lookup"><span data-stu-id="5b731-218">**Rename** the measure.</span></span>
- <span data-ttu-id="5b731-219">**删除** 度量。</span><span class="sxs-lookup"><span data-stu-id="5b731-219">**Delete** the measure.</span></span>
- <span data-ttu-id="5b731-220">**激活** 或 **停用**。</span><span class="sxs-lookup"><span data-stu-id="5b731-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="5b731-221">停用的度量在[计划刷新](system.md#schedule-tab)期间不会刷新。</span><span class="sxs-lookup"><span data-stu-id="5b731-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="5b731-222">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="5b731-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5b731-223">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="5b731-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5b731-224">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b731-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5b731-225">针对一个作业任务选择 **查看详细信息** 后，您将找到其他信息：处理时间、上次处理日期以及与该任务关联的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="5b731-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="5b731-226">下一步</span><span class="sxs-lookup"><span data-stu-id="5b731-226">Next step</span></span>

<span data-ttu-id="5b731-227">您可以使用现有度量创建[客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="5b731-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
