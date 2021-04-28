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
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895948"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="27084-103">将客户细分列表导出到 AdRoll（预览版）</span><span class="sxs-lookup"><span data-stu-id="27084-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="27084-104">将统一客户配置文件的客户细分导出到 AdRoll 中，并使用它们投放广告。</span><span class="sxs-lookup"><span data-stu-id="27084-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="27084-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="27084-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="27084-106">您具有 [AdRoll 帐户](https://www.adroll.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="27084-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="27084-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="27084-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="27084-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="27084-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="27084-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="27084-109">Known limitations</span></span>

- <span data-ttu-id="27084-110">对于每个导出，您最多可以将 250'000 个配置文件导出到 AdRoll 中。</span><span class="sxs-lookup"><span data-stu-id="27084-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="27084-111">您不能将配置文件少于 100 个的客户细分导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="27084-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="27084-112">导出到 AdRoll 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="27084-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="27084-113">最多将 250'000 个配置文件导出到 AdRoll 可能需要 10 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="27084-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="27084-114">可以导出到 AdRoll 的配置文件数与 AdRoll 的合同相关并受其限制。</span><span class="sxs-lookup"><span data-stu-id="27084-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="27084-115">设置与 AdRoll 的连接</span><span class="sxs-lookup"><span data-stu-id="27084-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="27084-116">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="27084-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="27084-117">选择 **添加连接** 并选择 **AdRoll** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="27084-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="27084-118">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="27084-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="27084-119">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="27084-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="27084-120">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="27084-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="27084-121">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="27084-121">Choose who can use this connection.</span></span> <span data-ttu-id="27084-122">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="27084-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="27084-123">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="27084-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="27084-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="27084-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="27084-125">选择 **连接** 以初始化与 AdRoll 的连接。</span><span class="sxs-lookup"><span data-stu-id="27084-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="27084-126">选择 **使用 AdRoll 进行身份验证** 并提供您的 AdRoll 管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="27084-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="27084-127">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="27084-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="27084-128">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="27084-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="27084-129">配置导出</span><span class="sxs-lookup"><span data-stu-id="27084-129">Configure an export</span></span>

<span data-ttu-id="27084-130">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="27084-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="27084-131">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="27084-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="27084-132">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="27084-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="27084-133">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="27084-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="27084-134">在 **导出连接** 字段中，从 AdRoll 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="27084-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="27084-135">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="27084-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="27084-136">输入您的 **AdRoll 广告商 ID**。有关更多信息，请参阅 [AdRoll 广告商配置文件](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="27084-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="27084-137">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="27084-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="27084-138">需要将客户细分导出到 AdRoll。</span><span class="sxs-lookup"><span data-stu-id="27084-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="27084-139">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="27084-139">Select the segments you want to export.</span></span> <span data-ttu-id="27084-140">选择至少包含 100 个成员的客户细分。</span><span class="sxs-lookup"><span data-stu-id="27084-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="27084-141">不能导出较小的客户细分。</span><span class="sxs-lookup"><span data-stu-id="27084-141">You can't export smaller segments.</span></span> <span data-ttu-id="27084-142">此外，对于每个导出，要导出的客户细分的最大大小为 250'000 个成员。</span><span class="sxs-lookup"><span data-stu-id="27084-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="27084-143">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="27084-143">Select **Save**.</span></span>

<span data-ttu-id="27084-144">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="27084-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="27084-145">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="27084-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="27084-146">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="27084-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="27084-147">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="27084-147">Data privacy and compliance</span></span>

<span data-ttu-id="27084-148">当您启用 Dynamics 365 Customer Insights 将数据传输到 AdRoll 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="27084-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="27084-149">Microsoft 将在您的指导下传输此类数据，但您有责任确保 AdRoll 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="27084-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="27084-150">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="27084-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="27084-151">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="27084-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>