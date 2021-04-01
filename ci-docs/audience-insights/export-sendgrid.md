---
title: 将 Customer Insights 数据导出到 SendGrid
description: 了解如何配置与 SendGrid 的连接。
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597270"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="ae2c1-103">用于 SendGrid 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="ae2c1-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="ae2c1-104">将统一客户配置文件的客户细分导出到 SendGrid 联系人列表，并在 SendGrid 中将其用于市场活动和电子邮件市场营销。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ae2c1-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="ae2c1-105">Prerequisites</span></span>

-   <span data-ttu-id="ae2c1-106">您具有 [SendGrid 帐户](https://sendgrid.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ae2c1-107">SendGrid 中已有联系人列表和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="ae2c1-108">有关详细信息，请参阅 [SendGrid - 管理联系人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="ae2c1-109">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ae2c1-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="ae2c1-111">连接到 SendGrid</span><span class="sxs-lookup"><span data-stu-id="ae2c1-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="ae2c1-112">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae2c1-113">在 **SendGrid** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="ae2c1-114">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid 导出配置窗格。":::

1. <span data-ttu-id="ae2c1-116">输入您的 **SendGrid API 密钥** [SendGrid API 密钥](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="ae2c1-117">输入您的 **[SendGrid 列表 ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="ae2c1-118">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ae2c1-119">选择 **连接** 以初始化与 SendGrid 的连接。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="ae2c1-120">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ae2c1-121">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ae2c1-122">配置连接器</span><span class="sxs-lookup"><span data-stu-id="ae2c1-122">Configure the connector</span></span>

1. <span data-ttu-id="ae2c1-123">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ae2c1-124">对于其他可选字段（例如 **名**、**姓**、**国家/地区**、**省/自治区/直辖市**、**市/县** 和 **邮政编码**），请重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="ae2c1-125">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-125">Select the segments you want to export.</span></span> <span data-ttu-id="ae2c1-126">我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 SendGrid。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="ae2c1-127">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae2c1-128">导出数据</span><span class="sxs-lookup"><span data-stu-id="ae2c1-128">Export the data</span></span>

<span data-ttu-id="ae2c1-129">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ae2c1-130">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ae2c1-131">已知限制</span><span class="sxs-lookup"><span data-stu-id="ae2c1-131">Known limitations</span></span>

- <span data-ttu-id="ae2c1-132">总共最多可以将 100'000 个配置文件导出到 SendGrid。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="ae2c1-133">导出到 SendGrid 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="ae2c1-134">将多达 100'000 个配置文件导出到 SendGrid 可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ae2c1-135">可以导出到 SendGrid 的配置文件数与 SendGrid 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ae2c1-136">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="ae2c1-136">Data privacy and compliance</span></span>

<span data-ttu-id="ae2c1-137">当您启用 Dynamics 365 Customer Insights 将数据传输到 SendGrid 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ae2c1-138">Microsoft 将在您的指导下传输此类数据，但您有责任确保 SendGrid 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ae2c1-139">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ae2c1-140">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ae2c1-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]