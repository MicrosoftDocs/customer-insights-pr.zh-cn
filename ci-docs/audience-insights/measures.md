---
title: 创建和编辑度量
description: 定义与客户有关的度量，以分析和反映某些业务领域的绩效。
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405223"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="82076-103">定义和管理度量</span><span class="sxs-lookup"><span data-stu-id="82076-103">Define and manage measures</span></span>

<span data-ttu-id="82076-104">**度量** 表示可影响特定业务领域的绩效和运行状况的关键绩效指标 (KPI)。</span><span class="sxs-lookup"><span data-stu-id="82076-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="82076-105">访问群体见解提供一种直观的体验，用于使用不需要您手动对度量进行编码或验证的查询生成器来生成不同类型的度量。</span><span class="sxs-lookup"><span data-stu-id="82076-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="82076-106">可以在 **主页** 中跟踪业务度量，在 **客户卡** 中查看特定客户的度量，以及在 **细分** 页中使用度量定义客户细分。</span><span class="sxs-lookup"><span data-stu-id="82076-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="82076-107">创建度量</span><span class="sxs-lookup"><span data-stu-id="82076-107">Create a measure</span></span>

<span data-ttu-id="82076-108">此部分演示如何从头创建度量。</span><span class="sxs-lookup"><span data-stu-id="82076-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="82076-109">您可以使用通过 Customer entity 连接的多个数据源的数据建立度量。</span><span class="sxs-lookup"><span data-stu-id="82076-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="82076-110">某些[服务限制](service-limits.md)适用。</span><span class="sxs-lookup"><span data-stu-id="82076-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="82076-111">在访问群体见解中，转到 **度量**。</span><span class="sxs-lookup"><span data-stu-id="82076-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="82076-112">选择 **新度量**。</span><span class="sxs-lookup"><span data-stu-id="82076-112">Select **New measure**.</span></span>

