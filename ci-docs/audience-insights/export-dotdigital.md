---
title: 将 Customer Insights 数据导出到 DotDigital
description: 了解如何配置连接和导出到 DotDigital。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759948"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="11063-103">将客户细分列表导出到 DotDigital（预览版）</span><span class="sxs-lookup"><span data-stu-id="11063-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="11063-104">将统一客户配置文件的客户细分导出到 DotDigital 通讯簿，并将其用于市场活动、电子邮件市场营销和使用 DotDigital 生成客户细分。</span><span class="sxs-lookup"><span data-stu-id="11063-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="11063-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="11063-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="11063-106">您具有 [DotDigital 帐户](https://dotdigital.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="11063-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="11063-107">DotDigital 中有现有通讯簿和相应的 ID。</span><span class="sxs-lookup"><span data-stu-id="11063-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="11063-108">当您选择并打开通讯簿时，可以在 URL 中找到 ID。</span><span class="sxs-lookup"><span data-stu-id="11063-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="11063-109">有关详细信息，请参阅 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。</span><span class="sxs-lookup"><span data-stu-id="11063-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="11063-110">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="11063-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="11063-111">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="11063-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="11063-112">已知限制</span><span class="sxs-lookup"><span data-stu-id="11063-112">Known limitations</span></span>

- <span data-ttu-id="11063-113">每次最多可以向 DotDigital 导出 100 万个配置文件。</span><span class="sxs-lookup"><span data-stu-id="11063-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="11063-114">导出到 DotDigital 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="11063-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="11063-115">由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。</span><span class="sxs-lookup"><span data-stu-id="11063-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="11063-116">可以导出到 DotDigital 的配置文件数与 DotDigital 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="11063-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="11063-117">设置与 DotDigital 的连接</span><span class="sxs-lookup"><span data-stu-id="11063-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="11063-118">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="11063-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="11063-119">选择 **添加连接** 并选择 **DotDigital** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="11063-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="11063-120">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="11063-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="11063-121">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="11063-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="11063-122">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="11063-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="11063-123">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="11063-123">Choose who can use this connection.</span></span> <span data-ttu-id="11063-124">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="11063-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="11063-125">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="11063-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="11063-126">输入您的 **DotDigital 用户名和密码**。</span><span class="sxs-lookup"><span data-stu-id="11063-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="11063-127">输入您的 **[DotDigital 通讯簿 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。</span><span class="sxs-lookup"><span data-stu-id="11063-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="11063-128">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="11063-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="11063-129">选择 **连接** 以初始化与 DotDigital 的连接。</span><span class="sxs-lookup"><span data-stu-id="11063-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="11063-130">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="11063-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="11063-131">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="11063-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="11063-132">配置导出</span><span class="sxs-lookup"><span data-stu-id="11063-132">Configure an export</span></span>

<span data-ttu-id="11063-133">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="11063-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="11063-134">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="11063-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="11063-135">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="11063-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="11063-136">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="11063-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="11063-137">在 **导出连接** 字段中，从 DotDigital 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="11063-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="11063-138">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="11063-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="11063-139">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="11063-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="11063-140">对于其他可选字段（例如 **名**、**姓**、**全名**、**性别** 和 **邮政编码**），请重复相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="11063-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="11063-141">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="11063-141">Select the segments you want to export.</span></span> <span data-ttu-id="11063-142">您总共可以将最多 100 万个客户配置文件导出到 DotDigital 中。</span><span class="sxs-lookup"><span data-stu-id="11063-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="11063-143">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="11063-143">Select **Save**.</span></span>

<span data-ttu-id="11063-144">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="11063-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="11063-145">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="11063-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="11063-146">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="11063-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="11063-147">在 DotDigital 中，您现在可以在 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)中找到您的客户细分。</span><span class="sxs-lookup"><span data-stu-id="11063-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="11063-148">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="11063-148">Data privacy and compliance</span></span>

<span data-ttu-id="11063-149">当您启用 Dynamics 365 Customer Insights 将数据传输到 DotDigital 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="11063-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="11063-150">Microsoft 将在您的指导下传输此类数据，但您有责任确保 DotDigital 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="11063-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="11063-151">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="11063-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="11063-152">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="11063-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
