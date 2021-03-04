---
title: 新功能和未来的功能
description: 有关新功能、改进和 Bug 修复的信息。
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9183c8af4fb9f9f08ac63d8d0cd37c6868bba310
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270421"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="4f260-103">Dynamics 365 Customer Insights 的访问群体见解功能中的新增功能</span><span class="sxs-lookup"><span data-stu-id="4f260-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4f260-104">我们非常激动地发布我们的最新更新！</span><span class="sxs-lookup"><span data-stu-id="4f260-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="4f260-105">本文总结了公开预览功能、正式发布版本的增强和功能更新。</span><span class="sxs-lookup"><span data-stu-id="4f260-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="4f260-106">若要查看长期功能计划，请参阅 [Dynamics 365 和 Power Platform 发行计划](https://docs.microsoft.com/dynamics365/release-plans/)。</span><span class="sxs-lookup"><span data-stu-id="4f260-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](https://docs.microsoft.com/dynamics365/release-plans/).</span></span>

<span data-ttu-id="4f260-107">您还可以观看以下视频，以了解有关最近六个月的计划功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-107">You can also watch the following video to learn more about the capabilities planned for the last six months.</span></span>

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

<span data-ttu-id="4f260-108">我们将按地区推出更新。</span><span class="sxs-lookup"><span data-stu-id="4f260-108">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="4f260-109">因此，某些地区可能先于其他地区看到功能。</span><span class="sxs-lookup"><span data-stu-id="4f260-109">So certain regions might see features before others.</span></span> <span data-ttu-id="4f260-110">除非另行指定，否则您无需执行任何操作，我们会自动更新应用，无需停机。</span><span class="sxs-lookup"><span data-stu-id="4f260-110">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="4f260-111">若要提交功能请求和产品建议及投票，请访问 [Dynamics 365 应用程序意见门户](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。</span><span class="sxs-lookup"><span data-stu-id="4f260-111">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="4f260-112">2021 年 1 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-112">January 2021 updates</span></span>

<span data-ttu-id="4f260-113">2021 年 1 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-113">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-114">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-114">Extensibility</span></span>

- <span data-ttu-id="4f260-115">**SFTP 导出的扩展功能和增强性能**：现在，您可以将所有输出实体从 Customer Insights 导出到 SFTP 主机。</span><span class="sxs-lookup"><span data-stu-id="4f260-115">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="4f260-116">以前，导出仅限于客户细分实体。</span><span class="sxs-lookup"><span data-stu-id="4f260-116">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="4f260-117">此外，SFTP 导出的性能可以在更短时间内导出更多数据量，具体取决于 SFTP 主机的性能。</span><span class="sxs-lookup"><span data-stu-id="4f260-117">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="4f260-118">有关详细信息，请参阅[用于 SFTP 的连接器（预览版）](export-sftp.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-118">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="4f260-119">客户细分</span><span class="sxs-lookup"><span data-stu-id="4f260-119">Segments</span></span>

- <span data-ttu-id="4f260-120">**由机器学习提供支持的建议客户细分可以改进指标**：有一种发现和创建客户细分的新方法。</span><span class="sxs-lookup"><span data-stu-id="4f260-120">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="4f260-121">系统使用 AI 模型来建议可以帮助改进您已在跟踪的 KPI（度量）的客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-121">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="4f260-122">我们将显示您选择的属性对度量或其他主要属性的影响程度。</span><span class="sxs-lookup"><span data-stu-id="4f260-122">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="4f260-123">此信息有助于查找提供商机的潜在客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-123">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="4f260-124">有关详细信息，请参阅[建议的客户细分（预览版）](suggested-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-124">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="4f260-125">数据统一</span><span class="sxs-lookup"><span data-stu-id="4f260-125">Data unification</span></span>

- <span data-ttu-id="4f260-126">**增强的匹配体验**：在数据统一区域中更新了匹配体验。</span><span class="sxs-lookup"><span data-stu-id="4f260-126">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="4f260-127">它允许您配置和查看匹配规则，包括详细统计信息，以进一步解释匹配的工作方式。</span><span class="sxs-lookup"><span data-stu-id="4f260-127">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="4f260-128">有一些选项可禁用匹配规则，以便在保留配置、拖放匹配规则等时该规则不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="4f260-128">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="4f260-129">有关详细信息，请参阅[匹配实体](match-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-129">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="4f260-130">**匹配过程中的删除重复输出可用作实体**：现在，匹配过程中的删除重复过程输出可以写入到单独的实体中，以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="4f260-130">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="4f260-131">该实体由删除重复过程中使用的字段、入选记录以及与入选记录合并的相应备用记录组成。</span><span class="sxs-lookup"><span data-stu-id="4f260-131">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="4f260-132">有关详细信息，请参阅[实体形式的删除重复输出](match-entities.md#deduplication-output-as-an-entity)。</span><span class="sxs-lookup"><span data-stu-id="4f260-132">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="4f260-133">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-133">System administration</span></span>

- <span data-ttu-id="4f260-134">**将数据与 Microsoft Dataverse 无缝共享**：现在，您可以使用 Microsoft Dataverse 托管 Data Lake 与 Microsoft Dataverse 应用程序共享 Customer Insights 输出。</span><span class="sxs-lookup"><span data-stu-id="4f260-134">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="4f260-135">将 Dataverse 环境与 Customer Insights 关联后，便可以选择启用数据共享。</span><span class="sxs-lookup"><span data-stu-id="4f260-135">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="4f260-136">有关详细信息，请参阅[管理环境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-136">For more information, see [Manage environments](manage-environments.md).</span></span>


## <a name="december-2020-updates"></a><span data-ttu-id="4f260-137">2020 年 12 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-137">December 2020 updates</span></span>

<span data-ttu-id="4f260-138">2020 年 12 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-138">The updates in December 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-december-2020"></a><span data-ttu-id="4f260-139">2020 年 12 月的新功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-139">New and updated features in December 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="4f260-140">数据扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-140">Data enrichment</span></span>

- <span data-ttu-id="4f260-141">**改进的品牌和兴趣相似性扩充**</span><span class="sxs-lookup"><span data-stu-id="4f260-141">**Improved Brand and Interest affinity enrichments**</span></span>
  
  <span data-ttu-id="4f260-142">我们简化了相似性分数，以使其更易于理解和使用。</span><span class="sxs-lookup"><span data-stu-id="4f260-142">We simplified our affinity scores to make them easier to understand and use.</span></span> <span data-ttu-id="4f260-143">现在，您可以根据客户的给定品牌或兴趣的相似性程度来快速确定客户。</span><span class="sxs-lookup"><span data-stu-id="4f260-143">You can now quickly identify customers based on how much affinity they have for a given brand or interest.</span></span>

  <span data-ttu-id="4f260-144">此外，我们添加了新的配置选项，以更好地控制您希望如何扩充客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="4f260-144">Additionally, we have added new configuration options to better control how you want your customer profiles to be enriched.</span></span> 

  <span data-ttu-id="4f260-145">有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-145">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

- <span data-ttu-id="4f260-146">**控制要扩充的配置文件**</span><span class="sxs-lookup"><span data-stu-id="4f260-146">**Control which profiles to enrich**</span></span>

  <span data-ttu-id="4f260-147">现在，您可以使用选择客户细分实体而非默认客户实体的选项来仅扩充客户配置文件的子集。</span><span class="sxs-lookup"><span data-stu-id="4f260-147">You can now enrich only a subset of your customer profiles with the option to select a segment entity instead of the default customer entity.</span></span> <span data-ttu-id="4f260-148">使用您想要扩充的客户配置文件创建一个客户细分，并在扩充配置中为客户数据集选择该客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-148">Create a segment with the customer profiles you would like to enrich and select it in the enrichment configuration for your customer data set.</span></span>
  <span data-ttu-id="4f260-149">该功能目前仅适用于 Experian 和 HERE Technologies 提供的扩充。</span><span class="sxs-lookup"><span data-stu-id="4f260-149">This feature is currently available only for enrichments provided by Experian and HERE Technologies.</span></span> <span data-ttu-id="4f260-150">我们不久将使此功能可用于更多扩充。</span><span class="sxs-lookup"><span data-stu-id="4f260-150">We will be enabling this capability to more enrichments soon.</span></span>

  <span data-ttu-id="4f260-151">有关详细信息，请参阅[利用 Experian 的人口统计信息扩充客户配置文件](enrichment-experian.md)或[通过 HERE Technologies 扩充客户配置文件](enrichment-here.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-151">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md) or [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-152">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-152">Extensibility</span></span>

- <span data-ttu-id="4f260-153">**通过 Autopilot 激活您的客户细分**</span><span class="sxs-lookup"><span data-stu-id="4f260-153">**Activate your segments through Autopilot**</span></span>

  <span data-ttu-id="4f260-154">将客户细分导出到 Autopilot，并将其用于市场营销目的。</span><span class="sxs-lookup"><span data-stu-id="4f260-154">Export segments to Autopilot and use them for marketing purposes.</span></span> <span data-ttu-id="4f260-155">有关详细信息，请参阅[用于 Autopilot 的连接器（预览版）](export-autopilot.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-155">For more information, see [Connector for Autopilot (preview)](export-autopilot.md).</span></span>

- <span data-ttu-id="4f260-156">**通过 SendGrid 激活您的客户细分**</span><span class="sxs-lookup"><span data-stu-id="4f260-156">**Activate your segments through SendGrid**</span></span>

  <span data-ttu-id="4f260-157">将客户细分导出到 SendGrid，并将其用于市场营销目的。</span><span class="sxs-lookup"><span data-stu-id="4f260-157">Export segments to SendGrid and use them for marketing purposes.</span></span> <span data-ttu-id="4f260-158">有关详细信息，请参阅[用于 SendGrid 的连接器](export-sendgrid.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-158">For more information, see [Connector for SendGrid](export-sendgrid.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="4f260-159">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-159">System administration</span></span>

- <span data-ttu-id="4f260-160">**更新的环境管理体验**</span><span class="sxs-lookup"><span data-stu-id="4f260-160">**Updated environment management experience**</span></span>
  
  <span data-ttu-id="4f260-161">现在，您可以直接从应用标题中的环境选择器创建、编辑、删除和重置环境。</span><span class="sxs-lookup"><span data-stu-id="4f260-161">You can now create, edit, delete, and reset environments directly from the environment picker in the app header.</span></span> 
  
  <span data-ttu-id="4f260-162">此外，您使用的环境将固定在环境面板的顶部，因此您无需再搜索它。</span><span class="sxs-lookup"><span data-stu-id="4f260-162">Additionally, the environment you are using will be pinned at the top of the environment panel so you don't need to search for it anymore.</span></span>

  <span data-ttu-id="4f260-163">有关详细信息，请参阅[管理环境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-163">For more information, see [Manage environments](manage-environments.md).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="4f260-164">2020 年 11 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-164">November 2020 updates</span></span>

<span data-ttu-id="4f260-165">2020 年 11 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-165">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="4f260-166">2020 年 11 月的新功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-166">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="4f260-167">数据扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-167">Data enrichment</span></span>

- <span data-ttu-id="4f260-168">**通过安全文件传输协议 (SFTP) 自定义导入引入您自己的扩充数据**</span><span class="sxs-lookup"><span data-stu-id="4f260-168">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="4f260-169">通过 SFTP 自定义导入，您可以导入不需要完成数据统一流程的扩充数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-169">SFTP custom import lets you import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4f260-170">了解有关 SFTP 自定义导入的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-170">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="4f260-171">有关详细信息，请参阅[使用自定义数据扩充客户配置文件（预览）](enrichment-SFTP-custom-import.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-171">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="4f260-172">**使用来自 HERE Technologies 的位置数据扩充客户数据**</span><span class="sxs-lookup"><span data-stu-id="4f260-172">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="4f260-173">通过 HERE Technologies 的数据扩充服务，您可以使用地址标准化、维度和精度提取等来更准确地了解客户的位置信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-173">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="4f260-174">了解有关使用 HERE Technologies 扩充的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-174">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="4f260-175">有关详细信息，请参阅[使用 HERE Technologies 扩充客户配置文件](enrichment-here.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-175">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="4f260-176">数据统一</span><span class="sxs-lookup"><span data-stu-id="4f260-176">Data unification</span></span>

- <span data-ttu-id="4f260-177">**允许对从存储帐户中选择的实体和字段进行数据分析的灵活性**</span><span class="sxs-lookup"><span data-stu-id="4f260-177">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="4f260-178">您可以指示在您的 Azure Data Lake 存储帐户中您想要对 Common Data Model 文件夹中的哪些数据实体和字段启用数据分析作为数据引入流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="4f260-178">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="4f260-179">有关详细信息，请参阅[连接到 Common Data Model 文件夹](connect-common-data-model.md#connect-to-a-common-data-model-folder)。</span><span class="sxs-lookup"><span data-stu-id="4f260-179">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-180">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-180">Extensibility</span></span>

- <span data-ttu-id="4f260-181">**通过 Google Ads 激活您的客户细分**</span><span class="sxs-lookup"><span data-stu-id="4f260-181">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="4f260-182">将客户细分导出到 Google Ads 访问群体列表，并使用这些列表在 Google Search、Google Display Network、YouTube 和 Gmail 上投放广告。</span><span class="sxs-lookup"><span data-stu-id="4f260-182">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="4f260-183">了解有关通过 Google Ads 激活您的客户细分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-183">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="4f260-184">有关详细信息，请参阅[用于 Google Ads 的连接器](export-google-ads.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-184">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="4f260-185">**通过 Marketo 激活您的客户细分**</span><span class="sxs-lookup"><span data-stu-id="4f260-185">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="4f260-186">将客户细分导出到 Marketo 访问群体，并将这些访问群体用于市场营销自动化。</span><span class="sxs-lookup"><span data-stu-id="4f260-186">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="4f260-187">了解有关通过 Marketo 激活您的客户细分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-187">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="4f260-188">有关详细信息，请参阅[用于 Marketo 的连接器](export-marketo.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-188">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="4f260-189">**通过 DotDigital 激活您的客户细分**</span><span class="sxs-lookup"><span data-stu-id="4f260-189">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="4f260-190">将客户细分导出到 DotDigital，并将其用于市场营销目的。</span><span class="sxs-lookup"><span data-stu-id="4f260-190">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="4f260-191">了解有关通过 DotDigital 激活您的客户细分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-191">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="4f260-192">有关详细信息，请参阅[用于 DotDigital 的连接器](export-dotdigital.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-192">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="4f260-193">预测</span><span class="sxs-lookup"><span data-stu-id="4f260-193">Predictions</span></span>

- <span data-ttu-id="4f260-194">**预测交易流失**</span><span class="sxs-lookup"><span data-stu-id="4f260-194">**Predict transactional churn**</span></span>

  <span data-ttu-id="4f260-195">通过交易流失预测功能，您可以在没有数据科学家帮助的情况下，预测客户停止购买产品或服务的可能性。</span><span class="sxs-lookup"><span data-stu-id="4f260-195">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="4f260-196">使用预测分数，您可以合并有关客户的其他信息（例如客户价值），以创建高流失风险或高价值客户的客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-196">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="4f260-197">使用此客户细分以通过市场营销活动、客户支持和其他方案直接面向客户，以降低流失风险。</span><span class="sxs-lookup"><span data-stu-id="4f260-197">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="4f260-198">将流失定义配置为特定于业务的基于时间的时间范围，并定义何时将客户视为已流失。</span><span class="sxs-lookup"><span data-stu-id="4f260-198">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="4f260-199">例如，如果客户在过去 30 天内未购买任何商品，杂货店可能想要将该客户视为已流失。</span><span class="sxs-lookup"><span data-stu-id="4f260-199">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="4f260-200">在继续创建预测时，我们将指导您需要哪些数据，并允许您将业务数据映射到预测客户流失所需的字段。</span><span class="sxs-lookup"><span data-stu-id="4f260-200">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="4f260-201">您还可以根据系统中的新信息设置计划以对模型进行重新定型，从而适应不断变化的业务环境。</span><span class="sxs-lookup"><span data-stu-id="4f260-201">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="4f260-202">有关详细信息，请参阅[交易流失预测（预览）](predict-transactional-churn.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-202">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="4f260-203">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-203">System administration</span></span>

- <span data-ttu-id="4f260-204">**重置环境**</span><span class="sxs-lookup"><span data-stu-id="4f260-204">**Reset environment**</span></span>

  <span data-ttu-id="4f260-205">将所选实例的环境中的所有内容重置为全新。</span><span class="sxs-lookup"><span data-stu-id="4f260-205">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="4f260-206">有关详细信息，请参阅[重置现有环境](manage-environments.md#reset-an-existing-environment)。</span><span class="sxs-lookup"><span data-stu-id="4f260-206">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="4f260-207">**使用服务主体连接到 Azure Data Lake 存储帐户**</span><span class="sxs-lookup"><span data-stu-id="4f260-207">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="4f260-208">使用 Azure 服务主体将数据输出写入存储帐户并从中读取数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-208">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="4f260-209">现有存储帐户连接可以继续使用帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="4f260-209">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="4f260-210">它们还提供一个升级选项，以在继续操作时使用服务主体。</span><span class="sxs-lookup"><span data-stu-id="4f260-210">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="4f260-211">新连接将基于您的存储帐户的服务主体身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="4f260-211">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="4f260-212">有关详细信息，请参阅[针对访问群体见解使用 Azure 服务主体连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-212">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="4f260-213">2020 年 10 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-213">October 2020 updates</span></span>

<span data-ttu-id="4f260-214">2020 年 10 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-214">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="4f260-215">2020 年 10 月的新功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-215">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-216">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-216">Extensibility</span></span>

- <span data-ttu-id="4f260-217">**导出到 Mailchimp**</span><span class="sxs-lookup"><span data-stu-id="4f260-217">**Export to Mailchimp**</span></span>

<span data-ttu-id="4f260-218">将客户细分导出到 Mailchimp 中的现有访问群体列表，以为您的客户提供个性化的电子邮件体验。</span><span class="sxs-lookup"><span data-stu-id="4f260-218">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="4f260-219">有关详细信息，请参阅[用于 Mailchimp 的连接器](export-mailchimp.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-219">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="4f260-220">数据扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-220">Data enrichment</span></span>

- <span data-ttu-id="4f260-221">**对匹配实体中的源记录执行删除重复**</span><span class="sxs-lookup"><span data-stu-id="4f260-221">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="4f260-222">针对匹配流程中使用的实体指定删除重复以标识重复的记录。</span><span class="sxs-lookup"><span data-stu-id="4f260-222">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="4f260-223">将它们合并在一个记录中，并将所有源记录链接到该合并的记录。</span><span class="sxs-lookup"><span data-stu-id="4f260-223">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="4f260-224">然后，将在跨实体匹配流程中使用此经过删除重复的记录。</span><span class="sxs-lookup"><span data-stu-id="4f260-224">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="4f260-225">有关详细信息，请参阅[在匹配实体上定义删除重复](match-entities.md#define-deduplication-on-a-match-entity)。</span><span class="sxs-lookup"><span data-stu-id="4f260-225">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="4f260-226">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-226">System administration</span></span>

- <span data-ttu-id="4f260-227">**业务流程：合并中的新刷新选项**</span><span class="sxs-lookup"><span data-stu-id="4f260-227">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="4f260-228">在此之前，当您运行合并流程时，系统运行的是依赖于合并和后续流程的所有下游流程。</span><span class="sxs-lookup"><span data-stu-id="4f260-228">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="4f260-229">现在，您可以验证合并流程的输出（统一的客户实体），然后在下游流程（例如客户细分或度量）中使用它。</span><span class="sxs-lookup"><span data-stu-id="4f260-229">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="4f260-230">在合并页面上，您现在可以选择仅运行合并步骤并仅运行此流程。</span><span class="sxs-lookup"><span data-stu-id="4f260-230">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="4f260-231">若要还刷新所有下游流程，您可以选择运行合并和下游流程。</span><span class="sxs-lookup"><span data-stu-id="4f260-231">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="4f260-232">2020 年 9 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-232">September 2020 updates</span></span>

<span data-ttu-id="4f260-233">2020 年 9 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-233">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="4f260-234">2020 年 9 月的新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-234">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="4f260-235">活动</span><span class="sxs-lookup"><span data-stu-id="4f260-235">Activities</span></span>

- <span data-ttu-id="4f260-236">**属性语义的智能预测**</span><span class="sxs-lookup"><span data-stu-id="4f260-236">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="4f260-237">此新功能预测传递到数据统一过程的输入属性的语义类型。</span><span class="sxs-lookup"><span data-stu-id="4f260-237">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="4f260-238">它使用可提高准确性和节省时间的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="4f260-238">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="4f260-239">扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-239">Enrichments</span></span>

- <span data-ttu-id="4f260-240">**Experian 的人口统计数据扩充**</span><span class="sxs-lookup"><span data-stu-id="4f260-240">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="4f260-241">Experian 的人口统计数据扩充现在可以预览。</span><span class="sxs-lookup"><span data-stu-id="4f260-241">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="4f260-242">Experian 是消费者和企业信用报告以及营销服务的全球领导者。</span><span class="sxs-lookup"><span data-stu-id="4f260-242">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="4f260-243">借助 [Experian 的数据扩充服务](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)，您可以通过人口统计数据（如家庭人数、收入等）扩充客户配置文件，从而加深对客户的了解。</span><span class="sxs-lookup"><span data-stu-id="4f260-243">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="4f260-244">若要使用此功能，必须有有效的 Experian 订阅。</span><span class="sxs-lookup"><span data-stu-id="4f260-244">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="4f260-245">有关详细信息，请参阅[使用来自 Experian 的人口统计数据扩充客户配置文件](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="4f260-245">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="4f260-246">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-246">System administration</span></span>

- <span data-ttu-id="4f260-247">**任务详细信息窗格**</span><span class="sxs-lookup"><span data-stu-id="4f260-247">**Task details pane**</span></span>

<span data-ttu-id="4f260-248">任务详细信息窗格可让您查看系统运行的任务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-248">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="4f260-249">通过这种方式，可以轻松发现配置存在的问题并找到解决方案。</span><span class="sxs-lookup"><span data-stu-id="4f260-249">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="4f260-250">查看错误消息，了解如何解决潜在问题。</span><span class="sxs-lookup"><span data-stu-id="4f260-250">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="4f260-251">**处理添加到更多页面的信息**</span><span class="sxs-lookup"><span data-stu-id="4f260-251">**Processing information added to more pages**</span></span>

<span data-ttu-id="4f260-252">此改进在 **实体** 和 **客户** 页上添加了有关实体状态的信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-252">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="4f260-253">此外，您还可以在这两个页面上找到有关流程进度的详细信息以及任务详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-253">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="4f260-254">**系统状态页的改进**</span><span class="sxs-lookup"><span data-stu-id="4f260-254">**Improvements to system status page**</span></span>

<span data-ttu-id="4f260-255">我们改进了查看数据导出时，**系统** > **状态** 上状态详细信息表的结构。</span><span class="sxs-lookup"><span data-stu-id="4f260-255">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="4f260-256">此外，**详细信息** 列中的错误现在更详细，更具可操作性。</span><span class="sxs-lookup"><span data-stu-id="4f260-256">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="4f260-257">**“取消”将作业还原到之前状态**</span><span class="sxs-lookup"><span data-stu-id="4f260-257">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="4f260-258">当您取消某个任务时（例如，在匹配过程中），它将还原到最新状态。</span><span class="sxs-lookup"><span data-stu-id="4f260-258">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="4f260-259">例如，如果匹配过程在昨天完成，您在今天将其取消，它会还原到昨天的成功状态。</span><span class="sxs-lookup"><span data-stu-id="4f260-259">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="4f260-260">2020 年 8 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-260">August 2020 updates</span></span>

<span data-ttu-id="4f260-261">2020 年 8 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-261">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="4f260-262">2020 年 8 月的新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-262">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="4f260-263">数据统一</span><span class="sxs-lookup"><span data-stu-id="4f260-263">Data unification</span></span>

- <span data-ttu-id="4f260-264">**改进了数据统一过程中映射阶段的体验**</span><span class="sxs-lookup"><span data-stu-id="4f260-264">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="4f260-265">利用数据统一过程中映射阶段的体验，您可以以更加无缝的方式选择实体、属性和定义语义。</span><span class="sxs-lookup"><span data-stu-id="4f260-265">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="4f260-266">这些更改包括：</span><span class="sxs-lookup"><span data-stu-id="4f260-266">The changes include:</span></span>
  
  - <span data-ttu-id="4f260-267">添加实体和字段所需的交互更少</span><span class="sxs-lookup"><span data-stu-id="4f260-267">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="4f260-268">改进了映射页上的搜索功能</span><span class="sxs-lookup"><span data-stu-id="4f260-268">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="4f260-269">可以轻松直观地识别建议的字段类型</span><span class="sxs-lookup"><span data-stu-id="4f260-269">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="4f260-270">扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-270">Enrichment</span></span>

- <span data-ttu-id="4f260-271">**兴趣相似性扩充在更多市场中可用**</span><span class="sxs-lookup"><span data-stu-id="4f260-271">**Interest affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="4f260-272">我们正在将兴趣相似性扩充的可用性扩展到美国以外的其他五个市场：加拿大、澳大利亚、英国、法国德国。</span><span class="sxs-lookup"><span data-stu-id="4f260-272">We're extending the availability of the interest affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="4f260-273">通过此扩展，您可以用适用于这些市场更多兴趣来扩充客户数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-273">With this extension, you can enrich your customer data with more interests applicable to these markets.</span></span> <span data-ttu-id="4f260-274">我们还将使用来自 Microsoft Graph 的本地专有数据来扩充您在这些市场中的客户资料。</span><span class="sxs-lookup"><span data-stu-id="4f260-274">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="4f260-275">有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="4f260-275">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="4f260-276">2020 年 7 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-276">July 2020 updates</span></span>

<span data-ttu-id="4f260-277">2020 年 7 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-277">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="4f260-278">2020 年 7 月的新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-278">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-279">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-279">Extensibility</span></span>

- <span data-ttu-id="4f260-280">**Power Automate 已完成统一过程触发器**</span><span class="sxs-lookup"><span data-stu-id="4f260-280">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="4f260-281">我们扩展了 Power Automate 的触发器，允许您在统一过程（映射、匹配、合并）的刷新完成时创建通知或操作。</span><span class="sxs-lookup"><span data-stu-id="4f260-281">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="4f260-282">有关详细信息，请参阅 [Power Automate 连接器](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="4f260-282">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="4f260-283">扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-283">Enrichment</span></span>

- <span data-ttu-id="4f260-284">**品牌相似性扩充在更多市场中可用**</span><span class="sxs-lookup"><span data-stu-id="4f260-284">**Brand affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="4f260-285">我们正在将品牌相似性扩充的可用性扩展到美国以外的其他五个市场：加拿大、澳大利亚、英国、法国德国。</span><span class="sxs-lookup"><span data-stu-id="4f260-285">We're extending the availability of the brand affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="4f260-286">通过此扩展，您可以利用这些市场的本地品牌来扩充您的客户数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-286">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="4f260-287">我们还将使用来自 Microsoft Graph 的本地专有数据来扩充您在这些市场中的客户资料。</span><span class="sxs-lookup"><span data-stu-id="4f260-287">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="4f260-288">有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="4f260-288">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="4f260-289">2020 年 6 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-289">June 2020 updates</span></span>

<span data-ttu-id="4f260-290">2020 年 6 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-290">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="4f260-291">2020 年 6 月的新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-291">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="4f260-292">扩充</span><span class="sxs-lookup"><span data-stu-id="4f260-292">Enrichment</span></span>

- <span data-ttu-id="4f260-293">**使用来自 Leadspace 的公司数据扩充**</span><span class="sxs-lookup"><span data-stu-id="4f260-293">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="4f260-294">在统一客户资料中定义用于从 Leadspace 查找相关公司数据的字段。</span><span class="sxs-lookup"><span data-stu-id="4f260-294">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="4f260-295">运行扩充过程后，B2B 配置文件将使用更多属性进行扩充，包括公司规模、位置、行业等。</span><span class="sxs-lookup"><span data-stu-id="4f260-295">After running the enrichment process, B2B profiles are enriched with more attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="4f260-296">通过这种协作，您可以利用第三方服务的输入来提高数据质量。</span><span class="sxs-lookup"><span data-stu-id="4f260-296">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="4f260-297">要使用此扩充，您需要获得 Leadspace 的许可证来访问其 B2B 公司数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-297">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="4f260-298">系统将使用该许可证以使您的数据持续扩充。</span><span class="sxs-lookup"><span data-stu-id="4f260-298">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="4f260-299">有关详细信息，请参阅[利用 Leadspace 扩充公司资料](enrichment-leadspace.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-299">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="4f260-300">**扩充中心页面**</span><span class="sxs-lookup"><span data-stu-id="4f260-300">**Enrichment hub page**</span></span>

  <span data-ttu-id="4f260-301">来自第一方和第三方扩充提供商的所有可用数据扩充都在同一位置进行配置。</span><span class="sxs-lookup"><span data-stu-id="4f260-301">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="4f260-302">配置数据扩充是一种无缝体验，从一个公共位置进行管理。</span><span class="sxs-lookup"><span data-stu-id="4f260-302">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="4f260-303">有关详细信息，请参阅[客户资料扩充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-303">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="4f260-304">**拆分品牌和兴趣相似性扩充**</span><span class="sxs-lookup"><span data-stu-id="4f260-304">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="4f260-305">品牌和兴趣相似性现在可以作为两个独立扩充提供。</span><span class="sxs-lookup"><span data-stu-id="4f260-305">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="4f260-306">拆分的扩充使您可以根据业务要求或需求灵活地单独进行配置和管理。</span><span class="sxs-lookup"><span data-stu-id="4f260-306">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="4f260-307">有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-307">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-308">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-308">Extensibility</span></span>

- <span data-ttu-id="4f260-309">**Dynamics 365 客户卡加载项上统一活动的可点击 URL**</span><span class="sxs-lookup"><span data-stu-id="4f260-309">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="4f260-310">客户卡加载项中的统一活动现在显示可单击的 URL，前提是已在配置活动期间定义此类 URL。</span><span class="sxs-lookup"><span data-stu-id="4f260-310">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="4f260-311">有关详细信息，请参阅[客户卡加载项](customer-card-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-311">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="4f260-312">**Dynamics 365 客户卡加载项上提供品牌和兴趣相似性**</span><span class="sxs-lookup"><span data-stu-id="4f260-312">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="4f260-313">使用 Dynamics 365 客户卡加载项上的新控件，您可以在 Dynamics 365 中客户互动应用中的联系人上显示品牌和兴趣扩充。</span><span class="sxs-lookup"><span data-stu-id="4f260-313">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="4f260-314">有关详细信息，请参阅[客户卡加载项](customer-card-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-314">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="4f260-315">**更多 Power Automate 触发器**</span><span class="sxs-lookup"><span data-stu-id="4f260-315">**More Power Automate triggers**</span></span>

  <span data-ttu-id="4f260-316">我们扩展了 Power Automate 的触发器，增加了以下触发器：</span><span class="sxs-lookup"><span data-stu-id="4f260-316">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="4f260-317">在自动完全刷新（数据源、统一、客户细分、度量、导出）完成时，获取通知或执行操作</span><span class="sxs-lookup"><span data-stu-id="4f260-317">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="4f260-318">为业务度量定义阈值。</span><span class="sxs-lookup"><span data-stu-id="4f260-318">Define a threshold for a business measure.</span></span> <span data-ttu-id="4f260-319">例如，您可以创建一个在超过定义的阈值时发送的通知。</span><span class="sxs-lookup"><span data-stu-id="4f260-319">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="4f260-320">此外，触发器还带来了一些信息，使您可以在 Power Automate 中构建更复杂的工作流。</span><span class="sxs-lookup"><span data-stu-id="4f260-320">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="4f260-321">有关详细信息，请参阅 [Power Automate 连接器](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="4f260-321">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="4f260-322">**导出到 Facebook 广告管理器**</span><span class="sxs-lookup"><span data-stu-id="4f260-322">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="4f260-323">此功能允许您将客户细分导出到 Facebook Ads Manager。</span><span class="sxs-lookup"><span data-stu-id="4f260-323">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="4f260-324">在 Facebook 市场营销活动和广告中，客户细分将导出为客户访问群体以使用统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="4f260-324">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="4f260-325">自定义受众也可用于通过 Facebook 广告管理器在 Instagram 上创建市场活动。</span><span class="sxs-lookup"><span data-stu-id="4f260-325">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="4f260-326">有关详细信息，请参阅 [Facebook 广告管理器的连接器](export-facebook.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-326">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="4f260-327">预测</span><span class="sxs-lookup"><span data-stu-id="4f260-327">Predictions</span></span>

- <span data-ttu-id="4f260-328">**订阅流失预测**</span><span class="sxs-lookup"><span data-stu-id="4f260-328">**Subscription churn prediction**</span></span>

  <span data-ttu-id="4f260-329">按照引导式体验，在云服务、客户成员身份和其他分区等订阅区域创建流失预测。</span><span class="sxs-lookup"><span data-stu-id="4f260-329">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="4f260-330">订阅流失预测功能使您可以在不依靠数据科学家的情况下，预测客户停止使用基于订阅的产品或服务的可能性。</span><span class="sxs-lookup"><span data-stu-id="4f260-330">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="4f260-331">使用预测分数，您可以结合有关客户的其他信息来创建高流失风险的客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-331">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="4f260-332">借助此客户细分，您可以直接面向市场营销、客户支持和其他方案中的客户，以降低特定客户的流失风险，从而提高收入并降低成本。</span><span class="sxs-lookup"><span data-stu-id="4f260-332">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="4f260-333">在此体验中，您可以将客户流失的定义配置为特定于您的业务的基于时间的窗口。</span><span class="sxs-lookup"><span data-stu-id="4f260-333">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="4f260-334">例如，具有每月订阅流程的视频流业务可能需要考虑在订阅期满 15 天后已流失的客户。</span><span class="sxs-lookup"><span data-stu-id="4f260-334">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="4f260-335">在继续进行预测时，我们将指导您确定需要哪些数据，并使您能够将有关业务的数据映射到预测客户流失所需的字段。</span><span class="sxs-lookup"><span data-stu-id="4f260-335">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="4f260-336">随着业务信息的更改，您还可以设置时间表来重新训练系统中的新信息，以适应不断变化的业务环境。</span><span class="sxs-lookup"><span data-stu-id="4f260-336">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="4f260-337">有关详细信息，请参阅[订阅流失预测（预览）](predict-subscription-churn.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-337">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="4f260-338">客户细分</span><span class="sxs-lookup"><span data-stu-id="4f260-338">Segments</span></span>

- <span data-ttu-id="4f260-339">**查找相似客户**</span><span class="sxs-lookup"><span data-stu-id="4f260-339">**Find similar customers**</span></span>
  
  <span data-ttu-id="4f260-340">使用人工智能在您的客户群中查找相似客户。</span><span class="sxs-lookup"><span data-stu-id="4f260-340">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="4f260-341">二元分类机器学习模型为扩展客户细分中的客户分配相似性分数。</span><span class="sxs-lookup"><span data-stu-id="4f260-341">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="4f260-342">分数基于与源客户细分中客户的相似性。</span><span class="sxs-lookup"><span data-stu-id="4f260-342">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="4f260-343">根据相似性分数，客户资料将添加到新创建的客户细分中。</span><span class="sxs-lookup"><span data-stu-id="4f260-343">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="4f260-344">它在数字营销中有时称为相似模型，此模型使用 AI 模型，通过考虑更多属性来帮助查找与另一个客户细分中的客户相似的客户。</span><span class="sxs-lookup"><span data-stu-id="4f260-344">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in more attributes.</span></span> <span data-ttu-id="4f260-345">它不仅允许您选择属性，还允许您指定应属于此新客户细分的最大客户数量。</span><span class="sxs-lookup"><span data-stu-id="4f260-345">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="4f260-346">然后，AI 模型将根据您选择的属性为每个客户计算相似性分数，并查找平均相似性分数较高的客户。</span><span class="sxs-lookup"><span data-stu-id="4f260-346">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="4f260-347">最终的客户细分将包括看起来与原始客户细分中的客户相似的客户。</span><span class="sxs-lookup"><span data-stu-id="4f260-347">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="4f260-348">有关详细信息，请参阅[相似客户](find-similar-customer-segments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-348">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="4f260-349">**客户细分重叠和差异**</span><span class="sxs-lookup"><span data-stu-id="4f260-349">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="4f260-350">通过客户细分重叠，您可以查看两个或多个客户细分共有多少个客户以及哪些客户是共同的。</span><span class="sxs-lookup"><span data-stu-id="4f260-350">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="4f260-351">例如，高消费客户细分与高满意度客户细分的重叠情况，或流失客户细分与低满意度客户细分的重叠情况。</span><span class="sxs-lookup"><span data-stu-id="4f260-351">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="4f260-352">此外，您可以根据您选择的额外属性来分析重叠的变化方式。</span><span class="sxs-lookup"><span data-stu-id="4f260-352">Additionally, you can analyze how the overlap changes based on an extra attribute of your choice.</span></span>

  <span data-ttu-id="4f260-353">客户细分差异发现一个细分与其余客户或另一个客户细分之间有哪些不同。</span><span class="sxs-lookup"><span data-stu-id="4f260-353">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="4f260-354">您要做的就是确定一个客户细分，然后系统将确定资料属性和度量，来以经过排名的差异列表（从最强差异到最弱差异）的形式区分该客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-354">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="4f260-355">有关详细信息，请参阅[客户细分见解（预览）](segment-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-355">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="4f260-356">**客户细分生命周期**</span><span class="sxs-lookup"><span data-stu-id="4f260-356">**Segment lifetime**</span></span>
  
  <span data-ttu-id="4f260-357">定义激活或停用客户细分的计划。</span><span class="sxs-lookup"><span data-stu-id="4f260-357">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="4f260-358">有关详细信息，请参阅[管理现有客户细分](segments.md#manage-existing-segments)。</span><span class="sxs-lookup"><span data-stu-id="4f260-358">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="4f260-359">2020 年 5 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-359">May 2020 updates</span></span>

<span data-ttu-id="4f260-360">2020 年 5 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-360">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="4f260-361">2020 年 5 月的新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-361">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="4f260-362">数据引入</span><span class="sxs-lookup"><span data-stu-id="4f260-362">Data ingestion</span></span>

- <span data-ttu-id="4f260-363">**实时数据引入：历史记录视图**</span><span class="sxs-lookup"><span data-stu-id="4f260-363">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="4f260-364">使用我们的 API 引入实时更新时，您可以在 30 天内看到这些更新的汇总历史记录。</span><span class="sxs-lookup"><span data-stu-id="4f260-364">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="4f260-365">您有权访问所有成功或失败的 API 调用的集合，包括它们的结果、源系统和其他有用的元数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-365">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="4f260-366">有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-366">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="4f260-367">**实时数据引入：配置文件更新**</span><span class="sxs-lookup"><span data-stu-id="4f260-367">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="4f260-368">实时数据引入的这种扩展使您可以在几秒钟内看到对特定用户配置文件字段的更改。</span><span class="sxs-lookup"><span data-stu-id="4f260-368">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="4f260-369">除了活动的实时功能外，系统还支持对配置文件字段进行低延迟更新。</span><span class="sxs-lookup"><span data-stu-id="4f260-369">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="4f260-370">配置文件字段的实时更新具有到期时间，因此不能替代计划刷新。</span><span class="sxs-lookup"><span data-stu-id="4f260-370">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="4f260-371">有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-371">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-372">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-372">Extensibility</span></span>

- <span data-ttu-id="4f260-373">**更新了客户卡加载项上的时间线和分页**</span><span class="sxs-lookup"><span data-stu-id="4f260-373">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="4f260-374">客户卡加载项解决方案的时间线与活动时间线相匹配。</span><span class="sxs-lookup"><span data-stu-id="4f260-374">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="4f260-375">时间线的分页进行了改进，一次最多可显示 50 个活动。</span><span class="sxs-lookup"><span data-stu-id="4f260-375">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="4f260-376">它还允许在时间线中加载更多活动。</span><span class="sxs-lookup"><span data-stu-id="4f260-376">It also allows loading more activities in the timeline.</span></span>    
  <span data-ttu-id="4f260-377">有关详细信息，请参阅[客户卡加载项](customer-card-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-377">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="4f260-378">**用于客户细分更改的 Power Automate 触发器**</span><span class="sxs-lookup"><span data-stu-id="4f260-378">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="4f260-379">Power Automate 的触发器定义可以从其构建流的内容。</span><span class="sxs-lookup"><span data-stu-id="4f260-379">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="4f260-380">新添加的触发器可让您定义客户细分的阈值。</span><span class="sxs-lookup"><span data-stu-id="4f260-380">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="4f260-381">例如，您可以创建一个在超过定义的阈值时发送的通知。</span><span class="sxs-lookup"><span data-stu-id="4f260-381">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="4f260-382">有关详细信息，请参阅 [Power Automate 连接器](export-power-automate.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-382">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="4f260-383">**对自定义模型的多组织支持**</span><span class="sxs-lookup"><span data-stu-id="4f260-383">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="4f260-384">使用其他 Azure 机器学习租户的 Web 服务为自定义模型配置工作流。</span><span class="sxs-lookup"><span data-stu-id="4f260-384">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="4f260-385">在为自定义模型创建新的工作流时，您可以登录到 Azure 机器学习租户。</span><span class="sxs-lookup"><span data-stu-id="4f260-385">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="4f260-386">此功能是与您自己的自定义 Azure 机器学习 Web 服务集成的现有功能的补充。</span><span class="sxs-lookup"><span data-stu-id="4f260-386">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="4f260-387">有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-387">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="4f260-388">客户细分</span><span class="sxs-lookup"><span data-stu-id="4f260-388">Segments</span></span>

- <span data-ttu-id="4f260-389">**实体路径自动化**</span><span class="sxs-lookup"><span data-stu-id="4f260-389">**Entity path automation**</span></span>

  <span data-ttu-id="4f260-390">在创建客户细分时，用户需要定义实体路径。</span><span class="sxs-lookup"><span data-stu-id="4f260-390">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="4f260-391">此功能迈出了自动化实体路径定义的第一步，让您可以专注于要考虑的细分划分条件。</span><span class="sxs-lookup"><span data-stu-id="4f260-391">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="4f260-392">如果要用来细分客户的实体与统一的客户实体直接相关，则无需再定义实体路径。</span><span class="sxs-lookup"><span data-stu-id="4f260-392">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="4f260-393">但是，如果存在多个可能的实体路径，则仍然需要手动定义它。</span><span class="sxs-lookup"><span data-stu-id="4f260-393">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="4f260-394">**对多个客户细分执行的操作**</span><span class="sxs-lookup"><span data-stu-id="4f260-394">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="4f260-395">用户可以单击选择多个客户细分并对其执行操作，如刷新客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-395">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="4f260-396">**刷新细分**</span><span class="sxs-lookup"><span data-stu-id="4f260-396">**Refresh segments**</span></span>

  <span data-ttu-id="4f260-397">用户可以刷新单个客户细分或仅选择他们想要刷新的客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-397">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="4f260-398">**对复合客户细分的改进**</span><span class="sxs-lookup"><span data-stu-id="4f260-398">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="4f260-399">用户可以创建、编辑和删除基于其他客户细分的客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-399">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="4f260-400">例如，在基于其他客户细分构建的另一个客户细分的基础上构建的客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-400">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="4f260-401">**客户细分列表页**</span><span class="sxs-lookup"><span data-stu-id="4f260-401">**Segment list page**</span></span>

  <span data-ttu-id="4f260-402">客户细分页面的新设计使用一种列表格式，可让您一次查看更多客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-402">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="4f260-403">添加了搜索字段可快速查找客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-403">A search field is added to find segments quickly.</span></span> <span data-ttu-id="4f260-404">用户现在可以一次在多个客户细分上应用诸如下载或删除之类的操作。</span><span class="sxs-lookup"><span data-stu-id="4f260-404">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="4f260-405">引入了新的趋势体验，可以快速发现客户细分的重大变化。</span><span class="sxs-lookup"><span data-stu-id="4f260-405">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="4f260-406">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-406">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="4f260-407">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-407">System administration</span></span>

- <span data-ttu-id="4f260-408">**Microsoft Dynamics 365 Online Government 中提供的 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="4f260-408">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="4f260-409">交互渠道越来越多，公民数据散布在无数个系统中，导致数据孤立，掌握的公民交互信息零碎。</span><span class="sxs-lookup"><span data-stu-id="4f260-409">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="4f260-410">如果不能全面了解每个公民在各个渠道中的交互情况，政府就不可能大规模进行现代化。</span><span class="sxs-lookup"><span data-stu-id="4f260-410">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="4f260-411">Microsoft 致力于支持政府在满足公民对一致和响应式体验的期望方面的技术需求。</span><span class="sxs-lookup"><span data-stu-id="4f260-411">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="4f260-412">在 2020 年发行版本第 1 波中，Dynamics 365 Customer Insights 将面向政府社区云 (GCC) 提供，该环境旨在满足美国政府机构的更高合规性需求。</span><span class="sxs-lookup"><span data-stu-id="4f260-412">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="4f260-413">政府机构获得公民的统一信息，使用预构建的 AI 来获得改进交互、提升员工和改变社区的见解，同时降低 IT 复杂性并满足美国的合规性与安全标准。</span><span class="sxs-lookup"><span data-stu-id="4f260-413">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="4f260-414">Dynamics 365 Government 可以满足美国联邦风险与授权管理计划 (FedRAMP) 的严苛要求，让美国联邦机构可以从 Microsoft Cloud 节省的成本和严格的安全性中受益。</span><span class="sxs-lookup"><span data-stu-id="4f260-414">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="4f260-415">2020 年 4 月更新</span><span class="sxs-lookup"><span data-stu-id="4f260-415">April 2020 updates</span></span>

<span data-ttu-id="4f260-416">2020 年 4 月的更新中包括多项功能、性能升级和 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="4f260-416">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="4f260-417">2020 年 4 月的新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="4f260-417">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="4f260-418">活动</span><span class="sxs-lookup"><span data-stu-id="4f260-418">Activities</span></span>

- <span data-ttu-id="4f260-419">**将活动实体映射到标准活动类型**</span><span class="sxs-lookup"><span data-stu-id="4f260-419">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="4f260-420">活动配置和存储当前基于静态设计，可以在时间线中进行查看。</span><span class="sxs-lookup"><span data-stu-id="4f260-420">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="4f260-421">活动的语义含义在 AI 模型中可能有多个用例，目前尚未完全使用。</span><span class="sxs-lookup"><span data-stu-id="4f260-421">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="4f260-422">我们计划根据活动类型和对活动的更好的语义理解，使活动时间线更加动态。</span><span class="sxs-lookup"><span data-stu-id="4f260-422">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="4f260-423">此功能用于识别 Common Data Model 中为任何一个引入的活动定义的活动类型。</span><span class="sxs-lookup"><span data-stu-id="4f260-423">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="4f260-424">有关详细信息，请参阅[自定义活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-424">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="4f260-425">数据引入</span><span class="sxs-lookup"><span data-stu-id="4f260-425">Data ingestion</span></span>

- <span data-ttu-id="4f260-426">**实时数据引入：活动**</span><span class="sxs-lookup"><span data-stu-id="4f260-426">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="4f260-427">实时数据引入将立即提供数据以供使用，直到后续计划刷新从数据源中提取此数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-427">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="4f260-428">有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-428">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="4f260-429">**对数据准备的改进**</span><span class="sxs-lookup"><span data-stu-id="4f260-429">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="4f260-430">了解有关实体中引入的数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f260-430">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="4f260-431">通过数据摘要，您可以了解可帮助采取相应操作的数据质量特征。</span><span class="sxs-lookup"><span data-stu-id="4f260-431">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="4f260-432">有关详细信息，请参阅[探索实体数据](entities.md#exploring-a-specific-entitys-data)。</span><span class="sxs-lookup"><span data-stu-id="4f260-432">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="4f260-433">**使用 Common Data Service 从 Dynamics 365 引入分析数据**</span><span class="sxs-lookup"><span data-stu-id="4f260-433">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="4f260-434">Common Data Service 可用作创建数据源的一种方式。</span><span class="sxs-lookup"><span data-stu-id="4f260-434">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="4f260-435">现有 Dynamics 365 客户可以将分析实体从 Common Data Service 引入到 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="4f260-435">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="4f260-436">单个数据源可以在 Customer Insights 环境中同时使用相同的 Common Data Service 托管湖。</span><span class="sxs-lookup"><span data-stu-id="4f260-436">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="4f260-437">有关详细信息，请参阅[连接到 Common Data Service 托管数据湖中的数据](connect-common-data-service-lake.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-437">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="4f260-438">扩展性</span><span class="sxs-lookup"><span data-stu-id="4f260-438">Extensibility</span></span>

- <span data-ttu-id="4f260-439">**导出至 LiveRamp**</span><span class="sxs-lookup"><span data-stu-id="4f260-439">**Export to LiveRamp**</span></span>

  <span data-ttu-id="4f260-440">在 LiveRamp® 中激活数据，以便跨数字、社交和 TV 生态系统与超过 500 个平台连接。</span><span class="sxs-lookup"><span data-stu-id="4f260-440">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="4f260-441">使用 LiveRamp 中的数据来定位、隐藏和个性化广告活动。</span><span class="sxs-lookup"><span data-stu-id="4f260-441">Use your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="4f260-442">有关详细信息，请参阅 [LiveRamp&reg; 连接器](export-liveramp.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-442">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="4f260-443">**Customer Insights Teams 加载项**</span><span class="sxs-lookup"><span data-stu-id="4f260-443">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="4f260-444">机器人为统一客服配置文件提供查找功能。</span><span class="sxs-lookup"><span data-stu-id="4f260-444">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="4f260-445">它将显示一张卡，其中最多可包含来自生成的客户资料的 15 个字段。</span><span class="sxs-lookup"><span data-stu-id="4f260-445">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="4f260-446">多个匹配项将返回可在其中选择配置文件的结果的列表。</span><span class="sxs-lookup"><span data-stu-id="4f260-446">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="4f260-447">有关详细信息，请参阅 [Customer Insights 的 Teams 机器人](export-teams-bot.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-447">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="4f260-448">度量</span><span class="sxs-lookup"><span data-stu-id="4f260-448">Measures</span></span>

- <span data-ttu-id="4f260-449">**度量列表页**</span><span class="sxs-lookup"><span data-stu-id="4f260-449">**Measure list page**</span></span>
  
  <span data-ttu-id="4f260-450">度量页面的改进包括对一个度量和一次多个度量执行操作的支持。</span><span class="sxs-lookup"><span data-stu-id="4f260-450">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="4f260-451">此外，您还会发现一个搜索字段，可以用来快速查找和跟踪度量。</span><span class="sxs-lookup"><span data-stu-id="4f260-451">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="4f260-452">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-452">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="4f260-453">**对复合度量的改进**</span><span class="sxs-lookup"><span data-stu-id="4f260-453">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="4f260-454">用户可以创建、编辑和删除基于其他度量的度量。</span><span class="sxs-lookup"><span data-stu-id="4f260-454">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="4f260-455">例如，在基于其他度量构建的另一个度量的基础上构建的度量。</span><span class="sxs-lookup"><span data-stu-id="4f260-455">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="4f260-456">客户细分</span><span class="sxs-lookup"><span data-stu-id="4f260-456">Segments</span></span>

- <span data-ttu-id="4f260-457">**其他运算符**</span><span class="sxs-lookup"><span data-stu-id="4f260-457">**Another operator**</span></span>
  
  <span data-ttu-id="4f260-458">In-set 运算符允许按几个可能的字符串值对客户进行细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-458">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="4f260-459">在添加此运算符之前，您必须使用多个 OR 条件构建此类客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-459">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="4f260-460">In-set 运算符让您可以在一个条件下执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4f260-460">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="4f260-461">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-461">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="4f260-462">系统管理</span><span class="sxs-lookup"><span data-stu-id="4f260-462">System administration</span></span>

- <span data-ttu-id="4f260-463">**将配置设置复制到新环境**</span><span class="sxs-lookup"><span data-stu-id="4f260-463">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="4f260-464">将您的配置从一个环境复制到另一个环境。</span><span class="sxs-lookup"><span data-stu-id="4f260-464">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="4f260-465">创建新环境时，可以选择要从中复制配置的现有环境。</span><span class="sxs-lookup"><span data-stu-id="4f260-465">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="4f260-466">当前，我们支持复制数据源、数据统一、关系、度量和客户细分。</span><span class="sxs-lookup"><span data-stu-id="4f260-466">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="4f260-467">不会复制数据源凭据和实际数据。</span><span class="sxs-lookup"><span data-stu-id="4f260-467">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="4f260-468">有关详细信息，请参阅[管理环境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f260-468">For more information, see [Manage environments](manage-environments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]