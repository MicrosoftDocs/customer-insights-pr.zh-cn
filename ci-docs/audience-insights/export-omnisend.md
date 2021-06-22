---
title: 将 Customer Insights 数据导出到 Omnisend
description: 了解如何配置连接和导出到 Omnisend。
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124460"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="94d49-103">将客户细分导出到 Omnisend（预览版）</span><span class="sxs-lookup"><span data-stu-id="94d49-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="94d49-104">将统一客户配置文件的客户细分导出到 Omnisend，并将其用于市场营销活动。</span><span class="sxs-lookup"><span data-stu-id="94d49-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94d49-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="94d49-105">Prerequisites</span></span>

-   <span data-ttu-id="94d49-106">您有一个 [Omnisend 帐户](https://www.omnisend.com/)和相应的管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="94d49-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="94d49-107">您在访问群体见解中具有[配置的客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="94d49-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="94d49-108">导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="94d49-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94d49-109">已知限制</span><span class="sxs-lookup"><span data-stu-id="94d49-109">Known limitations</span></span>

- <span data-ttu-id="94d49-110">对于每次导出，您可以向 Omnisend 导出多达 100 万个配置文件，最多可能需要 4 个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="94d49-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="94d49-111">导出到 Omnisend 仅限于客户细分。</span><span class="sxs-lookup"><span data-stu-id="94d49-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="94d49-112">您可以导出到 Omnisend 的配置文件数量取决于您与 Omnisend 之间的合同。</span><span class="sxs-lookup"><span data-stu-id="94d49-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="94d49-113">设置与 Omnisend 的连接</span><span class="sxs-lookup"><span data-stu-id="94d49-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="94d49-114">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="94d49-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="94d49-115">选择 **添加连接** 并选择 **Omnisend** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="94d49-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="94d49-116">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="94d49-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="94d49-117">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="94d49-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="94d49-118">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="94d49-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="94d49-119">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="94d49-119">Choose who can use this connection.</span></span> <span data-ttu-id="94d49-120">默认情况下，它只是管理员。</span><span class="sxs-lookup"><span data-stu-id="94d49-120">By default it's only administrators.</span></span> <span data-ttu-id="94d49-121">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="94d49-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="94d49-122">输入 [Omnisend API 密钥](https://support.omnisend.com/en/articles/1061890-generating-api-key)。</span><span class="sxs-lookup"><span data-stu-id="94d49-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="94d49-123">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="94d49-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94d49-124">选择 **连接** 以初始化与 Omnisend 的连接。</span><span class="sxs-lookup"><span data-stu-id="94d49-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="94d49-125">选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。</span><span class="sxs-lookup"><span data-stu-id="94d49-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="94d49-126">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="94d49-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="94d49-127">配置导出</span><span class="sxs-lookup"><span data-stu-id="94d49-127">Configure an export</span></span>

<span data-ttu-id="94d49-128">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="94d49-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="94d49-129">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="94d49-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="94d49-130">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="94d49-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="94d49-131">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="94d49-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="94d49-132">在 **导出连接** 字段中，从 Omnisend 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="94d49-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="94d49-133">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="94d49-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="94d49-134">在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="94d49-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="94d49-135">必须将客户细分导出到 Omnisend。</span><span class="sxs-lookup"><span data-stu-id="94d49-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="94d49-136">（可选）您可以导出名、姓、地址、国家/地区、省/市/自治区、市/县和邮政编码以创建更个性化的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="94d49-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="94d49-137">选择 **添加属性** 以映射这些字段。</span><span class="sxs-lookup"><span data-stu-id="94d49-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="94d49-138">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="94d49-138">Select **Save**.</span></span>

<span data-ttu-id="94d49-139">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="94d49-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="94d49-140">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="94d49-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94d49-141">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="94d49-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94d49-142">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="94d49-142">Data privacy and compliance</span></span>

<span data-ttu-id="94d49-143">当您启用 Dynamics 365 Customer Insights 以将数据传输到 Ommisend 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。</span><span class="sxs-lookup"><span data-stu-id="94d49-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94d49-144">Microsoft 将在您的指示下传输此类数据，但您有责任确保 Omnisend 履行您可能具有的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="94d49-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="94d49-145">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="94d49-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="94d49-146">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="94d49-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
