---
title: 将 Customer Insights 数据导出到 Facebook Ads Manager
description: 了解如何配置连接和导出到 Facebook Ads Manager。
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976031"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="d69ea-103">向 Facebook Ads Manager 导出客户细分列表（预览版）</span><span class="sxs-lookup"><span data-stu-id="d69ea-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="d69ea-104">将统一客户配置文件的细分导出到 Facebook Ads Manager，以在 Facebook 和 Instagram 上创建市场活动。</span><span class="sxs-lookup"><span data-stu-id="d69ea-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d69ea-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="d69ea-105">Prerequisites for connection</span></span>

- <span data-ttu-id="d69ea-106">您需要具有一个包含 [**Facebook 业务帐户**](https://business.facebook.com/)的 [**Facebook 广告帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。</span><span class="sxs-lookup"><span data-stu-id="d69ea-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="d69ea-107">您需要是 [**Facebook 广告帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)的管理员。</span><span class="sxs-lookup"><span data-stu-id="d69ea-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d69ea-108">已知限制</span><span class="sxs-lookup"><span data-stu-id="d69ea-108">Known limitations</span></span>

- <span data-ttu-id="d69ea-109">每次向 Facebook Ads Manager 导出的客户配置文件最多为 1000 万个。</span><span class="sxs-lookup"><span data-stu-id="d69ea-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="d69ea-110">导出到 Facebook Ads Manager 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="d69ea-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="d69ea-111">在 Facebook 中仅创建或更新 *客户列表* 类型的自定义受众。</span><span class="sxs-lookup"><span data-stu-id="d69ea-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="d69ea-112">导出总共包含 1000 万个配置文件的客户细分可能最多需要 90 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="d69ea-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="d69ea-113">设置与 Facebook Ads Manager 的连接</span><span class="sxs-lookup"><span data-stu-id="d69ea-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="d69ea-114">在用户创建导出之前，管理员必须配置与服务的连接，并允许参与者使用该连接。</span><span class="sxs-lookup"><span data-stu-id="d69ea-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="d69ea-115">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d69ea-116">选择 **添加连接** 并选择 **Facebook Ads Manager** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="d69ea-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="d69ea-117">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="d69ea-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d69ea-118">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="d69ea-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d69ea-119">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="d69ea-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d69ea-120">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="d69ea-120">Choose who can use this connection.</span></span> <span data-ttu-id="d69ea-121">如果不采取任何行动，默认值将是 **管理员**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="d69ea-122">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="d69ea-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d69ea-123">使用 Facebook Ads 进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="d69ea-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="d69ea-124">选择 **继续使用 Facebook** 登录到您的 Facebook 广告帐户。</span><span class="sxs-lookup"><span data-stu-id="d69ea-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="d69ea-125">在使用 Facebook 进行身份验证后，允许 **ads_management** 权限。</span><span class="sxs-lookup"><span data-stu-id="d69ea-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="d69ea-126">选择您要使用的 **Facebook 广告帐户**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="d69ea-127">从下拉列表中选择 **现有自定义访问群体** 或创建 **新自定义访问群体**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="d69ea-128">有关详细信息，请参阅 [**Facebook Ads Manager 中的访问群体**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。</span><span class="sxs-lookup"><span data-stu-id="d69ea-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="d69ea-129">您在 Facebook 上使用此导出只能创建或更新 *客户列表* 类型的自定义受众。</span><span class="sxs-lookup"><span data-stu-id="d69ea-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="d69ea-130">在某些情况下，您在下拉列表中会看到不同类型的自定义受众。</span><span class="sxs-lookup"><span data-stu-id="d69ea-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="d69ea-131">选择不同于 *客户列表* 的类型将导致导出失败。</span><span class="sxs-lookup"><span data-stu-id="d69ea-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="d69ea-132">查看 **数据隐私和合规性**，并选择 **我同意**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="d69ea-133">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="d69ea-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d69ea-134">配置导出</span><span class="sxs-lookup"><span data-stu-id="d69ea-134">Configure an export</span></span>

<span data-ttu-id="d69ea-135">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="d69ea-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d69ea-136">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="d69ea-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d69ea-137">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d69ea-138">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="d69ea-139">在 **导出连接** 中，从 **Facebook Ads Manager** 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="d69ea-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="d69ea-140">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="d69ea-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d69ea-141">在 **选择您的密钥标识符字段** 中，选择 **电子邮件**、**名称和地址** 或 **电话** 以发送到 Facebook Ads Manager。</span><span class="sxs-lookup"><span data-stu-id="d69ea-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="d69ea-142">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="d69ea-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d69ea-143">映射所选密钥标识符的统一客户实体中的相应属性。</span><span class="sxs-lookup"><span data-stu-id="d69ea-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="d69ea-144">[提示] 如果选择 **电子邮件** 作为密钥标识符，匹配的最佳机会将出现。</span><span class="sxs-lookup"><span data-stu-id="d69ea-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="d69ea-145">添加其他标识符可以改进匹配。</span><span class="sxs-lookup"><span data-stu-id="d69ea-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="d69ea-146">选择 **添加属性** 以映射要发送到 Facebook Ads Manager 的更多属性。</span><span class="sxs-lookup"><span data-stu-id="d69ea-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="d69ea-147">Facebook Ads Manager 中的属性映射到以下用户友好名称：**FN** = **名**、**LN** = **姓**、**FI** = **姓氏首字母大写**、**PHONE** = **电话**、**GEN** = **性别**、**DOB** = **出生日期**、**ST** = **省/自治区/直辖市**、**CT** = **市/县**、**ZIP** = **邮政编码**、**COUNTRY** = **国家/地区**</span><span class="sxs-lookup"><span data-stu-id="d69ea-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="d69ea-148">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="d69ea-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d69ea-149">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="d69ea-149">Select **Save**.</span></span>

<span data-ttu-id="d69ea-150">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="d69ea-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d69ea-151">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="d69ea-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d69ea-152">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="d69ea-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d69ea-153">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="d69ea-153">Data privacy and compliance</span></span>

<span data-ttu-id="d69ea-154">当您启用 Dynamics 365 Customer Insights 将数据传输到 Facebook Ads Manager 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="d69ea-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d69ea-155">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Facebook Ads 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="d69ea-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d69ea-156">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="d69ea-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d69ea-157">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d69ea-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
