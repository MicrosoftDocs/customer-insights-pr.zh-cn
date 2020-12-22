---
title: 通过第三方扩充 Leadspace 扩充公司配置文件
description: 有关 Leadspace 第三方扩充的常规信息。
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668712"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="b8fcd-103">通过 Leadspace 扩充公司配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="b8fcd-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="b8fcd-104">Leadspace 是一家提供 B2B 客户数据平台的数据科学公司。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="b8fcd-105">它使那些具有公司统一客户配置文件的客户能够扩充其数据。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="b8fcd-106">扩充包括其他属性，例如公司规模、位置、行业等。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8fcd-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="b8fcd-107">Prerequisites</span></span>

<span data-ttu-id="b8fcd-108">要配置 Leadspace，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="b8fcd-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b8fcd-109">您具有有效的 Leadspace 许可证和“永久密钥”（称为 **Leadspace 令牌**）。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="b8fcd-110">请直接联系 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) 了解有关其产品的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="b8fcd-111">您具有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="b8fcd-112">您具有公司[统一客户配置文件](customer-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="b8fcd-113">配置</span><span class="sxs-lookup"><span data-stu-id="b8fcd-113">Configuration</span></span>

1. <span data-ttu-id="b8fcd-114">在访问群体见解中，转到 **数据** > **扩充**。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b8fcd-115">在 Leadspace 磁贴上选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 磁贴的屏幕截图。":::

1. <span data-ttu-id="b8fcd-117">选择 **入门**，然后输入有效的 **Leadspace 令牌**（永久密钥）。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="b8fcd-118">进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="b8fcd-119">通过选择 **连接到 Leadspace** 确认输入。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="b8fcd-120">选择 **映射数据** 并定义应使用统一配置文件中的哪些字段来查找 Leadspace 中的匹配公司数据。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="b8fcd-121">**公司名称** 字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-121">The **Name of company** field is required.</span></span> <span data-ttu-id="b8fcd-122">为了使匹配精度更高，可添加最多两个其他字段：**公司网站** 和 **公司位置**。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 字段映射窗格。":::
   
1. <span data-ttu-id="b8fcd-124">选择 **应用** 以完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="b8fcd-125">选择 **运行** 以丰富公司配置文件。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="b8fcd-126">扩充花费的时间取决于统一客户配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b8fcd-127">扩充结果</span><span class="sxs-lookup"><span data-stu-id="b8fcd-127">Enrichment results</span></span>

<span data-ttu-id="b8fcd-128">刷新扩充后，您可以在[我的扩充](enrichment-hub.md)下查看新扩充的公司数据。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="b8fcd-129">您可以查找上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b8fcd-130">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="b8fcd-131">有关详细信息，请参阅 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8fcd-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b8fcd-132">Next steps</span></span>

<span data-ttu-id="b8fcd-133">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b8fcd-134">创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b8fcd-135">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="b8fcd-135">Data privacy and compliance</span></span>

<span data-ttu-id="b8fcd-136">当您启用 Dynamics 365 Customer Insights 将数据传输到 Leadspace 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b8fcd-137">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Leadspace 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b8fcd-138">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b8fcd-139">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b8fcd-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>