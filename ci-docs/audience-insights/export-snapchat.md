---
title: 将 Customer Insights 数据导出到 Snapchat
description: 了解如何配置连接和导出到 Snapchat。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760480"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="1aa5d-103">将客户细分列表导出到 Snapchat（预览版）</span><span class="sxs-lookup"><span data-stu-id="1aa5d-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="1aa5d-104">将统一客户配置文件的客户细分导出到 Snapchat，并将其用于广告。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1aa5d-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="1aa5d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="1aa5d-106">您有一个 [Snapchat 业务帐户](https://business.snapchat.com/)、一个 [Snapchat 广告帐户](https://ads.snapchat.com/)以及相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1aa5d-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1aa5d-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1aa5d-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="1aa5d-109">Known limitations</span></span>

- <span data-ttu-id="1aa5d-110">导出到 Snapchat 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="1aa5d-111">向 Snapchat 导出多达 100 万个配置文件可能最多需要 15 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="1aa5d-112">设置与 Snapchat 的连接</span><span class="sxs-lookup"><span data-stu-id="1aa5d-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="1aa5d-113">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1aa5d-114">选择 **添加连接** 并选择 **Snapchat** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="1aa5d-115">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1aa5d-116">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1aa5d-117">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1aa5d-118">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-118">Choose who can use this connection.</span></span> <span data-ttu-id="1aa5d-119">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1aa5d-120">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1aa5d-121">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1aa5d-122">选择 **连接** 以初始化与 Snapchat 的连接。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="1aa5d-123">选择 **使用 Snapchat 进行身份验证**，并为 Snapchat 提供您的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="1aa5d-124">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1aa5d-125">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1aa5d-126">配置导出</span><span class="sxs-lookup"><span data-stu-id="1aa5d-126">Configure an export</span></span>

<span data-ttu-id="1aa5d-127">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1aa5d-128">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1aa5d-129">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1aa5d-130">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1aa5d-131">在 **导出连接** 字段中，从 Snapchat 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="1aa5d-132">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1aa5d-133">输入 [**Snapchat 受众 ID**](https://businesshelp.snapchat.com/s/article/custom-audiences)。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="1aa5d-134">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1aa5d-135">必须将客户细分导出到 Snapchat。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="1aa5d-136">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="1aa5d-137">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-137">Select **Save**.</span></span>

<span data-ttu-id="1aa5d-138">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1aa5d-139">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1aa5d-140">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1aa5d-141">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="1aa5d-141">Data privacy and compliance</span></span>

<span data-ttu-id="1aa5d-142">当您启用 Dynamics 365 Customer Insights 以将数据传输到 Snapchat 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1aa5d-143">Microsoft 将在您的指示下传输此类数据，但您有责任确保 Snapchat 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1aa5d-144">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1aa5d-145">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="1aa5d-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
