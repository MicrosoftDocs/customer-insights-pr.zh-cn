---
title: 将 Customer Insights 数据导出到 Autopilot
description: 了解如何配置连接和导出到 Autopilot。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760132"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="296b7-103">将细分市场导出到 Autopilot（预览版）</span><span class="sxs-lookup"><span data-stu-id="296b7-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="296b7-104">将统一客户配置文件的客户细分导出到 Autopilot，并在 Autopilot 中将其用于电子邮件市场营销。</span><span class="sxs-lookup"><span data-stu-id="296b7-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="296b7-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="296b7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="296b7-106">您具有 [Autopilot 帐户](https://www.autopilothq.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="296b7-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="296b7-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="296b7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="296b7-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="296b7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="296b7-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="296b7-109">Known limitations</span></span>

- <span data-ttu-id="296b7-110">您总共可以将最多 100'000 个客户配置文件导出到 Autopilot 中。</span><span class="sxs-lookup"><span data-stu-id="296b7-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="296b7-111">导出到 Autopilot 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="296b7-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="296b7-112">将多达 100'000 个配置文件导出到 Autopilot 可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="296b7-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="296b7-113">可以导出到 Autopilot 的配置文件数与 Autopilot 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="296b7-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="296b7-114">设置与 Autopilot 的连接</span><span class="sxs-lookup"><span data-stu-id="296b7-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="296b7-115">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="296b7-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="296b7-116">选择 **添加连接** 并选择 **Mailchimp** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="296b7-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="296b7-117">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="296b7-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="296b7-118">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="296b7-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="296b7-119">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="296b7-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="296b7-120">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="296b7-120">Choose who can use this connection.</span></span> <span data-ttu-id="296b7-121">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="296b7-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="296b7-122">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="296b7-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="296b7-123">输入 [Autopilot API 密钥](https://autopilot.docs.apiary.io/#)。</span><span class="sxs-lookup"><span data-stu-id="296b7-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="296b7-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="296b7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="296b7-125">选择 **连接** 以初始化与 Autopilot 的连接。</span><span class="sxs-lookup"><span data-stu-id="296b7-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="296b7-126">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="296b7-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="296b7-127">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="296b7-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="296b7-128">配置导出</span><span class="sxs-lookup"><span data-stu-id="296b7-128">Configure an export</span></span>

<span data-ttu-id="296b7-129">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="296b7-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="296b7-130">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="296b7-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="296b7-131">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="296b7-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="296b7-132">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="296b7-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="296b7-133">在 **导出连接** 字段中，从 Autopilot 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="296b7-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="296b7-134">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="296b7-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="296b7-135">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="296b7-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="296b7-136">对于其他可选字段（例如名 **名** 和 **姓**），请重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="296b7-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="296b7-137">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="296b7-137">Select the segments you want to export.</span></span> <span data-ttu-id="296b7-138">我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="296b7-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="296b7-139">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="296b7-139">Select **Save**.</span></span>

<span data-ttu-id="296b7-140">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="296b7-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="296b7-141">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="296b7-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="296b7-142">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="296b7-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="296b7-143">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="296b7-143">Data privacy and compliance</span></span>

<span data-ttu-id="296b7-144">当您启用 Dynamics 365 Customer Insights 将数据传输到 Autopilot 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="296b7-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="296b7-145">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Autopilot 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="296b7-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="296b7-146">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="296b7-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="296b7-147">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="296b7-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
