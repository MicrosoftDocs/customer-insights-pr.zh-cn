---
title: 使用来自 Microsoft 的数据扩充客户配置文件
description: 使用来自 Microsoft 的专有数据用品牌和兴趣相似性扩充客户配置文件。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896591"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="dea62-103">使用品牌和兴趣相似性扩充客户配置文件（预览版）</span><span class="sxs-lookup"><span data-stu-id="dea62-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="dea62-104">使用 Microsoft 的专有数据用品牌和兴趣相似性扩充客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="dea62-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="dea62-105">这些相似性基于与您的客户具有相似人口统计信息的人员的数据确定。</span><span class="sxs-lookup"><span data-stu-id="dea62-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="dea62-106">这些信息可帮助您根据客户在特定品牌和兴趣方面的相似性更好地了解和细分客户。</span><span class="sxs-lookup"><span data-stu-id="dea62-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="dea62-107">在访问群体见解中，转到 **数据** > **扩充** 以[配置和查看扩充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="dea62-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="dea62-108">若要配置品牌相似性扩充，请转到 **发现** 选项卡，并选择 **品牌** 磁贴上的 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="dea62-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="dea62-109">若要配置兴趣相似性扩充，请转到 **发现** 选项卡，并选择 **兴趣** 磁贴上的 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="dea62-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dea62-110">![品牌和兴趣磁贴](media/BrandsInterest-tile-Hub.png "品牌和兴趣磁贴")</span><span class="sxs-lookup"><span data-stu-id="dea62-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="dea62-111">我们如何确定相似性</span><span class="sxs-lookup"><span data-stu-id="dea62-111">How we determine affinities</span></span>

<span data-ttu-id="dea62-112">我们使用 Microsoft 的在线搜索数据来查找不同人口统计细分市场（按年龄、性别或位置定义）的品牌和兴趣相似性。</span><span class="sxs-lookup"><span data-stu-id="dea62-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="dea62-113">品牌或兴趣的联机搜索量决定人口统计细分与其他细分相比在该品牌或兴趣方面的相似程度。</span><span class="sxs-lookup"><span data-stu-id="dea62-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="dea62-114">品牌或兴趣。</span><span class="sxs-lookup"><span data-stu-id="dea62-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="dea62-115">相似性级别和分数</span><span class="sxs-lookup"><span data-stu-id="dea62-115">Affinity level and score</span></span>

<span data-ttu-id="dea62-116">在每个扩充的客户配置文件中，我们将提供两个相关值 - 相似性级别和相似性分数。</span><span class="sxs-lookup"><span data-stu-id="dea62-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="dea62-117">这些值有助于确定与其他人口统计客户细分相比，该配置文件的人口统计客户细分中品牌或兴趣的相似性强度。</span><span class="sxs-lookup"><span data-stu-id="dea62-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="dea62-118">*相似性级别* 由四个级别组成，并且 *相似性分数* 是根据映射到相似性级别的100 分等级计算的。</span><span class="sxs-lookup"><span data-stu-id="dea62-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="dea62-119">相似性级别</span><span class="sxs-lookup"><span data-stu-id="dea62-119">Affinity level</span></span> |<span data-ttu-id="dea62-120">关联分数</span><span class="sxs-lookup"><span data-stu-id="dea62-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="dea62-121">非常高</span><span class="sxs-lookup"><span data-stu-id="dea62-121">Very high</span></span>     | <span data-ttu-id="dea62-122">85-100</span><span class="sxs-lookup"><span data-stu-id="dea62-122">85-100</span></span>       |
|<span data-ttu-id="dea62-123">高</span><span class="sxs-lookup"><span data-stu-id="dea62-123">High</span></span>     | <span data-ttu-id="dea62-124">70-84</span><span class="sxs-lookup"><span data-stu-id="dea62-124">70-84</span></span>        |
|<span data-ttu-id="dea62-125">中</span><span class="sxs-lookup"><span data-stu-id="dea62-125">Medium</span></span>     | <span data-ttu-id="dea62-126">35-69</span><span class="sxs-lookup"><span data-stu-id="dea62-126">35-69</span></span>        |
|<span data-ttu-id="dea62-127">低</span><span class="sxs-lookup"><span data-stu-id="dea62-127">Low</span></span>     | <span data-ttu-id="dea62-128">1-34</span><span class="sxs-lookup"><span data-stu-id="dea62-128">1-34</span></span>        |

<span data-ttu-id="dea62-129">取决于想要用于测量相似性的粒度，您可以使用相似性级别或分数。</span><span class="sxs-lookup"><span data-stu-id="dea62-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="dea62-130">相似性分数使您可以更精确地进行控制。</span><span class="sxs-lookup"><span data-stu-id="dea62-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="dea62-131">支持的国家/地区</span><span class="sxs-lookup"><span data-stu-id="dea62-131">Supported countries/regions</span></span>