3. <span data-ttu-id="82076-113">选择度量的 **类型**：</span><span class="sxs-lookup"><span data-stu-id="82076-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="82076-114">**客户属性**：每个客户一个字段，用于反映客户的分数、价值或状态。</span><span class="sxs-lookup"><span data-stu-id="82076-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="82076-115">客户属性作为系统生成的一个名称为 **Customer_Measure** 的实体中的属性创建。</span><span class="sxs-lookup"><span data-stu-id="82076-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="82076-116">**客户度量**：按所选维度进行了细分的客户行为见解。</span><span class="sxs-lookup"><span data-stu-id="82076-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="82076-117">将为每个度量生成一个新实体，并且每个客户可能有多个记录。</span><span class="sxs-lookup"><span data-stu-id="82076-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="82076-118">**业务度量**：跟踪业务绩效和业务运行状况。</span><span class="sxs-lookup"><span data-stu-id="82076-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="82076-119">业务度量可能有两种不同输出：**主页** 上显示的数值输出，或 **实体** 页上的新实体。</span><span class="sxs-lookup"><span data-stu-id="82076-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="82076-120">提供 **名称** 和可选的 **显示名称**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="82076-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="82076-121">在 **实体** 部分中，从下拉列表中选择第一个实体。</span><span class="sxs-lookup"><span data-stu-id="82076-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="82076-122">此时应确定度量定义中是否需要更多实体。</span><span class="sxs-lookup"><span data-stu-id="82076-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82076-123">![度量定义](media/measure-definition.png "度量定义")</span><span class="sxs-lookup"><span data-stu-id="82076-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="82076-124">若要添加更多实体，请选择 **添加实体**，然后选择要用于度量的实体。</span><span class="sxs-lookup"><span data-stu-id="82076-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="82076-125">只能选择与您的起始实体之间存在关系的实体。</span><span class="sxs-lookup"><span data-stu-id="82076-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="82076-126">有关定义关系的详细信息，请参阅[关系](relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="82076-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="82076-127">（可选）可以配置变量。</span><span class="sxs-lookup"><span data-stu-id="82076-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="82076-128">在 **变量** 部分中，选择 **新建变量**。</span><span class="sxs-lookup"><span data-stu-id="82076-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="82076-129">变量是对您选择的每个记录进行的计算。</span><span class="sxs-lookup"><span data-stu-id="82076-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="82076-130">例如，计算您的客户的每个记录的销售点 (POS) 和在线销售的总和。</span><span class="sxs-lookup"><span data-stu-id="82076-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="82076-131">为变量提供 **名称**。</span><span class="sxs-lookup"><span data-stu-id="82076-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="82076-132">在 **表达式** 区域中，选择用于开始进行计算的字段。</span><span class="sxs-lookup"><span data-stu-id="82076-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="82076-133">在 **表达式** 区域中键入表达式，同时选择计算中要包含的更多字段。</span><span class="sxs-lookup"><span data-stu-id="82076-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="82076-134">当前，仅支持算术表达式。</span><span class="sxs-lookup"><span data-stu-id="82076-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="82076-135">此外，不支持对来自不同[实体对](relationships.md)的实体进行变量计算。</span><span class="sxs-lookup"><span data-stu-id="82076-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="82076-136">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="82076-136">Select **Done**.</span></span>

11. <span data-ttu-id="82076-137">在 **度量定义** 部分中，定义如何在新度量实体或属性中聚合所选实体和计算的变量。</span><span class="sxs-lookup"><span data-stu-id="82076-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="82076-138">选择 **新维度**。</span><span class="sxs-lookup"><span data-stu-id="82076-138">Select **New dimension**.</span></span> <span data-ttu-id="82076-139">可以将维度视为 *分组依据* 函数。</span><span class="sxs-lookup"><span data-stu-id="82076-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="82076-140">将按您定义的所有维度为您的度量实体或属性的数据输出分组。</span><span class="sxs-lookup"><span data-stu-id="82076-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="82076-141">![选择聚合周期](media/measures-businessreport-measure-definition2.png "选择聚合周期")</span><span class="sxs-lookup"><span data-stu-id="82076-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="82076-142">选择或输入以下信息作为维度的定义的一部分：</span><span class="sxs-lookup"><span data-stu-id="82076-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="82076-143">**实体**：如果您定义度量实体，其中应至少包含一个属性。</span><span class="sxs-lookup"><span data-stu-id="82076-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="82076-144">如果您定义度量属性，默认情况下其中将仅包含一个属性。</span><span class="sxs-lookup"><span data-stu-id="82076-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="82076-145">此项选择与选择包含该属性的实体有关。</span><span class="sxs-lookup"><span data-stu-id="82076-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="82076-146">**字段**：选择要包含在度量实体或属性中的具体属性。</span><span class="sxs-lookup"><span data-stu-id="82076-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="82076-147">**Bucket**：选择要按天、月还是年聚合数据。</span><span class="sxs-lookup"><span data-stu-id="82076-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="82076-148">仅当选择了日期类型属性，才必须进行此选择。</span><span class="sxs-lookup"><span data-stu-id="82076-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="82076-149">**作为**：定义新字段的名称。</span><span class="sxs-lookup"><span data-stu-id="82076-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="82076-150">**显示名称**：定义字段的显示名称。</span><span class="sxs-lookup"><span data-stu-id="82076-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="82076-151">您的业务度量将保存为一位数实体，并在 **主页** 中显示，除非您向度量添加更多维度。</span><span class="sxs-lookup"><span data-stu-id="82076-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="82076-152">添加更多维度之后，**主页** 中将 *不* 显示该度量。</span><span class="sxs-lookup"><span data-stu-id="82076-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="82076-153">（可选）添加聚合函数。</span><span class="sxs-lookup"><span data-stu-id="82076-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="82076-154">您创建的任何聚合都会在度量实体或属性内生成新值。</span><span class="sxs-lookup"><span data-stu-id="82076-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="82076-155">支持的聚合函数为：**最小**、**最大**、**平均**、**中值**、**总和**、**唯一计数**、**第一个**（采用维度值的第一个记录）和 **最后一个**（采用向维度值添加的最后一个记录）。</span><span class="sxs-lookup"><span data-stu-id="82076-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="82076-156">选择 **保存** 应用对字段进行的更改。</span><span class="sxs-lookup"><span data-stu-id="82076-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="82076-157">管理度量</span><span class="sxs-lookup"><span data-stu-id="82076-157">Manage your measures</span></span>

<span data-ttu-id="82076-158">在创建至少一个度量后，您将在 **度量** 页面上看到度量的列表。</span><span class="sxs-lookup"><span data-stu-id="82076-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="82076-159">可以找到有关度量类型、创建者、创建日期和时间、上次编辑日期和时间、状态（度量为活动、不活动还是失败）和上次刷新日期和时间的信息。</span><span class="sxs-lookup"><span data-stu-id="82076-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="82076-160">从列表中选择度量时，可以查看其输出的预览。</span><span class="sxs-lookup"><span data-stu-id="82076-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="82076-161">若要同时刷新所有度量，请在不选择特定度量的情况下选择 **全部刷新**。</span><span class="sxs-lookup"><span data-stu-id="82076-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="82076-162">![用于管理单个度量的操作](media/measure-actions.png "用于管理单个度量的操作")</span><span class="sxs-lookup"><span data-stu-id="82076-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="82076-163">或者，从列表中选择度量，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="82076-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="82076-164">选择度量名称以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="82076-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="82076-165">**编辑** 度量的配置。</span><span class="sxs-lookup"><span data-stu-id="82076-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="82076-166">**重命名** 度量。</span><span class="sxs-lookup"><span data-stu-id="82076-166">**Rename** the measure.</span></span>
- <span data-ttu-id="82076-167">**删除** 度量。</span><span class="sxs-lookup"><span data-stu-id="82076-167">**Delete** the measure.</span></span>
- <span data-ttu-id="82076-168">选择省略号 (...)，然后选择 **刷新** 开始度量的刷新过程。</span><span class="sxs-lookup"><span data-stu-id="82076-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="82076-169">选择省略号 (...)，然后选择 **下载** 以获取度量的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="82076-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="82076-170">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="82076-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="82076-171">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="82076-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="82076-172">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82076-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="82076-173">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="82076-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="82076-174">下一步</span><span class="sxs-lookup"><span data-stu-id="82076-174">Next step</span></span>

<span data-ttu-id="82076-175">可以使用现有度量创建 **细分** 页中的第一个客户细分。</span><span class="sxs-lookup"><span data-stu-id="82076-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="82076-176">有关详细信息，请参阅[细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="82076-176">For more information, see [Segments](segments.md).</span></span>
