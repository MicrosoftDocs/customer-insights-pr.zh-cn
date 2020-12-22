---
title: 将 Customer Insights 数据导出到 Dynamics 365 Marketing
description: 了解如何配置与 Dynamics 365 Marketing 之间的连接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643762"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="9d04b-103">Dynamics 365 Marketing 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="9d04b-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9d04b-104">使用[客户细分](segments.md)来生成市场活动，并通过 Dynamics 365 Marketing 联系特定客户组。</span><span class="sxs-lookup"><span data-stu-id="9d04b-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="9d04b-105">有关详细信息，请参阅[将来自 Dynamics 365 Customer Insights 的客户细分与 Dynamics 365 Marketing 结合使用](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="9d04b-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="9d04b-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="9d04b-106">Prerequisite</span></span>

<span data-ttu-id="9d04b-107">[使用 Common Data Service 引入的 Dynamics 365 Marketing](connect-power-query.md)的联系人记录。</span><span class="sxs-lookup"><span data-stu-id="9d04b-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="9d04b-108">配置 Marketing 的连接器</span><span class="sxs-lookup"><span data-stu-id="9d04b-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="9d04b-109">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="9d04b-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9d04b-110">在 **Dynamics 365 Marketing** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="9d04b-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="9d04b-111">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="9d04b-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9d04b-112">在 **服务器地址** 字段中输入组织的 Marketing URL。</span><span class="sxs-lookup"><span data-stu-id="9d04b-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9d04b-113">在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Marketing 帐户。</span><span class="sxs-lookup"><span data-stu-id="9d04b-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="9d04b-114">将客户 ID 字段映射到 Dynamics 365 联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="9d04b-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9d04b-115">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="9d04b-115">Select **Next**.</span></span>

1. <span data-ttu-id="9d04b-116">选择一个或多个客户细分。</span><span class="sxs-lookup"><span data-stu-id="9d04b-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="9d04b-117">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="9d04b-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9d04b-118">导出数据</span><span class="sxs-lookup"><span data-stu-id="9d04b-118">Export the data</span></span>

<span data-ttu-id="9d04b-119">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="9d04b-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9d04b-120">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="9d04b-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
