---
title: 通过第三方扩充 Experian 扩充
description: 有关 Experian 第三方扩充的常规信息。
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597776"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="af0cc-103">使用来自 Experian 的人口统计数据扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="af0cc-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="af0cc-104">Experian 是消费者和企业信用报告以及营销服务的全球领导者。</span><span class="sxs-lookup"><span data-stu-id="af0cc-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="af0cc-105">借助 Experian 的数据扩充服务，您可以通过人口统计数据（如家庭人数、收入等）扩充客户配置文件，从而加深对客户的了解。</span><span class="sxs-lookup"><span data-stu-id="af0cc-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af0cc-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="af0cc-106">Prerequisites</span></span>

<span data-ttu-id="af0cc-107">要配置 Experian，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="af0cc-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="af0cc-108">您有有效的 Experian 订阅。</span><span class="sxs-lookup"><span data-stu-id="af0cc-108">You have an active Experian subscription.</span></span> <span data-ttu-id="af0cc-109">若要获取订阅，请直接[联系 Experian](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="af0cc-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="af0cc-110">[了解有关 Experian 数据扩充的详细信息](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="af0cc-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="af0cc-111">您有 Experian 为您创建的已启用 SSH 的安全传输 (ST) 帐户的用户 ID、参与方 ID 和型号。</span><span class="sxs-lookup"><span data-stu-id="af0cc-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="af0cc-112">您在访问群体见解中具有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="af0cc-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="af0cc-113">配置</span><span class="sxs-lookup"><span data-stu-id="af0cc-113">Configuration</span></span>

1. <span data-ttu-id="af0cc-114">转到 **数据** > **扩充**，选择 **发现** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="af0cc-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="af0cc-115">在 Experian 磁贴上选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="af0cc-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="af0cc-116">![Experian 磁贴](media/experian-tile.png "Experian 磁贴")</span><span class="sxs-lookup"><span data-stu-id="af0cc-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="af0cc-117">选择 **开始**，输入您的 Experian 安全传输帐户的用户 ID、参与方 ID 和型号。</span><span class="sxs-lookup"><span data-stu-id="af0cc-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="af0cc-118">进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。</span><span class="sxs-lookup"><span data-stu-id="af0cc-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="af0cc-119">选择 **应用** 确认所有输入。</span><span class="sxs-lookup"><span data-stu-id="af0cc-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="af0cc-120">映射字段</span><span class="sxs-lookup"><span data-stu-id="af0cc-120">Map your fields</span></span>

1.  <span data-ttu-id="af0cc-121">选择 **添加数据** 并选择要使用 Experian 的统计信息数据扩充的 **客户数据集**。</span><span class="sxs-lookup"><span data-stu-id="af0cc-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="af0cc-122">您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="af0cc-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="af0cc-123">从 **姓名和地址**、**电子邮件** 或 **电话** 中选择您的密钥标识符，以发送给 Experian 进行身份解析。</span><span class="sxs-lookup"><span data-stu-id="af0cc-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="af0cc-124">发送给 Experian 的密钥标识符属性越多，匹配率会越高。</span><span class="sxs-lookup"><span data-stu-id="af0cc-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="af0cc-125">选择 **下一步**，为所选密钥标识符字段映射统一客户实体中的对应属性。</span><span class="sxs-lookup"><span data-stu-id="af0cc-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="af0cc-126">选择 **添加属性** 可映射您想要发送到 Experian 的任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="af0cc-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="af0cc-127">选择 **保存** 完成字段映射。</span><span class="sxs-lookup"><span data-stu-id="af0cc-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af0cc-128">![Experian 字段映射](media/experian-field-mapping.png "Experian 字段映射")</span><span class="sxs-lookup"><span data-stu-id="af0cc-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="af0cc-129">扩充结果</span><span class="sxs-lookup"><span data-stu-id="af0cc-129">Enrichment results</span></span>

<span data-ttu-id="af0cc-130">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="af0cc-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="af0cc-131">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="af0cc-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="af0cc-132">处理时间取决于客户数据的大小和 Experian 为您的帐户设置的扩充流程。</span><span class="sxs-lookup"><span data-stu-id="af0cc-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="af0cc-133">扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="af0cc-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="af0cc-134">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="af0cc-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="af0cc-135">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="af0cc-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af0cc-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="af0cc-136">Next steps</span></span>

<span data-ttu-id="af0cc-137">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="af0cc-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="af0cc-138">创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="af0cc-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="af0cc-139">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="af0cc-139">Data privacy and compliance</span></span>

<span data-ttu-id="af0cc-140">当您启用 Dynamics 365 Customer Insights 将数据传输到 Experian 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="af0cc-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="af0cc-141">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Experian 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="af0cc-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="af0cc-142">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="af0cc-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="af0cc-143">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="af0cc-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]