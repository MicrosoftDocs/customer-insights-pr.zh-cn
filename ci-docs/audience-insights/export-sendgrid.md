---
title: 将 Customer Insights 数据导出到 SendGrid
description: 了解如何配置连接和导出到 SendGrid。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759754"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="7b7aa-103">将客户细分导出到 SendGrid（预览版）</span><span class="sxs-lookup"><span data-stu-id="7b7aa-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="7b7aa-104">将统一客户配置文件的客户细分导出到 SendGrid 联系人列表，并在 SendGrid 中将其用于市场活动和电子邮件市场营销。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7b7aa-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="7b7aa-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7b7aa-106">您具有 [SendGrid 帐户](https://sendgrid.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7b7aa-107">SendGrid 中已有联系人列表和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="7b7aa-108">有关详细信息，请参阅 [SendGrid - 管理联系人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="7b7aa-109">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7b7aa-110">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7b7aa-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="7b7aa-111">Known limitations</span></span>

- <span data-ttu-id="7b7aa-112">总共最多可以将 100'000 个配置文件导出到 SendGrid。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="7b7aa-113">导出到 SendGrid 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="7b7aa-114">将多达 100'000 个配置文件导出到 SendGrid 可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="7b7aa-115">可以导出到 SendGrid 的配置文件数与 SendGrid 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="7b7aa-116">设置与 SendGrid 的连接</span><span class="sxs-lookup"><span data-stu-id="7b7aa-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="7b7aa-117">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7b7aa-118">选择 **添加连接** 并选择 **SendGrid** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="7b7aa-119">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7b7aa-120">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7b7aa-121">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7b7aa-122">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-122">Choose who can use this connection.</span></span> <span data-ttu-id="7b7aa-123">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7b7aa-124">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7b7aa-125">输入您的 **SendGrid API 密钥** [SendGrid API 密钥](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="7b7aa-126">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7b7aa-127">选择 **连接** 以初始化与 SendGrid 的连接。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="7b7aa-128">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7b7aa-129">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7b7aa-130">配置导出</span><span class="sxs-lookup"><span data-stu-id="7b7aa-130">Configure an export</span></span>

<span data-ttu-id="7b7aa-131">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7b7aa-132">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7b7aa-133">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7b7aa-134">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7b7aa-135">在 **导出连接** 字段中，从 SendGrid 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="7b7aa-136">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7b7aa-137">输入您的 **[SendGrid 列表 ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="7b7aa-138">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7b7aa-139">对于其他可选字段（例如 **名**、**姓**、**国家/地区**、**省/自治区/直辖市**、**市/县** 和 **邮政编码**），请重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="7b7aa-140">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-140">Select the segments you want to export.</span></span> <span data-ttu-id="7b7aa-141">我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 SendGrid。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="7b7aa-142">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-142">Select **Save**.</span></span>

<span data-ttu-id="7b7aa-143">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7b7aa-144">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7b7aa-145">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7b7aa-146">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="7b7aa-146">Data privacy and compliance</span></span>

<span data-ttu-id="7b7aa-147">当您启用 Dynamics 365 Customer Insights 将数据传输到 SendGrid 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7b7aa-148">Microsoft 将在您的指导下传输此类数据，但您有责任确保 SendGrid 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7b7aa-149">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7b7aa-150">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="7b7aa-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]