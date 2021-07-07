---
title: 客户活动
description: 定义客户活动并在客户时间线中查看它们。
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304915"
---
# <a name="customer-activities"></a><span data-ttu-id="37afd-103">客户活动</span><span class="sxs-lookup"><span data-stu-id="37afd-103">Customer activities</span></span>

<span data-ttu-id="37afd-104">在 Dynamics 365 Customer Insights 中将来自[各种数据源](data-sources.md)的客户活动组合一起，创建一个按时间顺序列出活动的时间线。</span><span class="sxs-lookup"><span data-stu-id="37afd-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="37afd-105">将时间线包含在带[客户卡加载项](customer-card-add-in.md)解决方案的 Dynamics 365 应用中，或包含在 Power BI 仪表板中。</span><span class="sxs-lookup"><span data-stu-id="37afd-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="37afd-106">定义活动</span><span class="sxs-lookup"><span data-stu-id="37afd-106">Define an activity</span></span>

<span data-ttu-id="37afd-107">数据源可以包含实体，这些实体的事务数据和活动数据来自多个数据源。</span><span class="sxs-lookup"><span data-stu-id="37afd-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="37afd-108">确定这些实体，并选择要在客户的时间线上查看的活动。</span><span class="sxs-lookup"><span data-stu-id="37afd-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="37afd-109">选择其中包含目标活动的实体。</span><span class="sxs-lookup"><span data-stu-id="37afd-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="37afd-110">只能向客户时间线添加至少有一个类型为 **日期** 的属性的实体，并且不能添加无 **日期** 字段的实体。</span><span class="sxs-lookup"><span data-stu-id="37afd-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="37afd-111">如果未找到此类实体，将禁用 **添加活动** 控件。</span><span class="sxs-lookup"><span data-stu-id="37afd-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="37afd-112">在访问群体见解中，转到 **数据** > **活动**。</span><span class="sxs-lookup"><span data-stu-id="37afd-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="37afd-113">选择 **添加活动** 以启动活动设置过程的引导式体验。</span><span class="sxs-lookup"><span data-stu-id="37afd-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="37afd-114">在 **活动数据** 步骤中，为以下字段设置值：</span><span class="sxs-lookup"><span data-stu-id="37afd-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="37afd-115">**活动名称**：为您的活动选择一个名称。</span><span class="sxs-lookup"><span data-stu-id="37afd-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="37afd-116">**实体**：选择其中包含事务数据或活动数据的实体。</span><span class="sxs-lookup"><span data-stu-id="37afd-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="37afd-117">**主键**：选择唯一标识记录的字段。</span><span class="sxs-lookup"><span data-stu-id="37afd-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="37afd-118">其中不应包含任何重复值、空值或缺少值。</span><span class="sxs-lookup"><span data-stu-id="37afd-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="使用名称、实体和主键设置活动数据。":::

1. <span data-ttu-id="37afd-120">选择 **下一步** 以继续进行下一步。</span><span class="sxs-lookup"><span data-stu-id="37afd-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="37afd-121">在 **关系** 步骤中，配置详细信息，将您的活动数据连接到相应的客户。</span><span class="sxs-lookup"><span data-stu-id="37afd-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="37afd-122">此步骤显示实体之间的连接。</span><span class="sxs-lookup"><span data-stu-id="37afd-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="37afd-123">**第一**：活动实体中的外键字段，将用于与另一个实体建立关系。</span><span class="sxs-lookup"><span data-stu-id="37afd-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="37afd-124">**第二**：将与您的活动实体有关系的相应源客户实体。</span><span class="sxs-lookup"><span data-stu-id="37afd-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="37afd-125">您只能与数据统一过程中使用的源客户实体关联。</span><span class="sxs-lookup"><span data-stu-id="37afd-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="37afd-126">**第三**：如果此活动实体与所选源客户实体之间已经存在关系，则关系名称将处于仅读模式。</span><span class="sxs-lookup"><span data-stu-id="37afd-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="37afd-127">如果不存在此关系，将使用您在此框中提供的名称创建新关系。</span><span class="sxs-lookup"><span data-stu-id="37afd-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="定义实体关系。":::

