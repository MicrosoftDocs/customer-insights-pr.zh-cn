---
title: 将 Customer Insights 数据导出到 RollWorks
description: 了解如何配置连接和导出到 RollWorks。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124078"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="ce3ae-103">将客户细分导出到 RollWorks（预览版）</span><span class="sxs-lookup"><span data-stu-id="ce3ae-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="ce3ae-104">将统一客户配置文件的客户细分导出到 RollWorks，并将其用于广告。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ce3ae-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="ce3ae-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ce3ae-106">您有一个 [RollWorks 帐户](https://www.rollworks.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ce3ae-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ce3ae-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ce3ae-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="ce3ae-109">Known limitations</span></span>

- <span data-ttu-id="ce3ae-110">对于每次导出，您可以向 RollWorks 导出多达 250'000 个配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="ce3ae-111">您不能将配置文件少于 100 个的客户细分导出到 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="ce3ae-112">导出到 RollWorks 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="ce3ae-113">向 RollWorks 导出多达 250'000 个配置文件可能最多需要 10 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ce3ae-114">您可以导出到 RollWorks 的配置文件数量取决于并受限于您的 RollWorks 联系人。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="ce3ae-115">设置与 RollWorks 的连接</span><span class="sxs-lookup"><span data-stu-id="ce3ae-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="ce3ae-116">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ce3ae-117">选择 **添加连接** 并选择 **RollWorks** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="ce3ae-118">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ce3ae-119">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ce3ae-120">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ce3ae-121">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-121">Choose who can use this connection.</span></span> <span data-ttu-id="ce3ae-122">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ce3ae-123">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ce3ae-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ce3ae-125">选择 **连接** 以初始化与 RollWorks 的连接。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="ce3ae-126">选择 **使用 RollWorks 进行身份验证**，并为 RollWorks 提供您的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="ce3ae-127">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ce3ae-128">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ce3ae-129">配置导出</span><span class="sxs-lookup"><span data-stu-id="ce3ae-129">Configure an export</span></span>

<span data-ttu-id="ce3ae-130">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ce3ae-131">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ce3ae-132">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce3ae-133">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ce3ae-134">在 **导出连接** 字段中，从 RollWorks 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="ce3ae-135">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ce3ae-136">输入您的 **RollWorks 广告商 ID** [RollWorks 播发信息](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ce3ae-137">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ce3ae-138">必须将客户细分导出到 RollWorks。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="ce3ae-139">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-139">Select the segments you want to export.</span></span> <span data-ttu-id="ce3ae-140">选择至少包含 100 个成员的客户细分。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ce3ae-141">不能导出较小的客户细分。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-141">You can't export smaller segments.</span></span> <span data-ttu-id="ce3ae-142">此外，对于每个导出，要导出的客户细分的最大大小为 250'000 个成员。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="ce3ae-143">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-143">Select **Save**.</span></span>

<span data-ttu-id="ce3ae-144">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ce3ae-145">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce3ae-146">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ce3ae-147">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="ce3ae-147">Data privacy and compliance</span></span>

<span data-ttu-id="ce3ae-148">当您启用 Dynamics 365 Customer Insights 以将数据传输到 RollWorks 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ce3ae-149">Microsoft 将在您的指示下传输此类数据，但您有责任确保 RollWorks 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ce3ae-150">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ce3ae-151">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ce3ae-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
