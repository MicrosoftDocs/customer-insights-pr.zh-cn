---
title: 新功能和未来的功能
description: 有关新功能、改进和 Bug 修复的信息。
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988909"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="ca8e7-103">Dynamics 365 Customer Insights 的访问群体见解功能中的新增功能</span><span class="sxs-lookup"><span data-stu-id="ca8e7-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ca8e7-104">我们非常激动地发布我们的最新更新！</span><span class="sxs-lookup"><span data-stu-id="ca8e7-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="ca8e7-105">本文总结了公开预览功能、正式发布版本的增强和功能更新。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="ca8e7-106">若要查看长期功能计划，请参阅 [Dynamics 365 和 Power Platform 发行计划](/dynamics365/release-plans/)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](/dynamics365/release-plans/).</span></span>

<span data-ttu-id="ca8e7-107">我们将按地区推出更新。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-107">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="ca8e7-108">因此，某些地区可能先于其他地区看到功能。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-108">So certain regions might see features before others.</span></span> <span data-ttu-id="ca8e7-109">除非另行指定，否则您无需执行任何操作，我们会自动更新应用，无需停机。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-109">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="ca8e7-110">若要提交功能请求和产品建议及投票，请访问 [Dynamics 365 应用程序意见门户](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-110">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="april-2021-updates"></a><span data-ttu-id="ca8e7-111">2021 年 4 月更新</span><span class="sxs-lookup"><span data-stu-id="ca8e7-111">April 2021 updates</span></span>

<span data-ttu-id="ca8e7-112">2021 年 4 月中的更新包括多项功能、性能升级和错误修复。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-112">The updates in April 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="data-unification"></a><span data-ttu-id="ca8e7-113">数据统一</span><span class="sxs-lookup"><span data-stu-id="ca8e7-113">Data unification</span></span>
 
- <span data-ttu-id="ca8e7-114">**增强的数据统一合并体验**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-114">**Enhanced merge experience for data unification**</span></span>    
  
   <span data-ttu-id="ca8e7-115">现在，我们在数据统一过程的合并配置中增强了用户体验。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-115">We now have an enhanced user experience in the merge configuration of the data unification process.</span></span> <span data-ttu-id="ca8e7-116">这些更改包括直观排序合并字段以及合并和单一字段的详细统计信息。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-116">The changes include intuitive ordering of the merged fields and detailed statistics on combined and singleton fields.</span></span>

- <span data-ttu-id="ca8e7-117">**实体重新排序并将所有源记录配置到客户实体中**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-117">**Entity reordering and configure all source records into the Customer entity**</span></span>  
      
   <span data-ttu-id="ca8e7-118">现在，您可以在数据统一过程中重新排序和删除现有实施规划中的实体。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-118">You can now reorder and remove entities from an existing conflation plan in the data unification process.</span></span> <span data-ttu-id="ca8e7-119">系统提供了根据业务需求在匹配过程中对实体进行重新排序的灵活性。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-119">It gives flexibility to reorder the entities in the match process according to business needs.</span></span> <span data-ttu-id="ca8e7-120">此外，我们允许将所有不匹配的记录包括到最终 *客户* 实体中，这使他们可以进行客户配置文件数据集定义。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-120">Additionally, we enable include all non-matched records into the final *Customer* entity, which lets them define their customer profile dataset definition.</span></span>

