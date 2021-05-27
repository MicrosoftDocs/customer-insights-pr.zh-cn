---
title: 创建和管理细分
description: 创建客户细分，以便根据各种属性为客户分组。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064926"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="bc82c-103">创建和管理细分</span><span class="sxs-lookup"><span data-stu-id="bc82c-103">Create and manage segments</span></span>

<span data-ttu-id="bc82c-104">围绕着统一客户实体及其相关实体定义复杂筛选器。</span><span class="sxs-lookup"><span data-stu-id="bc82c-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="bc82c-105">每个客户细分在处理之后都会创建一组您可以导出并对其执行操作的客户记录。</span><span class="sxs-lookup"><span data-stu-id="bc82c-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="bc82c-106">在 **客户细分** 页面上管理客户细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="bc82c-107">下面的示例演示了细分功能。</span><span class="sxs-lookup"><span data-stu-id="bc82c-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="bc82c-108">我们为过去 90 天至少订购了 500 美元的货物的客户 *和* 已升级的客户服务呼叫中涉及的客户定义了一个细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="客户细分生成器 UI 的屏幕截图，其中包含两个指定客户细分的组。":::

## <a name="create-a-new-segment"></a><span data-ttu-id="bc82c-110">新建细分</span><span class="sxs-lookup"><span data-stu-id="bc82c-110">Create a new segment</span></span>

