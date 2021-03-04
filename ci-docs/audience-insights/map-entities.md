---
title: 映射数据统一的实体
description: 映射数据以创建统一客户配置文件。
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267024"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="466ce-103">映射实体和属性</span><span class="sxs-lookup"><span data-stu-id="466ce-103">Map entities and attributes</span></span>

<span data-ttu-id="466ce-104">**映射** 是访问群体见解的数据统一流程中的第一阶段。</span><span class="sxs-lookup"><span data-stu-id="466ce-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="466ce-105">映射包含三个阶段：</span><span class="sxs-lookup"><span data-stu-id="466ce-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="466ce-106">*选择实体*：确定将生成包含有关客户的更完整信息的数据集的可合并实体。</span><span class="sxs-lookup"><span data-stu-id="466ce-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="466ce-107">*选择属性*：为每个实体确定要在 *匹配* 和 *合并* 阶段合并和协调的列。</span><span class="sxs-lookup"><span data-stu-id="466ce-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="466ce-108">这些列称为 *属性*。</span><span class="sxs-lookup"><span data-stu-id="466ce-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="466ce-109">*主键和语义类型选择*：对于每个实体，确定要定义为该实体的主键的属性，对于每个属性，确定最能描述该属性的语义类型。</span><span class="sxs-lookup"><span data-stu-id="466ce-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="466ce-110">有关一般的数据统一流程的详细信息，请参阅[统一](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="466ce-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="466ce-111">选择第一个实体</span><span class="sxs-lookup"><span data-stu-id="466ce-111">Select the first entities</span></span>

1. <span data-ttu-id="466ce-112">在访问群体见解中，转到 **数据** > **统一** > **映射**。</span><span class="sxs-lookup"><span data-stu-id="466ce-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="466ce-113">通过选择 **选择实体** 开始执行映射阶段。</span><span class="sxs-lookup"><span data-stu-id="466ce-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="466ce-114">选择要在 *匹配* 和 *合并* 阶段使用的实体和属性。</span><span class="sxs-lookup"><span data-stu-id="466ce-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="466ce-115">您可以通过选择实体级别的 **包括所有字段** 复选框，从实体中单独选择所需的属性，或包含实体中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="466ce-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="466ce-116">建议至少选择两个实体，以便利用数据统一过程。</span><span class="sxs-lookup"><span data-stu-id="466ce-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="466ce-117">![添加实体示例](media/data-manager-configure-map-add-entities-example.png "添加实体示例")</span><span class="sxs-lookup"><span data-stu-id="466ce-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="466ce-118">在此示例中，我们要添加 **eCommerceContacts** 和 **loyCustomers** 实体。</span><span class="sxs-lookup"><span data-stu-id="466ce-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="466ce-119">通过选择这些实体，您可以得出有关哪些在线业务客户是忠诚度计划成员的见解。</span><span class="sxs-lookup"><span data-stu-id="466ce-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="466ce-120">您可以在所有属性和实体中搜索关键字，来选择要映射的所需属性。</span><span class="sxs-lookup"><span data-stu-id="466ce-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="466ce-121">![搜索字段示例](media/data-manager-configure-map-search-fields-example.png "搜索字段示例")</span><span class="sxs-lookup"><span data-stu-id="466ce-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="466ce-122">选择 **应用** 确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="466ce-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="466ce-123">为属性选择主键和语义类型</span><span class="sxs-lookup"><span data-stu-id="466ce-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="466ce-124">选择实体后，**映射** 页将列出所选实体，供您查看。</span><span class="sxs-lookup"><span data-stu-id="466ce-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="466ce-125">定义实体的主键并确定实体中属性的语义类型。</span><span class="sxs-lookup"><span data-stu-id="466ce-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="466ce-126">**主键**：为每个实体选择一个属性作为主键。</span><span class="sxs-lookup"><span data-stu-id="466ce-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="466ce-127">若要使属性成为有效主键，它不应包括重复值、缺少值或 null 值。</span><span class="sxs-lookup"><span data-stu-id="466ce-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="466ce-128">字符串、整数和 GUID 数据类型属性被作为主键支持，将显示在一个字段中供您选择。</span><span class="sxs-lookup"><span data-stu-id="466ce-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="466ce-129">**属性语义类型**：属性的类别，如电子邮件地址或姓名。</span><span class="sxs-lookup"><span data-stu-id="466ce-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="466ce-130">要将 AI 模型用于语义智能预测，节省时间并提高准确性，请将 **智能映射** 设置为 **开**。</span><span class="sxs-lookup"><span data-stu-id="466ce-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="466ce-131">智能映射在 **类型** 字段中突出显示基于 AI 的语义建议。</span><span class="sxs-lookup"><span data-stu-id="466ce-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="466ce-132">如果将其设置为 **关**，您将看到我们的常规映射建议。</span><span class="sxs-lookup"><span data-stu-id="466ce-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="466ce-133">您可以从可用的选项列表中选择任意一种语义类型，来替代建议的选择。</span><span class="sxs-lookup"><span data-stu-id="466ce-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="466ce-134">![属性类型和语义预测](media/data-manager-configure-map-add-attributes-semantic-prediction.png "属性类型和语义预测")</span><span class="sxs-lookup"><span data-stu-id="466ce-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="466ce-135">还可以添加自定义语义类型。</span><span class="sxs-lookup"><span data-stu-id="466ce-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="466ce-136">选择属性的类型字段，然后键入自定义语义类型名称。</span><span class="sxs-lookup"><span data-stu-id="466ce-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="466ce-137">这样，您还可以更改系统确定的属性类型。</span><span class="sxs-lookup"><span data-stu-id="466ce-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="466ce-138">将自动识别其语义类型的所有属性都在 **查看映射字段** 部分分组。</span><span class="sxs-lookup"><span data-stu-id="466ce-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="466ce-139">查看这些属性及其语义类型，因为它们将用于在数据统一的合并步骤中合并您的实体。</span><span class="sxs-lookup"><span data-stu-id="466ce-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="466ce-140">不会自动映射到语义类型的属性在 **在未映射字段中定义数据** 部分进行分组。</span><span class="sxs-lookup"><span data-stu-id="466ce-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="466ce-141">选择未映射属性的语义类型字段，或输入您的自定义属性类型名称。</span><span class="sxs-lookup"><span data-stu-id="466ce-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="466ce-142">![主键和属性类型](media/data-manager-configure-map-add-attributes.png "主键和属性类型")</span><span class="sxs-lookup"><span data-stu-id="466ce-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="466ce-143">应将一个字段映射到语义类型 Person. FullName 以填充客户卡中的客户名称。</span><span class="sxs-lookup"><span data-stu-id="466ce-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="466ce-144">否则，客户卡将显示为无名称。</span><span class="sxs-lookup"><span data-stu-id="466ce-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="466ce-145">添加和删除属性和实体</span><span class="sxs-lookup"><span data-stu-id="466ce-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="466ce-146">在 **统一** > **映射** 中，选择 **编辑字段**。</span><span class="sxs-lookup"><span data-stu-id="466ce-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="466ce-147">在 **编辑字段** 窗格中，添加或删除属性和实体。</span><span class="sxs-lookup"><span data-stu-id="466ce-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="466ce-148">使用搜索或滚动查找和选择您感兴趣的属性和实体。</span><span class="sxs-lookup"><span data-stu-id="466ce-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="466ce-149">如果属性或实体已经匹配，则无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="466ce-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="466ce-150">![添加或删除属性](media/configure-data-map-edit.png "添加或删除属性")</span><span class="sxs-lookup"><span data-stu-id="466ce-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="466ce-151">选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="466ce-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="466ce-152">向配置文件添加图像</span><span class="sxs-lookup"><span data-stu-id="466ce-152">Add images to profiles</span></span>

<span data-ttu-id="466ce-153">如果实体中包含 URL 以公开发布配置文件图像或徽标，可以将其添加到统一客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="466ce-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="466ce-154">选择实体并查找其中包含配置文件图像的 URL 的字段。</span><span class="sxs-lookup"><span data-stu-id="466ce-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="466ce-155">在 **类型** 输入字段中，手动输入以下值：</span><span class="sxs-lookup"><span data-stu-id="466ce-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="466ce-156">对于个人：Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="466ce-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="466ce-157">对于组织：Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="466ce-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="466ce-158">继续执行统一步骤，并确保在[合并](merge-entities.md)步骤中也添加了包含图像 URL 的属性。</span><span class="sxs-lookup"><span data-stu-id="466ce-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="466ce-159">设置组织的属性</span><span class="sxs-lookup"><span data-stu-id="466ce-159">Set attributes for organizations</span></span>

<span data-ttu-id="466ce-160">对于组织（预览），属性类型应该映射到“Organization.Name”</span><span class="sxs-lookup"><span data-stu-id="466ce-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="466ce-161">![主键和属性类型 B2B](media/configure-data-map-edit-b2b.png "主键和属性类型 B2B")</span><span class="sxs-lookup"><span data-stu-id="466ce-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="466ce-162">下一步</span><span class="sxs-lookup"><span data-stu-id="466ce-162">Next step</span></span>

<span data-ttu-id="466ce-163">在数据统一过程中，转到 **匹配** 页。</span><span class="sxs-lookup"><span data-stu-id="466ce-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="466ce-164">访问 [**匹配**](match-entities.md)以了解此阶段。</span><span class="sxs-lookup"><span data-stu-id="466ce-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="466ce-165">观看以下视频：[入门：创建统一的客户配置文件](https://youtu.be/oBfGEhucAxs)。</span><span class="sxs-lookup"><span data-stu-id="466ce-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]