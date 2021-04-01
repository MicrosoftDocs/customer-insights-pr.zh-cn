---
title: LiveRamp 连接器
description: 了解如何将数据导出到 LiveRamp。
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597546"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="78ed1-103">LiveRamp&reg; 连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="78ed1-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="78ed1-104">在 LiveRamp 中激活数据，以便跨数字、社交和 TV 生态系统与超过 500 个平台连接。</span><span class="sxs-lookup"><span data-stu-id="78ed1-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="78ed1-105">在 LiveRamp 中处理数据以便为广告市场活动设置目标，隐藏广告市场活动和个性化广告市场活动。</span><span class="sxs-lookup"><span data-stu-id="78ed1-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78ed1-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="78ed1-106">Prerequisites</span></span>

- <span data-ttu-id="78ed1-107">需要 LiveRamp 订阅才能使用此连接器。</span><span class="sxs-lookup"><span data-stu-id="78ed1-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="78ed1-108">若要获取订阅，请直接[联系 LiveRamp](https://liveramp.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="78ed1-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="78ed1-109">[详细了解 LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/)。</span><span class="sxs-lookup"><span data-stu-id="78ed1-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="78ed1-110">连接到 LiveRamp</span><span class="sxs-lookup"><span data-stu-id="78ed1-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="78ed1-111">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="78ed1-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="78ed1-112">在 **LiveRamp** 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="78ed1-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="78ed1-113">在 **显示名称** 字段中为目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="78ed1-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="78ed1-114">为 LiveRamp Secure FTP (SFTP) 帐户提供 **用户名** 和 **密码**。</span><span class="sxs-lookup"><span data-stu-id="78ed1-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="78ed1-115">这些凭据可能与您的 LiveRamp Onboarding 凭据不同。</span><span class="sxs-lookup"><span data-stu-id="78ed1-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="78ed1-116">选择 **验证** 以测试与 LiveRamp 之间的连接。</span><span class="sxs-lookup"><span data-stu-id="78ed1-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="78ed1-117">验证成功之后，选中 **我同意** 复选框同意 **数据隐私和合规性**。</span><span class="sxs-lookup"><span data-stu-id="78ed1-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="78ed1-118">选择 **下一步** 设置 LiveRamp 连接器。</span><span class="sxs-lookup"><span data-stu-id="78ed1-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="78ed1-119">配置连接器</span><span class="sxs-lookup"><span data-stu-id="78ed1-119">Configure the connector</span></span>

1. <span data-ttu-id="78ed1-120">在 **选择密钥标识符** 字段中，选择要发送到 LiveRamp 以进行身份识别的 **电子邮件**、**姓名和地址** 或 **电话**。</span><span class="sxs-lookup"><span data-stu-id="78ed1-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="78ed1-121">映射所选密钥标识符的统一客户实体中的相应属性。</span><span class="sxs-lookup"><span data-stu-id="78ed1-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="78ed1-122">选择 **添加属性** 映射要发送到 LiveRamp 的更多属性。</span><span class="sxs-lookup"><span data-stu-id="78ed1-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="78ed1-123">向 LiveRamp 发送更多密钥标识符属性可提高匹配率。</span><span class="sxs-lookup"><span data-stu-id="78ed1-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="78ed1-124">选择要导出到 LiveRamp 的细分。</span><span class="sxs-lookup"><span data-stu-id="78ed1-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="78ed1-125">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="78ed1-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="78ed1-126">![具有属性映射的 LiveRamp 连接器](media/export-liveramp-segments.png "具有属性映射的 LiveRamp 连接器")</span><span class="sxs-lookup"><span data-stu-id="78ed1-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="78ed1-127">导出数据</span><span class="sxs-lookup"><span data-stu-id="78ed1-127">Export the data</span></span>

<span data-ttu-id="78ed1-128">如果满足所有导出必要条件，很快将开始导出。</span><span class="sxs-lookup"><span data-stu-id="78ed1-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="78ed1-129">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="78ed1-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="78ed1-130">成功完成导出之后，可以登录 LiveRamp Onboarding 激活和分发数据。</span><span class="sxs-lookup"><span data-stu-id="78ed1-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="78ed1-131">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="78ed1-131">Data privacy and compliance</span></span>

<span data-ttu-id="78ed1-132">当您启用 Dynamics 365 Customer Insights 将数据传输到 Liveramp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="78ed1-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="78ed1-133">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Liveramp 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="78ed1-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="78ed1-134">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="78ed1-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="78ed1-135">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="78ed1-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]