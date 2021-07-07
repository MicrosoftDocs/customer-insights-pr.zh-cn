---
title: 将 Customer Insights 数据导出到 Sendinblue
description: 了解如何配置连接和导出到 Sendinblue。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314583"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="65fbc-103">将客户细分导出到 Sendinblue（预览）</span><span class="sxs-lookup"><span data-stu-id="65fbc-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="65fbc-104">导出统一客户配置文件的客户细分来生成市场活动，提供电子邮件市场营销，并通过 Sendinblue 使用特定客户组。</span><span class="sxs-lookup"><span data-stu-id="65fbc-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="65fbc-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="65fbc-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="65fbc-106">您具有 [Sendinblue 帐户](https://www.sendinblue.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="65fbc-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="65fbc-107">Sendinblue 中存在现有列表和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="65fbc-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="65fbc-108">您已[配置客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="65fbc-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="65fbc-109">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="65fbc-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="65fbc-110">已知限制</span><span class="sxs-lookup"><span data-stu-id="65fbc-110">Known limitations</span></span>

- <span data-ttu-id="65fbc-111">每个导出最多将 100 万个配置文件导出到 Sendinblue。</span><span class="sxs-lookup"><span data-stu-id="65fbc-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="65fbc-112">导出到 Sendinblue 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="65fbc-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="65fbc-113">导出总数为 100 万个配置文件的客户细分可能需要最多 90 分钟。</span><span class="sxs-lookup"><span data-stu-id="65fbc-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="65fbc-114">可以导出到 Sendinblue 的配置文件数依赖于您与 AdRoll 的合同并受其限制。</span><span class="sxs-lookup"><span data-stu-id="65fbc-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="65fbc-115">设置与 Sendinblue 的连接</span><span class="sxs-lookup"><span data-stu-id="65fbc-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="65fbc-116">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="65fbc-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="65fbc-117">选择 **添加连接** 并选择 **Sendinblue** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="65fbc-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="65fbc-118">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="65fbc-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="65fbc-119">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="65fbc-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="65fbc-120">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="65fbc-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="65fbc-121">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="65fbc-121">Choose who can use this connection.</span></span> <span data-ttu-id="65fbc-122">默认情况下，它只是管理员。</span><span class="sxs-lookup"><span data-stu-id="65fbc-122">By default it's only administrators.</span></span> <span data-ttu-id="65fbc-123">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="65fbc-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="65fbc-124">输入 **[SendinBlue API 密钥](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**。</span><span class="sxs-lookup"><span data-stu-id="65fbc-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="65fbc-125">选择 **我同意** 确认 **数据隐私与合规性**，然后选择 **连接** 以初始化与 Sendinblue 的连接。</span><span class="sxs-lookup"><span data-stu-id="65fbc-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="65fbc-126">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="65fbc-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="65fbc-127">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="65fbc-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="65fbc-128">配置导出</span><span class="sxs-lookup"><span data-stu-id="65fbc-128">Configure an export</span></span>

<span data-ttu-id="65fbc-129">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="65fbc-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="65fbc-130">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="65fbc-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="65fbc-131">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="65fbc-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="65fbc-132">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="65fbc-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="65fbc-133">在 **用于导出的连接** 字段中，从 Sendinblue 部分中选择连接。</span><span class="sxs-lookup"><span data-stu-id="65fbc-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="65fbc-134">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="65fbc-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="65fbc-135">输入您的 **Sendinblue 列表 ID**</span><span class="sxs-lookup"><span data-stu-id="65fbc-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="65fbc-136">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="65fbc-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="65fbc-137">您也可以选择导出 **名**、**姓** 和 **电话号码** 来创建更个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="65fbc-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="65fbc-138">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="65fbc-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="65fbc-139">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="65fbc-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="65fbc-140">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="65fbc-140">Select **Save**.</span></span>

<span data-ttu-id="65fbc-141">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="65fbc-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="65fbc-142">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="65fbc-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="65fbc-143">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="65fbc-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="65fbc-144">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="65fbc-144">Data privacy and compliance</span></span>

<span data-ttu-id="65fbc-145">当启用 Dynamics 365 Customer Insights 将数据传输到 Sendinblue 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="65fbc-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="65fbc-146">Microsoft 将根据您的指示传输此类数据，但您负责确保 Sendinblue 满足您可能承担的任何隐私或安全责任。</span><span class="sxs-lookup"><span data-stu-id="65fbc-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="65fbc-147">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="65fbc-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="65fbc-148">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="65fbc-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
