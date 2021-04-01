---
title: 扩充统一的客户配置文件
description: 使用功能扩充您的客户数据。
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597684"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="be031-103">扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="be031-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="be031-104">使用来自 Microsoft 和其他合作伙伴之类的源的数据来扩充您的客户数据。</span><span class="sxs-lookup"><span data-stu-id="be031-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="扩充中心页面":::

<span data-ttu-id="be031-106">在访问群体见解中，转到 **数据** > **扩充** 以使用扩充选项。</span><span class="sxs-lookup"><span data-stu-id="be031-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="be031-107">您需要具有参与者或管理员权限才能创建或编辑扩充。</span><span class="sxs-lookup"><span data-stu-id="be031-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="be031-108">有关详细信息，请参阅[权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="be031-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="be031-109">在 **发现** 选项卡上，您将看到以下扩充：</span><span class="sxs-lookup"><span data-stu-id="be031-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="be031-110">由 Microsoft Graph 提供的[品牌](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="be031-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="be031-111">由 Microsoft Graph 提供的[兴趣](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="be031-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="be031-112">Leadspace 提供的[公司数据](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="be031-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="be031-113">Experian 提供的[人口统计数据](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="be031-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="be031-114">HERE Technologies 提供的[位置数据](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="be031-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="be031-115">通过安全文件传输协议 (SFTP) [自定义数据](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="be031-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="be031-116">在 **我的扩充** 选项卡上，您可以查看您已配置的扩充并编辑其属性。</span><span class="sxs-lookup"><span data-stu-id="be031-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="be031-117">管理现有扩充</span><span class="sxs-lookup"><span data-stu-id="be031-117">Manage existing enrichments</span></span>

<span data-ttu-id="be031-118">转到 **我的扩充** 查看所有已配置的扩充。</span><span class="sxs-lookup"><span data-stu-id="be031-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="be031-119">每个扩充表示为一行，其中包含有关扩充的其他信息。</span><span class="sxs-lookup"><span data-stu-id="be031-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="be031-120">选择一个扩充来查看可用选项。</span><span class="sxs-lookup"><span data-stu-id="be031-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="be031-121">或者，您可以选择列表项上的省略号 (...) 来查看选项。</span><span class="sxs-lookup"><span data-stu-id="be031-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用于管理扩充列表中的扩充的选项":::

- <span data-ttu-id="be031-123">**查看** 扩充详细信息以及扩充的客户资料的数量。</span><span class="sxs-lookup"><span data-stu-id="be031-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="be031-124">**编辑** 扩充配置。</span><span class="sxs-lookup"><span data-stu-id="be031-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="be031-125">**运行** 扩充，使用最新数据更新客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="be031-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="be031-126">**停用** 现有扩充以阻止其在每次执行计划刷新时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="be031-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="be031-127">来自上一次成功刷新的数据将继续可用。</span><span class="sxs-lookup"><span data-stu-id="be031-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="be031-128">**激活** 停用扩充以重新启动在每次执行计划刷新时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="be031-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="be031-129">**删除** 扩充。</span><span class="sxs-lookup"><span data-stu-id="be031-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="be031-130">您可以通过在列表中选择扩充来一次运行或停用多个扩充。</span><span class="sxs-lookup"><span data-stu-id="be031-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="be031-131">查看和编辑选项不能用作批量操作，一次只能对一个扩充执行。</span><span class="sxs-lookup"><span data-stu-id="be031-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]