---
title: 创建和管理细分
description: 创建客户细分，以便根据各种属性为客户分组。
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597040"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="7fe7b-103">创建和管理细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-103">Create and manage segments</span></span>

<span data-ttu-id="7fe7b-104">通过客户细分，您可以基于人口统计、交易或行为属性对客户进行分组。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="7fe7b-105">您可以使用客户细分来确定促销活动、销售活动和客户支持操作的目标，以实现您的业务目标。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="7fe7b-106">可定义客户配置文件实体及其相关实体的复杂筛选器。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="7fe7b-107">每个客户细分在处理之后都会创建一组您可以导出并对其执行操作的客户记录。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="7fe7b-108">某些[服务限制](service-limits.md)适用。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="7fe7b-109">除非另有规定，否则所有客户细分都是 **动态客户细分**，将根据定期计划刷新。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="7fe7b-110">下面的示例演示了细分功能。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="7fe7b-111">我们为过去 90 天至少订购了 500 美元的货物的客户 *和* 已升级的客户服务呼叫中涉及的客户定义了一个细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7fe7b-112">![多个组](media/segmentation-group1-2.png "多个组")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="7fe7b-113">新建细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-113">Create a new segment</span></span>

<span data-ttu-id="7fe7b-114">在 **客户细分** 页面上管理客户细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="7fe7b-115">在访问群体见解中，转到 **客户细分** 页面。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="7fe7b-116">选择 **新建** > **空白客户细分**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="7fe7b-117">在 **新细分** 窗格中，选择细分类型，然后提供 **名称**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="7fe7b-118">（可选）提供有助于识别细分的显示名称和描述。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="7fe7b-119">选择 **下一步** 转到 **细分生成器**，在此处定义组。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="7fe7b-120">组是一组客户。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="7fe7b-121">选择其中包含要充当细分依据的属性的实体。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="7fe7b-122">选择细分依据属性。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="7fe7b-123">此属性可以采用以下四种值类型之一：数字、字符串、日期或布尔值。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="7fe7b-124">为所选属性选择运算符和值。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe7b-125">![自定义组筛选器](media/customer-group-numbers.png "客户组筛选器")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="7fe7b-126">号码</span><span class="sxs-lookup"><span data-stu-id="7fe7b-126">Number</span></span> |<span data-ttu-id="7fe7b-127">定义</span><span class="sxs-lookup"><span data-stu-id="7fe7b-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="7fe7b-128">1</span><span class="sxs-lookup"><span data-stu-id="7fe7b-128">1</span></span>     |<span data-ttu-id="7fe7b-129">Entity</span><span class="sxs-lookup"><span data-stu-id="7fe7b-129">Entity</span></span>          |
   |<span data-ttu-id="7fe7b-130">2</span><span class="sxs-lookup"><span data-stu-id="7fe7b-130">2</span></span>     |<span data-ttu-id="7fe7b-131">属性</span><span class="sxs-lookup"><span data-stu-id="7fe7b-131">Attribute</span></span>          |
   |<span data-ttu-id="7fe7b-132">3</span><span class="sxs-lookup"><span data-stu-id="7fe7b-132">3</span></span>    |<span data-ttu-id="7fe7b-133">操作员</span><span class="sxs-lookup"><span data-stu-id="7fe7b-133">Operator</span></span>         |
   |<span data-ttu-id="7fe7b-134">4</span><span class="sxs-lookup"><span data-stu-id="7fe7b-134">4</span></span>    |<span data-ttu-id="7fe7b-135">值</span><span class="sxs-lookup"><span data-stu-id="7fe7b-135">Value</span></span>         |

8. <span data-ttu-id="7fe7b-136">如果实体通过[关系](relationships.md)连接到统一客户实体，您需要定义关系路径才能创建有效细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="7fe7b-137">添加关系路径中的实体，直到从下拉列表中选择 **客户：CustomerInsights** 实体。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="7fe7b-138">然后为每个条件选择 **所有记录**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe7b-139">![细分创建过程中的关系路径](media/segments-multiple-relationships.png "细分创建过程中的关系路径")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="7fe7b-140">默认情况下，客户细分会生成一个输出实体，其中包含与所定义筛选器匹配的客户配置文件的所有属性。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="7fe7b-141">如果细分市场基于 *客户* 实体以外的其他实体，则可以将这些实体中的更多属性添加到输出实体中。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="7fe7b-142">选择 **项目属性** 以选择将附加到输出实体的属性。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="7fe7b-143">示例：客户细分基于包含与 *客户* 实体相关的客户活动数据的实体。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="7fe7b-144">该客户细分会查找过去 60 天内致电过服务台的所有客户。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="7fe7b-145">您可以选择将呼叫持续时间和呼叫次数追加到输出实体中的所有匹配客户记录。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="7fe7b-146">在将包含联机帮助文章和常见问题解答的帮助链接的电子邮件发送给经常致电的客户时，这些信息可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="7fe7b-147">选择 **保存** 以保存细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="7fe7b-148">将保存您的细分，如果验证了所有要求，将处理该细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="7fe7b-149">否则，将把其保存为草稿。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="7fe7b-150">选择 **返回到客户细分** 以返回到 **客户细分** 页。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="7fe7b-151">管理现有细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-151">Manage existing segments</span></span>

