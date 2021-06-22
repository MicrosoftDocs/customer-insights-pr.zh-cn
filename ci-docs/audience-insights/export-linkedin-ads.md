---
title: 将 Customer Insights 数据导出到 LinkedIn Ads
description: 了解如何配置连接和导出到 LinkedIn Ads。
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124461"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="ce039-103">向 LinkedIn Ads 导出客户细分（预览版）</span><span class="sxs-lookup"><span data-stu-id="ce039-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="ce039-104">将统一客户配置文件的客户细分导出到 LinkedIn Ads，以创建匹配的访问群体。</span><span class="sxs-lookup"><span data-stu-id="ce039-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="ce039-105">将匹配的访问群体用于确定目标公司和目标联系人。</span><span class="sxs-lookup"><span data-stu-id="ce039-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ce039-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="ce039-106">Prerequisites</span></span>

-   <span data-ttu-id="ce039-107">您有一个 [LinkedIn Campaign Manager 帐户](https://business.linkedin.com/marketing-solutions/ads)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="ce039-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ce039-108">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="ce039-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ce039-109">已导出客户细分中的客户配置文件包含带有电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="ce039-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ce039-110">已知限制</span><span class="sxs-lookup"><span data-stu-id="ce039-110">Known limitations</span></span>

- <span data-ttu-id="ce039-111">对于每次导出，您可以向 LinkedIn Ads 导出多达 100K 个配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce039-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="ce039-112">导出到 LinkedIn Ads 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="ce039-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="ce039-113">向 LinkedIn Ads 导出多达 100K 个配置文件可能最多需要 10 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="ce039-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="ce039-114">设置与 LinkedIn Ads 的连接</span><span class="sxs-lookup"><span data-stu-id="ce039-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="ce039-115">在受众见解中，转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="ce039-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ce039-116">选择 **添加连接** 并选择 **LinkedIn Ads** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="ce039-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="ce039-117">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="ce039-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ce039-118">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="ce039-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ce039-119">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="ce039-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ce039-120">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="ce039-120">Choose who can use this connection.</span></span> <span data-ttu-id="ce039-121">如果不采取任何行动，默认值是管理员。</span><span class="sxs-lookup"><span data-stu-id="ce039-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="ce039-122">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="ce039-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ce039-123">提供您的 [LinkedIn Campaign Manager 帐户 ID](https://www.linkedin.com/help/lms/answer/a424270)。</span><span class="sxs-lookup"><span data-stu-id="ce039-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="ce039-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="ce039-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ce039-125">选择 **连接** 以初始化与 Campaign Monitor 的连接。</span><span class="sxs-lookup"><span data-stu-id="ce039-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="ce039-126">选择 **使用 LinkedIn 进行身份验证**，并为 LinkedIn Campaign Manager 提供您的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="ce039-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="ce039-127">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="ce039-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ce039-128">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="ce039-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ce039-129">配置导出</span><span class="sxs-lookup"><span data-stu-id="ce039-129">Configure an export</span></span>

<span data-ttu-id="ce039-130">如果您有权访问此类类型的连接，则可以配置导出。</span><span class="sxs-lookup"><span data-stu-id="ce039-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ce039-131">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="ce039-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ce039-132">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="ce039-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce039-133">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="ce039-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ce039-134">在 **导出连接** 字段中，从 LinkedIn Ads 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="ce039-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="ce039-135">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="ce039-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ce039-136">选择是要导出数据以在 LinkedIn 中[确定目标联系人](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)还是[确定目标公司](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。</span><span class="sxs-lookup"><span data-stu-id="ce039-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="ce039-137">在 **数据匹配** 部分，在代表客户电子邮件地址的统一客户配置文件中选择相应字段。</span><span class="sxs-lookup"><span data-stu-id="ce039-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ce039-138">必须将客户细分导出到 LinkedIn Ads。</span><span class="sxs-lookup"><span data-stu-id="ce039-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="ce039-139">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="ce039-139">Select the segments you want to export.</span></span> <span data-ttu-id="ce039-140">将使用您选择导出的客户细分的名称自动创建 LinkedIn Campaign Manager 中匹配的访问群体。</span><span class="sxs-lookup"><span data-stu-id="ce039-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="ce039-141">每个客户细分将产生一个单独的匹配访问群体。</span><span class="sxs-lookup"><span data-stu-id="ce039-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="ce039-142">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="ce039-142">Select **Save**.</span></span>

<span data-ttu-id="ce039-143">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="ce039-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ce039-144">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="ce039-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce039-145">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="ce039-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ce039-146">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="ce039-146">Data privacy and compliance</span></span>

<span data-ttu-id="ce039-147">当您启用 Dynamics 365 Customer Insights 以将数据传输到 LinkedIn Ads 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="ce039-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ce039-148">Microsoft 将在您的指示下传输此类数据，但您有责任确保 LinkedIn Ads 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="ce039-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ce039-149">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="ce039-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ce039-150">Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来停止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ce039-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
