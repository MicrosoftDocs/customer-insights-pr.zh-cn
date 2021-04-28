---
title: 通过第三方扩充 Experian 扩充
description: 有关 Experian 第三方扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896362"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="65255-103">使用来自 Experian 的人口统计数据扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="65255-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="65255-104">Experian 是消费者和企业信用报告以及营销服务的全球领导者。</span><span class="sxs-lookup"><span data-stu-id="65255-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="65255-105">借助 Experian 的数据扩充服务，您可以通过人口统计数据（如家庭人数、收入等）扩充客户配置文件，从而加深对客户的了解。</span><span class="sxs-lookup"><span data-stu-id="65255-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65255-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="65255-106">Prerequisites</span></span>

<span data-ttu-id="65255-107">要配置 Experian，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="65255-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="65255-108">您有有效的 Experian 订阅。</span><span class="sxs-lookup"><span data-stu-id="65255-108">You have an active Experian subscription.</span></span> <span data-ttu-id="65255-109">若要获取订阅，请直接[联系 Experian](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="65255-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="65255-110">[了解有关 Experian 数据扩充的详细信息](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="65255-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="65255-111">管理员已配置 Experian 连接，*或者* 您拥有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="65255-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="65255-112">对于 Experian 为您创建的支持 SSH 的安全传输 (ST) 帐户，您还需要用户 ID、参与方 ID 和型号。</span><span class="sxs-lookup"><span data-stu-id="65255-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="65255-113">配置扩充</span><span class="sxs-lookup"><span data-stu-id="65255-113">Configure the enrichment</span></span>

1. <span data-ttu-id="65255-114">转到 **数据** > **扩充**，选择 **发现** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="65255-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="65255-115">在 Experian 磁贴上选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="65255-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65255-116">![Experian 磁贴](media/experian-tile.png "Experian 磁贴")</span><span class="sxs-lookup"><span data-stu-id="65255-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="65255-117">从下拉列表选择[连接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="65255-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="65255-118">如果没有连接可用，请联系管理员。</span><span class="sxs-lookup"><span data-stu-id="65255-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="65255-119">如果您是管理员，则可以通过选择 **添加连接** 并从下拉列表中选择 Experian 来创建连接。</span><span class="sxs-lookup"><span data-stu-id="65255-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="65255-120">选择 **连接到 Experian** 以确认连接选择。</span><span class="sxs-lookup"><span data-stu-id="65255-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="65255-121">选择 **下一步**，然后选择您希望利用 Experian 提供的人口统计数据扩充的 **客户数据集**。</span><span class="sxs-lookup"><span data-stu-id="65255-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="65255-122">您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="65255-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. <span data-ttu-id="65255-124">选择 **下一步**，并定义应使用统一配置文件中的哪种字段来查找来自 Experian 的匹配人口统计数据。</span><span class="sxs-lookup"><span data-stu-id="65255-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="65255-125">至少需要 **名称和地址**、**电话** 或 **电子邮件** 中的一个字段。</span><span class="sxs-lookup"><span data-stu-id="65255-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="65255-126">为了提高匹配精度，最多可添加其他两个字段。</span><span class="sxs-lookup"><span data-stu-id="65255-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="65255-127">此选项会影响您可以在下一步中访问的映射字段。</span><span class="sxs-lookup"><span data-stu-id="65255-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="65255-128">发送给 Experian 的密钥标识符属性越多，匹配率会越高。</span><span class="sxs-lookup"><span data-stu-id="65255-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="65255-129">选择 **下一步** 以开始字段映射。</span><span class="sxs-lookup"><span data-stu-id="65255-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="65255-130">定义应使用统一配置文件中的哪些字段来查找来自 Experian 的匹配人口统计数据。</span><span class="sxs-lookup"><span data-stu-id="65255-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="65255-131">必填字段都有标记。</span><span class="sxs-lookup"><span data-stu-id="65255-131">Required fields are marked.</span></span>

1. <span data-ttu-id="65255-132">提供扩充的名称和输出实体的名称。</span><span class="sxs-lookup"><span data-stu-id="65255-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="65255-133">在查看您的选择后选择 **保存扩充**。</span><span class="sxs-lookup"><span data-stu-id="65255-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="65255-134">针对 Experian 配置连接</span><span class="sxs-lookup"><span data-stu-id="65255-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="65255-135">您必须是管理员才能配置连接。</span><span class="sxs-lookup"><span data-stu-id="65255-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="65255-136">配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在 Experian 磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="65255-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="65255-137">选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="65255-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="65255-138">在 **显示名称** 框中输入连接的名称。</span><span class="sxs-lookup"><span data-stu-id="65255-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="65255-139">输入 Experian 扩展安全传输帐户的有效用户 ID、参与方 ID 和型号。</span><span class="sxs-lookup"><span data-stu-id="65255-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="65255-140">进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**</span><span class="sxs-lookup"><span data-stu-id="65255-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="65255-141">选择 **验证** 以验证配置。</span><span class="sxs-lookup"><span data-stu-id="65255-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="65255-142">完成验证后，选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="65255-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 连接配置窗格。":::

## <a name="enrichment-results"></a><span data-ttu-id="65255-144">扩充结果</span><span class="sxs-lookup"><span data-stu-id="65255-144">Enrichment results</span></span>

<span data-ttu-id="65255-145">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="65255-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="65255-146">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="65255-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="65255-147">处理时间取决于客户数据的大小和 Experian 为您的帐户设置的扩充流程。</span><span class="sxs-lookup"><span data-stu-id="65255-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="65255-148">扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="65255-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="65255-149">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="65255-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="65255-150">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="65255-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="65255-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="65255-151">Next steps</span></span>

<span data-ttu-id="65255-152">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="65255-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="65255-153">创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="65255-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="65255-154">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="65255-154">Data privacy and compliance</span></span>

<span data-ttu-id="65255-155">当您启用 Dynamics 365 Customer Insights 将数据传输到 Experian 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="65255-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="65255-156">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Experian 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="65255-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="65255-157">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="65255-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="65255-158">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="65255-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
