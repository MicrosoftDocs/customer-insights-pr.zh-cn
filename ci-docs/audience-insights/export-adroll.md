---
title: 将 Customer Insights 数据导出到 AdRoll
description: 了解如何配置连接和导出到 AdRoll。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304793"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="b2098-103">将客户细分导出到 AdRoll（预览版）</span><span class="sxs-lookup"><span data-stu-id="b2098-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="b2098-104">将统一客户配置文件的客户细分导出到 AdRoll 中，并使用它们投放广告。</span><span class="sxs-lookup"><span data-stu-id="b2098-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b2098-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="b2098-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b2098-106">您具有 [AdRoll 帐户](https://www.adroll.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="b2098-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b2098-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="b2098-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b2098-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="b2098-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b2098-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="b2098-109">Known limitations</span></span>

- <span data-ttu-id="b2098-110">一次最多可以将 250,000 个配置文件导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="b2098-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="b2098-111">您不能将配置文件少于 100 个的客户细分导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="b2098-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="b2098-112">导出到 AdRoll 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="b2098-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="b2098-113">最多将 250,000 个配置文件导出到 AdRoll 可能最多需要 10 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="b2098-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="b2098-114">可以导出到 AdRoll 的配置文件数依赖于您与 AdRoll 的合同。</span><span class="sxs-lookup"><span data-stu-id="b2098-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="b2098-115">设置与 AdRoll 的连接</span><span class="sxs-lookup"><span data-stu-id="b2098-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="b2098-116">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="b2098-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b2098-117">选择 **添加连接** 并选择 **AdRoll** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="b2098-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="b2098-118">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="b2098-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b2098-119">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="b2098-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b2098-120">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="b2098-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b2098-121">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="b2098-121">Choose who can use this connection.</span></span> <span data-ttu-id="b2098-122">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="b2098-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b2098-123">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="b2098-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b2098-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="b2098-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b2098-125">选择 **连接** 以初始化与 AdRoll 的连接。</span><span class="sxs-lookup"><span data-stu-id="b2098-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="b2098-126">选择 **使用 AdRoll 进行身份验证** 并提供您的 AdRoll 管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="b2098-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="b2098-127">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="b2098-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b2098-128">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="b2098-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b2098-129">配置导出</span><span class="sxs-lookup"><span data-stu-id="b2098-129">Configure an export</span></span>

<span data-ttu-id="b2098-130">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="b2098-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b2098-131">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="b2098-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b2098-132">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="b2098-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b2098-133">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="b2098-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b2098-134">在 **导出连接** 字段中，从 AdRoll 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="b2098-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="b2098-135">如果看不到此部分名称，则没有此类型的连接可用。</span><span class="sxs-lookup"><span data-stu-id="b2098-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="b2098-136">输入您的 **AdRoll 广告厂商 ID**。</span><span class="sxs-lookup"><span data-stu-id="b2098-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="b2098-137">有关详细信息，请参阅 [AdRoll 广告厂商配置文件](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="b2098-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="b2098-138">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="b2098-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b2098-139">需要将客户细分导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="b2098-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="b2098-140">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="b2098-140">Select the segments you want to export.</span></span> <span data-ttu-id="b2098-141">选择至少包含 100 个成员的客户细分。</span><span class="sxs-lookup"><span data-stu-id="b2098-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="b2098-142">不能导出较小的客户细分。</span><span class="sxs-lookup"><span data-stu-id="b2098-142">You can't export smaller segments.</span></span> <span data-ttu-id="b2098-143">此外，对于每个导出，要导出的客户细分的最大大小为 250,000 个成员。</span><span class="sxs-lookup"><span data-stu-id="b2098-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="b2098-144">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="b2098-144">Select **Save**.</span></span>

<span data-ttu-id="b2098-145">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="b2098-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b2098-146">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="b2098-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="b2098-147">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="b2098-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b2098-148">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="b2098-148">Data privacy and compliance</span></span>

<span data-ttu-id="b2098-149">当您启用 Dynamics 365 Customer Insights 将数据传输到 AdRoll 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="b2098-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b2098-150">Microsoft 将在您的指导下传输此类数据，但您有责任确保 AdRoll 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="b2098-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b2098-151">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="b2098-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b2098-152">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b2098-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
