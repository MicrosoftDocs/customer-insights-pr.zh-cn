---
title: 将 Customer Insights 数据导出到 ActiveCampaign
description: 了解如何配置连接和导出到 ActiveCampaign。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314584"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="75f04-103">将客户细分导出到 ActiveCampaign（预览）</span><span class="sxs-lookup"><span data-stu-id="75f04-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="75f04-104">将统一客户配置文件的客户细分导出到 ActiveCampaign，并将其用于市场营销活动。</span><span class="sxs-lookup"><span data-stu-id="75f04-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75f04-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="75f04-105">Prerequisites</span></span>

-   <span data-ttu-id="75f04-106">您具有 [ActiveCampaign 帐户](https://www.activecampaign.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="75f04-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="75f04-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="75f04-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="75f04-108">已导出客户细分中的统一客户配置文件包含带有电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="75f04-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="75f04-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="75f04-109">Known limitations</span></span>

- <span data-ttu-id="75f04-110">每个导出最多可以将 100 万个配置文件导出到 ActiveCampaign，且可能需要最多 90 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="75f04-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="75f04-111">导出到 ActiveCampaign 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="75f04-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="75f04-112">可以导出到 ActiveCampaign 的配置文件数取决于您与 ActiveCampaign 的合同。</span><span class="sxs-lookup"><span data-stu-id="75f04-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="75f04-113">设置与 ActiveCampaign 的连接</span><span class="sxs-lookup"><span data-stu-id="75f04-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="75f04-114">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="75f04-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="75f04-115">选择 **添加连接** 并选择 **ActiveCampaign** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="75f04-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="75f04-116">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="75f04-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="75f04-117">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="75f04-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="75f04-118">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="75f04-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="75f04-119">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="75f04-119">Choose who can use this connection.</span></span> <span data-ttu-id="75f04-120">默认情况下，仅限管理员。</span><span class="sxs-lookup"><span data-stu-id="75f04-120">By default, it's only administrators.</span></span> <span data-ttu-id="75f04-121">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="75f04-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="75f04-122">输入您的 [ActiveCampaign API 密钥和 REST 终结点主机名](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key)。</span><span class="sxs-lookup"><span data-stu-id="75f04-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="75f04-123">REST 终结点主机名是纯主机名，不带 https://。</span><span class="sxs-lookup"><span data-stu-id="75f04-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="75f04-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="75f04-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="75f04-125">选择 **连接** 以初始化与 ActiveCampaign 的连接。</span><span class="sxs-lookup"><span data-stu-id="75f04-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="75f04-126">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="75f04-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="75f04-127">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="75f04-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="75f04-128">配置导出</span><span class="sxs-lookup"><span data-stu-id="75f04-128">Configure an export</span></span>

<span data-ttu-id="75f04-129">如果您有权访问此类类型的连接，则可以配置导出。</span><span class="sxs-lookup"><span data-stu-id="75f04-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="75f04-130">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="75f04-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="75f04-131">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="75f04-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="75f04-132">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="75f04-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="75f04-133">在 **用于导出的连接** 字段中，从 ActiveCampaign 部分中选择连接。</span><span class="sxs-lookup"><span data-stu-id="75f04-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="75f04-134">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="75f04-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="75f04-135">输入您的 [**ActiveCampaign 列表 ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)。</span><span class="sxs-lookup"><span data-stu-id="75f04-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="75f04-136">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="75f04-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="75f04-137">在将客户细分导出到 ActiveCampaign 时需要它。</span><span class="sxs-lookup"><span data-stu-id="75f04-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="75f04-138">您也可以选择导出名、姓和电话号码来创建更个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="75f04-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="75f04-139">选择添加属性以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="75f04-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="75f04-140">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="75f04-140">Select **Save**.</span></span>

<span data-ttu-id="75f04-141">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="75f04-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="75f04-142">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="75f04-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="75f04-143">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="75f04-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="75f04-144">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="75f04-144">Data privacy and compliance</span></span>

<span data-ttu-id="75f04-145">当启用 Dynamics 365 Customer Insights 将数据传输到 ActiveCampaign 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="75f04-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="75f04-146">Microsoft 将根据您的指示传输此类数据，但您负责确保 ActiveCampaign 满足您可能承担的任何隐私或安全责任。</span><span class="sxs-lookup"><span data-stu-id="75f04-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="75f04-147">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="75f04-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="75f04-148">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="75f04-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