1. <span data-ttu-id="37afd-129">选择 **下一步** 以继续进行下一步。</span><span class="sxs-lookup"><span data-stu-id="37afd-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="37afd-130">在 **活动统一** 步骤中，选择活动事件和活动开始时间。</span><span class="sxs-lookup"><span data-stu-id="37afd-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="37afd-131">**必填字段**</span><span class="sxs-lookup"><span data-stu-id="37afd-131">**Required fields**</span></span>
      - <span data-ttu-id="37afd-132">**事件活动**：作为该活动的事件的字段。</span><span class="sxs-lookup"><span data-stu-id="37afd-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="37afd-133">**时间戳**：表示活动开始时间的字段。</span><span class="sxs-lookup"><span data-stu-id="37afd-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="37afd-134">**可选字段**</span><span class="sxs-lookup"><span data-stu-id="37afd-134">**Optional fields**</span></span>
      - <span data-ttu-id="37afd-135">**其他详细信息**：具有此活动的相关信息的字段。</span><span class="sxs-lookup"><span data-stu-id="37afd-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="37afd-136">**图标**：最能代表此活动类型的图标。</span><span class="sxs-lookup"><span data-stu-id="37afd-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="37afd-137">**网址**：包含此活动相关信息的 URL 的字段。</span><span class="sxs-lookup"><span data-stu-id="37afd-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="37afd-138">例如，提供该活动的交易系统。</span><span class="sxs-lookup"><span data-stu-id="37afd-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="37afd-139">此 URL 可以是数据源中的任何字段，也可以使用 Power Query 转换将其构建为新字段。</span><span class="sxs-lookup"><span data-stu-id="37afd-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="37afd-140">URL 数据将存储在 *统一活动* 实体中，可以通过 [API](apis.md) 在下游使用该实体。</span><span class="sxs-lookup"><span data-stu-id="37afd-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="在统一活动实体中指定客户活动数据。":::

1. <span data-ttu-id="37afd-142">选择 **下一步** 以移至下一个步骤。</span><span class="sxs-lookup"><span data-stu-id="37afd-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="37afd-143">您可以选择 **完成并查看**，以立即保存活动并将活动类型设置为 **其他**。</span><span class="sxs-lookup"><span data-stu-id="37afd-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="37afd-144">在 **活动类型** 步骤中，选择活动类型，并根据需要选择是否要在语意上映射某些活动类型，以便在 Customer Insights 的其他区域中使用。</span><span class="sxs-lookup"><span data-stu-id="37afd-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="37afd-145">当前，在同意映射字段后，可以在语义上映射 *Subscription* 和 *SalesOrderLine* 活动类型。</span><span class="sxs-lookup"><span data-stu-id="37afd-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="37afd-146">如果活动类型与新活动无关，您可以为自定义活动类型选择 *其他* 或 *新建*。</span><span class="sxs-lookup"><span data-stu-id="37afd-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="37afd-147">选择 **下一步** 以移至下一个步骤。</span><span class="sxs-lookup"><span data-stu-id="37afd-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="37afd-148">在 **查看** 步骤中，验证您的选择。</span><span class="sxs-lookup"><span data-stu-id="37afd-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="37afd-149">返回到上述任何步骤并在必要时更新信息。</span><span class="sxs-lookup"><span data-stu-id="37afd-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="查看活动的指定字段。":::
   
1. <span data-ttu-id="37afd-151">选择 **保存活动** 以应用您的更改，并选择 **完成** 以返回到 **数据** > **活动**。</span><span class="sxs-lookup"><span data-stu-id="37afd-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="37afd-152">在这里，您可以看到哪些活动设置为在时间线中显示。</span><span class="sxs-lookup"><span data-stu-id="37afd-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="37afd-153">在 **活动** 页面上，选择 **运行** 来处理活动。</span><span class="sxs-lookup"><span data-stu-id="37afd-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="37afd-154">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="37afd-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="37afd-155">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="37afd-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="37afd-156">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="37afd-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="37afd-157">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="37afd-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="37afd-158">管理现有活动</span><span class="sxs-lookup"><span data-stu-id="37afd-158">Manage existing activities</span></span>

<span data-ttu-id="37afd-159">在 **数据** > **活动** 上，您可以查看所有保存的活动并管理它们。</span><span class="sxs-lookup"><span data-stu-id="37afd-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="37afd-160">每个活动都由行表示，其中还包括有关源、实体和活动类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="37afd-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="37afd-161">当您选择活动时，可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="37afd-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="37afd-162">**编辑**：在审核步骤上打开活动设置。</span><span class="sxs-lookup"><span data-stu-id="37afd-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="37afd-163">您可以从此步骤更改当前的任何或全部配置。</span><span class="sxs-lookup"><span data-stu-id="37afd-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="37afd-164">更改配置后，选择 **保存活动**，然后选择 **运行** 来处理更改。</span><span class="sxs-lookup"><span data-stu-id="37afd-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="37afd-165">**重命名**：打开一个对话框，您可以在其中为选定活动输入不同的名称。</span><span class="sxs-lookup"><span data-stu-id="37afd-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="37afd-166">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="37afd-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="37afd-167">**删除**：打开对话框以确认删除所选活动。</span><span class="sxs-lookup"><span data-stu-id="37afd-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="37afd-168">您也可以通过选择活动然后选择删除图标同时删除多个活动。</span><span class="sxs-lookup"><span data-stu-id="37afd-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="37afd-169">选择 **删除** 以确认删除。</span><span class="sxs-lookup"><span data-stu-id="37afd-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
