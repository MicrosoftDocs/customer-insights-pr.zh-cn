---
title: 将 Customer Insights 数据导出到 Dynamics 365 Sales
description: 了解如何配置与 Dynamics 365 Sales 之间的连接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643807"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="13ea0-103">Dynamics 365 Sales 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="13ea0-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="13ea0-104">使用您的客户数据通过 Dynamics 365 Sales 创建市场营销列表、跟进工作流以及发出促销。</span><span class="sxs-lookup"><span data-stu-id="13ea0-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="13ea0-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="13ea0-105">Prerequisite</span></span>

<span data-ttu-id="13ea0-106">[来自使用 Common Data Service 引入的 Dynamics 365 Sales](connect-power-query.md)的联系人记录。</span><span class="sxs-lookup"><span data-stu-id="13ea0-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="13ea0-107">配置 Sales 的连接器</span><span class="sxs-lookup"><span data-stu-id="13ea0-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="13ea0-108">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="13ea0-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="13ea0-109">在 **Dynamics 365 Sales** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="13ea0-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="13ea0-110">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="13ea0-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="13ea0-111">在 **服务器地址** 字段中输入组织的 Sales URL。</span><span class="sxs-lookup"><span data-stu-id="13ea0-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="13ea0-112">在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Sales 帐户。</span><span class="sxs-lookup"><span data-stu-id="13ea0-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="13ea0-113">将客户 ID 字段映射到 Dynamics 365 联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="13ea0-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="13ea0-114">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="13ea0-114">Select **Next**.</span></span>

1. <span data-ttu-id="13ea0-115">选择一个或多个客户细分。</span><span class="sxs-lookup"><span data-stu-id="13ea0-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="13ea0-116">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="13ea0-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="13ea0-117">导出数据</span><span class="sxs-lookup"><span data-stu-id="13ea0-117">Export the data</span></span>

<span data-ttu-id="13ea0-118">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="13ea0-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="13ea0-119">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="13ea0-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
