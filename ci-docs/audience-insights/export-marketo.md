---
title: 将 Customer Insights 数据导出到 Marketo
description: 了解如何配置与 Marketo 的连接。
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597960"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="f1e72-103">用于 Marketo 的连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="f1e72-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="f1e72-104">导出统一客户配置文件的客户细分以生成市场活动，提供电子邮件市场营销，并通过 Marketo 使用特定客户组。</span><span class="sxs-lookup"><span data-stu-id="f1e72-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1e72-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="f1e72-105">Prerequisites</span></span>

-   <span data-ttu-id="f1e72-106">您具有 [Marketo 帐户](https://login.marketo.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="f1e72-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f1e72-107">Marketo 中有现有列表和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="f1e72-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="f1e72-108">有关详细信息，请参阅 [Marketo 列表](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。</span><span class="sxs-lookup"><span data-stu-id="f1e72-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="f1e72-109">您已[配置客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="f1e72-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="f1e72-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="f1e72-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="f1e72-111">连接到 Marketo</span><span class="sxs-lookup"><span data-stu-id="f1e72-111">Connect to Marketo</span></span>

1. <span data-ttu-id="f1e72-112">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="f1e72-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f1e72-113">在 **Marketo** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="f1e72-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="f1e72-114">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="f1e72-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f1e72-115">输入您的 **[Marketo 客户端 ID、客户端密码和 REST 终结点主机名](https://developers.marketo.com/rest-api/authentication/)**。</span><span class="sxs-lookup"><span data-stu-id="f1e72-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="f1e72-116">输入您的 **[Marketo 列表 ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="f1e72-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="f1e72-117">选择 **我同意** 确认 **数据隐私与合规性**，然后选择 **连接** 以初始化与 Marketo 的连接。</span><span class="sxs-lookup"><span data-stu-id="f1e72-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="f1e72-118">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="f1e72-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="导出 Marketo 连接的屏幕截图":::

1. <span data-ttu-id="f1e72-120">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="f1e72-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f1e72-121">配置连接器</span><span class="sxs-lookup"><span data-stu-id="f1e72-121">Configure the connector</span></span>

1. <span data-ttu-id="f1e72-122">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="f1e72-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f1e72-123">或者，您可以导出 **名**、**姓**、**市/县**、**省/市/自治区** 和 **国家/地区** 作为其他字段，以创建更多个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f1e72-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="f1e72-124">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="f1e72-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f1e72-125">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="f1e72-125">Select the segments you want to export.</span></span> <span data-ttu-id="f1e72-126">您总共可以将最多 100 万个客户配置文件导出到 Marketo 中。</span><span class="sxs-lookup"><span data-stu-id="f1e72-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="选择要导出到 Marketo 的字段和客户细分":::

1. <span data-ttu-id="f1e72-128">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="f1e72-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f1e72-129">导出数据</span><span class="sxs-lookup"><span data-stu-id="f1e72-129">Export the data</span></span>

<span data-ttu-id="f1e72-130">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="f1e72-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f1e72-131">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="f1e72-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f1e72-132">在 Marketo 中，您现在可以在 [Marketo 列表](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)下找到您的客户细分。</span><span class="sxs-lookup"><span data-stu-id="f1e72-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f1e72-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="f1e72-133">Known limitations</span></span>

- <span data-ttu-id="f1e72-134">每次最多可以向 Marketo 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="f1e72-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="f1e72-135">导出到 Marketo 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="f1e72-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="f1e72-136">导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。</span><span class="sxs-lookup"><span data-stu-id="f1e72-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="f1e72-137">可以导出到 Marketo 的配置文件数与 Marketo 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="f1e72-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1e72-138">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="f1e72-138">Data privacy and compliance</span></span>

<span data-ttu-id="f1e72-139">当您启用 Dynamics 365 Customer Insights 将数据传输到 Marketo 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="f1e72-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1e72-140">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Marketo 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="f1e72-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1e72-141">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="f1e72-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1e72-142">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="f1e72-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]