---
title: 将 Customer Insights 数据导出到 DotDigital
description: 了解如何配置与 DotDigital 的连接。
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598006"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="8a254-103">用于 DotDigital 的连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="8a254-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="8a254-104">将统一客户配置文件的客户细分导出到 DotDigital 通讯簿，并将其用于市场活动、电子邮件市场营销和使用 DotDigital 生成客户细分。</span><span class="sxs-lookup"><span data-stu-id="8a254-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8a254-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="8a254-105">Prerequisites</span></span>

-   <span data-ttu-id="8a254-106">您具有 [DotDigital 帐户](https://dotdigital.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="8a254-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8a254-107">DotDigital 中有现有通讯簿和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="8a254-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="8a254-108">当您选择并打开通讯簿时，可以在 URL 中找到 ID。</span><span class="sxs-lookup"><span data-stu-id="8a254-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="8a254-109">有关详细信息，请参阅 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。</span><span class="sxs-lookup"><span data-stu-id="8a254-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="8a254-110">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="8a254-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8a254-111">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="8a254-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="8a254-112">连接到 DotDigital</span><span class="sxs-lookup"><span data-stu-id="8a254-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="8a254-113">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="8a254-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8a254-114">在 **DotDigital** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="8a254-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="8a254-115">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="8a254-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="用于 DotDigital 导出的配置窗格。":::

1. <span data-ttu-id="8a254-117">输入您的 **DotDigital 用户名和密码**。</span><span class="sxs-lookup"><span data-stu-id="8a254-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="8a254-118">输入您的 **[DotDigital 通讯簿 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。</span><span class="sxs-lookup"><span data-stu-id="8a254-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="8a254-119">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="8a254-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8a254-120">选择 **连接** 以初始化与 DotDigital 的连接。</span><span class="sxs-lookup"><span data-stu-id="8a254-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="8a254-121">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="8a254-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8a254-122">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="8a254-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8a254-123">配置连接器</span><span class="sxs-lookup"><span data-stu-id="8a254-123">Configure the connector</span></span>

1. <span data-ttu-id="8a254-124">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="8a254-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8a254-125">对于其他可选字段（例如 **名**、**姓**、**全名**、**性别** 和 **邮政编码**），请重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="8a254-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="8a254-126">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="8a254-126">Select the segments you want to export.</span></span> <span data-ttu-id="8a254-127">您总共可以将最多 100 万个客户配置文件导出到 DotDigital 中。</span><span class="sxs-lookup"><span data-stu-id="8a254-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="8a254-128">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="8a254-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8a254-129">导出数据</span><span class="sxs-lookup"><span data-stu-id="8a254-129">Export the data</span></span>

<span data-ttu-id="8a254-130">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="8a254-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8a254-131">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="8a254-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8a254-132">在 DotDigital 中，您现在可以在 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)中找到您的客户细分。</span><span class="sxs-lookup"><span data-stu-id="8a254-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8a254-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="8a254-133">Known limitations</span></span>

- <span data-ttu-id="8a254-134">每次最多可以向 DotDigital 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="8a254-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="8a254-135">导出到 DotDigital 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="8a254-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="8a254-136">由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。</span><span class="sxs-lookup"><span data-stu-id="8a254-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8a254-137">可以导出到 DotDigital 的配置文件数与 DotDigital 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="8a254-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8a254-138">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="8a254-138">Data privacy and compliance</span></span>

<span data-ttu-id="8a254-139">当您启用 Dynamics 365 Customer Insights 将数据传输到 DotDigital 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="8a254-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8a254-140">Microsoft 将在您的指导下传输此类数据，但您有责任确保 DotDigital 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="8a254-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8a254-141">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="8a254-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8a254-142">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="8a254-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]