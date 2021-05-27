---
title: Power Automate 连接器 | Microsoft Docs
description: 利用 Dynamics 365 Customer Insights 在 Microsoft Power Automate 中创建流。
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976077"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="1baec-103">Power Automate 连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="1baec-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="1baec-104">促使特定事件在数据更改时自动发生，并直接在 [Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。</span><span class="sxs-lookup"><span data-stu-id="1baec-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="1baec-105">Power Automate 触发器</span><span class="sxs-lookup"><span data-stu-id="1baec-105">Power Automate triggers</span></span>

<span data-ttu-id="1baec-106">使用触发器创建云端流并自动执行重复任务，例如发出通知或执行更高级的操作。</span><span class="sxs-lookup"><span data-stu-id="1baec-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="1baec-107">当数据源刷新失败时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="1baec-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="1baec-108">当数据源刷新成功时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="1baec-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="1baec-109">当客户细分超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="1baec-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="1baec-110">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="1baec-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="1baec-111">当业务度量超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="1baec-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="1baec-112">仅支持没有维度的业务度量。</span><span class="sxs-lookup"><span data-stu-id="1baec-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="1baec-113">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="1baec-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="1baec-114">在完成完全刷新（数据源、客户细分、度量......）时触发。</span><span class="sxs-lookup"><span data-stu-id="1baec-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="1baec-115">完成统一过程（映射、匹配、合并）的刷新时触发。</span><span class="sxs-lookup"><span data-stu-id="1baec-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="1baec-116">[在 Power Automate 中配置触发器](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。</span><span class="sxs-lookup"><span data-stu-id="1baec-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="1baec-117">Power Automate 操作</span><span class="sxs-lookup"><span data-stu-id="1baec-117">Power Automate actions</span></span>
<span data-ttu-id="1baec-118">Power Automate 连接器提供的操作与可用触发器不同。</span><span class="sxs-lookup"><span data-stu-id="1baec-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="1baec-119">有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)”。</span><span class="sxs-lookup"><span data-stu-id="1baec-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="1baec-120">创建 Power Automate 流</span><span class="sxs-lookup"><span data-stu-id="1baec-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="1baec-121">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="1baec-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1baec-122">在 **Power Automate** 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="1baec-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="1baec-123">Power Automate 中的 Customer Insights 连接器（预览版）将会打开。</span><span class="sxs-lookup"><span data-stu-id="1baec-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="1baec-124">**登录** 到 Power Automate。</span><span class="sxs-lookup"><span data-stu-id="1baec-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="1baec-125">选择可用触发器之一，然后向新流中添加更多步骤。</span><span class="sxs-lookup"><span data-stu-id="1baec-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="1baec-126">有关详细信息，请参阅[在 Power Automate 中创建云端流](/power-automate/get-started-logic-flow)。</span><span class="sxs-lookup"><span data-stu-id="1baec-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="1baec-127">关于如何使用流的示例：</span><span class="sxs-lookup"><span data-stu-id="1baec-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="1baec-128">如果数据源刷新失败，则将消息发布到 Microsoft Teams 渠道。</span><span class="sxs-lookup"><span data-stu-id="1baec-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="1baec-129">超过客户细分阈值时，向数据所有者发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1baec-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