<span data-ttu-id="dea62-132">目前，我们支持以下国家/地区选项：澳大利亚、加拿大（英语）、法国、德国、英国或美国（英语）。</span><span class="sxs-lookup"><span data-stu-id="dea62-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="dea62-133">要选择国家/地区，打开 **品牌扩充** 或 **兴趣扩充**，然后选择 **国家/地区** 旁边的 **更改**。</span><span class="sxs-lookup"><span data-stu-id="dea62-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="dea62-134">在 **国家/地区设置** 窗格中，选择一个选项，然后选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="dea62-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="dea62-135">与国家/地区选择相关的含义</span><span class="sxs-lookup"><span data-stu-id="dea62-135">Implications related to country selection</span></span>

- <span data-ttu-id="dea62-136">在[选择自己的品牌](#define-your-brands-or-interests)时，系统会基于所选的国家/地区提供建议。</span><span class="sxs-lookup"><span data-stu-id="dea62-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="dea62-137">在[选择行业](#define-your-brands-or-interests)时，您将基于所选国家/地区获得最相关的品牌或兴趣。</span><span class="sxs-lookup"><span data-stu-id="dea62-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="dea62-138">在[扩充配置文件](#refresh-enrichment)时，我们将扩充获取所选品牌和兴趣数据所针对的所有客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="dea62-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="dea62-139">包括未在选定国家/地区中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="dea62-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="dea62-140">例如，如果您选择了德国，并且我们有可用于美国中的选定品牌和兴趣的数据，那么我们将扩充位于美国的个人资料。</span><span class="sxs-lookup"><span data-stu-id="dea62-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="dea62-141">配置扩充</span><span class="sxs-lookup"><span data-stu-id="dea62-141">Configure Enrichment</span></span>

<span data-ttu-id="dea62-142">引导式体验可帮助您完成扩充配置。</span><span class="sxs-lookup"><span data-stu-id="dea62-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="dea62-143">定义您的品牌或兴趣</span><span class="sxs-lookup"><span data-stu-id="dea62-143">Define your brands or interests</span></span>

<span data-ttu-id="dea62-144">请选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="dea62-144">Select one of the following options:</span></span>

- <span data-ttu-id="dea62-145">**行业**：系统确定与您的行业有关的排名靠前品牌或兴趣，并将其用于扩充您的客户数据。</span><span class="sxs-lookup"><span data-stu-id="dea62-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="dea62-146">**选择您自己的项目**：从品牌或兴趣列表中选择最多五个与您的组织关系最近的项。</span><span class="sxs-lookup"><span data-stu-id="dea62-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="dea62-147">若要添加品牌或兴趣，请在输入区域中输入该品牌或兴趣，以获取基于匹配项的建议。</span><span class="sxs-lookup"><span data-stu-id="dea62-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="dea62-148">如果我们未列出您在查找的品牌或兴趣，请使用 **建议** 链接向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="dea62-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="dea62-149">查看扩充首选项</span><span class="sxs-lookup"><span data-stu-id="dea62-149">Review enrichment preferences</span></span>

<span data-ttu-id="dea62-150">查看默认扩充首选项，然后根据需要更新这些首选项。</span><span class="sxs-lookup"><span data-stu-id="dea62-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="扩充首选项窗口的屏幕截图。":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="dea62-152">选择要扩充的实体</span><span class="sxs-lookup"><span data-stu-id="dea62-152">Select entity to enrich</span></span>

<span data-ttu-id="dea62-153">选择 **扩充的实体**，然后选择您希望利用 Microsoft 提供的公司数据扩充的数据集。</span><span class="sxs-lookup"><span data-stu-id="dea62-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="dea62-154">您可以选择客户实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="dea62-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="dea62-155">映射字段</span><span class="sxs-lookup"><span data-stu-id="dea62-155">Map your fields</span></span>

<span data-ttu-id="dea62-156">映射来自统一客户实体的字段，以定义希望系统用于扩充客户数据的人口统计客户细分。</span><span class="sxs-lookup"><span data-stu-id="dea62-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="dea62-157">映射国家/地区，并至少映射“出生日期”或“性别”属性。</span><span class="sxs-lookup"><span data-stu-id="dea62-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="dea62-158">此外，必须至少映射一个市/县（和省/市/自治区）或邮政编码。</span><span class="sxs-lookup"><span data-stu-id="dea62-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="dea62-159">选择 **编辑** 以定义字段的映射，然后在完成后选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="dea62-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="dea62-160">选择 **保存** 完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="dea62-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="dea62-161">支持下列格式和值，值不区分大小写：</span><span class="sxs-lookup"><span data-stu-id="dea62-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="dea62-162">**出生日期**：我们建议在数据引入期间将出生日期转换为日期/时间类型。</span><span class="sxs-lookup"><span data-stu-id="dea62-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="dea62-163">或者，可以使用 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 格式“yyyy-MM-dd”或“yyyy-MM-ddTHH:mm:ssZ”的字符串。</span><span class="sxs-lookup"><span data-stu-id="dea62-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="dea62-164">**性别**：男、女、未知</span><span class="sxs-lookup"><span data-stu-id="dea62-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="dea62-165">**邮政编码**：美国的五位数邮政编码，其他地方的标准邮政编码</span><span class="sxs-lookup"><span data-stu-id="dea62-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="dea62-166">**市/县**：英文的市/县名称</span><span class="sxs-lookup"><span data-stu-id="dea62-166">**City**: City name in English</span></span>
- <span data-ttu-id="dea62-167">**州/省**：美国和加拿大的两个字母的缩写。</span><span class="sxs-lookup"><span data-stu-id="dea62-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="dea62-168">澳大利亚的两个或三个字母的缩写。</span><span class="sxs-lookup"><span data-stu-id="dea62-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="dea62-169">不适用于法国、德国或英国。</span><span class="sxs-lookup"><span data-stu-id="dea62-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="dea62-170">**国家/地区**：</span><span class="sxs-lookup"><span data-stu-id="dea62-170">**Country/Region**:</span></span>

  - <span data-ttu-id="dea62-171">US：United States of America、United States、USA、US、America</span><span class="sxs-lookup"><span data-stu-id="dea62-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="dea62-172">CA：Canada、CA</span><span class="sxs-lookup"><span data-stu-id="dea62-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="dea62-173">GB：United Kingdom、UK、Great Britain、GB、United Kingdom of Great Britain and Northern Ireland、United Kingdom of Great Britain</span><span class="sxs-lookup"><span data-stu-id="dea62-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="dea62-174">AU：Australia、AU、Common Wealth of Australia</span><span class="sxs-lookup"><span data-stu-id="dea62-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="dea62-175">FR：France、FR、French Republic</span><span class="sxs-lookup"><span data-stu-id="dea62-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="dea62-176">DE：Germany、German、Deutschland、Allemagne、DE、Federal Republic of Germany、Republic of Germany</span><span class="sxs-lookup"><span data-stu-id="dea62-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="dea62-177">查看并命名扩充</span><span class="sxs-lookup"><span data-stu-id="dea62-177">Review and name the enrichment</span></span>

<span data-ttu-id="dea62-178">最后，您可以针对扩充查看信息并提供名称。</span><span class="sxs-lookup"><span data-stu-id="dea62-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="兴趣查看和命名页面。":::

## <a name="refresh-enrichment"></a><span data-ttu-id="dea62-180">刷新扩充</span><span class="sxs-lookup"><span data-stu-id="dea62-180">Refresh enrichment</span></span>

<span data-ttu-id="dea62-181">为人口统计数据配置品牌、兴趣和字段映射之后运行扩充。</span><span class="sxs-lookup"><span data-stu-id="dea62-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="dea62-182">若要启动此流程，请在品牌或兴趣配置页上选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="dea62-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="dea62-183">此外，还可以让系统在执行计划的刷新期间自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="dea62-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="dea62-184">根据客户数据的大小，可能需要几分钟，扩充才能运行完成。</span><span class="sxs-lookup"><span data-stu-id="dea62-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="dea62-185">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="dea62-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="dea62-186">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="dea62-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="dea62-187">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dea62-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="dea62-188">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="dea62-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="dea62-189">扩充结果</span><span class="sxs-lookup"><span data-stu-id="dea62-189">Enrichment results</span></span>

<span data-ttu-id="dea62-190">运行扩充流程之后，转到 **我的扩充**，以在扩充后的客户配置文件中查看扩充的客户总数和品牌或兴趣明细。</span><span class="sxs-lookup"><span data-stu-id="dea62-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="运行扩充流程后预览结果":::

<span data-ttu-id="dea62-192">通过在图表中选择 **查看扩充的数据** 查看扩充的数据。</span><span class="sxs-lookup"><span data-stu-id="dea62-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="dea62-193">扩充的品牌数据将进入 **BrandAffinityFromMicrosoft** 实体。</span><span class="sxs-lookup"><span data-stu-id="dea62-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="dea62-194">兴趣的数据位于 **InterestAffinityFromMicrosoft** 实体中。</span><span class="sxs-lookup"><span data-stu-id="dea62-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="dea62-195">还可以发现 **数据** > **实体** 中的 **扩充** 组内列出了这些实体。</span><span class="sxs-lookup"><span data-stu-id="dea62-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="dea62-196">查看客户卡中的扩充数据</span><span class="sxs-lookup"><span data-stu-id="dea62-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="dea62-197">也可以在各客户卡中查看品牌和兴趣相似度。</span><span class="sxs-lookup"><span data-stu-id="dea62-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="dea62-198">转到 **客户**，然后选择客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="dea62-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="dea62-199">在客户卡中，您会找到品牌或兴趣的图表，此图表反映了该客户的人口统计特征中人们具有的品牌或兴趣相似性。</span><span class="sxs-lookup"><span data-stu-id="dea62-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含扩充后数据的客户卡":::

## <a name="next-steps"></a><span data-ttu-id="dea62-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dea62-201">Next steps</span></span>

<span data-ttu-id="dea62-202">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="dea62-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dea62-203">创建[细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="dea62-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
