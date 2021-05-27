---
title: 将 Customer Insights 数据导出到 Marketo
description: 了解如何配置连接和导出到 Marketo。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059305"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="e9bdd-103">将细分市场导出到 Marketo（预览版）</span><span class="sxs-lookup"><span data-stu-id="e9bdd-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="e9bdd-104">导出统一客户配置文件的客户细分以生成市场活动，提供电子邮件市场营销，并通过 Marketo 使用特定客户组。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e9bdd-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="e9bdd-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e9bdd-106">您具有 [Marketo 帐户](https://login.marketo.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e9bdd-107">Marketo 中有现有列表和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e9bdd-108">有关详细信息，请参阅 [Marketo 列表](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e9bdd-109">您已[配置客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e9bdd-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e9bdd-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="e9bdd-111">Known limitations</span></span>

- <span data-ttu-id="e9bdd-112">每次最多可以向 Marketo 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e9bdd-113">导出到 Marketo 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e9bdd-114">导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e9bdd-115">可以导出到 Marketo 的配置文件数与 Marketo 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="e9bdd-116">设置与 Marketo 的连接</span><span class="sxs-lookup"><span data-stu-id="e9bdd-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="e9bdd-117">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e9bdd-118">选择 **添加连接** 并选择 **Marketo** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="e9bdd-119">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e9bdd-120">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e9bdd-121">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e9bdd-122">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-122">Choose who can use this connection.</span></span> <span data-ttu-id="e9bdd-123">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e9bdd-124">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e9bdd-125">输入您的 **[Marketo 客户端 ID、客户端密码和 REST 终结点主机名](https://developers.marketo.com/rest-api/authentication/)**。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="e9bdd-126">REST 终结点主机名是纯主机名，不带 `https://`。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="e9bdd-127">示例：`xyz-abc-123.mktorest.com`。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="e9bdd-128">选择 **我同意** 确认 **数据隐私与合规性**，然后选择 **连接** 以初始化与 Marketo 的连接。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e9bdd-129">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e9bdd-130">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e9bdd-131">配置导出</span><span class="sxs-lookup"><span data-stu-id="e9bdd-131">Configure an export</span></span>

<span data-ttu-id="e9bdd-132">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e9bdd-133">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e9bdd-134">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e9bdd-135">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e9bdd-136">在 **导出连接** 字段中，从 Marketo 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="e9bdd-137">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e9bdd-138">输入您的 **[Marketo 列表 ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="e9bdd-139">列表 ID 是一个纯数值。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="e9bdd-140">例如，如果 Marketo 列表 ID 为 ST12345A7，请删除数字之前和之后的字符，并输入 `12345`。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="e9bdd-141">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e9bdd-142">（可选）您可以导出 **名**、**姓**、**市/县**、**省/市/自治区** 和 **国家/地区** 以创建更个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="e9bdd-143">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e9bdd-144">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-144">Select the segments you want to export.</span></span> <span data-ttu-id="e9bdd-145">您总共可以将最多 100 万个客户配置文件导出到 Marketo 中。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="e9bdd-146">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-146">Select **Save**.</span></span>

<span data-ttu-id="e9bdd-147">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e9bdd-148">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e9bdd-149">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e9bdd-150">在 Marketo 中，您现在可以在 [Marketo 列表](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)下找到您的客户细分。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e9bdd-151">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="e9bdd-151">Data privacy and compliance</span></span>

<span data-ttu-id="e9bdd-152">当您启用 Dynamics 365 Customer Insights 将数据传输到 Marketo 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e9bdd-153">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Marketo 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e9bdd-154">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e9bdd-155">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="e9bdd-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