<span data-ttu-id="7fe7b-152">在 **细分** 页上，可以查看和管理所有保存的细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="7fe7b-153">每个客户细分都由包含有关客户细分的其他信息的行来表示。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="7fe7b-154">可以通过选择列标题对列中的细分进行排序。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="7fe7b-155">可使用右上角的 **搜索** 框筛选客户细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7fe7b-156">![用于管理现有细分的选项](media/segments-selected-segment.png "用于管理现有细分的选项")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="7fe7b-157">选择客户细分时可以使用以下操作：</span><span class="sxs-lookup"><span data-stu-id="7fe7b-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="7fe7b-158">**查看** 细分详细信息，包括细分成员的成员计数趋势预览。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="7fe7b-159">**编辑** 细分以更改其属性。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="7fe7b-160">**创建客户细分的重复项**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="7fe7b-161">您可以选择立即编辑其属性或只是保存重复项。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="7fe7b-162">**刷新** 细分以包括最新数据。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="7fe7b-163">**激活** 或 **停用** 细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="7fe7b-164">客户细分具有两种可能的状态 - 活动或停用。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="7fe7b-165">这些状态在编辑客户细分时很有用。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="7fe7b-166">对于停用的客户细分，存在客户细分定义，但不包含任何客户。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="7fe7b-167">激活客户细分时，其状态将从“停用”变为“活动”，然后开始查找匹配客户细分定义的客户。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="7fe7b-168">如果配置了 [计划刷新](system.md#schedule-tab)，停用客户细分会将 **状态** 列为 **已跳过**，指示还没有尝试刷新。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="7fe7b-169">激活停用客户细分后，它将刷新，并包括在计划刷新中。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="7fe7b-170">或者，您可以使用 **激活/停用** 下拉列表中的 **以后计划** 功能指定将来的日期和时间来激活和停用特定客户细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="7fe7b-171">**重命名** 细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-171">**Rename** the segment.</span></span>
- <span data-ttu-id="7fe7b-172">以 .CSV 文件格式 **下载** 成员列表。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="7fe7b-173">**添加到** 选项将发送客户细分中的客户 ID 列表，以在另一个应用程序中进行处理。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="7fe7b-174">**删除** 细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="7fe7b-175">刷新细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-175">Refresh segments</span></span>

<span data-ttu-id="7fe7b-176">您可以通过选择 **客户细分** 页上的 **全部刷新** 来同时刷新所有客户细分；也可以选择一个或多个客户细分，然后从选项中选择 **刷新** 来刷新它们。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="7fe7b-177">也可以在 **管理** > **系统** > **计划** 中配置定期刷新。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="7fe7b-178">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7fe7b-179">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7fe7b-180">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7fe7b-181">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="7fe7b-182">下载和导出细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-182">Download and export segments</span></span>

<span data-ttu-id="7fe7b-183">可以将细分导出到 CSV 文件或 Dynamics 365 Sales。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="7fe7b-184">将细分导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="7fe7b-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="7fe7b-185">在访问群体见解中，转到 **客户细分** 页面。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="7fe7b-186">选择特定细分的磁贴中的省略号。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="7fe7b-187">从操作下拉列表选择 **下载为 CSV**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="7fe7b-188">将细分导出到 Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="7fe7b-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="7fe7b-189">将细分导出到 Dynamics 365 Sales 之前，管理员需要为 Dynamics 365 Sales [创建导出目标](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="7fe7b-190">在访问群体见解中，转到 **客户细分** 页面。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="7fe7b-191">选择特定细分的磁贴中的省略号。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="7fe7b-192">从操作下拉列表中选择 **添加到**，然后选择要将数据发送到的导出目标。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="7fe7b-193">细分的草稿模式</span><span class="sxs-lookup"><span data-stu-id="7fe7b-193">Draft mode for segments</span></span>

<span data-ttu-id="7fe7b-194">如果未满足细分的所有要求，可以将细分保存为草稿，并通过 **细分** 页访问。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="7fe7b-195">将保存为不可用细分，并且有效前不可激活。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="7fe7b-196">向组添加更多条件</span><span class="sxs-lookup"><span data-stu-id="7fe7b-196">Add more conditions to a group</span></span>

<span data-ttu-id="7fe7b-197">若要向组添加更多条件，可以使用两种逻辑运算符：</span><span class="sxs-lookup"><span data-stu-id="7fe7b-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="7fe7b-198">**AND** 运算符：细分过程中必须同时满足两个条件。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="7fe7b-199">如果要为不同实体定义条件，此选项最有用。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="7fe7b-200">**OR** 运算符：细分过程中需要满足其中一个条件。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="7fe7b-201">如果要为同一个实体定义多个条件，此选项最有用。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe7b-202">![需要满足其中一个条件时的 OR 运算符](media/segmentation-either-condition.png "需要满足其中一个条件时的 OR 运算符")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="7fe7b-203">现在可以将 **OR** 运算符嵌套到 **AND** 运算符下，反之则不可以。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="7fe7b-204">合并多个组</span><span class="sxs-lookup"><span data-stu-id="7fe7b-204">Combine multiple groups</span></span>

<span data-ttu-id="7fe7b-205">每个组都会生成一组特定客户。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="7fe7b-206">可以合并这些组以包含您的业务案例所需客户。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="7fe7b-207">在访问群体见解中，转到 **客户细分** 页面并选择客户细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="7fe7b-208">选择 **添加组**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe7b-209">![客户组添加组](media/customer-group-add-group.png "客户组添加组")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="7fe7b-210">选择以下集运算符之一：**并集**、**相交** 或 **除非**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fe7b-211">![客户组添加联合](media/customer-group-union.png "客户组添加联合")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="7fe7b-212">选择一个 set 运算符来定义一个新组。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="7fe7b-213">保存不同的组以确定保留哪些数据：</span><span class="sxs-lookup"><span data-stu-id="7fe7b-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="7fe7b-214">**联合** 用于联合两个组。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="7fe7b-215">**相交** 用于重叠两个组。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="7fe7b-216">仅在统一组中保留这两个组 *共有* 的数据。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="7fe7b-217">**除外** 用于合并两个组。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-217">**Except** combines the two groups.</span></span> <span data-ttu-id="7fe7b-218">仅保留 A 组中与 B 组中的数据 *不共有* 的数据。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="7fe7b-219">查看处理历史记录和细分成员</span><span class="sxs-lookup"><span data-stu-id="7fe7b-219">View processing history and segment members</span></span>

<span data-ttu-id="7fe7b-220">可以通过查看细分的详细信息来查看有关该细分的合并数据。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="7fe7b-221">在 **细分** 页上，选择要查看的细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="7fe7b-222">此页面的上半部分中有一个趋势图，该趋势图显示成员计数的变化。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="7fe7b-223">将光标悬停在数据点上方可查看特定日期的成员计数。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="7fe7b-224">可以更新可视化的时间段。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7fe7b-225">![细分时间范围](media/segment-time-range.png "细分时间范围")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="7fe7b-226">下半部分中包含细分成员列表。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="7fe7b-227">此列表中显示的字段基于细分的实体属性。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="7fe7b-228">此列表是匹配的细分成员的预览，并显示您的细分的前 100 条记录，以便您快速评估该细分和在需要时查看其定义。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="7fe7b-229">若要查看所有匹配的记录，需要[导出细分](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="7fe7b-230">快速细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-230">Quick segments</span></span>

<span data-ttu-id="7fe7b-231">除了客户细分生成器之外，还有一种方法可用于创建客户细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="7fe7b-232">可通过快速细分使用即时见解构建简单细分（通过一个运算符）。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="7fe7b-233">在 **细分** 页中，选择 **新建** > **快速创建自**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="7fe7b-234">若要生成基于统一的客户实体的细分，请选择 **配置文件** 选项。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="7fe7b-235">若要基于您之前在 **度量** 页中创建的度量的每个客户属性类型生成细分，请选择 **度量** 选项。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="7fe7b-236">选择 **智能** 以根据您使用 **预测** 或 **自定义模型** 功能生成的一个输出实体构建细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="7fe7b-237">在 **新快速客户细分** 对话框中，从 **字段** 下拉列表选择属性。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="7fe7b-238">系统将提供一些额外见解，帮助您创建更好的客户细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="7fe7b-239">对于分类字段，我们将显示排名最靠前的 10 类客户的计数。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="7fe7b-240">选择一个 **值**，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="7fe7b-241">对于数值属性，系统将显示哪个属性值归入每个客户的百分比下。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="7fe7b-242">选择 **运算符** 和 **值**，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="7fe7b-243">系统将为您提供 **估算的细分大小**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="7fe7b-244">可以选择要生成已定义的细分，还是先再次访问该细分以获取不同的细分大小。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7fe7b-245">![快速细分的名称和估算](media/quick-segment-name.png "快速细分的名称和估算")</span><span class="sxs-lookup"><span data-stu-id="7fe7b-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="7fe7b-246">为细分提供 **名称**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="7fe7b-247">（可选）提供 **显示名称**。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="7fe7b-248">选择 **保存** 以创建细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="7fe7b-249">处理完细分之后，可以就像创建的其他细分一样查看该细分。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="7fe7b-250">对于以下情况，建议使用细分生成器，而不是推荐的细分功能。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="7fe7b-251">当运算符不是 **是** 时对类别字段使用筛选器来创建细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="7fe7b-252">当运算符不是 **介于**、**大于** 和 **小于** 时对数值字段使用筛选器来创建细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="7fe7b-253">通过筛选日期类型字段创建细分</span><span class="sxs-lookup"><span data-stu-id="7fe7b-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="7fe7b-254">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7fe7b-254">Next steps</span></span>

<span data-ttu-id="7fe7b-255">[导出细分](export-destinations.md)和浏览[客户卡](customer-card-add-in.md)和[连接器](export-power-bi.md)以获取客户级见解。</span><span class="sxs-lookup"><span data-stu-id="7fe7b-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]