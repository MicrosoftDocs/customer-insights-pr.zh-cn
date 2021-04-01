---
title: 将 Customer Insights 数据导出到 Google Ads
description: 了解如何配置与 Google Ads 的连接。
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598236"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="94499-103">用于 Google Ads 的连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="94499-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="94499-104">将统一客户配置文件的客户细分导出到 Google Ads 访问群体列表，并使用它们在 Google Search、Gmail、YouTube 和 Google Display Network 上投放广告。</span><span class="sxs-lookup"><span data-stu-id="94499-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="94499-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="94499-105">Prerequisites</span></span>

-   <span data-ttu-id="94499-106">您具有 [Google Ads 帐户](https://ads.google.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="94499-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="94499-107">Google Ads 中有现有访问群体和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="94499-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="94499-108">有关详细信息，请参阅 [Google Ads 访问群体](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。</span><span class="sxs-lookup"><span data-stu-id="94499-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="94499-109">您已[配置客户细分](segments.md)</span><span class="sxs-lookup"><span data-stu-id="94499-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="94499-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址、名和姓的字段</span><span class="sxs-lookup"><span data-stu-id="94499-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="94499-111">连接到 Google Ads</span><span class="sxs-lookup"><span data-stu-id="94499-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="94499-112">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="94499-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="94499-113">在 **Google Ads** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="94499-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="94499-114">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="94499-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="94499-115">输入您的 **[Google Ads 客户 ID](https://support.google.com/google-ads/answer/1704344)**。</span><span class="sxs-lookup"><span data-stu-id="94499-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="94499-116">输入您的 **[Google Ads 审批的开发人员令牌](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。</span><span class="sxs-lookup"><span data-stu-id="94499-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="94499-117">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="94499-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94499-118">输入您的 **[Google Ads 访问群体 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**，然后选择 **连接** 以初始化与 Google Ads 的连接。</span><span class="sxs-lookup"><span data-stu-id="94499-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="94499-119">选择 **使用 Google Ads 进行身份验证** 并提供您的 Google Ads 凭据。</span><span class="sxs-lookup"><span data-stu-id="94499-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="94499-120">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="94499-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="导出 Google Ads 连接的屏幕截图":::

1. <span data-ttu-id="94499-122">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="94499-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="94499-123">配置连接器</span><span class="sxs-lookup"><span data-stu-id="94499-123">Configure the connector</span></span>

1. <span data-ttu-id="94499-124">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="94499-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="94499-125">对**名**和 **姓** 字段重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="94499-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="94499-126">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="94499-126">Select the segments you want to export.</span></span> <span data-ttu-id="94499-127">您总共可以将最多 100 万个客户配置文件导出到 Google Ads 中。</span><span class="sxs-lookup"><span data-stu-id="94499-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="94499-128">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="94499-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="94499-129">导出数据</span><span class="sxs-lookup"><span data-stu-id="94499-129">Export the data</span></span>

<span data-ttu-id="94499-130">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="94499-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="94499-131">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="94499-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94499-132">在 Google Ads 中，您现在可以在 [Google Ads 访问群体](https://support.google.com/google-ads/answer/7558048?hl=en/)下找到您的客户细分。</span><span class="sxs-lookup"><span data-stu-id="94499-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94499-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="94499-133">Known limitations</span></span>

- <span data-ttu-id="94499-134">每次最多可以向 Google Ads 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="94499-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="94499-135">导出到 Google Ads 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="94499-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="94499-136">由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="94499-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="94499-137">在 Google Ads 中匹配可能最多需要 48 个小时。</span><span class="sxs-lookup"><span data-stu-id="94499-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94499-138">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="94499-138">Data privacy and compliance</span></span>

<span data-ttu-id="94499-139">当您启用 Dynamics 365 Customer Insights 将数据传输到 Google Ads 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="94499-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94499-140">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Google Ads 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="94499-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="94499-141">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="94499-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94499-142">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="94499-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]