---
title: 将 Customer Insights 数据导出到 Dynamics 365 Sales
description: 了解如何配置与 Dynamics 365 Sales 之间的连接。
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598098"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="60364-103">Dynamics 365 Sales 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="60364-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="60364-104">使用您的客户数据通过 Dynamics 365 Sales 创建市场营销列表、跟进工作流以及发出促销。</span><span class="sxs-lookup"><span data-stu-id="60364-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="60364-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="60364-105">Prerequisite</span></span>

1. <span data-ttu-id="60364-106">Dynamics 365 Sales 中必须先存在联系人记录，然后才能从 Customer Insights 中将客户细分导出到 Sales。</span><span class="sxs-lookup"><span data-stu-id="60364-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="60364-107">详细了解如何[在 Dynamics 365 Sales 中使用 Common Data Services](connect-power-query.md)引入联系人。</span><span class="sxs-lookup"><span data-stu-id="60364-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="60364-108">如果将客户细分从受众见解导出到 Sales，则将不会在 Sales 实例中创建新的联系人记录。</span><span class="sxs-lookup"><span data-stu-id="60364-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="60364-109">Sales 中的联系人记录必须引入到受众见解中，并用作数据源。</span><span class="sxs-lookup"><span data-stu-id="60364-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="60364-110">在导出客户细分之前，还需要将它们包含在统一客户实体中，以将客户 ID 映射到联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="60364-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="60364-111">配置 Sales 的连接器</span><span class="sxs-lookup"><span data-stu-id="60364-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="60364-112">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="60364-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="60364-113">在 **Dynamics 365 Sales** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="60364-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="60364-114">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="60364-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="60364-115">在 **服务器地址** 字段中输入组织的 Sales URL。</span><span class="sxs-lookup"><span data-stu-id="60364-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="60364-116">在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Sales 帐户。</span><span class="sxs-lookup"><span data-stu-id="60364-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="60364-117">将客户 ID 字段映射到 Dynamics 365 联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="60364-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="60364-118">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="60364-118">Select **Next**.</span></span>

1. <span data-ttu-id="60364-119">选择一个或多个客户细分。</span><span class="sxs-lookup"><span data-stu-id="60364-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="60364-120">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="60364-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="60364-121">导出数据</span><span class="sxs-lookup"><span data-stu-id="60364-121">Export the data</span></span>

<span data-ttu-id="60364-122">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="60364-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="60364-123">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="60364-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]