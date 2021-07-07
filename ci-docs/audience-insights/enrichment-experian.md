---
title: 通过第三方扩充 Experian 进行的扩充
description: 有关 Experian 第三方扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309809"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="5855a-103">使用 Experian 中的人口统计信息扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="5855a-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="5855a-104">Experian 是消费者和企业信用报告以及市场营销服务领域的全球领先者。</span><span class="sxs-lookup"><span data-stu-id="5855a-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="5855a-105">使用 Experian 的数据扩充服务，您可以通过使用人口统计数据（例如家庭规模、收入等）扩充客户配置文件，以进一步了解您的客户。</span><span class="sxs-lookup"><span data-stu-id="5855a-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5855a-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="5855a-106">Prerequisites</span></span>

<span data-ttu-id="5855a-107">若要配置 Experian，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="5855a-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5855a-108">拥有有效的 Experian 订阅。</span><span class="sxs-lookup"><span data-stu-id="5855a-108">You have an active Experian subscription.</span></span> <span data-ttu-id="5855a-109">若要获取订阅，请直接[与 Experian 联系](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="5855a-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="5855a-110">[了解有关 Experian 数据扩充的详细信息](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="5855a-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="5855a-111">管理员已配置 Experian 连接，*或者* 您拥有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="5855a-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="5855a-112">还需要为 Experian 为您创建的启用 SSH 的安全传输 (ST) 帐户的用户 ID、参与方 ID 和型号。</span><span class="sxs-lookup"><span data-stu-id="5855a-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="5855a-113">支持的国家/地区</span><span class="sxs-lookup"><span data-stu-id="5855a-113">Supported countries/regions</span></span>

<span data-ttu-id="5855a-114">我们当前仅支持在美国扩充客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="5855a-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="5855a-115">配置扩充</span><span class="sxs-lookup"><span data-stu-id="5855a-115">Configure the enrichment</span></span>

1. <span data-ttu-id="5855a-116">转到 **数据** > **扩充**，选择 **发现** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5855a-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="5855a-117">在 Experian 磁贴上选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="5855a-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5855a-118">![Experian 磁贴](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="5855a-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="5855a-119">从下拉列表中选择[连接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="5855a-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="5855a-120">如果没有连接可用，请联系管理员。</span><span class="sxs-lookup"><span data-stu-id="5855a-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="5855a-121">如果您是管理员，可以通过选择 **添加连接** 并从下拉列表中选择 Experian 来创建连接。</span><span class="sxs-lookup"><span data-stu-id="5855a-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="5855a-122">选择 **连接到 Experian** 以确认连接选择。</span><span class="sxs-lookup"><span data-stu-id="5855a-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="5855a-123">选择 **下一步**，然后选择要使用 Experian 中的人口统计数据扩充的 **客户数据集**。</span><span class="sxs-lookup"><span data-stu-id="5855a-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="5855a-124">您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="5855a-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. <span data-ttu-id="5855a-126">选择 **下一步**，定义应该使用统一配置文件中的哪些字段类型来查找 Experian 中的匹配统计人口数据。</span><span class="sxs-lookup"><span data-stu-id="5855a-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="5855a-127">至少需要 **名称和地址**、**电话** 或 **电子邮件** 中的一个字段。</span><span class="sxs-lookup"><span data-stu-id="5855a-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="5855a-128">为了提高匹配精度，最多可添加其他两个字段。</span><span class="sxs-lookup"><span data-stu-id="5855a-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="5855a-129">此选项会影响您可以在下一步中访问的映射字段。</span><span class="sxs-lookup"><span data-stu-id="5855a-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="5855a-130">发送到 Experian 的密钥标识符属性越多，生成的匹配率可能就越高。</span><span class="sxs-lookup"><span data-stu-id="5855a-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="5855a-131">选择 **下一步** 以开始字段映射。</span><span class="sxs-lookup"><span data-stu-id="5855a-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="5855a-132">定义应该使用统一配置文件中的哪些字段来查找 Experian 中的匹配统计人口数据。</span><span class="sxs-lookup"><span data-stu-id="5855a-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="5855a-133">必填字段都有标记。</span><span class="sxs-lookup"><span data-stu-id="5855a-133">Required fields are marked.</span></span>

1. <span data-ttu-id="5855a-134">提供扩充的名称和输出实体的名称。</span><span class="sxs-lookup"><span data-stu-id="5855a-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="5855a-135">在查看您的选择后选择 **保存扩充**。</span><span class="sxs-lookup"><span data-stu-id="5855a-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="5855a-136">配置 Experian 的连接</span><span class="sxs-lookup"><span data-stu-id="5855a-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="5855a-137">您必须是管理员才能配置连接。</span><span class="sxs-lookup"><span data-stu-id="5855a-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="5855a-138">当配置扩充时选择 **添加连接**，*或者* 转到 **管理** > **连接**，然后在 Experian 磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="5855a-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="5855a-139">选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="5855a-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="5855a-140">在 **显示名称** 框中输入连接的名称。</span><span class="sxs-lookup"><span data-stu-id="5855a-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="5855a-141">为 Experian 安全传输帐户输入有效的用户 ID、参与方 ID 和型号。</span><span class="sxs-lookup"><span data-stu-id="5855a-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="5855a-142">通过选择 **我同意**，查看并同意 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="5855a-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="5855a-143">选择 **验证** 以验证配置。</span><span class="sxs-lookup"><span data-stu-id="5855a-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="5855a-144">完成验证后，选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="5855a-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 连接配置窗格。":::

## <a name="enrichment-results"></a><span data-ttu-id="5855a-146">扩充结果</span><span class="sxs-lookup"><span data-stu-id="5855a-146">Enrichment results</span></span>

<span data-ttu-id="5855a-147">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="5855a-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5855a-148">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="5855a-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5855a-149">处理时间取决于客户数据的大小以及 Experian 为您的帐户设置的扩充处理流程。</span><span class="sxs-lookup"><span data-stu-id="5855a-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="5855a-150">扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="5855a-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="5855a-151">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="5855a-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5855a-152">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="5855a-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5855a-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5855a-153">Next steps</span></span>

<span data-ttu-id="5855a-154">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="5855a-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5855a-155">创建[细分](segments.md)和[度量](measures.md)，甚至[导出数据](export-destinations.md)，以向客户提供个性化体验。</span><span class="sxs-lookup"><span data-stu-id="5855a-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5855a-156">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="5855a-156">Data privacy and compliance</span></span>

<span data-ttu-id="5855a-157">当启用 Dynamics 365 Customer Insights 将数据传输到 Experian 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="5855a-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5855a-158">Microsoft 将根据您的指示传输此类数据，但您负责确保 Experian 满足您可能承担的任何隐私或安全责任。</span><span class="sxs-lookup"><span data-stu-id="5855a-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5855a-159">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="5855a-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5855a-160">您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="5855a-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
