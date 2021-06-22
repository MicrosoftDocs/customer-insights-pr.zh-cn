---
title: 新功能和未来的功能
description: 有关新功能、改进和 Bug 修复的信息。
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 355dc22ac381145b231848830cefc47eda7968f4
ms.sourcegitcommit: 6944c1592877eb92ec789df5f2e0dbecef638837
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "6263240"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="10f6f-103">Dynamics 365 Customer Insights 的访问群体见解功能中的新增功能</span><span class="sxs-lookup"><span data-stu-id="10f6f-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="10f6f-104">我们非常激动地发布我们的最新更新！</span><span class="sxs-lookup"><span data-stu-id="10f6f-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="10f6f-105">本文总结了公开预览功能、正式发布版本的增强和功能更新。</span><span class="sxs-lookup"><span data-stu-id="10f6f-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="10f6f-106">若要查看长期功能计划，请参阅 [Dynamics 365 和 Power Platform 发行计划](/dynamics365/release-plans/)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](/dynamics365/release-plans/).</span></span>

<span data-ttu-id="10f6f-107">我们将按地区推出更新。</span><span class="sxs-lookup"><span data-stu-id="10f6f-107">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="10f6f-108">因此，某些地区可能先于其他地区看到功能。</span><span class="sxs-lookup"><span data-stu-id="10f6f-108">So certain regions might see features before others.</span></span> <span data-ttu-id="10f6f-109">除非另行指定，否则您无需执行任何操作，我们会自动更新应用，无需停机。</span><span class="sxs-lookup"><span data-stu-id="10f6f-109">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="10f6f-110">若要提交功能请求和产品建议及投票，请访问 [Dynamics 365 应用程序意见门户](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-110">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="may-2021-updates"></a><span data-ttu-id="10f6f-111">2021 年 5 月更新</span><span class="sxs-lookup"><span data-stu-id="10f6f-111">May 2021 updates</span></span>

<span data-ttu-id="10f6f-112">2021 年 5 月中的更新包括多项功能、性能升级和错误修复。</span><span class="sxs-lookup"><span data-stu-id="10f6f-112">The updates in May 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="data-ingestion"></a><span data-ttu-id="10f6f-113">数据引入</span><span class="sxs-lookup"><span data-stu-id="10f6f-113">Data ingestion</span></span>

- <span data-ttu-id="10f6f-114">**在附加 Azure Data Lake Storage 中的数据时查看或修改元数据或实体定义** 在 Azure Data Lake Storage 中附加 Common Data Model 文件夹中的数据时，现在可以在访问群体见解中查看和编辑元数据或实体定义。</span><span class="sxs-lookup"><span data-stu-id="10f6f-114">**View or modify metadata or entity definition when attaching data from your Azure Data Lake Storage** You can now view and edit metadata or entity definition in audience insights when attaching data from a Common Data Model folder in your Azure Data Lake Storage.</span></span> <span data-ttu-id="10f6f-115">此功能会提供实时反馈、模型验证和错误检查。</span><span class="sxs-lookup"><span data-stu-id="10f6f-115">This capability provides real-time feedback, model validation, and error checking.</span></span> <span data-ttu-id="10f6f-116">它允许您无缝编辑 model.json 和 manifest.json。</span><span class="sxs-lookup"><span data-stu-id="10f6f-116">It allows you to edit both model.json and manifest.json seamlessly.</span></span>

### <a name="extensibility"></a><span data-ttu-id="10f6f-117">扩展性</span><span class="sxs-lookup"><span data-stu-id="10f6f-117">Extensibility</span></span>

- <span data-ttu-id="10f6f-118">**改进了客户细分导出、自定义计划和重复** 您现在可以在列表中[查看特定客户细分的所有导出](export-destinations.md#view-exports-and-export-details)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-118">**Improved segment exports, custom schedule, and duplication** You can now [see all exports for a specific segment](export-destinations.md#view-exports-and-export-details) in a list.</span></span> <span data-ttu-id="10f6f-119">此新视图有助于管理特定客户细分的使用方式，并调整现有导出或创建新导出。</span><span class="sxs-lookup"><span data-stu-id="10f6f-119">This new view helps to manage how a specific segment is used and adapt existing or create new exports.</span></span>    
  <span data-ttu-id="10f6f-120">您可以同时为个别导出或多个导出[定义自定义刷新计划](export-destinations.md#schedule-and-run-exports)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-120">You can [define custom refresh schedules](export-destinations.md#schedule-and-run-exports) for individual exports or several exports at once.</span></span> <span data-ttu-id="10f6f-121">到目前为止，每次系统刷新时都会运行所有导出。</span><span class="sxs-lookup"><span data-stu-id="10f6f-121">Until now, all exports were run with every system refresh.</span></span>    
  <span data-ttu-id="10f6f-122">与其从头开始创建新的导出，不如从现有导出开始创建，这样可以节省一些时间。</span><span class="sxs-lookup"><span data-stu-id="10f6f-122">Rather than creating a new export from scratch, you can start based on an existing one to save some time.</span></span>

- <span data-ttu-id="10f6f-123">**将客户细分导出到 Microsoft Advertising** 我们已扩展导出目的地，以包括 Microsoft Advertising。</span><span class="sxs-lookup"><span data-stu-id="10f6f-123">**Export segments to Microsoft Advertising** We have extended our export destinations to include Microsoft Advertising.</span></span> <span data-ttu-id="10f6f-124">使用统一客户配置文件数据在 Microsoft Advertising 上创建客户匹配访问群体，并将这些访问群体用于广告市场活动。</span><span class="sxs-lookup"><span data-stu-id="10f6f-124">Create Customer Match audiences on Microsoft Advertising with your unified customer profile data and use these audiences for your advertising campaigns.</span></span> <span data-ttu-id="10f6f-125">有关更多信息，请参阅[将客户细分导出到 Microsoft Advertising](export-microsoft-advertising.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-125">For more information, see [Export segments to Microsoft Advertising](export-microsoft-advertising.md).</span></span>

- <span data-ttu-id="10f6f-126">**将客户细分导出到 LinkedIn Ads** 我们已扩展导出目标，以包括 LinkedIn Ads，并通过出口统一客户配置文件数据，使您能够通过 LinkedIn 解锁“确定目标联系人”和“确定目标公司”。</span><span class="sxs-lookup"><span data-stu-id="10f6f-126">**Export segments to LinkedIn Ads** We have extended our export destinations to include LinkedIn Ads and enable you to unlock Contact Targeting as well as Company Targeting through LinkedIn by exporting your unified customer profile data.</span></span> <span data-ttu-id="10f6f-127">有关更多信息，请参阅[将客户细分导出到 LinkedIn Ads](export-linkedin-ads.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-127">For more information, see [Export segments to LinkedIn Ads](export-linkedin-ads.md).</span></span>


- <span data-ttu-id="10f6f-128">**将客户细分导出到 Omnisend** 我们已扩展导出目标，以包括 Omnisend。</span><span class="sxs-lookup"><span data-stu-id="10f6f-128">**Export segments to Omnisend** We have extended our export destinations to include Omnisend.</span></span> <span data-ttu-id="10f6f-129">使用在访问群体见解中创建的客户细分来生成市场活动，提供电子邮件市场营销材料，并通过 Omnisend 使用特定客户组。</span><span class="sxs-lookup"><span data-stu-id="10f6f-129">Use the segments created in audience insights to generate campaigns, provide email marketing, and use specific groups of customers with Omnisend.</span></span> <span data-ttu-id="10f6f-130">有关更多信息，请参阅[将客户细分导出到 Omnisend](export-omnisend.md)</span><span class="sxs-lookup"><span data-stu-id="10f6f-130">For more information, see [Export segments to Omnisend](export-omnisend.md)</span></span>

### <a name="predictions"></a><span data-ttu-id="10f6f-131">预测</span><span class="sxs-lookup"><span data-stu-id="10f6f-131">Predictions</span></span>

- <span data-ttu-id="10f6f-132">**输入数据可用性报表** 输入数据可用性报表提供了现成预测可能会产生的错误和警告的综合视图。</span><span class="sxs-lookup"><span data-stu-id="10f6f-132">**Input Data Usability Report** The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="10f6f-133">它还就如何提高模型性能提出了建议。</span><span class="sxs-lookup"><span data-stu-id="10f6f-133">It also gives recommendations how to improve the model performance.</span></span>    
  <span data-ttu-id="10f6f-134">该报表在模型完成训练过程后可用。</span><span class="sxs-lookup"><span data-stu-id="10f6f-134">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="10f6f-135">无论是否成功完成，系统都将单独为每个模型创建此报表。</span><span class="sxs-lookup"><span data-stu-id="10f6f-135">It's created for each model separately, regardless of whether it completed successfully or not.</span></span>
  <span data-ttu-id="10f6f-136">目前，此功能仅适用于交易流失模型。</span><span class="sxs-lookup"><span data-stu-id="10f6f-136">Currently, this feature is only available for the Transaction Churn model.</span></span> <span data-ttu-id="10f6f-137">有关更多信息，请参阅[输入数据可用性报表](manage-predictions.md#input-data-usability-report)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-137">For more information, see [Input data usability report](manage-predictions.md#input-data-usability-report).</span></span>

### <a name="relationships"></a><span data-ttu-id="10f6f-138">关系</span><span class="sxs-lookup"><span data-stu-id="10f6f-138">Relationships</span></span>

- <span data-ttu-id="10f6f-139">**关系可视化工具** 利用关系可视化工具视图，您可以查看实体与其基数之间的所有现有关系。</span><span class="sxs-lookup"><span data-stu-id="10f6f-139">**Relationship visualizer** The relationship visualizer view allows you to see all existing relationships between entities and their cardinality.</span></span> <span data-ttu-id="10f6f-140">现在按组来组织关系：用户创建、系统和继承关系。</span><span class="sxs-lookup"><span data-stu-id="10f6f-140">Relationships are now organized in groups: user created, system, and inherited relationships.</span></span> <span data-ttu-id="10f6f-141">您还可以将视图导出为图像。</span><span class="sxs-lookup"><span data-stu-id="10f6f-141">You can also export a view as an image.</span></span> <span data-ttu-id="10f6f-142">有关详细信息，请参阅[查看关系](relationships.md#view-relationships)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-142">For more information, see [View relationships](relationships.md#view-relationships).</span></span> 

## <a name="april-2021-updates"></a><span data-ttu-id="10f6f-143">2021 年 4 月更新</span><span class="sxs-lookup"><span data-stu-id="10f6f-143">April 2021 updates</span></span>

<span data-ttu-id="10f6f-144">2021 年 4 月中的更新包括多项功能、性能升级和错误修复。</span><span class="sxs-lookup"><span data-stu-id="10f6f-144">The updates in April 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="data-unification"></a><span data-ttu-id="10f6f-145">数据统一</span><span class="sxs-lookup"><span data-stu-id="10f6f-145">Data unification</span></span>
 
- <span data-ttu-id="10f6f-146">**增强的数据统一合并体验**</span><span class="sxs-lookup"><span data-stu-id="10f6f-146">**Enhanced merge experience for data unification**</span></span>    
  
   <span data-ttu-id="10f6f-147">现在，我们在数据统一过程的合并配置中增强了用户体验。</span><span class="sxs-lookup"><span data-stu-id="10f6f-147">We now have an enhanced user experience in the merge configuration of the data unification process.</span></span> <span data-ttu-id="10f6f-148">这些更改包括直观排序合并字段以及合并和单一字段的详细统计信息。</span><span class="sxs-lookup"><span data-stu-id="10f6f-148">The changes include intuitive ordering of the merged fields and detailed statistics on combined and singleton fields.</span></span>

- <span data-ttu-id="10f6f-149">**实体重新排序并将所有源记录配置到客户实体中**</span><span class="sxs-lookup"><span data-stu-id="10f6f-149">**Entity reordering and configure all source records into the Customer entity**</span></span>  
      
   <span data-ttu-id="10f6f-150">现在，您可以在数据统一过程中重新排序和删除现有实施规划中的实体。</span><span class="sxs-lookup"><span data-stu-id="10f6f-150">You can now reorder and remove entities from an existing conflation plan in the data unification process.</span></span> <span data-ttu-id="10f6f-151">系统提供了根据业务需求在匹配过程中对实体进行重新排序的灵活性。</span><span class="sxs-lookup"><span data-stu-id="10f6f-151">It gives flexibility to reorder the entities in the match process according to business needs.</span></span> <span data-ttu-id="10f6f-152">此外，我们允许将所有不匹配的记录包括到最终 *客户* 实体中，这使他们可以进行客户配置文件数据集定义。</span><span class="sxs-lookup"><span data-stu-id="10f6f-152">Additionally, we enable include all non-matched records into the final *Customer* entity, which lets them define their customer profile dataset definition.</span></span>

### <a name="enrichments"></a><span data-ttu-id="10f6f-153">扩充</span><span class="sxs-lookup"><span data-stu-id="10f6f-153">Enrichments</span></span>

 - <span data-ttu-id="10f6f-154">**新扩充：增强型地址**</span><span class="sxs-lookup"><span data-stu-id="10f6f-154">**New enrichment: Enhanced addresses**</span></span>    
  
   <span data-ttu-id="10f6f-155">我们很高兴推出用于增强客户数据中的地址的新扩充功能。</span><span class="sxs-lookup"><span data-stu-id="10f6f-155">We're excited to introduce a new enrichment to enhance addresses in your customer data.</span></span> <span data-ttu-id="10f6f-156">数据中的地址可能无结构、不完整或不正确。</span><span class="sxs-lookup"><span data-stu-id="10f6f-156">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="10f6f-157">此功能使用 Microsoft 的模型按 Common Data Model 格式标准化并扩充您的地址，以获得更佳的准确性和见解。</span><span class="sxs-lookup"><span data-stu-id="10f6f-157">This feature uses Microsoft's models to normalize and enrich your addresses into the Common Data Model format for better accuracy and insights.</span></span>
 
   <span data-ttu-id="10f6f-158">有关详细信息，请参阅[使用增强的地址扩充客户配置文件](enrichment-enhanced-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-158">For more information, see [Enrichment of customer profiles with enhanced addresses](enrichment-enhanced-addresses.md).</span></span>

- <span data-ttu-id="10f6f-159">**扩充的引导式配置体验**</span><span class="sxs-lookup"><span data-stu-id="10f6f-159">**Guided configuration experience for enrichments**</span></span>    
  
   <span data-ttu-id="10f6f-160">我们用简单的引导式体验重新感受了扩充的配置体验。</span><span class="sxs-lookup"><span data-stu-id="10f6f-160">We revisited the configuration experience for enrichments with a simple, guided experience.</span></span> <span data-ttu-id="10f6f-161">现在，您具有一个用于创建和编辑扩充的清晰分步流程。</span><span class="sxs-lookup"><span data-stu-id="10f6f-161">You now have a clear step-by-step process for creating and editing enrichments.</span></span>
 
   <span data-ttu-id="10f6f-162">此外，我们分离了第三方扩充功能的连接配置，以使多个扩充功能可以使用同一连接。</span><span class="sxs-lookup"><span data-stu-id="10f6f-162">Additionally, we separated the configuration of connections for third-party enrichments to enable the same connection to be used by multiple enrichments.</span></span> <span data-ttu-id="10f6f-163">只有管理员才能配置新的连接，但创建的连接可供管理员和参与者使用。</span><span class="sxs-lookup"><span data-stu-id="10f6f-163">Only administrators can configure new connections, but the created connections are available to both administrators and contributors.</span></span>    

   <span data-ttu-id="10f6f-164">有关详细信息，请参阅[连接概述](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-164">For more information, see [Connections overview](connections.md).</span></span>

- <span data-ttu-id="10f6f-165">**相同类型的多项扩充**</span><span class="sxs-lookup"><span data-stu-id="10f6f-165">**Multiple enrichments of the same type**</span></span>    
  
   <span data-ttu-id="10f6f-166">现在，我们允许用户创建和管理相同扩充类型的多个扩充。</span><span class="sxs-lookup"><span data-stu-id="10f6f-166">We now allow users to create and manage multiple enrichments of the same enrichment type.</span></span> <span data-ttu-id="10f6f-167">例如，您现在可以创建两个单独的地址扩充，以扩充两个不同的客户细分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-167">For example, you can now create two separate address enrichments to enrich two different customer segments.</span></span> <span data-ttu-id="10f6f-168">关于可以创建多少个相同类型的扩充，具有一些限制，具体取决于扩充类型。</span><span class="sxs-lookup"><span data-stu-id="10f6f-168">Limits apply on how many enrichments of the same type can be created and vary depending on the enrichment type.</span></span>
  
   <span data-ttu-id="10f6f-169">有关详细信息，请参阅[客户资料扩充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-169">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

## <a name="march-2021-updates"></a><span data-ttu-id="10f6f-170">2021 年 3 月更新</span><span class="sxs-lookup"><span data-stu-id="10f6f-170">March 2021 updates</span></span>

<span data-ttu-id="10f6f-171">2021 年 3 月中的更新包括多项功能、性能升级和错误修复。</span><span class="sxs-lookup"><span data-stu-id="10f6f-171">The updates in March 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="activities"></a><span data-ttu-id="10f6f-172">活动</span><span class="sxs-lookup"><span data-stu-id="10f6f-172">Activities</span></span>

- <span data-ttu-id="10f6f-173">**活动向导和语义类型**</span><span class="sxs-lookup"><span data-stu-id="10f6f-173">**Activity wizard and semantic types**</span></span>

   <span data-ttu-id="10f6f-174">我们改进和更新了活动映射体验，以指导和简化活动映射的创建过程。</span><span class="sxs-lookup"><span data-stu-id="10f6f-174">We have improved and updated our activity mapping experience to guide and simplify the creation of activity mapping.</span></span> <span data-ttu-id="10f6f-175">在这种新体验中，用户将获得引导式体验，以帮助完成流程的每一步。</span><span class="sxs-lookup"><span data-stu-id="10f6f-175">In this new experience, users get a guided experience to help completing of each step of the process.</span></span> <span data-ttu-id="10f6f-176">在活动映射步骤中，除了从许多活动类型中进行选择外，用户还可以选择在语义上将 *订阅* 和/或 *SalesOrderLine* 的数据映射到行业标准架构，这些架构可用于下游消费。</span><span class="sxs-lookup"><span data-stu-id="10f6f-176">At the activity mapping step, in addition to choosing from many activity types, the user can choose to semantically map data for *Subscription* and/or *SalesOrderLine* to industry standard schemas, which can be used for downstream consumption.</span></span>   

   <span data-ttu-id="10f6f-177">有关详细信息，请参阅[自定义活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-177">For more information, see [Customer activities](activities.md).</span></span>

### <a name="data-ingestion"></a><span data-ttu-id="10f6f-178">数据引入</span><span class="sxs-lookup"><span data-stu-id="10f6f-178">Data ingestion</span></span>

- <span data-ttu-id="10f6f-179">**使用 Power Platform 数据流和网关连接到本地数据源** 我们很高兴地宣布将使用 Customer Insights 中的网关以及关联的 Power Platform 或 Dataverse 环境来预览 Power Platform 数据流和本地连接。</span><span class="sxs-lookup"><span data-stu-id="10f6f-179">**Connect to on-premises data sources using Power Platform dataflows and gateways** We are pleased to announce the preview of Power Platform dataflows and on-premises connectivity using gateways in Customer Insights with an associated Power Platform or Dataverse environment.</span></span> <span data-ttu-id="10f6f-180">在具有链接的 Dataverse 环境的 Customer Insights 环境中创建的任何新数据源都将默认为 Power Platform 数据流，此数据流将引入本地数据连接以及一组丰富的连接器和转换功能。</span><span class="sxs-lookup"><span data-stu-id="10f6f-180">Any new data sources created in a Customer Insights environment with a linked Dataverse environment will default to Power Platform dataflows bringing in the on-premises data connectivity and a rich set of connectors and transformation capabilities.</span></span>

### <a name="extensibility"></a><span data-ttu-id="10f6f-181">扩展性</span><span class="sxs-lookup"><span data-stu-id="10f6f-181">Extensibility</span></span>

- <span data-ttu-id="10f6f-182">**在连接和导出中组织的导出** 我们已将 **导出目标** 页面的名称更改为 **连接**，并添加了单独的 **导出** 页面。</span><span class="sxs-lookup"><span data-stu-id="10f6f-182">**Exports organized in connections and exports** We have changed the name of the **Export destinations** page to **Connections** and added a separate page for **Exports**.</span></span> <span data-ttu-id="10f6f-183">在此更新过程中，我们会将现有的导出转换为连接和导出（使用该连接）对。</span><span class="sxs-lookup"><span data-stu-id="10f6f-183">As part of this update, we'll transition existing exports into pairs of a connection and an export using that connection.</span></span> <span data-ttu-id="10f6f-184">管理员现在可以在 **连接** 页面上更清晰地了解传出数据。</span><span class="sxs-lookup"><span data-stu-id="10f6f-184">Administrators now have more clarity over outgoing data on the **Connections** page.</span></span> <span data-ttu-id="10f6f-185">所有用户角色都有权访问 **导出** 页面，但只有管理员可以选择允许参与者使用共享连接编辑特定的导出。</span><span class="sxs-lookup"><span data-stu-id="10f6f-185">All user roles have access to the **Exports** page, but only administrators can choose to allow contributors to edit specific exports with shared connections.</span></span>     
  <span data-ttu-id="10f6f-186">有关更多信息，请参阅[连接概述](connections.md)和[导出概述](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-186">For more information, see [Connections overview](connections.md) and [Exports overview](export-destinations.md).</span></span>

- <span data-ttu-id="10f6f-187">**将客户细分导出到 Campaign Monitor** 我们已扩展导出目标，以包括 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="10f6f-187">**Export segments to Campaign Monitor** We have extended our export destinations to include Campaign Monitor.</span></span> <span data-ttu-id="10f6f-188">现在，您可以将客户细分从 Customer Insights 导出到 Campaign Monitor列表，并将其用作市场营销活动的基线。</span><span class="sxs-lookup"><span data-stu-id="10f6f-188">You can now export segments from Customer Insights to Campaign Monitor lists and use them as the baseline for your marketing campaigns.</span></span>    
   <span data-ttu-id="10f6f-189">有关详细信息，请参阅[将数据导出至 Campaign Monitor](export-campaign-monitor.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-189">For more information, see [Export to Campaign Monitor](export-campaign-monitor.md).</span></span>

- <span data-ttu-id="10f6f-190">**将客户细分导出到 Constant Contact** 我们已扩展导出目标，以包括 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="10f6f-190">**Export segments to Constant Contact** We have extended our export destinations to include Constant Contact.</span></span> <span data-ttu-id="10f6f-191">现在，您可以将客户细分从 Customer Insights 导出到 Constant Contact 列表，并将其用作市场营销活动的基线。</span><span class="sxs-lookup"><span data-stu-id="10f6f-191">You can now export segments from Customer Insights to Constant Contact lists and use them as the baseline for your marketing campaigns.</span></span>   
   <span data-ttu-id="10f6f-192">有关详细信息，请参阅[将数据导出至 Constant Contact](export-constant-contact.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-192">For more information, see [Export to Constant Contact](export-constant-contact.md).</span></span>

- <span data-ttu-id="10f6f-193">**将客户细分导出到 RollWorks** 我们已扩展导出目标，以包括 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="10f6f-193">**Export segments to RollWorks** We have extended our export destinations to include RollWorks.</span></span> <span data-ttu-id="10f6f-194">现在，您可以将客户细分从 Customer Insights 导出到 RollWorks 受众，并将其用作 B2B 广告的基线。</span><span class="sxs-lookup"><span data-stu-id="10f6f-194">You can now export segments from Customer Insights to RollWorks audiences and use them as the baseline for your B2B advertising.</span></span>    
   <span data-ttu-id="10f6f-195">有关详细信息，请参阅[将数据导出至 RollWorks](export-rollworks.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-195">For more information, see [Export to RollWorks ](export-rollworks.md).</span></span>

- <span data-ttu-id="10f6f-196">**将客户细分导出到 Snapchat** 我们已扩展导出目标，以包括 Snapchat。</span><span class="sxs-lookup"><span data-stu-id="10f6f-196">**Export segments to Snapchat** We have extended our export destinations to include Snapchat.</span></span> <span data-ttu-id="10f6f-197">现在，您可以将客户细分从 Customer Insights 导出到 Snapchat 受众，并将其用作广告的基线。</span><span class="sxs-lookup"><span data-stu-id="10f6f-197">You can now export segments from Customer Insights to Snapchat audiences and use them as the baseline for your advertising.</span></span>     
   <span data-ttu-id="10f6f-198">有关详细信息，请参阅[将数据导出至 Snapchat](export-snapchat.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-198">For more information, see [Export to Snapchat](export-snapchat.md).</span></span>

### <a name="predictions"></a><span data-ttu-id="10f6f-199">预测</span><span class="sxs-lookup"><span data-stu-id="10f6f-199">Predictions</span></span>

- <span data-ttu-id="10f6f-200">**在预测产品建议中使用产品筛选器** 我们已在产品建议模型中添加了使用产品筛选器的功能。</span><span class="sxs-lookup"><span data-stu-id="10f6f-200">**Use product filters in predictive product recommendations** We have added the capability to use product filters in our product recommendation model.</span></span> <span data-ttu-id="10f6f-201">现在，您可以创建仅使用产品子集的预测。</span><span class="sxs-lookup"><span data-stu-id="10f6f-201">You can now create a prediction that uses only a subset of your products.</span></span>    
   <span data-ttu-id="10f6f-202">有关更多信息，请参阅[配置产品筛选器](predict-product-recommendation.md#configure-product-filters)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-202">For more information, see [Configure product filters](predict-product-recommendation.md#configure-product-filters).</span></span>

- <span data-ttu-id="10f6f-203">**从模型预测创建客户细分** 我们添加了使用预测模型结果创建客户细分的快速方法。</span><span class="sxs-lookup"><span data-stu-id="10f6f-203">**Create segments from model predictions** We have added a quick way to create segments using the results of a prediction model.</span></span> <span data-ttu-id="10f6f-204">从模型结果页面中，您可以通过选择新的 **创建客户细分** 选项来轻松创建新客户细分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-204">From the model results page, you can easily create a new segment by selecting the new **Create segment** option.</span></span>    
  <span data-ttu-id="10f6f-205">有关更多信息，请参阅[基于预测模型创建一个客户细分](prediction-based-segment.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-205">For more information, see [Create a segment based on a prediction model](prediction-based-segment.md).</span></span>

- <span data-ttu-id="10f6f-206">**产品建议的解释** 我们添加了信息，以解释 AI 模型为生成产品建议而了解的关键因素，以及这些因素对产品推荐的影响程度。</span><span class="sxs-lookup"><span data-stu-id="10f6f-206">**Explanations for product recommendations** We have added information explaining the key factors learned by the AI model to generate product recommendations and the degree to which those factors contribute towards the product recommendations.</span></span> <span data-ttu-id="10f6f-207">此信息已添加到模型结果屏幕。</span><span class="sxs-lookup"><span data-stu-id="10f6f-207">This information is added to the model results screen.</span></span>    
   <span data-ttu-id="10f6f-208">有关详细信息，请参阅[审阅预测状态和结果](predict-product-recommendation.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-208">For more information, see [Review a prediction status and results](predict-product-recommendation.md#review-a-prediction-status-and-results).</span></span>

## <a name="february-2021-updates"></a><span data-ttu-id="10f6f-209">2021 年 2 月更新</span><span class="sxs-lookup"><span data-stu-id="10f6f-209">February 2021 updates</span></span>

<span data-ttu-id="10f6f-210">2021 年 2 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="10f6f-210">The updates in February 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="10f6f-211">扩展性</span><span class="sxs-lookup"><span data-stu-id="10f6f-211">Extensibility</span></span>

- <span data-ttu-id="10f6f-212">**将客户细分导出到 AdRoll**</span><span class="sxs-lookup"><span data-stu-id="10f6f-212">**Export segments to AdRoll**</span></span>

  <span data-ttu-id="10f6f-213">我们已扩展了导出目标以包括 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="10f6f-213">We have extended our export destinations to include AdRoll.</span></span> <span data-ttu-id="10f6f-214">现在，您可以将 Customer Insights 中的客户细分导出到 AdRoll 访问群体，并使用它们作为广告的基线。</span><span class="sxs-lookup"><span data-stu-id="10f6f-214">You can now export segments from Customer Insights to AdRoll audiences and use them as the baseline for your advertising.</span></span> <span data-ttu-id="10f6f-215">有关详细信息，请参阅[用于 AdRoll 的连接器](export-adroll.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-215">For more information, see [Connector for AdRoll](export-adroll.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="10f6f-216">客户细分</span><span class="sxs-lookup"><span data-stu-id="10f6f-216">Segments</span></span>
 
- <span data-ttu-id="10f6f-217">**复制客户细分**</span><span class="sxs-lookup"><span data-stu-id="10f6f-217">**Duplicate a segment**</span></span>
  
  <span data-ttu-id="10f6f-218">若要基于现有客户细分创建新客户细分，现在可以复制某个客户细分，并编辑复制的客户细分以进一步优化该客户细分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-218">To create a new segment based on an existing one, you can now duplicate a segment and edit the duplicated segment to refine it further.</span></span> 

- <span data-ttu-id="10f6f-219">**向客户细分添加其他属性**</span><span class="sxs-lookup"><span data-stu-id="10f6f-219">**Add additional attributes to a segment**</span></span>

  <span data-ttu-id="10f6f-220">现在，您可以将属性包括在客户细分输出中，即使这些属性不是客户配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-220">You can now include attributes in your segment output, even if these attributes are not part of the customer profile.</span></span> <span data-ttu-id="10f6f-221">例如，在客户细分中包括订阅 ID，即使它是与客户实体具有 M:1 关系的订阅实体的一部分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-221">For example, include subscription IDs in a segment even though it is part of the subscription entity that has a M:1 relation with the customer entity.</span></span> <span data-ttu-id="10f6f-222">只要属性属于与客户实体相关的实体，就可以包括这些属性。</span><span class="sxs-lookup"><span data-stu-id="10f6f-222">As long as the attribute belongs to an entity related to the customer entity you can now include these attributes.</span></span>  

#### <a name="predictions"></a><span data-ttu-id="10f6f-223">预测</span><span class="sxs-lookup"><span data-stu-id="10f6f-223">Predictions</span></span>

- <span data-ttu-id="10f6f-224">**创建预测产品建议**</span><span class="sxs-lookup"><span data-stu-id="10f6f-224">**Create predictive product recommendations**</span></span>

  <span data-ttu-id="10f6f-225">了解客户的购买兴趣是什么是通过个性化和参与提高业务收入和建立客户忠诚度所需的第一步。</span><span class="sxs-lookup"><span data-stu-id="10f6f-225">Understanding what customers are interested in purchasing is one of the first steps needed to improve business revenue and build customer loyalty through personalization and engagement.</span></span> <span data-ttu-id="10f6f-226">如果推荐的产品不符合客户的兴趣，会使客户与您的企业之间产生脱节感，从而最终限制整体潜在收入和客户的体验。</span><span class="sxs-lookup"><span data-stu-id="10f6f-226">Providing recommendations for products that aren’t aligned to your customer’s interests can create a sense of disconnect between the customer and your business, and ultimately limit the overall potential revenue and experience for a customer.</span></span> 

  <span data-ttu-id="10f6f-227">现在您可以使用您自己的数据预测客户将来可能会购买的产品。</span><span class="sxs-lookup"><span data-stu-id="10f6f-227">Using your own data, you can now create predictions for what products your customers are likely to purchase in the future.</span></span> <span data-ttu-id="10f6f-228">有关详细信息，请参阅[产品建议预测](predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-228">For more information, see [Product recommendation prediction](predict-product-recommendation.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="10f6f-229">系统管理</span><span class="sxs-lookup"><span data-stu-id="10f6f-229">System administration</span></span>

- <span data-ttu-id="10f6f-230">**复制环境支持更多类型的数据源**</span><span class="sxs-lookup"><span data-stu-id="10f6f-230">**Copy environment support more types of data sources**</span></span>

  <span data-ttu-id="10f6f-231">管理员可以将环境配置复制到同一组织的新环境中。</span><span class="sxs-lookup"><span data-stu-id="10f6f-231">Admins can copy environment configurations to a new environment in the same organization.</span></span> <span data-ttu-id="10f6f-232">对于使用基于 Common Data Service 数据湖或 Common Data Model 文件夹的数据源的情况，此功能会扩展复制环境功能。</span><span class="sxs-lookup"><span data-stu-id="10f6f-232">This feature extends the copy environment functionality for cases in which data sources based on a Common Data Service data lake or a Common Data Model folder are used.</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="10f6f-233">2021 年 1 月更新</span><span class="sxs-lookup"><span data-stu-id="10f6f-233">January 2021 updates</span></span>

<span data-ttu-id="10f6f-234">2021 年 1 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="10f6f-234">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="10f6f-235">扩展性</span><span class="sxs-lookup"><span data-stu-id="10f6f-235">Extensibility</span></span>

- <span data-ttu-id="10f6f-236">**SFTP 导出的扩展功能和增强性能**：现在，您可以将所有输出实体从 Customer Insights 导出到 SFTP 主机。</span><span class="sxs-lookup"><span data-stu-id="10f6f-236">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="10f6f-237">以前，导出仅限于客户细分实体。</span><span class="sxs-lookup"><span data-stu-id="10f6f-237">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="10f6f-238">此外，SFTP 导出的性能可以在更短时间内导出更多数据量，具体取决于 SFTP 主机的性能。</span><span class="sxs-lookup"><span data-stu-id="10f6f-238">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="10f6f-239">有关详细信息，请参阅[用于 SFTP 的连接器（预览版）](export-sftp.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-239">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="10f6f-240">客户细分</span><span class="sxs-lookup"><span data-stu-id="10f6f-240">Segments</span></span>

- <span data-ttu-id="10f6f-241">**由机器学习提供支持的建议客户细分可以改进指标**：有一种发现和创建客户细分的新方法。</span><span class="sxs-lookup"><span data-stu-id="10f6f-241">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="10f6f-242">系统使用 AI 模型来建议可以帮助改进您已在跟踪的 KPI（度量）的客户细分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-242">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="10f6f-243">我们将显示您选择的属性对度量或其他主要属性的影响程度。</span><span class="sxs-lookup"><span data-stu-id="10f6f-243">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="10f6f-244">此信息有助于查找提供商机的潜在客户细分。</span><span class="sxs-lookup"><span data-stu-id="10f6f-244">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="10f6f-245">有关详细信息，请参阅[建议的客户细分（预览版）](suggested-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-245">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="10f6f-246">数据统一</span><span class="sxs-lookup"><span data-stu-id="10f6f-246">Data unification</span></span>

- <span data-ttu-id="10f6f-247">**增强的匹配体验**：在数据统一区域中更新了匹配体验。</span><span class="sxs-lookup"><span data-stu-id="10f6f-247">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="10f6f-248">它允许您配置和查看匹配规则，包括详细统计信息，以进一步解释匹配的工作方式。</span><span class="sxs-lookup"><span data-stu-id="10f6f-248">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="10f6f-249">有一些选项可禁用匹配规则，以便在保留配置、拖放匹配规则等时该规则不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="10f6f-249">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="10f6f-250">有关详细信息，请参阅[匹配实体](match-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-250">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="10f6f-251">**匹配过程中的删除重复输出可用作实体**：现在，匹配过程中的删除重复过程输出可以写入到单独的实体中，以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="10f6f-251">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="10f6f-252">该实体由删除重复过程中使用的字段、入选记录以及与入选记录合并的相应备用记录组成。</span><span class="sxs-lookup"><span data-stu-id="10f6f-252">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="10f6f-253">有关详细信息，请参阅[实体形式的删除重复输出](match-entities.md#deduplication-output-as-an-entity)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-253">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="10f6f-254">系统管理</span><span class="sxs-lookup"><span data-stu-id="10f6f-254">System administration</span></span>

- <span data-ttu-id="10f6f-255">**将数据与 Microsoft Dataverse 无缝共享**：现在，您可以使用 Microsoft Dataverse 托管 Data Lake 与 Microsoft Dataverse 应用程序共享 Customer Insights 输出。</span><span class="sxs-lookup"><span data-stu-id="10f6f-255">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="10f6f-256">将 Dataverse 环境与 Customer Insights 关联后，便可以选择启用数据共享。</span><span class="sxs-lookup"><span data-stu-id="10f6f-256">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="10f6f-257">有关详细信息，请参阅[管理环境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="10f6f-257">For more information, see [Manage environments](manage-environments.md).</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]