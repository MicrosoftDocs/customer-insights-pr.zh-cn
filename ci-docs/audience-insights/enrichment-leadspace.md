---
title: 通过第三方扩充 Leadspace 扩充公司配置文件
description: 有关 Leadspace 第三方扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895902"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="9bea5-103">通过 Leadspace 扩充公司配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="9bea5-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="9bea5-104">Leadspace 是一家提供 B2B 客户数据平台的数据科学公司。</span><span class="sxs-lookup"><span data-stu-id="9bea5-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="9bea5-105">它使那些具有公司统一客户配置文件的客户能够扩充其数据。</span><span class="sxs-lookup"><span data-stu-id="9bea5-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="9bea5-106">扩充包括更多属性，例如公司规模、位置、行业等。</span><span class="sxs-lookup"><span data-stu-id="9bea5-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bea5-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="9bea5-107">Prerequisites</span></span>

<span data-ttu-id="9bea5-108">要配置 Leadspace，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="9bea5-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9bea5-109">您有一个可用的 Leadspace 许可证。</span><span class="sxs-lookup"><span data-stu-id="9bea5-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="9bea5-110">您具有公司[统一客户配置文件](customer-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="9bea5-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="9bea5-111">管理员已配置 Leadspace 连接，或者您拥有 [管理员](permissions.md#administrator)权限和“永久密钥”（称为 **Leadspace 令牌**）。</span><span class="sxs-lookup"><span data-stu-id="9bea5-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="9bea5-112">直接联系 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)，了解有关其产品的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9bea5-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="9bea5-113">配置扩充</span><span class="sxs-lookup"><span data-stu-id="9bea5-113">Configure the enrichment</span></span>

1. <span data-ttu-id="9bea5-114">在访问群体见解中，转到 **数据** > **扩充**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9bea5-115">在 Leadspace 磁贴上选择 **扩充我的数据**，然后选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 磁贴的屏幕截图。":::

1. <span data-ttu-id="9bea5-117">从下拉列表选择[连接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="9bea5-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="9bea5-118">如果没有连接可用，请联系管理员。</span><span class="sxs-lookup"><span data-stu-id="9bea5-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="9bea5-119">如果您是管理员，则可以通过选择 **添加连接** 并选择 **Leadspace** 来创建连接。</span><span class="sxs-lookup"><span data-stu-id="9bea5-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="9bea5-120">选择 **连接到 Leadspace** 以确认连接。</span><span class="sxs-lookup"><span data-stu-id="9bea5-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="9bea5-121">选择 **下一步**，然后选择您希望利用 Leadspace 提供的公司数据扩充的 **客户数据集**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="9bea5-122">您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="9bea5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. <span data-ttu-id="9bea5-124">选择 **下一步**，并定义应使用统一配置文件中的哪些字段来查找来自 Leadspace 的匹配公司数据。</span><span class="sxs-lookup"><span data-stu-id="9bea5-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="9bea5-125">**公司名称** 字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="9bea5-125">The **Name of company** field is required.</span></span> <span data-ttu-id="9bea5-126">为了使匹配精度更高，可添加最多两个其他字段：**公司网站** 和 **公司位置**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 字段映射窗格。":::

1. <span data-ttu-id="9bea5-128">选择 **下一步** 以完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="9bea5-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="9bea5-129">提供扩充的名称，并在查看您的选择后选择 **保存扩充**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="9bea5-130">针对 Leadspace 配置连接</span><span class="sxs-lookup"><span data-stu-id="9bea5-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="9bea5-131">您必须是管理员才能配置连接。</span><span class="sxs-lookup"><span data-stu-id="9bea5-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="9bea5-132">配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在 Leadspace 磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="9bea5-133">选择 **开始**</span><span class="sxs-lookup"><span data-stu-id="9bea5-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="9bea5-134">在 **显示名称** 框中输入连接的名称。</span><span class="sxs-lookup"><span data-stu-id="9bea5-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="9bea5-135">提供有效的 Leadspace 令牌。</span><span class="sxs-lookup"><span data-stu-id="9bea5-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="9bea5-136">进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**</span><span class="sxs-lookup"><span data-stu-id="9bea5-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="9bea5-137">选择 **验证** 以验证配置。</span><span class="sxs-lookup"><span data-stu-id="9bea5-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="9bea5-138">完成验证后，选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="9bea5-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 连接配置页面。":::

## <a name="enrichment-results"></a><span data-ttu-id="9bea5-140">扩充结果</span><span class="sxs-lookup"><span data-stu-id="9bea5-140">Enrichment results</span></span>

<span data-ttu-id="9bea5-141">刷新扩充后，您可以在[我的扩充](enrichment-hub.md)下查看新扩充的公司数据。</span><span class="sxs-lookup"><span data-stu-id="9bea5-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="9bea5-142">您可以查找上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="9bea5-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9bea5-143">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="9bea5-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="9bea5-144">有关详细信息，请参阅 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。</span><span class="sxs-lookup"><span data-stu-id="9bea5-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bea5-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9bea5-145">Next steps</span></span>

<span data-ttu-id="9bea5-146">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="9bea5-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9bea5-147">创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="9bea5-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9bea5-148">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="9bea5-148">Data privacy and compliance</span></span>

<span data-ttu-id="9bea5-149">当您启用 Dynamics 365 Customer Insights 将数据传输到 Leadspace 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="9bea5-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9bea5-150">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Leadspace 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="9bea5-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9bea5-151">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="9bea5-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9bea5-152">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="9bea5-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
