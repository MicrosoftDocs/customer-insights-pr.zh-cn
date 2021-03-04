---
title: 将 Customer Insights 数据导出到 Mailchimp
description: 了解如何配置与 Mailchimp 的连接。
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267162"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="810a7-103">用于 Mailchimp 的连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="810a7-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="810a7-104">将统一客户配置文件的客户细分导出到 Mailchimp 以创建新闻速递和电子邮件市场活动。</span><span class="sxs-lookup"><span data-stu-id="810a7-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="810a7-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="810a7-105">Prerequisites</span></span>

-   <span data-ttu-id="810a7-106">您具有 [Mailchimp 帐户](https://mailchimp.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="810a7-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="810a7-107">Mailchimp 中有现有访问群体和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="810a7-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="810a7-108">有关详细信息，请参阅 [Mailchimp 访问群体](https://mailchimp.com/help/create-audience/)。</span><span class="sxs-lookup"><span data-stu-id="810a7-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="810a7-109">您已[配置客户细分](segments.md)</span><span class="sxs-lookup"><span data-stu-id="810a7-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="810a7-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="810a7-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="810a7-111">连接到 Mailchimp</span><span class="sxs-lookup"><span data-stu-id="810a7-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="810a7-112">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="810a7-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="810a7-113">在 **Mailchimp** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="810a7-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="810a7-114">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="810a7-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="810a7-115">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="810a7-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="810a7-116">输入您的 **[Mailchimp 访问群体 ID](https://mailchimp.com/help/find-audience-id/)**，然后选择 **连接** 以初始化与 Mailchimp 的连接。</span><span class="sxs-lookup"><span data-stu-id="810a7-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="810a7-117">选择 **使用 Mailchimp 进行身份验证** 并提供您的 Mailchimp 凭据。</span><span class="sxs-lookup"><span data-stu-id="810a7-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="810a7-118">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="810a7-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="导出 Mailchimp 连接的屏幕截图":::

1. <span data-ttu-id="810a7-120">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="810a7-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="810a7-121">配置连接器</span><span class="sxs-lookup"><span data-stu-id="810a7-121">Configure the connector</span></span>

1. <span data-ttu-id="810a7-122">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="810a7-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="810a7-123">或者，您可以导出 **名** 和 **姓** 作为其他字段，以创建更多个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="810a7-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="810a7-124">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="810a7-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="810a7-125">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="810a7-125">Select the segments you want to export.</span></span> <span data-ttu-id="810a7-126">您总共可以将最多 100 万个客户配置文件导出到 Mailchimp 中。</span><span class="sxs-lookup"><span data-stu-id="810a7-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="选择要导出到 Mailchimp 的字段和客户细分":::

1. <span data-ttu-id="810a7-128">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="810a7-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="810a7-129">导出数据</span><span class="sxs-lookup"><span data-stu-id="810a7-129">Export the data</span></span>

<span data-ttu-id="810a7-130">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="810a7-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="810a7-131">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="810a7-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="810a7-132">在 Mailchimp 中，您现在可以在 [Mailchimp 访问群体](https://mailchimp.com/help/create-audience/)下找到您的客户细分。</span><span class="sxs-lookup"><span data-stu-id="810a7-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="810a7-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="810a7-133">Known limitations</span></span>

- <span data-ttu-id="810a7-134">每次最多可以向 Mailchimp 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="810a7-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="810a7-135">导出到 Mailchimp 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="810a7-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="810a7-136">由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要三个小时。</span><span class="sxs-lookup"><span data-stu-id="810a7-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="810a7-137">可以导出到 Mailchimp 的配置文件数与 Mailchimp 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="810a7-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="810a7-138">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="810a7-138">Data privacy and compliance</span></span>

<span data-ttu-id="810a7-139">当您启用 Dynamics 365 Customer Insights 将数据传输到 Mailchimp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="810a7-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="810a7-140">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Mailchimp 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="810a7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="810a7-141">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="810a7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="810a7-142">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="810a7-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]