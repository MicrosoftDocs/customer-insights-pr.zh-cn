---
title: 实体和实体路径之间的关系
description: 创建和管理来自多个数据源的实体之间的关系。
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171153"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="08d12-103">实体之间的关系</span><span class="sxs-lookup"><span data-stu-id="08d12-103">Relationships between entities</span></span>

<span data-ttu-id="08d12-104">当实体共享一个通用标识符（一个外键）时，关系会关联实体并定义您的数据图表。</span><span class="sxs-lookup"><span data-stu-id="08d12-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="08d12-105">此外键可从一个实体引用到另一个实体。</span><span class="sxs-lookup"><span data-stu-id="08d12-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="08d12-106">通过连接的实体，可基于多个数据源定义客户细分和度量。</span><span class="sxs-lookup"><span data-stu-id="08d12-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="08d12-107">有以下三种类型的关系：</span><span class="sxs-lookup"><span data-stu-id="08d12-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="08d12-108">由系统在数据统一过程中创建的不可编辑的系统关系</span><span class="sxs-lookup"><span data-stu-id="08d12-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="08d12-109">通过引入数据源自动创建的不可编辑的继承关系</span><span class="sxs-lookup"><span data-stu-id="08d12-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="08d12-110">由用户创建和配置的可编辑自定义关系</span><span class="sxs-lookup"><span data-stu-id="08d12-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="08d12-111">不可编辑的系统关系</span><span class="sxs-lookup"><span data-stu-id="08d12-111">Non-editable system relationships</span></span>

<span data-ttu-id="08d12-112">在数据统一过程中，基于智能匹配自动创建系统关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="08d12-113">这些关系可以帮助将客户配置文件记录与相应记录关联。</span><span class="sxs-lookup"><span data-stu-id="08d12-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="08d12-114">下图说明了基于系统的三个关系的创建。</span><span class="sxs-lookup"><span data-stu-id="08d12-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="08d12-115">客户实体与其他实体匹配以生成统一的 *客户* 实体。</span><span class="sxs-lookup"><span data-stu-id="08d12-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="具有三个 1-n 关系的客户实体的关系路径图。":::

- <span data-ttu-id="08d12-117">创建了 *客户* 实体与 *联系人* 实体之间的 ***CustomerToContact* 关系**。</span><span class="sxs-lookup"><span data-stu-id="08d12-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="08d12-118">*客户* 实体获取了键字段 **Contact_contactID**，以便关联到 *联系人* 实体键字段 **contactID**。</span><span class="sxs-lookup"><span data-stu-id="08d12-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="08d12-119">创建了 *客户* 实体与 *帐户* 实体之间的 ***CustomerToAccount* 关系**。</span><span class="sxs-lookup"><span data-stu-id="08d12-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="08d12-120">*客户* 实体获取了键字段 **Account_accountID**，以便关联到 *帐户* 实体键字段 **accountID**。</span><span class="sxs-lookup"><span data-stu-id="08d12-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="08d12-121">创建了 *客户* 实体与 *WebAccount* 实体之间的 ***CustomerToWebAccount* 关系**。</span><span class="sxs-lookup"><span data-stu-id="08d12-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="08d12-122">*客户* 实体获取了键字段 **WebAccount_webaccountID**，以便关联到 *WebAccount* 实体键字段 **webaccountID**。</span><span class="sxs-lookup"><span data-stu-id="08d12-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="08d12-123">不可编辑的继承关系</span><span class="sxs-lookup"><span data-stu-id="08d12-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="08d12-124">在数据引入过程中，系统会检查现有关系的数据源。</span><span class="sxs-lookup"><span data-stu-id="08d12-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="08d12-125">如果没有关系，系统会自动创建它们。</span><span class="sxs-lookup"><span data-stu-id="08d12-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="08d12-126">这些关系也用于下游流程。</span><span class="sxs-lookup"><span data-stu-id="08d12-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="08d12-127">创建自定义关系</span><span class="sxs-lookup"><span data-stu-id="08d12-127">Create a custom relationship</span></span>

