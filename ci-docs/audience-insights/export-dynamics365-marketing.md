---
title: 将 Customer Insights 数据导出到 Dynamics 365 Marketing
description: 了解如何配置与 Dynamics 365 Marketing 之间的连接。
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269043"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="21521-103">Dynamics 365 Marketing 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="21521-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="21521-104">使用[客户细分](segments.md)来生成市场活动，并通过 Dynamics 365 Marketing 联系特定客户组。</span><span class="sxs-lookup"><span data-stu-id="21521-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="21521-105">有关详细信息，请参阅[将来自 Dynamics 365 Customer Insights 的客户细分与 Dynamics 365 Marketing 结合使用](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="21521-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="21521-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="21521-106">Prerequisite</span></span>

- <span data-ttu-id="21521-107">Dynamics 365 Marketing 中必须先存在联系人记录，然后才能从 Customer Insights 中将客户细分导出到 Marketing。</span><span class="sxs-lookup"><span data-stu-id="21521-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="21521-108">详细了解如何[在 Dynamics 365 Marketing 中使用 Common Data Services](connect-power-query.md)引入联系人。</span><span class="sxs-lookup"><span data-stu-id="21521-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="21521-109">如果将客户细分从受众见解导出到 Marketing，则将不会在 Marketing 实例中创建新的联系人记录。</span><span class="sxs-lookup"><span data-stu-id="21521-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="21521-110">Marketing 中的联系人记录必须引入到受众见解中，并用作数据源。</span><span class="sxs-lookup"><span data-stu-id="21521-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="21521-111">在导出客户细分之前，还需要将它们包含在统一客户实体中，以将客户 ID 映射到联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="21521-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="21521-112">配置 Marketing 的连接器</span><span class="sxs-lookup"><span data-stu-id="21521-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="21521-113">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="21521-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="21521-114">在 **Dynamics 365 Marketing** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="21521-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="21521-115">在 **显示名称** 字段中为导出目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="21521-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="21521-116">在 **服务器地址** 字段中输入组织的 Marketing URL。</span><span class="sxs-lookup"><span data-stu-id="21521-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="21521-117">在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Marketing 帐户。</span><span class="sxs-lookup"><span data-stu-id="21521-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="21521-118">将客户 ID 字段映射到 Dynamics 365 联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="21521-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="21521-119">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="21521-119">Select **Next**.</span></span>

1. <span data-ttu-id="21521-120">选择一个或多个客户细分。</span><span class="sxs-lookup"><span data-stu-id="21521-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="21521-121">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="21521-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="21521-122">导出数据</span><span class="sxs-lookup"><span data-stu-id="21521-122">Export the data</span></span>

<span data-ttu-id="21521-123">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="21521-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="21521-124">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="21521-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]