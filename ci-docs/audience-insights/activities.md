---
title: 客户活动
description: 定义客户活动并在客户时间线中查看它们。
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667218"
---
# <a name="customer-activities"></a><span data-ttu-id="92569-103">客户活动</span><span class="sxs-lookup"><span data-stu-id="92569-103">Customer activities</span></span>

<span data-ttu-id="92569-104">在 Dynamics 365 Customer Insights 中合并来自[各种数据源](data-sources.md)的客户活动，以创建按时间顺序列出活动的客户时间线。</span><span class="sxs-lookup"><span data-stu-id="92569-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="92569-105">您可以通过[客户卡加载项](customer-card-add-in.md)或在 Power BI 仪表板中将时间线包含在 Dynamics 365 中的客户互动应用中。</span><span class="sxs-lookup"><span data-stu-id="92569-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="92569-106">定义活动</span><span class="sxs-lookup"><span data-stu-id="92569-106">Define an activity</span></span>

<span data-ttu-id="92569-107">数据源中包含实体，这些实体的事务数据和活动数据来自多个数据源。</span><span class="sxs-lookup"><span data-stu-id="92569-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="92569-108">确定这些实体，并选择要在客户的时间线上查看的活动。</span><span class="sxs-lookup"><span data-stu-id="92569-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="92569-109">选择其中包含目标活动的实体。</span><span class="sxs-lookup"><span data-stu-id="92569-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="92569-110">在访问群体见解中，转到 **数据** > **活动**。</span><span class="sxs-lookup"><span data-stu-id="92569-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="92569-111">选择 **添加活动**。</span><span class="sxs-lookup"><span data-stu-id="92569-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92569-112">只能向客户时间线添加至少有一个类型为 **日期** 的属性的实体，并且不能添加无 **日期** 字段的实体。</span><span class="sxs-lookup"><span data-stu-id="92569-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="92569-113">如果未找到此类实体，将禁用 **添加活动** 控件。</span><span class="sxs-lookup"><span data-stu-id="92569-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="92569-114">在 **添加活动** 窗格中，设置以下字段的值：</span><span class="sxs-lookup"><span data-stu-id="92569-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="92569-115">**实体**：选择其中包含事务数据或活动数据的实体。</span><span class="sxs-lookup"><span data-stu-id="92569-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="92569-116">**主键**：选择唯一标识记录的字段。</span><span class="sxs-lookup"><span data-stu-id="92569-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="92569-117">其中不应包含任何重复值、空值或缺少值。</span><span class="sxs-lookup"><span data-stu-id="92569-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="92569-118">**时间戳**：选择表示活动开始时间的字段。</span><span class="sxs-lookup"><span data-stu-id="92569-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="92569-119">**事件**：选择充当活动的事件的字段。</span><span class="sxs-lookup"><span data-stu-id="92569-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="92569-120">**Web 地址**：选择字段以表示提供有关此活动的其他信息的 URL。</span><span class="sxs-lookup"><span data-stu-id="92569-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="92569-121">例如，提供该活动的交易系统。</span><span class="sxs-lookup"><span data-stu-id="92569-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="92569-122">此 URL 可以是数据源中的任何字段，也可以使用 Power Query 转换将其构建为新字段。</span><span class="sxs-lookup"><span data-stu-id="92569-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="92569-123">此 URL 数据将存储在“统一活动”实体中，可以通过 API 在下游使用该实体。</span><span class="sxs-lookup"><span data-stu-id="92569-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="92569-124">**详细信息**：（可选）选择为了提供更多详细信息而添加的字段。</span><span class="sxs-lookup"><span data-stu-id="92569-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="92569-125">**图标**：（可选）选择用于表示此活动的图标。</span><span class="sxs-lookup"><span data-stu-id="92569-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="92569-126">**活动类型**：定义对最贴切地描述活动语义定义的通用数据模型的活动类型引用。</span><span class="sxs-lookup"><span data-stu-id="92569-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="92569-127">在 **设置关系** 部分中，配置详细信息以将活动数据连接到其相应客户。</span><span class="sxs-lookup"><span data-stu-id="92569-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92569-128">![定义实体关系](media/activities-entities-define.png "定义实体关系")</span><span class="sxs-lookup"><span data-stu-id="92569-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="92569-129">**活动实体字段**：在活动实体中选择将用于建立与其他实体之间的关系的字段。</span><span class="sxs-lookup"><span data-stu-id="92569-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="92569-130">**客户实体**：选择您的活动实体将与其具有关系的相应源客户实体。</span><span class="sxs-lookup"><span data-stu-id="92569-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="92569-131">只能与数据统一过程中使用的源客户实体关联。</span><span class="sxs-lookup"><span data-stu-id="92569-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="92569-132">**客户实体字段**：此字段显示映射过程中选择的源客户实体的主键。</span><span class="sxs-lookup"><span data-stu-id="92569-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="92569-133">源客户实体中的主键字段用于建立与活动实体之间的关系。</span><span class="sxs-lookup"><span data-stu-id="92569-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="92569-134">**名称**：如果此活动实体与所选源客户实体之间的关系已存在，则关系名称处于只读模式。</span><span class="sxs-lookup"><span data-stu-id="92569-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="92569-135">如果不存在此类关系，则使用此处提供的名称创建新关系。</span><span class="sxs-lookup"><span data-stu-id="92569-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="92569-136">选择 **保存** 以应用您所做的更改。</span><span class="sxs-lookup"><span data-stu-id="92569-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="92569-137">在 **活动** 页中，选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="92569-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="92569-138">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="92569-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="92569-139">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="92569-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="92569-140">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="92569-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="92569-141">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="92569-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="92569-142">编辑活动</span><span class="sxs-lookup"><span data-stu-id="92569-142">Edit an activity</span></span>

1. <span data-ttu-id="92569-143">在访问群体见解中，转到 **数据** > **活动**。</span><span class="sxs-lookup"><span data-stu-id="92569-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="92569-144">选择要编辑的活动实体，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="92569-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="92569-145">或者将鼠标光标悬停在实体行上方，然后选择 **编辑** 图标。</span><span class="sxs-lookup"><span data-stu-id="92569-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="92569-146">单击 **编辑** 图标。</span><span class="sxs-lookup"><span data-stu-id="92569-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="92569-147">在 **编辑活动** 窗格中，更新值，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="92569-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="92569-148">在 **活动** 页中，选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="92569-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="92569-149">删除活动</span><span class="sxs-lookup"><span data-stu-id="92569-149">Delete an activity</span></span>

1. <span data-ttu-id="92569-150">在访问群体见解中，转到 **数据** > **活动**。</span><span class="sxs-lookup"><span data-stu-id="92569-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="92569-151">选择要删除的活动实体，然后选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="92569-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="92569-152">或者将鼠标光标悬停在实体行上方，然后选择 **删除** 图标。</span><span class="sxs-lookup"><span data-stu-id="92569-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="92569-153">也可以选择多个要一次性删除的活动实体。</span><span class="sxs-lookup"><span data-stu-id="92569-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92569-154">![编辑或删除实体关系](media/activities-entities-edit-delete.png "编辑或删除实体关系")</span><span class="sxs-lookup"><span data-stu-id="92569-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="92569-155">选择 **删除** 图标。</span><span class="sxs-lookup"><span data-stu-id="92569-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="92569-156">确认删除。</span><span class="sxs-lookup"><span data-stu-id="92569-156">Confirm your deletion.</span></span>
