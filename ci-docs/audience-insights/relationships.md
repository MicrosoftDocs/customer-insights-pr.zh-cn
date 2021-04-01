---
title: 实体和实体路径之间的关系
description: 创建和管理来自多个数据源的实体之间的关系。
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595201"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="1cc84-103">实体之间的关系</span><span class="sxs-lookup"><span data-stu-id="1cc84-103">Relationships between entities</span></span>

<span data-ttu-id="1cc84-104">当实体共用可在实体之间引用的通用标识（外键）时，关系可帮助您连接实体和生成数据图。</span><span class="sxs-lookup"><span data-stu-id="1cc84-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="1cc84-105">可通过连接的实体基于多个数据源定义细分和度量。</span><span class="sxs-lookup"><span data-stu-id="1cc84-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="1cc84-106">关系有两种。</span><span class="sxs-lookup"><span data-stu-id="1cc84-106">There are two types of relationships.</span></span> <span data-ttu-id="1cc84-107">不可编辑系统关系（这是自动创建的），以及用户创建和配置的自定义关系。</span><span class="sxs-lookup"><span data-stu-id="1cc84-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="1cc84-108">匹配和合并过程中，将基于智能匹配在后台创建系统关系。</span><span class="sxs-lookup"><span data-stu-id="1cc84-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="1cc84-109">这些关系可以帮助将客户配置文件记录与其他相应实体的记录关联。</span><span class="sxs-lookup"><span data-stu-id="1cc84-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="1cc84-110">下图演示当客户实体与更多实体匹配以生成最终客户配置文件实体时，创建三个系统关系。</span><span class="sxs-lookup"><span data-stu-id="1cc84-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cc84-111">![关系创建](media/relationships-entities-merge.png "关系创建")</span><span class="sxs-lookup"><span data-stu-id="1cc84-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="1cc84-112">创建了客户实体与联系人实体之间的 ***CustomerToContact* 关系**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="1cc84-113">客户实体获取了键字段 **Contact_contactId**，以便关联到联系人实体键字段 **contactId**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="1cc84-114">创建了客户实体与帐户实体之间的 ***CustomerToAccount* 关系**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="1cc84-115">客户实体获取了键字段 **Account_accountId**，以便关联到帐户实体键字段 **accountId**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="1cc84-116">创建了客户实体与 WebAccount 实体之间的 ***CustomerToWebAccount* 关系**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="1cc84-117">客户实体获取了键字段 **WebAccount_webaccountId**，以便关联到 WebAccount 实体键字段 **webaccountId**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="1cc84-118">创建关系</span><span class="sxs-lookup"><span data-stu-id="1cc84-118">Create a relationship</span></span>

<span data-ttu-id="1cc84-119">自定义关系在 **关系** 页中定义。</span><span class="sxs-lookup"><span data-stu-id="1cc84-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="1cc84-120">每个关系包含一个源实体（该实体中包含外键）和一个目标实体（这是源实体的外键指向的实体）。</span><span class="sxs-lookup"><span data-stu-id="1cc84-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="1cc84-121">在访问群体见解中，转到 **数据** > **关系**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1cc84-122">选择 **新建关系**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="1cc84-123">在 **添加关系** 窗格中，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="1cc84-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1cc84-124">![输入关系详细信息](media/relationships-add.png "输入关系详细信息")</span><span class="sxs-lookup"><span data-stu-id="1cc84-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="1cc84-125">**关系名称**：用于体现关系用途的名称（例如，**AccountWebLogs**）。</span><span class="sxs-lookup"><span data-stu-id="1cc84-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="1cc84-126">**说明**：关系的说明。</span><span class="sxs-lookup"><span data-stu-id="1cc84-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="1cc84-127">**源实体**：选择用作关系中的源的实体（例如，WebLog）。</span><span class="sxs-lookup"><span data-stu-id="1cc84-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="1cc84-128">**基数**：选择源实体记录的基数。</span><span class="sxs-lookup"><span data-stu-id="1cc84-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="1cc84-129">例如，“大量”表示多个 Weblog 记录与一个 WebAccount 关联。</span><span class="sxs-lookup"><span data-stu-id="1cc84-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="1cc84-130">**源键字段**：表示源实体中的外键字段。</span><span class="sxs-lookup"><span data-stu-id="1cc84-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="1cc84-131">例如，WebLog 的外键字段为 **accountId**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="1cc84-132">**目标实体**：选择用作关系中的目标的实体（例如，WebAccount）。</span><span class="sxs-lookup"><span data-stu-id="1cc84-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="1cc84-133">**目标基数**：选择目标实体记录的基数。</span><span class="sxs-lookup"><span data-stu-id="1cc84-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="1cc84-134">例如，“一个”表示多个 Weblog 记录与一个 WebAccount 关联。</span><span class="sxs-lookup"><span data-stu-id="1cc84-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="1cc84-135">**目标键字段**：此字段表示目标实体的键字段。</span><span class="sxs-lookup"><span data-stu-id="1cc84-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="1cc84-136">例如，WebAccount 的键字段为 **accountId**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="1cc84-137">仅支持多对一和一对一关系。</span><span class="sxs-lookup"><span data-stu-id="1cc84-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="1cc84-138">可以使用两个多对一关系和一个链接实体（用于连接源实体和目标实体的实体）创建多对多关系。</span><span class="sxs-lookup"><span data-stu-id="1cc84-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="1cc84-139">删除关系</span><span class="sxs-lookup"><span data-stu-id="1cc84-139">Delete a relationship</span></span>

1. <span data-ttu-id="1cc84-140">在访问群体见解中，转到 **数据** > **关系**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1cc84-141">选中要删除的关系的复选框。</span><span class="sxs-lookup"><span data-stu-id="1cc84-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="1cc84-142">选择 **关系** 表顶部的 **删除**。</span><span class="sxs-lookup"><span data-stu-id="1cc84-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="1cc84-143">确认删除。</span><span class="sxs-lookup"><span data-stu-id="1cc84-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="1cc84-144">下一步</span><span class="sxs-lookup"><span data-stu-id="1cc84-144">Next step</span></span>

<span data-ttu-id="1cc84-145">系统关系和自定义关系用于基于多个数据源创建不再分散的细分。</span><span class="sxs-lookup"><span data-stu-id="1cc84-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="1cc84-146">有关详细信息，请参阅[细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc84-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]