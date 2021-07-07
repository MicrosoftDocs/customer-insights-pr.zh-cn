---
title: 通过第三方扩充 HERE Technologies 进行的扩充
description: 有关 HERE Technologies 第三方扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305283"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f0c67-103">通过 HERE Technologies 扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="f0c67-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f0c67-104">HERE Technologies 是一家位置平台公司，可提供以位置为中心的数据和服务。</span><span class="sxs-lookup"><span data-stu-id="f0c67-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f0c67-105">通过 HERE Technologies 的数据扩充服务，您可以使用地址标准化、维度和精度提取等来更准确地了解客户的位置信息。</span><span class="sxs-lookup"><span data-stu-id="f0c67-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0c67-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="f0c67-106">Prerequisites</span></span>

<span data-ttu-id="f0c67-107">若要配置 HERE Technologies 扩充，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="f0c67-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f0c67-108">您具有有效的 HERE Technologies 订阅。</span><span class="sxs-lookup"><span data-stu-id="f0c67-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f0c67-109">若要获取订阅，您可以在[此处注册](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)或直接[与 HERE Technologies 联系](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。</span><span class="sxs-lookup"><span data-stu-id="f0c67-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f0c67-110">了解有关 HERE Technologies 位置扩充的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0c67-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f0c67-111">HERE [连接](connections.md)可用，*或者* 您具有[管理员](permissions.md#administrator)权限和 HERE Technologies API 密钥。</span><span class="sxs-lookup"><span data-stu-id="f0c67-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f0c67-112">配置扩充</span><span class="sxs-lookup"><span data-stu-id="f0c67-112">Configure the enrichment</span></span>

1. <span data-ttu-id="f0c67-113">转到 **数据** > **扩充**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="f0c67-114">在 HERE Technologies 磁贴上选择 **扩充我的数据**，然后选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f0c67-115">![HERE Technologies 磁贴](media/HERE-tile.png "HERE Technologies 磁贴")</span><span class="sxs-lookup"><span data-stu-id="f0c67-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f0c67-116">从下拉列表中选择[连接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c67-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="f0c67-117">如果没有连接可用，请联系管理员。</span><span class="sxs-lookup"><span data-stu-id="f0c67-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="f0c67-118">如果您是管理员，则可以通过选择 **添加连接** 来创建连接。</span><span class="sxs-lookup"><span data-stu-id="f0c67-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="f0c67-119">从下拉列表中选择 **HERE Technologies**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="f0c67-120">选择 **连接到 HERE Technologies** 以确认选择。</span><span class="sxs-lookup"><span data-stu-id="f0c67-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="f0c67-121">选择 **下一步**，然后选择您希望利用 HERE Technologies 提供的位置数据扩充的 **客户数据集**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="f0c67-122">您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="f0c67-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. <span data-ttu-id="f0c67-124">选择是否要将字段映射到主要地址和/或辅助地址。</span><span class="sxs-lookup"><span data-stu-id="f0c67-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f0c67-125">您可以为两个地址指定字段映射，并分别扩充这两个地址的配置文件。</span><span class="sxs-lookup"><span data-stu-id="f0c67-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f0c67-126">例如，如果有一个家庭地址和一个商业地址。</span><span class="sxs-lookup"><span data-stu-id="f0c67-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="f0c67-127">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-127">Select **Next**.</span></span>

1. <span data-ttu-id="f0c67-128">定义应使用统一配置文件中的哪些字段来查找 HERE Technologies 中的匹配位置数据。</span><span class="sxs-lookup"><span data-stu-id="f0c67-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f0c67-129">必须为所选的主要和/或辅助地址指定 **街道 1** 和 **邮政编码** 字段。</span><span class="sxs-lookup"><span data-stu-id="f0c67-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f0c67-130">为了使匹配精度更高，可添加更多字段。</span><span class="sxs-lookup"><span data-stu-id="f0c67-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f0c67-131">![HERE Technologies 扩充配置页面](media/enrichment-HERE-configuration.png "HERE Technologies 扩充配置页面")</span><span class="sxs-lookup"><span data-stu-id="f0c67-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f0c67-132">选择 **下一步** 以完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="f0c67-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="f0c67-133">提供扩充的名称。</span><span class="sxs-lookup"><span data-stu-id="f0c67-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="f0c67-134">在查看您的选择后选择 **保存扩充**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="f0c67-135">为 HERE Technologies 配置连接</span><span class="sxs-lookup"><span data-stu-id="f0c67-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="f0c67-136">您必须是管理员才能配置连接。</span><span class="sxs-lookup"><span data-stu-id="f0c67-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f0c67-137">配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在 HERE Technologies 磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="f0c67-138">在 **显示名称** 框中输入连接的名称。</span><span class="sxs-lookup"><span data-stu-id="f0c67-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f0c67-139">提供有效的 HERE Technologies API 密钥。</span><span class="sxs-lookup"><span data-stu-id="f0c67-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="f0c67-140">通过选择 **我同意**，查看并同意 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="f0c67-141">选择 **验证** 以验证配置。</span><span class="sxs-lookup"><span data-stu-id="f0c67-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f0c67-142">完成验证后，选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f0c67-143">![HERE Technologies 连接配置页面](media/enrichment-HERE-connection.png "HERE Technologies 连接配置页面")</span><span class="sxs-lookup"><span data-stu-id="f0c67-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f0c67-144">扩充结果</span><span class="sxs-lookup"><span data-stu-id="f0c67-144">Enrichment results</span></span>

<span data-ttu-id="f0c67-145">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="f0c67-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f0c67-146">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="f0c67-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f0c67-147">处理时间将取决于您的客户数据的大小和 HERE Technologies 的 API 响应时间。</span><span class="sxs-lookup"><span data-stu-id="f0c67-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f0c67-148">扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="f0c67-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f0c67-149">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="f0c67-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f0c67-150">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="f0c67-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0c67-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f0c67-151">Next steps</span></span>

<span data-ttu-id="f0c67-152">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="f0c67-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f0c67-153">创建[细分](segments.md)和[度量](measures.md)，甚至[导出数据](export-destinations.md)，以向客户提供个性化体验。</span><span class="sxs-lookup"><span data-stu-id="f0c67-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f0c67-154">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="f0c67-154">Data privacy and compliance</span></span>

<span data-ttu-id="f0c67-155">当您启用 Dynamics 365 Customer Insights 将数据传输到 HERE Technologies 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="f0c67-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f0c67-156">Microsoft 将在您的指导下传输此类数据，但您有责任确保 HERE Technologies 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="f0c67-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f0c67-157">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="f0c67-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f0c67-158">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="f0c67-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
