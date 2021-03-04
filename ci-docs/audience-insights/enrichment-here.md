---
title: 通过第三方扩充 HERE Technologies 扩充
description: 有关 HERE Technologies 第三方扩充的常规信息。
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269503"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="060d6-103">通过 HERE Technologies 扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="060d6-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="060d6-104">HERE Technologies 是一家位置平台公司，可提供以位置为中心的数据和服务。</span><span class="sxs-lookup"><span data-stu-id="060d6-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="060d6-105">通过 HERE Technologies 的数据扩充服务，您可以使用地址标准化、维度和精度提取等来更准确地了解客户的位置信息。</span><span class="sxs-lookup"><span data-stu-id="060d6-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="060d6-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="060d6-106">Prerequisites</span></span>

<span data-ttu-id="060d6-107">若要配置 HERE Technologies 扩充，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="060d6-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="060d6-108">您具有有效的 HERE Technologies 订阅。</span><span class="sxs-lookup"><span data-stu-id="060d6-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="060d6-109">若要获取订阅，您可以在[此处注册](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)或直接[与 HERE Technologies 联系](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。</span><span class="sxs-lookup"><span data-stu-id="060d6-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="060d6-110">了解有关 HERE Technologies 位置扩充的详细信息。</span><span class="sxs-lookup"><span data-stu-id="060d6-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="060d6-111">您具有 HERE Technologies API 密钥。</span><span class="sxs-lookup"><span data-stu-id="060d6-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="060d6-112">您具有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="060d6-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="060d6-113">配置</span><span class="sxs-lookup"><span data-stu-id="060d6-113">Configuration</span></span>

1. <span data-ttu-id="060d6-114">转到 **数据** > **扩充**。</span><span class="sxs-lookup"><span data-stu-id="060d6-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="060d6-115">在 HERE Technologies 磁贴上选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="060d6-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="060d6-116">![HERE Technologies 磁贴](media/HERE-tile.png "HERE Technologies 磁贴")</span><span class="sxs-lookup"><span data-stu-id="060d6-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="060d6-117">输入有效的 **HERE Technologies API 密钥**。</span><span class="sxs-lookup"><span data-stu-id="060d6-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="060d6-118">进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。</span><span class="sxs-lookup"><span data-stu-id="060d6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="060d6-119">通过选择 **连接到 HERE** 确认输入。</span><span class="sxs-lookup"><span data-stu-id="060d6-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="060d6-120">选择 **添加数据** 并选择要使用 HERE Technologies 的位置数据扩充的 **客户数据集**。</span><span class="sxs-lookup"><span data-stu-id="060d6-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="060d6-121">您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="060d6-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. <span data-ttu-id="060d6-123">选择是否要将字段映射到主要地址和/或辅助地址。</span><span class="sxs-lookup"><span data-stu-id="060d6-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="060d6-124">您可以为这两个地址（例如家庭和公司地址）指定字段映射，并分别扩充这两个地址的配置文件。</span><span class="sxs-lookup"><span data-stu-id="060d6-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="060d6-125">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="060d6-125">Select **Next**.</span></span>

1. <span data-ttu-id="060d6-126">定义应使用统一配置文件中的哪些字段来查找 HERE Technologies 中的匹配位置数据。</span><span class="sxs-lookup"><span data-stu-id="060d6-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="060d6-127">必须为所选的主要和/或辅助地址指定 **街道 1** 和 **邮政编码** 字段。</span><span class="sxs-lookup"><span data-stu-id="060d6-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="060d6-128">为了使匹配精度更高，可添加更多字段。</span><span class="sxs-lookup"><span data-stu-id="060d6-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="060d6-129">![HERE Technologies 扩充配置页面](media/enrichment-HERE-configuration.png "HERE Technologies 扩充配置页面")</span><span class="sxs-lookup"><span data-stu-id="060d6-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="060d6-130">选择 **应用** 以完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="060d6-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="060d6-131">扩充结果</span><span class="sxs-lookup"><span data-stu-id="060d6-131">Enrichment results</span></span>

<span data-ttu-id="060d6-132">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="060d6-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="060d6-133">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="060d6-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="060d6-134">处理时间将取决于您的客户数据的大小和 HERE Technologies 的 API 响应时间。</span><span class="sxs-lookup"><span data-stu-id="060d6-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="060d6-135">扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="060d6-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="060d6-136">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="060d6-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="060d6-137">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="060d6-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="060d6-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="060d6-138">Next steps</span></span>

<span data-ttu-id="060d6-139">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="060d6-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="060d6-140">创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="060d6-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="060d6-141">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="060d6-141">Data privacy and compliance</span></span>

<span data-ttu-id="060d6-142">当您启用 Dynamics 365 Customer Insights 将数据传输到 HERE Technologies 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="060d6-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="060d6-143">Microsoft 将在您的指导下传输此类数据，但您有责任确保 HERE Technologies 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="060d6-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="060d6-144">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="060d6-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="060d6-145">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="060d6-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]