<span data-ttu-id="bc82c-111">创建新客户细分的方法有多种。</span><span class="sxs-lookup"><span data-stu-id="bc82c-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="bc82c-112">本节介绍如何从头开始创建 *空白客户细分*。</span><span class="sxs-lookup"><span data-stu-id="bc82c-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="bc82c-113">您还可以根据现有实体创建 *快速客户细分*，或者使用机器学习模型获取 *建议的客户细分*。</span><span class="sxs-lookup"><span data-stu-id="bc82c-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="bc82c-114">详细信息：[客户细分概述](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="bc82c-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="bc82c-115">在创建客户细分时，可以保存草稿。</span><span class="sxs-lookup"><span data-stu-id="bc82c-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="bc82c-116">它将保存为停用的客户细分，完成之前无法通过有效配置激活它。</span><span class="sxs-lookup"><span data-stu-id="bc82c-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="bc82c-117">转到 **细分** 页。</span><span class="sxs-lookup"><span data-stu-id="bc82c-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="bc82c-118">选择 **新建** > **空白客户细分**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="bc82c-119">在 **新建客户细分** 窗格中，选择客户细分类型：</span><span class="sxs-lookup"><span data-stu-id="bc82c-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="bc82c-120">按定期计划进行 **动态客户细分**[刷新](segments.md#refresh-segments)。</span><span class="sxs-lookup"><span data-stu-id="bc82c-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="bc82c-121">在创建后运行一次 **静态客户细分**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="bc82c-122">为客户细分提供 **输出实体名称**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="bc82c-123">（可选）提供有助于识别细分的显示名称和描述。</span><span class="sxs-lookup"><span data-stu-id="bc82c-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="bc82c-124">选择 **下一步** 转到 **细分生成器**，在此处定义组。</span><span class="sxs-lookup"><span data-stu-id="bc82c-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="bc82c-125">组是一组客户。</span><span class="sxs-lookup"><span data-stu-id="bc82c-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="bc82c-126">选择其中包含要充当细分依据的属性的实体。</span><span class="sxs-lookup"><span data-stu-id="bc82c-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="bc82c-127">选择细分依据属性。</span><span class="sxs-lookup"><span data-stu-id="bc82c-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="bc82c-128">此属性可以采用以下四种值类型之一：数字、字符串、日期或布尔值。</span><span class="sxs-lookup"><span data-stu-id="bc82c-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="bc82c-129">为所选属性选择运算符和值。</span><span class="sxs-lookup"><span data-stu-id="bc82c-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc82c-130">![自定义组筛选器](media/customer-group-numbers.png "客户组筛选器")</span><span class="sxs-lookup"><span data-stu-id="bc82c-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="bc82c-131">数量</span><span class="sxs-lookup"><span data-stu-id="bc82c-131">Number</span></span> |<span data-ttu-id="bc82c-132">定义</span><span class="sxs-lookup"><span data-stu-id="bc82c-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="bc82c-133">1</span><span class="sxs-lookup"><span data-stu-id="bc82c-133">1</span></span>     |<span data-ttu-id="bc82c-134">Entity</span><span class="sxs-lookup"><span data-stu-id="bc82c-134">Entity</span></span>          |
   |<span data-ttu-id="bc82c-135">2</span><span class="sxs-lookup"><span data-stu-id="bc82c-135">2</span></span>     |<span data-ttu-id="bc82c-136">属性</span><span class="sxs-lookup"><span data-stu-id="bc82c-136">Attribute</span></span>          |
   |<span data-ttu-id="bc82c-137">3</span><span class="sxs-lookup"><span data-stu-id="bc82c-137">3</span></span>    |<span data-ttu-id="bc82c-138">操作员</span><span class="sxs-lookup"><span data-stu-id="bc82c-138">Operator</span></span>         |
   |<span data-ttu-id="bc82c-139">4</span><span class="sxs-lookup"><span data-stu-id="bc82c-139">4</span></span>    |<span data-ttu-id="bc82c-140">值</span><span class="sxs-lookup"><span data-stu-id="bc82c-140">Value</span></span>         |

   1. <span data-ttu-id="bc82c-141">若要向组添加更多条件，可以使用两种逻辑运算符：</span><span class="sxs-lookup"><span data-stu-id="bc82c-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="bc82c-142">**AND** 运算符：细分过程中必须同时满足两个条件。</span><span class="sxs-lookup"><span data-stu-id="bc82c-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="bc82c-143">如果要为不同实体定义条件，此选项最有用。</span><span class="sxs-lookup"><span data-stu-id="bc82c-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="bc82c-144">**OR** 运算符：细分过程中需要满足其中一个条件。</span><span class="sxs-lookup"><span data-stu-id="bc82c-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="bc82c-145">如果要为同一个实体定义多个条件，此选项最有用。</span><span class="sxs-lookup"><span data-stu-id="bc82c-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="bc82c-146">![需要满足其中一个条件时的 OR 运算符](media/segmentation-either-condition.png "需要满足其中一个条件时的 OR 运算符")</span><span class="sxs-lookup"><span data-stu-id="bc82c-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="bc82c-147">现在可以将 **OR** 运算符嵌套到 **AND** 运算符下，反之则不可以。</span><span class="sxs-lookup"><span data-stu-id="bc82c-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="bc82c-148">每个组都与一组客户匹配。</span><span class="sxs-lookup"><span data-stu-id="bc82c-148">Each group matches set of customers.</span></span> <span data-ttu-id="bc82c-149">您可以合并组以包括业务案例所需的客户。</span><span class="sxs-lookup"><span data-stu-id="bc82c-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="bc82c-150">选择 **添加组**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="bc82c-151">![客户组添加组](media/customer-group-add-group.png "客户组添加组")</span><span class="sxs-lookup"><span data-stu-id="bc82c-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="bc82c-152">选择一个设置的运算符：**并集**、**交集** 或 **排除**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc82c-153">![客户组添加联合](media/customer-group-union.png "客户组添加联合")</span><span class="sxs-lookup"><span data-stu-id="bc82c-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="bc82c-154">**联合** 用于联合两个组。</span><span class="sxs-lookup"><span data-stu-id="bc82c-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="bc82c-155">**相交** 用于重叠两个组。</span><span class="sxs-lookup"><span data-stu-id="bc82c-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="bc82c-156">仅在统一组中保留这两个组 *共有* 的数据。</span><span class="sxs-lookup"><span data-stu-id="bc82c-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="bc82c-157">**除外** 用于合并两个组。</span><span class="sxs-lookup"><span data-stu-id="bc82c-157">**Except** combines the two groups.</span></span> <span data-ttu-id="bc82c-158">仅保留 A 组中与 B 组中的数据 *不共有* 的数据。</span><span class="sxs-lookup"><span data-stu-id="bc82c-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="bc82c-159">如果实体通过[关系](relationships.md)连接到统一客户实体，您需要定义关系路径才能创建有效细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="bc82c-160">添加关系路径中的实体，直到从下拉列表中选择 **客户：CustomerInsights** 实体。</span><span class="sxs-lookup"><span data-stu-id="bc82c-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="bc82c-161">然后，针对每个步骤选择 **所有记录**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc82c-162">![细分创建过程中的关系路径](media/segments-multiple-relationships.png "细分创建过程中的关系路径")</span><span class="sxs-lookup"><span data-stu-id="bc82c-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="bc82c-163">默认情况下，客户细分会生成一个输出实体，其中包含与所定义筛选器匹配的客户配置文件的所有属性。</span><span class="sxs-lookup"><span data-stu-id="bc82c-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="bc82c-164">如果细分市场基于 *客户* 实体以外的其他实体，则可以将这些实体中的更多属性添加到输出实体中。</span><span class="sxs-lookup"><span data-stu-id="bc82c-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="bc82c-165">选择 **项目属性** 以选择将附加到输出实体的属性。</span><span class="sxs-lookup"><span data-stu-id="bc82c-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="bc82c-166">示例：客户细分基于包含与 *客户* 实体相关的客户活动数据的实体。</span><span class="sxs-lookup"><span data-stu-id="bc82c-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="bc82c-167">该客户细分会查找过去 60 天内致电过服务台的所有客户。</span><span class="sxs-lookup"><span data-stu-id="bc82c-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="bc82c-168">您可以选择将呼叫持续时间和呼叫次数追加到输出实体中的所有匹配客户记录。</span><span class="sxs-lookup"><span data-stu-id="bc82c-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="bc82c-169">在将包含联机帮助文章和常见问题解答的帮助链接的电子邮件发送给经常致电的客户时，这些信息可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="bc82c-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="bc82c-170">预测的属性仅适用于与客户实体具有一对多关系的实体。</span><span class="sxs-lookup"><span data-stu-id="bc82c-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="bc82c-171">例如，一个客户可以具有多个订阅。</span><span class="sxs-lookup"><span data-stu-id="bc82c-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="bc82c-172">您只能从正在构建的每组客户细分查询中所使用的实体预测属性。</span><span class="sxs-lookup"><span data-stu-id="bc82c-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="bc82c-173">在使用设置的运算符时，会将预测属性考虑在内。</span><span class="sxs-lookup"><span data-stu-id="bc82c-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="bc82c-174">选择 **保存** 以保存细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="bc82c-175">将保存您的细分，如果验证了所有要求，将处理该细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="bc82c-176">否则，将把其保存为草稿。</span><span class="sxs-lookup"><span data-stu-id="bc82c-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="bc82c-177">选择 **返回到客户细分** 以返回到 **客户细分** 页。</span><span class="sxs-lookup"><span data-stu-id="bc82c-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="bc82c-178">快速细分</span><span class="sxs-lookup"><span data-stu-id="bc82c-178">Quick segments</span></span>

<span data-ttu-id="bc82c-179">通过快速客户细分，您可以利用单个运算符快速构建简单的客户细分，以便更快地获取见解。</span><span class="sxs-lookup"><span data-stu-id="bc82c-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="bc82c-180">在 **客户细分** 页上，选择 **新建** > **创建自**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="bc82c-181">若要生成基于 *统一的客户* 实体的细分，请选择 **配置文件** 选项。</span><span class="sxs-lookup"><span data-stu-id="bc82c-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="bc82c-182">选择 **度量** 选项，以围绕先前创建的度量构建客户细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="bc82c-183">选择 **智能** 以根据您使用 **预测** 或 **自定义模型** 功能生成的一个输出实体构建细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="bc82c-184">在 **新快速客户细分** 对话框中，从 **字段** 下拉列表选择属性。</span><span class="sxs-lookup"><span data-stu-id="bc82c-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="bc82c-185">系统将提供一些额外见解，帮助您创建更好的客户细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="bc82c-186">对于分类字段，我们将显示排名最靠前的 10 类客户的计数。</span><span class="sxs-lookup"><span data-stu-id="bc82c-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="bc82c-187">选择一个 **值**，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="bc82c-188">对于数值属性，系统将显示哪个属性值归入每个客户的百分比下。</span><span class="sxs-lookup"><span data-stu-id="bc82c-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="bc82c-189">选择 **运算符** 和 **值**，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="bc82c-190">系统将为您提供 **估算的细分大小**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="bc82c-191">可以选择要生成已定义的细分，还是先再次访问该细分以获取不同的细分大小。</span><span class="sxs-lookup"><span data-stu-id="bc82c-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bc82c-192">![快速细分的名称和估算](media/quick-segment-name.png "快速细分的名称和估算")</span><span class="sxs-lookup"><span data-stu-id="bc82c-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="bc82c-193">为细分提供 **名称**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="bc82c-194">（可选）提供 **显示名称**。</span><span class="sxs-lookup"><span data-stu-id="bc82c-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="bc82c-195">选择 **保存** 以创建细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="bc82c-196">处理完细分之后，可以就像创建的其他细分一样查看该细分。</span><span class="sxs-lookup"><span data-stu-id="bc82c-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc82c-197">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bc82c-197">Next steps</span></span>

<span data-ttu-id="bc82c-198">[导出细分](export-destinations.md)和浏览[客户卡](customer-card-add-in.md)和[连接器](export-power-bi.md)以获取客户级见解。</span><span class="sxs-lookup"><span data-stu-id="bc82c-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
