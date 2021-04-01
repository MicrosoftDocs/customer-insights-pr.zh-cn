---
title: 将 Customer Insights 数据导出到 AdRoll
description: 了解如何配置与 AdRoll 的连接。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697063"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="a94b7-103">用于 AdRoll 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="a94b7-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="a94b7-104">将统一客户配置文件的客户细分导出到 AdRoll 中，并使用它们投放广告。</span><span class="sxs-lookup"><span data-stu-id="a94b7-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a94b7-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="a94b7-105">Prerequisites</span></span>

-   <span data-ttu-id="a94b7-106">您具有 [AdRoll 帐户](https://www.adroll.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="a94b7-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a94b7-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="a94b7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a94b7-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="a94b7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="a94b7-109">连接到 AdRoll</span><span class="sxs-lookup"><span data-stu-id="a94b7-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="a94b7-110">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="a94b7-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a94b7-111">在 **AdRoll** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="a94b7-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="a94b7-112">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="a94b7-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 连接的配置窗格。":::

1. <span data-ttu-id="a94b7-114">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="a94b7-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a94b7-115">选择 **连接** 以初始化与 AdRoll 的连接。</span><span class="sxs-lookup"><span data-stu-id="a94b7-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="a94b7-116">选择 **使用 AdRoll 进行身份验证** 并提供您的 AdRoll 管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="a94b7-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="a94b7-117">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="a94b7-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a94b7-118">输入您的 **AdRoll 广告厂商 ID** [AdRoll 播发功能](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="a94b7-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="a94b7-119">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="a94b7-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a94b7-120">配置连接器</span><span class="sxs-lookup"><span data-stu-id="a94b7-120">Configure the connector</span></span>

1. <span data-ttu-id="a94b7-121">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="a94b7-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a94b7-122">需要将客户细分导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="a94b7-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="a94b7-123">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="a94b7-123">Select the segments you want to export.</span></span> <span data-ttu-id="a94b7-124">选择至少包含 100 个成员的客户细分。</span><span class="sxs-lookup"><span data-stu-id="a94b7-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="a94b7-125">不能导出较小的客户细分。</span><span class="sxs-lookup"><span data-stu-id="a94b7-125">You can't export smaller segments.</span></span> <span data-ttu-id="a94b7-126">此外，对于每个导出，要导出的客户细分的最大大小为 250'000 个成员。</span><span class="sxs-lookup"><span data-stu-id="a94b7-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="a94b7-127">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="a94b7-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a94b7-128">导出数据</span><span class="sxs-lookup"><span data-stu-id="a94b7-128">Export the data</span></span>

<span data-ttu-id="a94b7-129">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="a94b7-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a94b7-130">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="a94b7-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a94b7-131">已知限制</span><span class="sxs-lookup"><span data-stu-id="a94b7-131">Known limitations</span></span>

- <span data-ttu-id="a94b7-132">对于每个导出，您最多可以将 250'000 个配置文件导出到 AdRoll 中。</span><span class="sxs-lookup"><span data-stu-id="a94b7-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="a94b7-133">您不能将配置文件少于 100 个的客户细分导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="a94b7-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="a94b7-134">导出到 AdRoll 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="a94b7-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="a94b7-135">最多将 250'000 个配置文件导出到 AdRoll 可能需要 10 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="a94b7-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="a94b7-136">可以导出到 AdRoll 的配置文件数与 AdRoll 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="a94b7-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a94b7-137">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="a94b7-137">Data privacy and compliance</span></span>

<span data-ttu-id="a94b7-138">当您启用 Dynamics 365 Customer Insights 将数据传输到 AdRoll 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="a94b7-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a94b7-139">Microsoft 将在您的指导下传输此类数据，但您有责任确保 AdRoll 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="a94b7-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a94b7-140">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="a94b7-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a94b7-141">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="a94b7-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
