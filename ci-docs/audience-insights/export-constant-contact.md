---
title: 将 Customer Insights 数据导出到 Constant Contact
description: 了解如何配置连接和导出到 Constant Contact。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760481"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="97ee6-103">将客户细分列表导出到 Constant Contact（预览版）</span><span class="sxs-lookup"><span data-stu-id="97ee6-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="97ee6-104">将统一客户配置文件的客户细分导出到 Constant Contact，并将其用于市场营销活动。</span><span class="sxs-lookup"><span data-stu-id="97ee6-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="97ee6-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="97ee6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="97ee6-106">您有一个 [Constant Contact 帐户](https://www.constantcontact.com/account-home)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="97ee6-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="97ee6-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="97ee6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="97ee6-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="97ee6-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97ee6-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="97ee6-109">Known limitations</span></span>

- <span data-ttu-id="97ee6-110">对于每次导出，您可以向 Constant Contact 导出多达 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="97ee6-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="97ee6-111">导出到 Constant Contact 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="97ee6-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="97ee6-112">向 Constant Contact 导出多达 100 万个配置文件可能最多需要 1 小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="97ee6-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="97ee6-113">您可以导出到 Constant Contact 的配置文件数量取决于并受限于您的 Constant Contact 联系人。</span><span class="sxs-lookup"><span data-stu-id="97ee6-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="97ee6-114">设置与 Constant Contact 的连接</span><span class="sxs-lookup"><span data-stu-id="97ee6-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="97ee6-115">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="97ee6-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="97ee6-116">选择 **添加连接** 并选择 **Constant Contact** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="97ee6-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="97ee6-117">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="97ee6-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="97ee6-118">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="97ee6-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="97ee6-119">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="97ee6-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="97ee6-120">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="97ee6-120">Choose who can use this connection.</span></span> <span data-ttu-id="97ee6-121">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="97ee6-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="97ee6-122">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="97ee6-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="97ee6-123">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="97ee6-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97ee6-124">选择 **连接** 以初始化与 Constant Contact 的连接。</span><span class="sxs-lookup"><span data-stu-id="97ee6-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="97ee6-125">选择 **使用 AdRoll 进行身份验证**，并为 Constant Contact 提供您的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="97ee6-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="97ee6-126">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="97ee6-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="97ee6-127">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="97ee6-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="97ee6-128">配置导出</span><span class="sxs-lookup"><span data-stu-id="97ee6-128">Configure an export</span></span>

<span data-ttu-id="97ee6-129">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="97ee6-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="97ee6-130">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="97ee6-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="97ee6-131">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="97ee6-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="97ee6-132">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="97ee6-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="97ee6-133">在 **导出连接** 字段中，从 Constant Contact 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="97ee6-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="97ee6-134">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="97ee6-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="97ee6-135">输入 [**Constant Contact 列表 ID**](https://app.constantcontact.com/pages/contacts/ui#lists)。</span><span class="sxs-lookup"><span data-stu-id="97ee6-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="97ee6-136">在 Constant Contact 中打开列表以查找 URL 中的列表 ID。</span><span class="sxs-lookup"><span data-stu-id="97ee6-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="97ee6-137">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="97ee6-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="97ee6-138">必须将客户细分导出到 Constant Contact。</span><span class="sxs-lookup"><span data-stu-id="97ee6-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="97ee6-139">或者，您可以导出名和姓作为其他字段，以创建更多个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="97ee6-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="97ee6-140">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="97ee6-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="97ee6-141">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="97ee6-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="97ee6-142">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="97ee6-142">Select **Save**.</span></span>

<span data-ttu-id="97ee6-143">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="97ee6-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="97ee6-144">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="97ee6-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="97ee6-145">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="97ee6-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97ee6-146">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="97ee6-146">Data privacy and compliance</span></span>

<span data-ttu-id="97ee6-147">当您启用 Dynamics 365 Customer Insights 以将数据传输到 Constant Contact 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="97ee6-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97ee6-148">Microsoft 将在您的指示下传输此类数据，但您有责任确保 Constant Contact 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="97ee6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97ee6-149">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="97ee6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="97ee6-150">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="97ee6-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
