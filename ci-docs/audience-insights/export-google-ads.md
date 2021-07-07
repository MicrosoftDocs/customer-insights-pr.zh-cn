---
title: 将 Customer Insights 数据导出到 Google Ads
description: 了解如何配置连接和导出到 Google Ads。
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305329"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="e5d9e-103">向 Google Ads 导出客户细分（预览版）</span><span class="sxs-lookup"><span data-stu-id="e5d9e-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="e5d9e-104">将统一客户配置文件的客户细分导出到 Google Ads 访问群体列表，并使用它们在 Google Search、Gmail、YouTube 和 Google Display Network 上投放广告。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e5d9e-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="e5d9e-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e5d9e-106">您具有 [Google Ads 帐户](https://ads.google.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e5d9e-107">您有一个[批准的 Google Ads 开发人员令牌](https://developers.google.com/google-ads/api/docs/first-call/dev-token)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="e5d9e-108">您满足[客户匹配策略](https://support.google.com/adspolicy/answer/6299717)的要求。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="e5d9e-109">您满足[重新市场营销列表大小](https://support.google.com/google-ads/answer/7558048)的要求。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="e5d9e-110">Google Ads 中有现有访问群体和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="e5d9e-111">有关详细信息，请参阅 [Google Ads 访问群体](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="e5d9e-112">您已[配置客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e5d9e-113">导出的客户细分中的统一客户配置文件包含表示电子邮件地址、名和姓的字段。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e5d9e-114">已知限制</span><span class="sxs-lookup"><span data-stu-id="e5d9e-114">Known limitations</span></span>

- <span data-ttu-id="e5d9e-115">每次最多可以向 Google Ads 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="e5d9e-116">导出到 Google Ads 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="e5d9e-117">由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="e5d9e-118">在 Google Ads 中匹配可能最多需要 48 个小时。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="e5d9e-119">设置与 Google Ads 的连接</span><span class="sxs-lookup"><span data-stu-id="e5d9e-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="e5d9e-120">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e5d9e-121">选择 **添加连接** 并选择 **Google Ads** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="e5d9e-122">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e5d9e-123">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e5d9e-124">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e5d9e-125">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-125">Choose who can use this connection.</span></span> <span data-ttu-id="e5d9e-126">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e5d9e-127">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e5d9e-128">输入您的 **[Google Ads 客户 ID](https://support.google.com/google-ads/answer/1704344)**。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="e5d9e-129">输入您的 **[Google Ads 审批的开发人员令牌](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="e5d9e-130">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e5d9e-131">选择 **使用 Google Ads 进行身份验证** 并提供您的 Google Ads 凭据。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="e5d9e-132">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e5d9e-133">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e5d9e-134">配置导出</span><span class="sxs-lookup"><span data-stu-id="e5d9e-134">Configure an export</span></span>

<span data-ttu-id="e5d9e-135">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e5d9e-136">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e5d9e-137">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e5d9e-138">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e5d9e-139">在 **导出连接** 字段中，从 Google Ads 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="e5d9e-140">如果看不到此部分名称，则没有此类型的连接可用。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="e5d9e-141">输入您的 **[Google Ads 访问群体 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**，然后选择 **连接** 以初始化与 Google Ads 的连接。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="e5d9e-142">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e5d9e-143">对 **名** 和 **姓** 字段重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="e5d9e-144">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-144">Select the segments you want to export.</span></span> <span data-ttu-id="e5d9e-145">您总共可以将最多 100 万个客户配置文件导出到 Google Ads 中。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="e5d9e-146">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e5d9e-147">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="e5d9e-148">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e5d9e-149">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="e5d9e-149">Data privacy and compliance</span></span>

<span data-ttu-id="e5d9e-150">当您启用 Dynamics 365 Customer Insights 将数据传输到 Google Ads 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e5d9e-151">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Google Ads 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e5d9e-152">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e5d9e-153">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
