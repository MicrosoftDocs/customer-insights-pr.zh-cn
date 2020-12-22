---
title: 通过 Microsoft Graph 扩充客户配置文件
description: 使用 Microsoft Graph 中的专用数据和品牌与兴趣相似性扩展客户数据。
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405192"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="1fb8e-103">使用品牌和兴趣相似性扩充客户配置文件（预览版）</span><span class="sxs-lookup"><span data-stu-id="1fb8e-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="1fb8e-104">使用 Microsoft Graph 中的专用数据和品牌与兴趣相似性扩展客户数据。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="1fb8e-105">这些相似性基于与您的客户具有相似人口统计信息的人员的数据确定。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="1fb8e-106">这些信息可帮助您根据客户在特定品牌和兴趣方面的相似性更好地了解和细分客户。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="1fb8e-107">在访问群体见解中，转到 **数据** > **扩充** 以[配置和查看扩充](enrichment-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-107">In ausience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="1fb8e-108">若要配置品牌相似性扩充，请转到 **发现** 选项卡，并选择 **品牌** 磁贴上的 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="1fb8e-109">若要配置兴趣相似性扩充，请转到 **发现** 选项卡，并选择 **兴趣** 磁贴上的 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fb8e-110">![品牌和兴趣磁贴](media/BrandsInterest-tile-Hub.png "品牌和兴趣磁贴")</span><span class="sxs-lookup"><span data-stu-id="1fb8e-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="1fb8e-111">关于 Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="1fb8e-111">About Microsoft Graph</span></span>

<span data-ttu-id="1fb8e-112">我们使用来自 Microsoft Graph 的联机搜索数据在（按年龄、性别或位置定义的）各种人口统计细分中查找品牌和兴趣的相似性。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="1fb8e-113">品牌或兴趣的联机搜索量决定人口统计细分与其他细分相比在该品牌或兴趣方面的相似程度。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="1fb8e-114">[详细了解 Microsoft Graph](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-score-and-confidence"></a><span data-ttu-id="1fb8e-115">相似度分数和置信度</span><span class="sxs-lookup"><span data-stu-id="1fb8e-115">Affinity score and confidence</span></span>

<span data-ttu-id="1fb8e-116">**相似度分数** 的计算基准为 100 点，100 表示细分的品牌或兴趣相似度最高。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-116">The **affinity score** is calculated on a 100-point scale, with 100 representing the segment that has the highest affinity for a brand or interest.</span></span>

<span data-ttu-id="1fb8e-117">**相似置信度** 也按 100 点的等级计算。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-117">The **affinity confidence** is also calculated on a 100-point scale.</span></span> <span data-ttu-id="1fb8e-118">其指示细分的品牌或兴趣相似性置信度级别。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-118">It indicates the system's confidence level that a segment has an affinity for the brand or interest.</span></span> <span data-ttu-id="1fb8e-119">置信度级别基于细分大小和细分粒度。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-119">Confidence level is based on the segment size and the segment granularity.</span></span> <span data-ttu-id="1fb8e-120">细分大小由我们拥有的给定细分数据量决定。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-120">Segment size is determined by the amount of data we have for a given segment.</span></span> <span data-ttu-id="1fb8e-121">细分粒度由配置文件中的属性（年龄、性别、位置）数量决定。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-121">Segment granularity is determined by how many attributes (age, gender, location) are available in a profile.</span></span>

<span data-ttu-id="1fb8e-122">我们不标准化您的数据集的分数。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-122">We don't normalize the scores for your dataset.</span></span> <span data-ttu-id="1fb8e-123">因此，您可能无法查看自己的数据集的所有可能的相似度分数值。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-123">Consequently, you may not see all possible affinity score values for your dataset.</span></span> <span data-ttu-id="1fb8e-124">例如，您的数据中没有相似性分数为 100 的未扩充配置文件。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-124">For example, there may be no enriched customer profile with affinity score 100 in your data.</span></span> <span data-ttu-id="1fb8e-125">如果给定品牌或兴趣评分为 100 的人口统计细分中没有客户，则可以。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-125">That's possible if no customers exist in the demographic segment that scored 100 for a given brand or interest.</span></span>

> [!TIP]
> <span data-ttu-id="1fb8e-126">使用相似度分数[创建细分](segments.md)时，请在决定正确的分数阈值之前，检查数据集的相似度分数分配。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-126">When [creating segments](segments.md) using affinity scores, review the distribution of affinity scores for your dataset before deciding on the appropriate score thresholds.</span></span> <span data-ttu-id="1fb8e-127">例如，可以认为在特定品牌或兴趣的最高相似度分数只有 25 的数据集中，相似度分数 10 相当大。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-127">For example, an affinity score of 10 can be considered significant in a dataset that has a highest affinity score of only 25 for a given brand or interest.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="1fb8e-128">支持的国家/地区</span><span class="sxs-lookup"><span data-stu-id="1fb8e-128">Supported countries/regions</span></span>

<span data-ttu-id="1fb8e-129">目前，我们支持以下国家/地区选项：澳大利亚、加拿大（英语）、法国、德国、英国或美国（英语）。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-129">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="1fb8e-130">要选择国家/地区，打开 **品牌扩充** 或 **兴趣扩充**，然后选择 **国家/地区** 旁边的 **更改**。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-130">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="1fb8e-131">在 **国家/地区设置** 窗格中，选择一个选项，然后选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-131">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="1fb8e-132">与国家/地区选择相关的含义</span><span class="sxs-lookup"><span data-stu-id="1fb8e-132">Implications related to country selection</span></span>

- <span data-ttu-id="1fb8e-133">当[选择您自己的品牌](#define-your-brands-or-interests)时，我们将根据所选国家/地区提供建议。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-133">When [choosing your own brands](#define-your-brands-or-interests), we will provide suggestions based on the selected country/region.</span></span>

- <span data-ttu-id="1fb8e-134">在[选择行业](#define-your-brands-or-interests)时，我们将根据所选的国家/地区确定最相关的品牌或兴趣。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-134">When [choosing an industry](#define-your-brands-or-interests), we will identify the most relevant brands or interests based on the selected country/region.</span></span>

- <span data-ttu-id="1fb8e-135">在[映射您的字段](#map-your-fields)时，如果未映射“国家/地区”字段，我们将使用来自所选国家/地区的 Microsoft Graph 数据来扩充您的客户资料。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-135">When [mapping your fields](#map-your-fields), if the Country/Region field isn't mapped, we'll use Microsoft Graph data from the selected country/region to enrich your customer profiles.</span></span> <span data-ttu-id="1fb8e-136">我们还将使用该选择来扩充没有可用国家/地区数据的客户资料。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-136">We'll also use that selection to enrich your customer profiles that don't have country/region data available.</span></span>

- <span data-ttu-id="1fb8e-137">在[扩充资料](#refresh-enrichment)时，我们将扩充我们有其所选品牌和兴趣的可用 Microsoft Graph 数据的所有客户资料，包括不在所选国家/地区的资料。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we have Microsoft Graph data available for the selected brands and interests, including profiles that are not in the selected country/region.</span></span> <span data-ttu-id="1fb8e-138">例如，如果您选择了德国，如果我们有美国的选定品牌和兴趣的可用 Microsoft Graph 数据，我们将扩充位于美国的资料。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="1fb8e-139">配置扩充</span><span class="sxs-lookup"><span data-stu-id="1fb8e-139">Configure Enrichment</span></span>

<span data-ttu-id="1fb8e-140">配置品牌或兴趣扩充包括以下两个步骤：</span><span class="sxs-lookup"><span data-stu-id="1fb8e-140">Configuring brands or interests enrichment consists of two steps:</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="1fb8e-141">定义您的品牌或兴趣</span><span class="sxs-lookup"><span data-stu-id="1fb8e-141">Define your brands or interests</span></span>

<span data-ttu-id="1fb8e-142">请选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="1fb8e-142">Select one of the following options:</span></span>

- <span data-ttu-id="1fb8e-143">**行业**：系统确定与您的行业有关的排名靠前品牌或兴趣，并将其用于扩充您的客户数据。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-143">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="1fb8e-144">**选择您自己的项目**：从品牌或兴趣列表中选择最多五个与您的组织关系最近的项。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-144">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="1fb8e-145">若要添加品牌或兴趣，请在输入区域中输入该品牌或兴趣，以获取基于匹配项的建议。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-145">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="1fb8e-146">如果我们未列出您在查找的品牌或兴趣，请使用 **建议** 链接向我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="1fb8e-147">映射字段</span><span class="sxs-lookup"><span data-stu-id="1fb8e-147">Map your fields</span></span>

<span data-ttu-id="1fb8e-148">将您的统一客户实体中的字段映射到至少两个属性，以定义您希望我们用于扩充您的客户数据的人口统计细分。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-148">Map fields from your unified customer entity to at least two attributes to define the demographic segment you want us to use for enriching your customer data.</span></span> <span data-ttu-id="1fb8e-149">选择 **编辑** 以定义字段的映射，然后在完成后选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-149">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="1fb8e-150">选择 **保存** 完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-150">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="1fb8e-151">支持下列格式和值，值不区分大小写：</span><span class="sxs-lookup"><span data-stu-id="1fb8e-151">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="1fb8e-152">**出生日期**：我们建议在数据引入期间将出生日期转换为日期/时间类型。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-152">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="1fb8e-153">或者，可以使用 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 格式“yyyy-MM-dd”或“yyyy-MM-ddTHH:mm:ssZ”的字符串。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-153">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="1fb8e-154">**性别**：男、女、未知</span><span class="sxs-lookup"><span data-stu-id="1fb8e-154">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="1fb8e-155">**邮政编码**：美国的五位数邮政编码，其他地方的标准邮政编码</span><span class="sxs-lookup"><span data-stu-id="1fb8e-155">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="1fb8e-156">**市/县**：英文的市/县名称</span><span class="sxs-lookup"><span data-stu-id="1fb8e-156">**City**: City name in English</span></span>
- <span data-ttu-id="1fb8e-157">**州/省**：美国和加拿大的两个字母的缩写。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-157">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="1fb8e-158">澳大利亚的两个或三个字母的缩写。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-158">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="1fb8e-159">不适用于法国、德国或英国。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-159">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="1fb8e-160">**国家/地区**：</span><span class="sxs-lookup"><span data-stu-id="1fb8e-160">**Country/Region**:</span></span>

  - <span data-ttu-id="1fb8e-161">US：United States of America、United States、USA、US、America</span><span class="sxs-lookup"><span data-stu-id="1fb8e-161">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="1fb8e-162">CA：Canada、CA</span><span class="sxs-lookup"><span data-stu-id="1fb8e-162">CA: Canada, CA</span></span>
  - <span data-ttu-id="1fb8e-163">GB：United Kingdom、UK、Great Britain、GB、United Kingdom of Great Britain and Northern Ireland、United Kingdom of Great Britain</span><span class="sxs-lookup"><span data-stu-id="1fb8e-163">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="1fb8e-164">AU：Australia、AU、Common Wealth of Australia</span><span class="sxs-lookup"><span data-stu-id="1fb8e-164">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="1fb8e-165">FR：France、FR、French Republic</span><span class="sxs-lookup"><span data-stu-id="1fb8e-165">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="1fb8e-166">DE：Germany、German、Deutschland、Allemagne、DE、Federal Republic of Germany、Republic of Germany</span><span class="sxs-lookup"><span data-stu-id="1fb8e-166">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="1fb8e-167">刷新扩充</span><span class="sxs-lookup"><span data-stu-id="1fb8e-167">Refresh enrichment</span></span>

<span data-ttu-id="1fb8e-168">为人口统计数据配置品牌、兴趣和字段映射之后运行扩充。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-168">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="1fb8e-169">若要启动此流程，请在品牌或兴趣配置页上选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-169">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="1fb8e-170">此外，还可以让系统在执行计划的刷新期间自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-170">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="1fb8e-171">根据客户数据的大小，可能需要几分钟，扩充才能运行完成。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-171">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="1fb8e-172">对于任务/流程，有[六种类型的状态](system.md#status-types)。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-172">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1fb8e-173">此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-173">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1fb8e-174">可以选择流程状态以查看有关整个作业的进度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-174">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1fb8e-175">在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-175">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="1fb8e-176">扩充结果</span><span class="sxs-lookup"><span data-stu-id="1fb8e-176">Enrichment results</span></span>

<span data-ttu-id="1fb8e-177">运行扩充流程之后，转到 **我的扩充**，以在扩充后的客户配置文件中查看扩充的客户总数和品牌或兴趣明细。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-177">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="运行扩充流程后预览结果":::

<span data-ttu-id="1fb8e-179">通过在图表中选择 **查看扩充的数据** 查看扩充的数据。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-179">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="1fb8e-180">扩充的品牌数据将进入 **BrandAffinityFromMicrosoft** 实体。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-180">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="1fb8e-181">兴趣的数据位于 **InterestAffinityFromMicrosoft** 实体中。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-181">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="1fb8e-182">还可以发现 **数据** > **实体** 中的 **扩充** 组内列出了这些实体。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-182">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="1fb8e-183">查看客户卡中的扩充数据</span><span class="sxs-lookup"><span data-stu-id="1fb8e-183">See enrichment data on the customer card</span></span>

<span data-ttu-id="1fb8e-184">也可以在各客户卡中查看品牌和兴趣相似度。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-184">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="1fb8e-185">转到 **客户**，然后选择客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-185">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="1fb8e-186">在客户卡中，您会找到品牌或兴趣的图表，此图表反映了该客户的人口统计特征中人们具有的品牌或兴趣相似性。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-186">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含扩充后数据的客户卡":::

## <a name="next-steps"></a><span data-ttu-id="1fb8e-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1fb8e-188">Next steps</span></span>

<span data-ttu-id="1fb8e-189">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-189">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1fb8e-190">创建[细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="1fb8e-190">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>
