---
title: 将 Customer Insights 数据导出到 Microsoft Advertising
description: 了解如何配置连接和导出到 Microsoft Advertising。
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124459"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="751b2-103">将客户细分导出到 Microsoft Advertising（预览版）</span><span class="sxs-lookup"><span data-stu-id="751b2-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="751b2-104">将 Customer Insights 客户细分导出到 Microsoft Advertising，以创建客户匹配访问群体。</span><span class="sxs-lookup"><span data-stu-id="751b2-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="751b2-105">将这些访问群体用于您的广告市场活动。</span><span class="sxs-lookup"><span data-stu-id="751b2-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="751b2-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="751b2-106">Prerequisites</span></span>

-   <span data-ttu-id="751b2-107">[Microsoft Advertising 帐户](https://ads.microsoft.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="751b2-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="751b2-108">您已接受客户匹配使用条款。</span><span class="sxs-lookup"><span data-stu-id="751b2-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="751b2-109">访问群体见解中的[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="751b2-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="751b2-110">已导出客户细分中的统一客户配置文件包含带有电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="751b2-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="751b2-111">已知限制</span><span class="sxs-lookup"><span data-stu-id="751b2-111">Known limitations</span></span>

- <span data-ttu-id="751b2-112">对于每次导出，您可以向 Microsoft Advertising 导出多达 500 K 个配置文件。</span><span class="sxs-lookup"><span data-stu-id="751b2-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="751b2-113">导出到 Microsoft Advertising 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="751b2-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="751b2-114">向 Microsoft Advertising 导出多达 500 K 个配置文件可能最多需要 10 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="751b2-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="751b2-115">设置与 Microsoft Advertising 的连接（预览版）</span><span class="sxs-lookup"><span data-stu-id="751b2-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="751b2-116">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="751b2-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="751b2-117">选择 **添加连接** 并选择 **Microsoft Advertising** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="751b2-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="751b2-118">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="751b2-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="751b2-119">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="751b2-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="751b2-120">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="751b2-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="751b2-121">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="751b2-121">Choose who can use this connection.</span></span> <span data-ttu-id="751b2-122">默认为管理员。</span><span class="sxs-lookup"><span data-stu-id="751b2-122">The default is administrators.</span></span> <span data-ttu-id="751b2-123">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="751b2-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="751b2-124">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="751b2-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="751b2-125">选择 **连接** 以初始化与 Microsoft Advertising 的连接。</span><span class="sxs-lookup"><span data-stu-id="751b2-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="751b2-126">选择 **使用 Microsoft Advertising 进行身份验证**，并为 Microsoft Advertising 提供您的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="751b2-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="751b2-127">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="751b2-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="751b2-128">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="751b2-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="751b2-129">配置导出</span><span class="sxs-lookup"><span data-stu-id="751b2-129">Configure an export</span></span>

<span data-ttu-id="751b2-130">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="751b2-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="751b2-131">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="751b2-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="751b2-132">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="751b2-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="751b2-133">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="751b2-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="751b2-134">在 **导出连接** 字段中，从 Microsoft Advertising 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="751b2-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="751b2-135">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="751b2-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="751b2-136">选择要导出的客户细分。</span><span class="sxs-lookup"><span data-stu-id="751b2-136">Select the segments to export.</span></span> <span data-ttu-id="751b2-137">会使用为导出选择的客户细分的名称自动创建 Microsoft Advertising 中的客户匹配访问群体。</span><span class="sxs-lookup"><span data-stu-id="751b2-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="751b2-138">每个客户细分将产生一个单独的客户匹配访问群体。</span><span class="sxs-lookup"><span data-stu-id="751b2-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="751b2-139">输入您的 **Microsoft Advertising 客户 ID 和帐户 ID**。</span><span class="sxs-lookup"><span data-stu-id="751b2-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="751b2-140">当您登录 Microsoft Advertising 时，您可以在 URL 的参数中查找客户 ID (`cid`) 和帐户 ID (`aid`)。</span><span class="sxs-lookup"><span data-stu-id="751b2-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="751b2-141">在 **数据匹配** 部分内的 **电子邮件** 字段中，在具有客户电子邮件地址的统一客户配置文件中选择相应字段。</span><span class="sxs-lookup"><span data-stu-id="751b2-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="751b2-142">必须将客户细分导出到 Microsoft Advertising。</span><span class="sxs-lookup"><span data-stu-id="751b2-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="751b2-143">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="751b2-143">Select **Save**.</span></span>

<span data-ttu-id="751b2-144">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="751b2-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="751b2-145">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="751b2-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="751b2-146">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="751b2-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="751b2-147">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="751b2-147">Data privacy and compliance</span></span>

<span data-ttu-id="751b2-148">当您启用 Dynamics 365 Customer Insights 以将数据传输到 Microsoft Advertising 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="751b2-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="751b2-149">Microsoft 将在您的指示下传输此类数据，但您有责任确保 Microsoft Advertising 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="751b2-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="751b2-150">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="751b2-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="751b2-151">Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来停止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="751b2-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