### <a name="enrichments"></a><span data-ttu-id="ca8e7-121">扩充</span><span class="sxs-lookup"><span data-stu-id="ca8e7-121">Enrichments</span></span>

 - <span data-ttu-id="ca8e7-122">**新扩充：增强型地址**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-122">**New enrichment: Enhanced addresses**</span></span>    
  
   <span data-ttu-id="ca8e7-123">我们很高兴推出用于增强客户数据中的地址的新扩充功能。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-123">We're excited to introduce a new enrichment to enhance addresses in your customer data.</span></span> <span data-ttu-id="ca8e7-124">数据中的地址可能无结构、不完整或不正确。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-124">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="ca8e7-125">此功能使用 Microsoft 的模型按 Common Data Model 格式标准化并扩充您的地址，以获得更佳的准确性和见解。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-125">This feature uses Microsoft's models to normalize and enrich your addresses into the Common Data Model format for better accuracy and insights.</span></span>
 
   <span data-ttu-id="ca8e7-126">有关详细信息，请参阅[使用增强的地址扩充客户配置文件](enrichment-enhanced-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-126">For more information, see [Enrichment of customer profiles with enhanced addresses](enrichment-enhanced-addresses.md).</span></span>

- <span data-ttu-id="ca8e7-127">**扩充的引导式配置体验**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-127">**Guided configuration experience for enrichments**</span></span>    
  
   <span data-ttu-id="ca8e7-128">我们用简单的引导式体验重新感受了扩充的配置体验。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-128">We revisited the configuration experience for enrichments with a simple, guided experience.</span></span> <span data-ttu-id="ca8e7-129">现在，您具有一个用于创建和编辑扩充的清晰分步流程。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-129">You now have a clear step-by-step process for creating and editing enrichments.</span></span>
 
   <span data-ttu-id="ca8e7-130">此外，我们分离了第三方扩充功能的连接配置，以使多个扩充功能可以使用同一连接。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-130">Additionally, we separated the configuration of connections for third-party enrichments to enable the same connection to be used by multiple enrichments.</span></span> <span data-ttu-id="ca8e7-131">只有管理员才能配置新的连接，但创建的连接可供管理员和参与者使用。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-131">Only administrators can configure new connections, but the created connections are available to both administrators and contributors.</span></span>    

   <span data-ttu-id="ca8e7-132">有关详细信息，请参阅[连接概述](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-132">For more information, see [Connections overview](connections.md).</span></span>

- <span data-ttu-id="ca8e7-133">**相同类型的多项扩充**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-133">**Multiple enrichments of the same type**</span></span>    
  
   <span data-ttu-id="ca8e7-134">现在，我们允许用户创建和管理相同扩充类型的多个扩充。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-134">We now allow users to create and manage multiple enrichments of the same enrichment type.</span></span> <span data-ttu-id="ca8e7-135">例如，您现在可以创建两个单独的地址扩充，以扩充两个不同的客户细分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-135">For example, you can now create two separate address enrichments to enrich two different customer segments.</span></span> <span data-ttu-id="ca8e7-136">关于可以创建多少个相同类型的扩充，具有一些限制，具体取决于扩充类型。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-136">Limits apply on how many enrichments of the same type can be created and vary depending on the enrichment type.</span></span>
  
   <span data-ttu-id="ca8e7-137">有关详细信息，请参阅[客户资料扩充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-137">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

## <a name="march-2021-updates"></a><span data-ttu-id="ca8e7-138">2021 年 3 月更新</span><span class="sxs-lookup"><span data-stu-id="ca8e7-138">March 2021 updates</span></span>

<span data-ttu-id="ca8e7-139">2021 年 3 月中的更新包括多项功能、性能升级和错误修复。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-139">The updates in March 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="activities"></a><span data-ttu-id="ca8e7-140">活动</span><span class="sxs-lookup"><span data-stu-id="ca8e7-140">Activities</span></span>

- <span data-ttu-id="ca8e7-141">**活动向导和语义类型**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-141">**Activity wizard and semantic types**</span></span>

   <span data-ttu-id="ca8e7-142">我们改进和更新了活动映射体验，以指导和简化活动映射的创建过程。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-142">We have improved and updated our activity mapping experience to guide and simplify the creation of activity mapping.</span></span> <span data-ttu-id="ca8e7-143">在这种新体验中，用户将获得引导式体验，以帮助完成流程的每一步。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-143">In this new experience, users get a guided experience to help completing of each step of the process.</span></span> <span data-ttu-id="ca8e7-144">在活动映射步骤中，除了从许多活动类型中进行选择外，用户还可以选择在语义上将 *订阅* 和/或 *SalesOrderLine* 的数据映射到行业标准架构，这些架构可用于下游消费。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-144">At the activity mapping step, in addition to choosing from many activity types, the user can choose to semantically map data for *Subscription* and/or *SalesOrderLine* to industry standard schemas, which can be used for downstream consumption.</span></span>   

   <span data-ttu-id="ca8e7-145">有关详细信息，请参阅[自定义活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-145">For more information, see [Customer activities](activities.md).</span></span>

### <a name="data-ingestion"></a><span data-ttu-id="ca8e7-146">数据引入</span><span class="sxs-lookup"><span data-stu-id="ca8e7-146">Data ingestion</span></span>

- <span data-ttu-id="ca8e7-147">**使用 Power Platform 数据流和网关连接到本地数据源** 我们很高兴地宣布将使用 Customer Insights 中的网关以及关联的 Power Platform 或 Dataverse 环境来预览 Power Platform 数据流和本地连接。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-147">**Connect to on-premises data sources using Power Platform dataflows and gateways** We are pleased to announce the preview of Power Platform dataflows and on-premises connectivity using gateways in Customer Insights with an associated Power Platform or Dataverse environment.</span></span> <span data-ttu-id="ca8e7-148">在具有链接的 Dataverse 环境的 Customer Insights 环境中创建的任何新数据源都将默认为 Power Platform 数据流，此数据流将引入本地数据连接以及一组丰富的连接器和转换功能。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-148">Any new data sources created in a Customer Insights environment with a linked Dataverse environment will default to Power Platform dataflows bringing in the on-premises data connectivity and a rich set of connectors and transformation capabilities.</span></span>

### <a name="extensibility"></a><span data-ttu-id="ca8e7-149">扩展性</span><span class="sxs-lookup"><span data-stu-id="ca8e7-149">Extensibility</span></span>

- <span data-ttu-id="ca8e7-150">**在连接和导出中组织的导出** 我们已将 **导出目标** 页面的名称更改为 **连接**，并添加了单独的 **导出** 页面。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-150">**Exports organized in connections and exports** We have changed the name of the **Export destinations** page to **Connections** and added a separate page for **Exports**.</span></span> <span data-ttu-id="ca8e7-151">在此更新过程中，我们会将现有的导出转换为连接和导出（使用该连接）对。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-151">As part of this update, we'll transition existing exports into pairs of a connection and an export using that connection.</span></span> <span data-ttu-id="ca8e7-152">管理员现在可以在 **连接** 页面上更清晰地了解传出数据。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-152">Administrators now have more clarity over outgoing data on the **Connections** page.</span></span> <span data-ttu-id="ca8e7-153">所有用户角色都有权访问 **导出** 页面，但只有管理员可以选择允许参与者使用共享连接编辑特定的导出。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-153">All user roles have access to the **Exports** page, but only administrators can choose to allow contributors to edit specific exports with shared connections.</span></span>     
  <span data-ttu-id="ca8e7-154">有关更多信息，请参阅[连接概述](connections.md)和[导出概述](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-154">For more information, see [Connections overview](connections.md) and [Exports overview](export-destinations.md).</span></span>

- <span data-ttu-id="ca8e7-155">**将客户细分导出到 Campaign Monitor** 我们已扩展导出目标，以包括 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-155">**Export segments to Campaign Monitor** We have extended our export destinations to include Campaign Monitor.</span></span> <span data-ttu-id="ca8e7-156">现在，您可以将客户细分从 Customer Insights 导出到 Campaign Monitor列表，并将其用作市场营销活动的基线。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-156">You can now export segments from Customer Insights to Campaign Monitor lists and use them as the baseline for your marketing campaigns.</span></span>    
   <span data-ttu-id="ca8e7-157">有关详细信息，请参阅[将数据导出至 Campaign Monitor](export-campaign-monitor.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-157">For more information, see [Export to Campaign Monitor](export-campaign-monitor.md).</span></span>

- <span data-ttu-id="ca8e7-158">**将客户细分导出到 Constant Contact** 我们已扩展导出目标，以包括 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-158">**Export segments to Constant Contact** We have extended our export destinations to include Constant Contact.</span></span> <span data-ttu-id="ca8e7-159">现在，您可以将客户细分从 Customer Insights 导出到 Constant Contact 列表，并将其用作市场营销活动的基线。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-159">You can now export segments from Customer Insights to Constant Contact lists and use them as the baseline for your marketing campaigns.</span></span>   
   <span data-ttu-id="ca8e7-160">有关详细信息，请参阅[将数据导出至 Constant Contact](export-constant-contact.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-160">For more information, see [Export to Constant Contact](export-constant-contact.md).</span></span>

- <span data-ttu-id="ca8e7-161">**将客户细分导出到 RollWorks** 我们已扩展导出目标，以包括 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-161">**Export segments to RollWorks** We have extended our export destinations to include RollWorks.</span></span> <span data-ttu-id="ca8e7-162">现在，您可以将客户细分从 Customer Insights 导出到 RollWorks 受众，并将其用作 B2B 广告的基线。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-162">You can now export segments from Customer Insights to RollWorks audiences and use them as the baseline for your B2B advertising.</span></span>    
   <span data-ttu-id="ca8e7-163">有关详细信息，请参阅[将数据导出至 RollWorks](export-rollworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-163">For more information, see [Export to RollWorks ](export-rollworks.md).</span></span>

- <span data-ttu-id="ca8e7-164">**将客户细分导出到 Snapchat** 我们已扩展导出目标，以包括 Snapchat。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-164">**Export segments to Snapchat** We have extended our export destinations to include Snapchat.</span></span> <span data-ttu-id="ca8e7-165">现在，您可以将客户细分从 Customer Insights 导出到 Snapchat 受众，并将其用作广告的基线。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-165">You can now export segments from Customer Insights to Snapchat audiences and use them as the baseline for your advertising.</span></span>     
   <span data-ttu-id="ca8e7-166">有关详细信息，请参阅[将数据导出至 Snapchat](export-snapchat.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-166">For more information, see [Export to Snapchat](export-snapchat.md).</span></span>

### <a name="predictions"></a><span data-ttu-id="ca8e7-167">预测</span><span class="sxs-lookup"><span data-stu-id="ca8e7-167">Predictions</span></span>

- <span data-ttu-id="ca8e7-168">**在预测产品建议中使用产品筛选器** 我们已在产品建议模型中添加了使用产品筛选器的功能。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-168">**Use product filters in predictive product recommendations** We have added the capability to use product filters in our product recommendation model.</span></span> <span data-ttu-id="ca8e7-169">现在，您可以创建仅使用产品子集的预测。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-169">You can now create a prediction that uses only a subset of your products.</span></span>    
   <span data-ttu-id="ca8e7-170">有关更多信息，请参阅[配置产品筛选器](predict-product-recommendation.md#configure-product-filters)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-170">For more information, see [Configure product filters](predict-product-recommendation.md#configure-product-filters).</span></span>

- <span data-ttu-id="ca8e7-171">**从模型预测创建客户细分** 我们添加了使用预测模型结果创建客户细分的快速方法。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-171">**Create segments from model predictions** We have added a quick way to create segments using the results of a prediction model.</span></span> <span data-ttu-id="ca8e7-172">从模型结果页面中，您可以通过选择新的 **创建客户细分** 选项来轻松创建新客户细分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-172">From the model results page, you can easily create a new segment by selecting the new **Create segment** option.</span></span>    
  <span data-ttu-id="ca8e7-173">有关更多信息，请参阅[基于预测模型创建一个客户细分](prediction-based-segment.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-173">For more information, see [Create a segment based on a prediction model](prediction-based-segment.md).</span></span>

- <span data-ttu-id="ca8e7-174">**产品建议的解释** 我们添加了信息，以解释 AI 模型为生成产品建议而了解的关键因素，以及这些因素对产品推荐的影响程度。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-174">**Explanations for product recommendations** We have added information explaining the key factors learned by the AI model to generate product recommendations and the degree to which those factors contribute towards the product recommendations.</span></span> <span data-ttu-id="ca8e7-175">此信息已添加到模型结果屏幕。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-175">This information is added to the model results screen.</span></span>    
   <span data-ttu-id="ca8e7-176">有关详细信息，请参阅[审阅预测状态和结果](predict-product-recommendation.md#review-a-prediction-status-and-results)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-176">For more information, see [Review a prediction status and results](predict-product-recommendation.md#review-a-prediction-status-and-results).</span></span>

## <a name="february-2021-updates"></a><span data-ttu-id="ca8e7-177">2021 年 2 月更新</span><span class="sxs-lookup"><span data-stu-id="ca8e7-177">February 2021 updates</span></span>

<span data-ttu-id="ca8e7-178">2021 年 2 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-178">The updates in February 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ca8e7-179">扩展性</span><span class="sxs-lookup"><span data-stu-id="ca8e7-179">Extensibility</span></span>

- <span data-ttu-id="ca8e7-180">**将客户细分导出到 AdRoll**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-180">**Export segments to AdRoll**</span></span>

  <span data-ttu-id="ca8e7-181">我们已扩展了导出目标以包括 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-181">We have extended our export destinations to include AdRoll.</span></span> <span data-ttu-id="ca8e7-182">现在，您可以将 Customer Insights 中的客户细分导出到 AdRoll 访问群体，并使用它们作为广告的基线。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-182">You can now export segments from Customer Insights to AdRoll audiences and use them as the baseline for your advertising.</span></span> <span data-ttu-id="ca8e7-183">有关详细信息，请参阅[用于 AdRoll 的连接器](export-adroll.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-183">For more information, see [Connector for AdRoll](export-adroll.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="ca8e7-184">客户细分</span><span class="sxs-lookup"><span data-stu-id="ca8e7-184">Segments</span></span>
 
- <span data-ttu-id="ca8e7-185">**复制客户细分**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-185">**Duplicate a segment**</span></span>
  
  <span data-ttu-id="ca8e7-186">若要基于现有客户细分创建新客户细分，现在可以复制某个客户细分，并编辑复制的客户细分以进一步优化该客户细分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-186">To create a new segment based on an existing one, you can now duplicate a segment and edit the duplicated segment to refine it further.</span></span> 

- <span data-ttu-id="ca8e7-187">**向客户细分添加其他属性**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-187">**Add additional attributes to a segment**</span></span>

  <span data-ttu-id="ca8e7-188">现在，您可以将属性包括在客户细分输出中，即使这些属性不是客户配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-188">You can now include attributes in your segment output, even if these attributes are not part of the customer profile.</span></span> <span data-ttu-id="ca8e7-189">例如，在客户细分中包括订阅 ID，即使它是与客户实体具有 M:1 关系的订阅实体的一部分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-189">For example, include subscription IDs in a segment even though it is part of the subscription entity that has a M:1 relation with the customer entity.</span></span> <span data-ttu-id="ca8e7-190">只要属性属于与客户实体相关的实体，就可以包括这些属性。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-190">As long as the attribute belongs to an entity related to the customer entity you can now include these attributes.</span></span>  

#### <a name="predictions"></a><span data-ttu-id="ca8e7-191">预测</span><span class="sxs-lookup"><span data-stu-id="ca8e7-191">Predictions</span></span>

- <span data-ttu-id="ca8e7-192">**创建预测产品建议**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-192">**Create predictive product recommendations**</span></span>

  <span data-ttu-id="ca8e7-193">了解客户的购买兴趣是什么是通过个性化和参与提高业务收入和建立客户忠诚度所需的第一步。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-193">Understanding what customers are interested in purchasing is one of the first steps needed to improve business revenue and build customer loyalty through personalization and engagement.</span></span> <span data-ttu-id="ca8e7-194">如果推荐的产品不符合客户的兴趣，会使客户与您的企业之间产生脱节感，从而最终限制整体潜在收入和客户的体验。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-194">Providing recommendations for products that aren’t aligned to your customer’s interests can create a sense of disconnect between the customer and your business, and ultimately limit the overall potential revenue and experience for a customer.</span></span> 

  <span data-ttu-id="ca8e7-195">现在您可以使用您自己的数据预测客户将来可能会购买的产品。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-195">Using your own data, you can now create predictions for what products your customers are likely to purchase in the future.</span></span> <span data-ttu-id="ca8e7-196">有关详细信息，请参阅[产品建议预测](predict-product-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-196">For more information, see [Product recommendation prediction](predict-product-recommendation.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ca8e7-197">系统管理</span><span class="sxs-lookup"><span data-stu-id="ca8e7-197">System administration</span></span>

- <span data-ttu-id="ca8e7-198">**复制环境支持更多类型的数据源**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-198">**Copy environment support more types of data sources**</span></span>

  <span data-ttu-id="ca8e7-199">管理员可以将环境配置复制到同一组织的新环境中。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-199">Admins can copy environment configurations to a new environment in the same organization.</span></span> <span data-ttu-id="ca8e7-200">对于使用基于 Common Data Service 数据湖或 Common Data Model 文件夹的数据源的情况，此功能会扩展复制环境功能。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-200">This feature extends the copy environment functionality for cases in which data sources based on a Common Data Service data lake or a Common Data Model folder are used.</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="ca8e7-201">2021 年 1 月更新</span><span class="sxs-lookup"><span data-stu-id="ca8e7-201">January 2021 updates</span></span>

<span data-ttu-id="ca8e7-202">2021 年 1 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-202">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ca8e7-203">扩展性</span><span class="sxs-lookup"><span data-stu-id="ca8e7-203">Extensibility</span></span>

- <span data-ttu-id="ca8e7-204">**SFTP 导出的扩展功能和增强性能**：现在，您可以将所有输出实体从 Customer Insights 导出到 SFTP 主机。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-204">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="ca8e7-205">以前，导出仅限于客户细分实体。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-205">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="ca8e7-206">此外，SFTP 导出的性能可以在更短时间内导出更多数据量，具体取决于 SFTP 主机的性能。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-206">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="ca8e7-207">有关详细信息，请参阅[用于 SFTP 的连接器（预览版）](export-sftp.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-207">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="ca8e7-208">客户细分</span><span class="sxs-lookup"><span data-stu-id="ca8e7-208">Segments</span></span>

- <span data-ttu-id="ca8e7-209">**由机器学习提供支持的建议客户细分可以改进指标**：有一种发现和创建客户细分的新方法。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-209">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="ca8e7-210">系统使用 AI 模型来建议可以帮助改进您已在跟踪的 KPI（度量）的客户细分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-210">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="ca8e7-211">我们将显示您选择的属性对度量或其他主要属性的影响程度。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-211">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="ca8e7-212">此信息有助于查找提供商机的潜在客户细分。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-212">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="ca8e7-213">有关详细信息，请参阅[建议的客户细分（预览版）](suggested-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-213">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="ca8e7-214">数据统一</span><span class="sxs-lookup"><span data-stu-id="ca8e7-214">Data unification</span></span>

- <span data-ttu-id="ca8e7-215">**增强的匹配体验**：在数据统一区域中更新了匹配体验。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-215">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="ca8e7-216">它允许您配置和查看匹配规则，包括详细统计信息，以进一步解释匹配的工作方式。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-216">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="ca8e7-217">有一些选项可禁用匹配规则，以便在保留配置、拖放匹配规则等时该规则不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-217">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="ca8e7-218">有关详细信息，请参阅[匹配实体](match-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-218">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="ca8e7-219">**匹配过程中的删除重复输出可用作实体**：现在，匹配过程中的删除重复过程输出可以写入到单独的实体中，以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-219">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="ca8e7-220">该实体由删除重复过程中使用的字段、入选记录以及与入选记录合并的相应备用记录组成。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-220">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="ca8e7-221">有关详细信息，请参阅[实体形式的删除重复输出](match-entities.md#deduplication-output-as-an-entity)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-221">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ca8e7-222">系统管理</span><span class="sxs-lookup"><span data-stu-id="ca8e7-222">System administration</span></span>

- <span data-ttu-id="ca8e7-223">**将数据与 Microsoft Dataverse 无缝共享**：现在，您可以使用 Microsoft Dataverse 托管 Data Lake 与 Microsoft Dataverse 应用程序共享 Customer Insights 输出。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-223">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="ca8e7-224">将 Dataverse 环境与 Customer Insights 关联后，便可以选择启用数据共享。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-224">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="ca8e7-225">有关详细信息，请参阅[管理环境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8e7-225">For more information, see [Manage environments](manage-environments.md).</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]