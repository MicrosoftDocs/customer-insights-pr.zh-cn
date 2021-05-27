---
title: 扩充统一的客户配置文件
description: 使用功能扩充您的客户数据。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954476"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="4c1ea-103">扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="4c1ea-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="4c1ea-104">使用来自 Microsoft 和其他合作伙伴之类的源的数据来扩充您的客户数据。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="扩充中心页面":::

<span data-ttu-id="4c1ea-106">在访问群体见解中，转到 **数据** > **扩充** 以使用扩充选项。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="4c1ea-107">您需要具有参与者或管理员权限才能创建或编辑扩充。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="4c1ea-108">有关详细信息，请参阅[权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="4c1ea-109">在 **发现** 选项卡上，您将看到以下扩充：</span><span class="sxs-lookup"><span data-stu-id="4c1ea-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="4c1ea-110">Microsoft 提供的[品牌](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="4c1ea-111">Microsoft 提供的[兴趣](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="4c1ea-112">Microsoft 提供的[增强地址](enrichment-enhanced-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="4c1ea-113">Leadspace 提供的[公司数据](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="4c1ea-114">Experian 提供的[人口统计数据](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="4c1ea-115">HERE Technologies 提供的[位置数据](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="4c1ea-116">通过安全文件传输协议 (SFTP) [自定义数据](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="4c1ea-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="4c1ea-117">在 **我的扩充** 选项卡上，您可以查看您已配置的扩充并编辑其属性。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="4c1ea-118">管理现有扩充</span><span class="sxs-lookup"><span data-stu-id="4c1ea-118">Manage existing enrichments</span></span>

<span data-ttu-id="4c1ea-119">转到 **我的扩充** 查看所有已配置的扩充。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="4c1ea-120">每个扩充表示为一行，其中包含有关扩充的其他信息。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="4c1ea-121">选择一个扩充来查看可用选项。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="4c1ea-122">您还可以选择列表项上的椭圆 (...) 以查看选项。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用于管理扩充列表中的扩充的选项":::

- <span data-ttu-id="4c1ea-124">**查看** 扩充详细信息以及扩充的客户资料的数量。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="4c1ea-125">**编辑** 扩充配置。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="4c1ea-126">**运行** 扩充，使用最新数据更新客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="4c1ea-127">**停用** 现有扩充以阻止其在每次执行计划刷新时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="4c1ea-128">来自上一次成功刷新的数据将继续可用。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="4c1ea-129">**激活** 停用扩充以重新启动在每次执行计划刷新时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="4c1ea-130">**删除** 扩充。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="4c1ea-131">您可以通过在列表中选择扩充来一次运行或停用多个扩充。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="4c1ea-132">查看和编辑选项不能用作批量操作，一次只能对一个扩充执行。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="4c1ea-133">扩充和连接</span><span class="sxs-lookup"><span data-stu-id="4c1ea-133">Enrichments and connections</span></span>

<span data-ttu-id="4c1ea-134">使用管理员用凭据设置并且同意进行数据传输的[连接](connections.md)配置了第三方扩充。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="4c1ea-135">然后，管理员和参与者可以使用这些连接配置扩充。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="4c1ea-136">相同类型的多项扩充</span><span class="sxs-lookup"><span data-stu-id="4c1ea-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="4c1ea-137">扩充配置期间已指定了要扩充的实体，这允许您仅扩充配置文件子集。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="4c1ea-138">例如，仅针对特定客户细分扩充数据。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="4c1ea-139">您可以配置相同类型的多项扩充并重复使用相同的连接。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="4c1ea-140">某些扩充对可创建的相同类型的扩充数量有限制。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="4c1ea-141">可以在 **扩充** 页面上看到限制和当前使用情况。</span><span class="sxs-lookup"><span data-stu-id="4c1ea-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
