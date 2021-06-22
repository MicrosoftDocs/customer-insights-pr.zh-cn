---
title: 将 Customer Insights 数据导出到 Mailchimp
description: 了解如何配置连接和导出到 Mailchimp。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124216"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="5e5f3-103">将客户细分导出到 Mailchimp（预览版）</span><span class="sxs-lookup"><span data-stu-id="5e5f3-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="5e5f3-104">将统一客户配置文件的客户细分导出到 Mailchimp 以创建新闻速递和电子邮件市场活动。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="5e5f3-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="5e5f3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="5e5f3-106">您具有 [Mailchimp 帐户](https://mailchimp.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5e5f3-107">Mailchimp 中有现有访问群体和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="5e5f3-108">有关详细信息，请参阅 [Mailchimp 访问群体](https://mailchimp.com/help/create-audience/)。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="5e5f3-109">您已[配置客户细分](segments.md)</span><span class="sxs-lookup"><span data-stu-id="5e5f3-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="5e5f3-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5e5f3-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="5e5f3-111">Known limitations</span></span>

- <span data-ttu-id="5e5f3-112">每次最多可以向 Mailchimp 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="5e5f3-113">导出到 Mailchimp 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="5e5f3-114">导出具有 100 万个配置文件的客户细分可能需要最多三个小时。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="5e5f3-115">可以导出到 Mailchimp 的配置文件数与 Mailchimp 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="5e5f3-116">设置与 Mailchimp 的连接</span><span class="sxs-lookup"><span data-stu-id="5e5f3-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="5e5f3-117">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5e5f3-118">选择 **添加连接** 并选择 **Mailchimp** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="5e5f3-119">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5e5f3-120">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5e5f3-121">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5e5f3-122">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-122">Choose who can use this connection.</span></span> <span data-ttu-id="5e5f3-123">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5e5f3-124">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5e5f3-125">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5e5f3-126">选择 **连接** 以初始化与 Mailchimp 的连接。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="5e5f3-127">选择 **使用 Mailchimp 进行身份验证** 并提供您的 Mailchimp 凭据。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="5e5f3-128">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5e5f3-129">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="5e5f3-130">配置连接器</span><span class="sxs-lookup"><span data-stu-id="5e5f3-130">Configure the connector</span></span>

<span data-ttu-id="5e5f3-131">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5e5f3-132">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5e5f3-133">转到 **数据**> **导出**。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="5e5f3-134">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5e5f3-135">在 **导出连接** 字段中，从 Mailchimp 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="5e5f3-136">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5e5f3-137">输入您的 **[Mailchimp 受众 ID](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="5e5f3-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="5e5f3-138">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="5e5f3-139">（可选）您可以导出 **名** 和 **姓** 以创建更个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="5e5f3-140">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="5e5f3-141">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-141">Select the segments you want to export.</span></span> <span data-ttu-id="5e5f3-142">您总共可以将最多 100 万个客户配置文件导出到 Mailchimp 中。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="5e5f3-143">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-143">Select **Save**.</span></span>

<span data-ttu-id="5e5f3-144">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5e5f3-145">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5e5f3-146">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5e5f3-147">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="5e5f3-147">Data privacy and compliance</span></span>

<span data-ttu-id="5e5f3-148">当您启用 Dynamics 365 Customer Insights 将数据传输到 Mailchimp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5e5f3-149">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Mailchimp 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5e5f3-150">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5e5f3-151">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="5e5f3-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
