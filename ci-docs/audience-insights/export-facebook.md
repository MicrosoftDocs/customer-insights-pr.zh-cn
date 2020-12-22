---
title: 将 Customer Insights 数据导出到 Facebook Ads Manager
description: 了解如何配置与 Facebook Ads Manager 的连接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643672"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="8ae63-103">Facebook Ads Manager 连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="8ae63-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="8ae63-104">将统一客户配置文件的细分导出到 Facebook Ads Manager，以在 Facebook 和 Instagram 上创建市场活动。</span><span class="sxs-lookup"><span data-stu-id="8ae63-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ae63-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="8ae63-105">Prerequisites</span></span>

- <span data-ttu-id="8ae63-106">您需要有一个包含 [**Facebook 业务帐户**](https://business.facebook.com/)的 [**Facebook 广告帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。</span><span class="sxs-lookup"><span data-stu-id="8ae63-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="8ae63-107">您需要是 [**Facebook 广告帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)的管理员。</span><span class="sxs-lookup"><span data-stu-id="8ae63-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="8ae63-108">连接到 Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="8ae63-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="8ae63-109">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="8ae63-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8ae63-110">在 **Facebook Ads Manager** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="8ae63-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="8ae63-111">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="8ae63-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8ae63-112">选择 **继续使用 Facebook** 登录到您的 Facebook 广告帐户。</span><span class="sxs-lookup"><span data-stu-id="8ae63-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="8ae63-113">在使用 Facebook 进行身份验证后，允许 **ads_management** 权限。</span><span class="sxs-lookup"><span data-stu-id="8ae63-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="8ae63-114">选择您要使用的 **Facebook 广告帐户**。</span><span class="sxs-lookup"><span data-stu-id="8ae63-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="8ae63-115">从下拉列表中选择 **现有自定义访问群体** 或创建 **新自定义访问群体**。</span><span class="sxs-lookup"><span data-stu-id="8ae63-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="8ae63-116">有关详细信息，请参阅 [**Facebook Ads Manager 中的访问群体**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。</span><span class="sxs-lookup"><span data-stu-id="8ae63-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="8ae63-117">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="8ae63-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8ae63-118">选择 **下一步** 配置导出。</span><span class="sxs-lookup"><span data-stu-id="8ae63-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8ae63-119">配置连接器</span><span class="sxs-lookup"><span data-stu-id="8ae63-119">Configure the connector</span></span>

1. <span data-ttu-id="8ae63-120">在 **选择您的密钥标识符字段** 中，选择 **电子邮件**、**名称和地址** 或 **电话** 以发送到 Facebook Ads Manager。</span><span class="sxs-lookup"><span data-stu-id="8ae63-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="8ae63-121">映射所选密钥标识符的统一客户实体中的相应属性。</span><span class="sxs-lookup"><span data-stu-id="8ae63-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="8ae63-122">[提示] 如果选择 **电子邮件** 作为密钥标识符，匹配的最佳机会将出现。</span><span class="sxs-lookup"><span data-stu-id="8ae63-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="8ae63-123">添加其他标识符可以改进匹配。</span><span class="sxs-lookup"><span data-stu-id="8ae63-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="8ae63-124">选择 **添加属性** 来映射其他属性以发送到 Facebook Ads Manager。</span><span class="sxs-lookup"><span data-stu-id="8ae63-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="8ae63-125">Facebook Ads Manager 中的属性映射到以下用户友好名称：**FN** = **名**、**LN** = **姓**、**FI** = **姓氏首字母大写**、**PHONE** = **电话**、**GEN** = **性别**、**DOB** = **出生日期**、**ST** = **省/自治区/直辖市**、**CT** = **市/县**、**ZIP** = **邮政编码**、**COUNTRY** = **国家/地区**</span><span class="sxs-lookup"><span data-stu-id="8ae63-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="8ae63-126">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="8ae63-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8ae63-127">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="8ae63-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8ae63-128">导出数据</span><span class="sxs-lookup"><span data-stu-id="8ae63-128">Export the data</span></span>

<span data-ttu-id="8ae63-129">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="8ae63-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8ae63-130">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="8ae63-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ae63-131">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="8ae63-131">Data privacy and compliance</span></span>

<span data-ttu-id="8ae63-132">当您启用 Dynamics 365 Customer Insights 将数据传输到 Facebook Ads Manager 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="8ae63-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ae63-133">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Facebook Ads 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="8ae63-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ae63-134">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="8ae63-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8ae63-135">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="8ae63-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
