---
title: LiveRamp 连接器
description: 了解如何配置连接和导出到 LiveRamp。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760316"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="5688a-103">将细分市场导出到 LiveRamp&reg;（预览版）</span><span class="sxs-lookup"><span data-stu-id="5688a-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="5688a-104">在 LiveRamp 中激活您的数据，以在数字、社交和 TV 中与 500 多个平台进行连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="5688a-105">在 LiveRamp 中处理数据以便为广告市场活动设置目标，隐藏广告市场活动和个性化广告市场活动。</span><span class="sxs-lookup"><span data-stu-id="5688a-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="5688a-106">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="5688a-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="5688a-107">需要 LiveRamp 订阅才能使用此连接器。</span><span class="sxs-lookup"><span data-stu-id="5688a-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="5688a-108">若要获取订阅，请直接[联系 LiveRamp](https://liveramp.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="5688a-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="5688a-109">[详细了解 LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/)。</span><span class="sxs-lookup"><span data-stu-id="5688a-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="5688a-110">设置与 LiveRamp 的连接</span><span class="sxs-lookup"><span data-stu-id="5688a-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="5688a-111">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="5688a-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5688a-112">选择 **添加连接** 并选择 **LiveRamp** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="5688a-113">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="5688a-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5688a-114">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5688a-115">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="5688a-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5688a-116">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="5688a-116">Choose who can use this connection.</span></span> <span data-ttu-id="5688a-117">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="5688a-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5688a-118">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="5688a-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5688a-119">为 LiveRamp Secure FTP (SFTP) 帐户提供 **用户名** 和 **密码**。</span><span class="sxs-lookup"><span data-stu-id="5688a-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="5688a-120">这些凭据可能与您的 LiveRamp Onboarding 凭据不同。</span><span class="sxs-lookup"><span data-stu-id="5688a-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="5688a-121">选择 **验证** 以测试与 LiveRamp 之间的连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="5688a-122">验证成功之后，选中 **我同意** 复选框同意 **数据隐私和合规性**。</span><span class="sxs-lookup"><span data-stu-id="5688a-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="5688a-123">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5688a-124">配置导出</span><span class="sxs-lookup"><span data-stu-id="5688a-124">Configure an export</span></span>

<span data-ttu-id="5688a-125">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="5688a-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5688a-126">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="5688a-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5688a-127">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="5688a-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5688a-128">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="5688a-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5688a-129">在 **导出连接** 字段中，从 LiveRamp 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="5688a-130">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="5688a-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5688a-131">在 **选择密钥标识符** 字段中，选择要发送到 LiveRamp 以进行身份识别的 **电子邮件**、**姓名和地址** 或 **电话**。</span><span class="sxs-lookup"><span data-stu-id="5688a-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5688a-132">![具有属性映射的 LiveRamp 连接器](media/export-liveramp-segments.png "具有属性映射的 LiveRamp 连接器")</span><span class="sxs-lookup"><span data-stu-id="5688a-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="5688a-133">映射所选密钥标识符的统一客户实体中的相应属性。</span><span class="sxs-lookup"><span data-stu-id="5688a-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="5688a-134">选择 **添加属性** 以映射要发送到 LiveRamp 的更多属性。</span><span class="sxs-lookup"><span data-stu-id="5688a-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="5688a-135">向 LiveRamp 发送更多密钥标识符属性可提高匹配率。</span><span class="sxs-lookup"><span data-stu-id="5688a-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="5688a-136">选择要导出到 LiveRamp 的细分。</span><span class="sxs-lookup"><span data-stu-id="5688a-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="5688a-137">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="5688a-137">Select **Save**.</span></span>

<span data-ttu-id="5688a-138">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="5688a-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5688a-139">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="5688a-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5688a-140">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="5688a-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5688a-141">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="5688a-141">Data privacy and compliance</span></span>

<span data-ttu-id="5688a-142">当您启用 Dynamics 365 Customer Insights 将数据传输到 Liveramp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="5688a-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5688a-143">Microsoft 将在您的指导下传输此类数据，但您有责任确保 Liveramp 满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="5688a-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5688a-144">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="5688a-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5688a-145">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="5688a-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
