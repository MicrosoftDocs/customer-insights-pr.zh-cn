---
title: 将 Customer Insights 数据导出到 Campaign Monitor
description: 了解如何配置连接和导出到 Campaign Monitor。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124170"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="4bcdf-103">将客户细分导出到 Campaign Monitor（预览版）</span><span class="sxs-lookup"><span data-stu-id="4bcdf-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="4bcdf-104">将统一客户配置文件的客户细分导出到 Campaign Monitor，并将其用于市场营销活动。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bcdf-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="4bcdf-105">Prerequisites</span></span>

-   <span data-ttu-id="4bcdf-106">您有一个 [Campaign Monitor 帐户](https://www.campaignmonitor.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4bcdf-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4bcdf-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4bcdf-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="4bcdf-109">Known limitations</span></span>

- <span data-ttu-id="4bcdf-110">对于每次导出，您可以向 Campaign Monitor 导出多达 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="4bcdf-111">导出到 Campaign Monitor 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="4bcdf-112">向 Campaign Monitor 导出多达 100 万个配置文件可能最多需要 20 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="4bcdf-113">您可以导出到 Campaign Monitor 的配置文件数量取决于并受限于您的 Campaign Monitor 联系人。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="4bcdf-114">设置与 Campaign Monitor 的连接</span><span class="sxs-lookup"><span data-stu-id="4bcdf-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="4bcdf-115">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4bcdf-116">选择 **添加连接** 并选择 **Campaign Monitor** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="4bcdf-117">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4bcdf-118">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4bcdf-119">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4bcdf-120">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-120">Choose who can use this connection.</span></span> <span data-ttu-id="4bcdf-121">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4bcdf-122">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4bcdf-123">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4bcdf-124">选择 **连接** 以初始化与 Campaign Monitor 的连接。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="4bcdf-125">选择 **使用 Campaign Monitor 进行身份验证**，并为 Campaign Monitor 提供您的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="4bcdf-126">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4bcdf-127">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4bcdf-128">配置导出</span><span class="sxs-lookup"><span data-stu-id="4bcdf-128">Configure an export</span></span>

<span data-ttu-id="4bcdf-129">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4bcdf-130">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4bcdf-131">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4bcdf-132">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4bcdf-133">在 **导出连接** 字段中，从 Campaign Monitor 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="4bcdf-134">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4bcdf-135">输入 [**Campaign Monitor 列表 ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id)。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="4bcdf-136">首先从 Campaign Monitor 内的 **帐户设置** 中[生成 API 密钥](https://www.campaignmonitor.com/api/getting-started/)以查看 API 列表 ID。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="4bcdf-137">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4bcdf-138">必须将客户细分导出到 Campaign Monitor。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="4bcdf-139">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-139">Select **Save**.</span></span>

<span data-ttu-id="4bcdf-140">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4bcdf-141">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4bcdf-142">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4bcdf-143">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="4bcdf-143">Data privacy and compliance</span></span>

<span data-ttu-id="4bcdf-144">当您启用 Dynamics 365 Customer Insights 以将数据传输到 Campaign Monitor 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4bcdf-145">Microsoft 将在您的指示下传输此类数据，但您有责任确保 Campaign Monitor 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4bcdf-146">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4bcdf-147">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="4bcdf-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
