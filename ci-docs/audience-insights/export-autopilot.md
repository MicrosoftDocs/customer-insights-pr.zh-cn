---
title: 将 Customer Insights 数据导出到 Autopilot
description: 了解如何配置与 Autopilot 的连接。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269227"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="ed1f8-103">用于 Autopilot 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="ed1f8-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="ed1f8-104">将统一客户配置文件的客户细分导出到 Autopilot，并在 Autopilot 中将其用于电子邮件市场营销。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ed1f8-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="ed1f8-105">Prerequisites</span></span>

-   <span data-ttu-id="ed1f8-106">您具有 [Autopilot 帐户](https://www.autopilothq.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ed1f8-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ed1f8-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="ed1f8-109">连接到 Autopilot</span><span class="sxs-lookup"><span data-stu-id="ed1f8-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="ed1f8-110">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ed1f8-111">在 **Autopilot** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="ed1f8-112">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 连接的配置窗格。":::

1. <span data-ttu-id="ed1f8-114">输入您的 **Autopilot API 密钥** [Autopilot API 密钥](https://autopilot.docs.apiary.io/#)。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="ed1f8-115">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ed1f8-116">选择 **连接** 以初始化与 Autopilot 的连接。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="ed1f8-117">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ed1f8-118">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ed1f8-119">配置连接器</span><span class="sxs-lookup"><span data-stu-id="ed1f8-119">Configure the connector</span></span>

1. <span data-ttu-id="ed1f8-120">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ed1f8-121">对于其他可选字段（例如名 **名** 和 **姓**），请重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="ed1f8-122">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-122">Select the segments you want to export.</span></span> <span data-ttu-id="ed1f8-123">我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="ed1f8-124">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ed1f8-125">导出数据</span><span class="sxs-lookup"><span data-stu-id="ed1f8-125">Export the data</span></span>

<span data-ttu-id="ed1f8-126">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ed1f8-127">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ed1f8-128">已知限制</span><span class="sxs-lookup"><span data-stu-id="ed1f8-128">Known limitations</span></span>

- <span data-ttu-id="ed1f8-129">您总共可以将最多 100'000 个客户配置文件导出到 Autopilot 中。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="ed1f8-130">导出到 Autopilot 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="ed1f8-131">将多达 100'000 个配置文件导出到 Autopilot 可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ed1f8-132">可以导出到 Autopilot 的配置文件数与 Autopilot 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ed1f8-133">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="ed1f8-133">Data privacy and compliance</span></span>

<span data-ttu-id="ed1f8-134">当您启用 Dynamics 365 Customer Insights 将数据传输到 Autopilot 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ed1f8-135">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Autopilot 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ed1f8-136">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ed1f8-137">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ed1f8-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]