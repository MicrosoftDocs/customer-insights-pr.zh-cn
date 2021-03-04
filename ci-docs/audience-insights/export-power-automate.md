---
title: Power Automate 连接器 | Microsoft Docs
description: 在 Microsoft Power Automate 中从 Dynamics 365 Customer Insights 创建流。
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268813"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="e0485-103">Power Automate 连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="e0485-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="e0485-104">促使特定事件在数据更改时自动发生，并直接在 [Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。</span><span class="sxs-lookup"><span data-stu-id="e0485-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="e0485-105">Power Automate 触发器</span><span class="sxs-lookup"><span data-stu-id="e0485-105">Power Automate triggers</span></span>

<span data-ttu-id="e0485-106">使用触发器创建云端流并自动执行重复任务，例如发出通知或执行更高级的操作。</span><span class="sxs-lookup"><span data-stu-id="e0485-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="e0485-107">当数据源刷新失败时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="e0485-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="e0485-108">当数据源刷新成功时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="e0485-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="e0485-109">当客户细分超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="e0485-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="e0485-110">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="e0485-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="e0485-111">当业务度量超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="e0485-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="e0485-112">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="e0485-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="e0485-113">在完成完全刷新（数据源、客户细分、度量......）时触发。</span><span class="sxs-lookup"><span data-stu-id="e0485-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="e0485-114">完成统一过程（映射、匹配、合并）的刷新时触发。</span><span class="sxs-lookup"><span data-stu-id="e0485-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="e0485-115">[在 Power Automate 中配置触发器](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。</span><span class="sxs-lookup"><span data-stu-id="e0485-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="e0485-116">Power Automate 操作</span><span class="sxs-lookup"><span data-stu-id="e0485-116">Power Automate actions</span></span>
<span data-ttu-id="e0485-117">Power Automate 连接器提供的操作与可用触发器不同。</span><span class="sxs-lookup"><span data-stu-id="e0485-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="e0485-118">有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)”。</span><span class="sxs-lookup"><span data-stu-id="e0485-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="e0485-119">创建 Power Automate 流</span><span class="sxs-lookup"><span data-stu-id="e0485-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="e0485-120">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="e0485-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e0485-121">在 **Power Automate** 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="e0485-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="e0485-122">Power Automate 中的 Customer Insights 连接器（预览版）将会打开。</span><span class="sxs-lookup"><span data-stu-id="e0485-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="e0485-123">**登录** 到 Power Automate。</span><span class="sxs-lookup"><span data-stu-id="e0485-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="e0485-124">选择可用触发器之一，然后向新流中添加更多步骤。</span><span class="sxs-lookup"><span data-stu-id="e0485-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="e0485-125">有关详细信息，请参阅[在 Power Automate 中创建云端流](https://docs.microsoft.com/power-automate/get-started-logic-flow)。</span><span class="sxs-lookup"><span data-stu-id="e0485-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="e0485-126">关于如何使用流的示例：</span><span class="sxs-lookup"><span data-stu-id="e0485-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="e0485-127">如果数据源刷新失败，则将消息发布到 Microsoft Teams 渠道。</span><span class="sxs-lookup"><span data-stu-id="e0485-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="e0485-128">超过客户细分阈值时，向数据所有者发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e0485-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]