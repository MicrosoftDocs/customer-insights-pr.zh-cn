---
title: Power Automate 连接器 | Microsoft Docs
description: 利用 Dynamics 365 Customer Insights 在 Microsoft Power Automate 中创建流。
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305053"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="0dc32-103">Power Automate 连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="0dc32-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="0dc32-104">促使特定事件在数据更改时自动发生，并直接在 [Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。</span><span class="sxs-lookup"><span data-stu-id="0dc32-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="0dc32-105">Power Automate 触发器</span><span class="sxs-lookup"><span data-stu-id="0dc32-105">Power Automate triggers</span></span>

<span data-ttu-id="0dc32-106">使用触发器创建云端流并自动执行重复任务，例如发出通知或执行更高级的操作。</span><span class="sxs-lookup"><span data-stu-id="0dc32-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="0dc32-107">当数据源刷新失败时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="0dc32-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="0dc32-108">当数据源刷新成功时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="0dc32-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="0dc32-109">当客户细分超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="0dc32-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="0dc32-110">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="0dc32-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="0dc32-111">当业务度量超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="0dc32-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="0dc32-112">仅支持没有维度的业务度量。</span><span class="sxs-lookup"><span data-stu-id="0dc32-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="0dc32-113">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="0dc32-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="0dc32-114">在完成完全刷新（数据源、客户细分、度量......）时触发。</span><span class="sxs-lookup"><span data-stu-id="0dc32-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="0dc32-115">完成统一过程（映射、匹配、合并）的刷新时触发。</span><span class="sxs-lookup"><span data-stu-id="0dc32-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="0dc32-116">在 Power Automate 中配置触发器。</span><span class="sxs-lookup"><span data-stu-id="0dc32-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="0dc32-117">Power Automate 操作</span><span class="sxs-lookup"><span data-stu-id="0dc32-117">Power Automate actions</span></span>

<span data-ttu-id="0dc32-118">Power Automate 连接器提供的操作与可用触发器不同。</span><span class="sxs-lookup"><span data-stu-id="0dc32-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="0dc32-119">有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)”。</span><span class="sxs-lookup"><span data-stu-id="0dc32-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="0dc32-120">创建 Power Automate 流</span><span class="sxs-lookup"><span data-stu-id="0dc32-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="0dc32-121">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="0dc32-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0dc32-122">在 **Power Automate** 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="0dc32-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="0dc32-123">Power Automate 中的 Customer Insights 连接器（预览版）将会打开。</span><span class="sxs-lookup"><span data-stu-id="0dc32-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="0dc32-124">**登录** 到 Power Automate。</span><span class="sxs-lookup"><span data-stu-id="0dc32-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="0dc32-125">选择可用触发器之一，然后向新流中添加更多步骤。</span><span class="sxs-lookup"><span data-stu-id="0dc32-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="0dc32-126">有关详细信息，请参阅[在 Power Automate 中创建云端流](/power-automate/get-started-logic-flow)。</span><span class="sxs-lookup"><span data-stu-id="0dc32-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="0dc32-127">如何使用流的示例：</span><span class="sxs-lookup"><span data-stu-id="0dc32-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="0dc32-128">如果数据源刷新失败，则将消息发布到 Microsoft Teams 渠道。</span><span class="sxs-lookup"><span data-stu-id="0dc32-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="0dc32-129">超过客户细分阈值时，向数据所有者发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0dc32-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
