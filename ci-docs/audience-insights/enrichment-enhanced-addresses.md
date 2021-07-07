---
title: 地址增强扩充
description: 使用 Microsoft 模型扩充并标准化客户配置文件的地址信息。
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305421"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="03535-103">使用增强的地址扩充客户配置文件</span><span class="sxs-lookup"><span data-stu-id="03535-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="03535-104">数据中的地址可能无结构、不完整或不正确。</span><span class="sxs-lookup"><span data-stu-id="03535-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="03535-105">使用 Microsoft 的模型按 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/address)标准化并扩充您的地址，以获得更佳的准确性和见解。</span><span class="sxs-lookup"><span data-stu-id="03535-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="03535-106">如何增强地址</span><span class="sxs-lookup"><span data-stu-id="03535-106">How we enhance addresses</span></span>

<span data-ttu-id="03535-107">我们的模型将执行两个步骤来增强地址。</span><span class="sxs-lookup"><span data-stu-id="03535-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="03535-108">首先，它解析地址以标识其组成部分并使其成为结构化格式。</span><span class="sxs-lookup"><span data-stu-id="03535-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="03535-109">然后，我们使用 AI 来更正、完成和标准化地址中的值。</span><span class="sxs-lookup"><span data-stu-id="03535-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="03535-110">示例</span><span class="sxs-lookup"><span data-stu-id="03535-110">Example</span></span>

<span data-ttu-id="03535-111">地址信息可能采用非标准格式并且包含拼写错误。</span><span class="sxs-lookup"><span data-stu-id="03535-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="03535-112">该模型可以在统一客户配置文件中修复这些问题并创建一致的地址。</span><span class="sxs-lookup"><span data-stu-id="03535-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="03535-113">限制</span><span class="sxs-lookup"><span data-stu-id="03535-113">Limitations</span></span>

<span data-ttu-id="03535-114">增强型地址仅适用于引入的地址数据中已经存在的值。</span><span class="sxs-lookup"><span data-stu-id="03535-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="03535-115">此模型不会：</span><span class="sxs-lookup"><span data-stu-id="03535-115">The model doesn't:</span></span> 

1. <span data-ttu-id="03535-116">验证地址是否有效。</span><span class="sxs-lookup"><span data-stu-id="03535-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="03535-117">验证任意值（如邮政编码或街道名称）是否有效。</span><span class="sxs-lookup"><span data-stu-id="03535-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="03535-118">更改它无法识别的值。</span><span class="sxs-lookup"><span data-stu-id="03535-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="03535-119">该模型使用基于机器学习的技术来增强地址。</span><span class="sxs-lookup"><span data-stu-id="03535-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="03535-120">虽然我们在模型更改输入值时应用高置信度阈值，但与基于机器学习的任何模型一样，都不能保证 100% 的准确性。</span><span class="sxs-lookup"><span data-stu-id="03535-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="03535-121">支持的国家或地区</span><span class="sxs-lookup"><span data-stu-id="03535-121">Supported countries or regions</span></span>

<span data-ttu-id="03535-122">我们当前支持扩充以下国家或地区中的地址：</span><span class="sxs-lookup"><span data-stu-id="03535-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="03535-123">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="03535-123">Australia</span></span>
- <span data-ttu-id="03535-124">加拿大</span><span class="sxs-lookup"><span data-stu-id="03535-124">Canada</span></span>
- <span data-ttu-id="03535-125">英国</span><span class="sxs-lookup"><span data-stu-id="03535-125">United Kingdom</span></span>
- <span data-ttu-id="03535-126">美国</span><span class="sxs-lookup"><span data-stu-id="03535-126">United States</span></span>

<span data-ttu-id="03535-127">地址必须包含国家/地区值。</span><span class="sxs-lookup"><span data-stu-id="03535-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="03535-128">我们不处理不受支持的国家或地区的地址，也不处理未提供国家或地区的地址。</span><span class="sxs-lookup"><span data-stu-id="03535-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="03535-129">配置扩充</span><span class="sxs-lookup"><span data-stu-id="03535-129">Configure the enrichment</span></span>

1. <span data-ttu-id="03535-130">转到 **数据** > **扩充**。</span><span class="sxs-lookup"><span data-stu-id="03535-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="03535-131">在 **增强的地址** 磁贴上选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="03535-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="增强的地址磁贴的屏幕截图。":::

1. <span data-ttu-id="03535-133">选择 **客户数据集**，并选择包含要扩充的地址的实体。</span><span class="sxs-lookup"><span data-stu-id="03535-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="03535-134">您可以选择 *客户* 实体以扩充所有客户配置文件中的地址，也可以选择客户细分实体以仅扩充该客户细分所包含的客户配置文件中的地址。</span><span class="sxs-lookup"><span data-stu-id="03535-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="03535-135">选择在数据集中设置地址格式的方式。</span><span class="sxs-lookup"><span data-stu-id="03535-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="03535-136">如果数据中的地址使用单个字段，请选择 **单一属性地址**。</span><span class="sxs-lookup"><span data-stu-id="03535-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="03535-137">如果数据中的地址使用多个数据字段，请选择 **多属性地址**。</span><span class="sxs-lookup"><span data-stu-id="03535-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="03535-138">在单一属性和多属性地址中，国家/地区均是必需的。</span><span class="sxs-lookup"><span data-stu-id="03535-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="03535-139">将不会扩充不包含有效或受支持的国家/地区值的地址。</span><span class="sxs-lookup"><span data-stu-id="03535-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="03535-140">映射统一客户实体中的地址字段。</span><span class="sxs-lookup"><span data-stu-id="03535-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="增强的地址字段映射页。":::

1. <span data-ttu-id="03535-142">选择 **下一步** 以完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="03535-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="03535-143">提供扩充和输出实体的名称。</span><span class="sxs-lookup"><span data-stu-id="03535-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="03535-144">在查看您的选择后选择 **保存扩充**。</span><span class="sxs-lookup"><span data-stu-id="03535-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="03535-145">扩充结果</span><span class="sxs-lookup"><span data-stu-id="03535-145">Enrichment results</span></span>

<span data-ttu-id="03535-146">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="03535-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="03535-147">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="03535-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="03535-148">处理时间取决于客户数据的大小。</span><span class="sxs-lookup"><span data-stu-id="03535-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="03535-149">扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="03535-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="03535-150">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="03535-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="03535-151">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="03535-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03535-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="03535-152">Next steps</span></span>

<span data-ttu-id="03535-153">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="03535-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="03535-154">创建[细分](segments.md)和[度量](measures.md)，甚至[导出数据](export-destinations.md)，以向客户提供个性化体验。</span><span class="sxs-lookup"><span data-stu-id="03535-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