<span data-ttu-id="08d12-128">关系包括包含外键的 *源实体* 和源实体的外键所指向的 *目标实体*。</span><span class="sxs-lookup"><span data-stu-id="08d12-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="08d12-129">在访问群体见解中，转到 **数据** > **关系**。</span><span class="sxs-lookup"><span data-stu-id="08d12-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="08d12-130">选择 **新建关系**。</span><span class="sxs-lookup"><span data-stu-id="08d12-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="08d12-131">在 **新建关系** 窗格中，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="08d12-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="包含空输入字段的新关系侧窗格。":::

   - <span data-ttu-id="08d12-133">**关系名称**：反映关系目的的名称。</span><span class="sxs-lookup"><span data-stu-id="08d12-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="08d12-134">示例：CustomerToSupportCase。</span><span class="sxs-lookup"><span data-stu-id="08d12-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="08d12-135">**说明**：关系的说明。</span><span class="sxs-lookup"><span data-stu-id="08d12-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="08d12-136">**源实体**：在关系中用作来源的实体。</span><span class="sxs-lookup"><span data-stu-id="08d12-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="08d12-137">示例：SupportCase。</span><span class="sxs-lookup"><span data-stu-id="08d12-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="08d12-138">**目标实体**：在关系中用作目标的实体。</span><span class="sxs-lookup"><span data-stu-id="08d12-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="08d12-139">示例：客户。</span><span class="sxs-lookup"><span data-stu-id="08d12-139">Example: Customer.</span></span>
   - <span data-ttu-id="08d12-140">**来源基数**：指定来源实体的基数。</span><span class="sxs-lookup"><span data-stu-id="08d12-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="08d12-141">基数描述了集中可能的元素的数量。</span><span class="sxs-lookup"><span data-stu-id="08d12-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="08d12-142">它始终与目标基数相关。</span><span class="sxs-lookup"><span data-stu-id="08d12-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="08d12-143">您可以在 **一个** 和 **多个** 之间做出选择。</span><span class="sxs-lookup"><span data-stu-id="08d12-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="08d12-144">仅支持多对一和一对一关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="08d12-145">多对一：多个源记录可能与一个目标记录相关。</span><span class="sxs-lookup"><span data-stu-id="08d12-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="08d12-146">示例：单个客户的多个支持案例。</span><span class="sxs-lookup"><span data-stu-id="08d12-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="08d12-147">一对一：单个源记录与一个目标记录相关。</span><span class="sxs-lookup"><span data-stu-id="08d12-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="08d12-148">示例：单个客户的一个忠诚度 ID。</span><span class="sxs-lookup"><span data-stu-id="08d12-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="08d12-149">使用两个多对一关系和一个连接源实体和目标实体的链接实体，可以创建许多到多关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="08d12-150">**目标基数**：选择目标实体记录的基数。</span><span class="sxs-lookup"><span data-stu-id="08d12-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="08d12-151">**源键字段**：源实体中的外键字段。</span><span class="sxs-lookup"><span data-stu-id="08d12-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="08d12-152">示例：SupportCase 可以使用 CaseID 作为外键字段。</span><span class="sxs-lookup"><span data-stu-id="08d12-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="08d12-153">**目标键字段**：目标实体的键字段。</span><span class="sxs-lookup"><span data-stu-id="08d12-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="08d12-154">示例客户可以使用 **CustomerID** 键字段。</span><span class="sxs-lookup"><span data-stu-id="08d12-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="08d12-155">选择 **保存** 以创建自定义关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="08d12-156">查看视图</span><span class="sxs-lookup"><span data-stu-id="08d12-156">View relationships</span></span>

<span data-ttu-id="08d12-157">“关系”页列出了已创建的所有关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="08d12-158">每行都表示一种关系，其中还包括有关源实体、目标实体和基数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="08d12-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="关系页操作栏中的关系和选项列表。":::

<span data-ttu-id="08d12-160">此页面为现有和新关系提供了一组选项：</span><span class="sxs-lookup"><span data-stu-id="08d12-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="08d12-161">**新关系**：[创建自定义关系](#create-a-custom-relationship)。</span><span class="sxs-lookup"><span data-stu-id="08d12-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="08d12-162">**可视化工具**：[探索关系可视化工具](#explore-the-relationship-visualizer)，查看现有关系及其基数的网络图表。</span><span class="sxs-lookup"><span data-stu-id="08d12-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="08d12-163">**筛选依据**：选择列表中要显示的关系类型。</span><span class="sxs-lookup"><span data-stu-id="08d12-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="08d12-164">**搜索关系**：对关系属性使用基于文本的搜索。</span><span class="sxs-lookup"><span data-stu-id="08d12-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="08d12-165">探索关系可视化工具</span><span class="sxs-lookup"><span data-stu-id="08d12-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="08d12-166">关系可视化工具会显示已连接实体及其基数之间的现有关系的网络图表。</span><span class="sxs-lookup"><span data-stu-id="08d12-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="08d12-167">要自定义视图，您可以通过将框拖到画布上来更改框的位置。</span><span class="sxs-lookup"><span data-stu-id="08d12-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="关系可视化工具网络图的屏幕截图，其中包括相关实体之间的连接。":::

<span data-ttu-id="08d12-169">可用选项：</span><span class="sxs-lookup"><span data-stu-id="08d12-169">Available options:</span></span> 
- <span data-ttu-id="08d12-170">**导出为图像**：将当前视图保存为图像文件。</span><span class="sxs-lookup"><span data-stu-id="08d12-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="08d12-171">**更改为水平/垂直布局**：更改实体和关系的对齐。</span><span class="sxs-lookup"><span data-stu-id="08d12-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="08d12-172">**编辑**：更新编辑窗格中自定义关系的属性并保存更改。</span><span class="sxs-lookup"><span data-stu-id="08d12-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="08d12-173">管理现有关系</span><span class="sxs-lookup"><span data-stu-id="08d12-173">Manage existing relationships</span></span> 

<span data-ttu-id="08d12-174">在“关系”页上，每个关系都由行来表示。</span><span class="sxs-lookup"><span data-stu-id="08d12-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="08d12-175">选择关系并选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="08d12-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="08d12-176">**编辑**：更新编辑窗格中自定义关系的属性并保存更改。</span><span class="sxs-lookup"><span data-stu-id="08d12-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="08d12-177">**删除**：删除自定义关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="08d12-178">**视图**：查看系统创建和继承的关系。</span><span class="sxs-lookup"><span data-stu-id="08d12-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="08d12-179">下一步</span><span class="sxs-lookup"><span data-stu-id="08d12-179">Next step</span></span>

<span data-ttu-id="08d12-180">系统关系和自定义关系用于基于多个数据源[创建不再分散的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="08d12-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
