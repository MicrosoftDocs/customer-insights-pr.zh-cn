---
title: Power Automate 连接器 | Microsoft Docs
description: 在 Microsoft Power Automate 中从 Dynamics 365 Customer Insights 创建流。
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405180"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="7bde1-103">Power Automate 连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="7bde1-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="7bde1-104">促使特定事件在数据更改时自动发生，并直接在 [Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。</span><span class="sxs-lookup"><span data-stu-id="7bde1-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="7bde1-105">Power Automate 触发器</span><span class="sxs-lookup"><span data-stu-id="7bde1-105">Power Automate triggers</span></span>

<span data-ttu-id="7bde1-106">您可以使用允许创建流以自动执行重复性任务（如通知或更高级的操作）的多种触发器。</span><span class="sxs-lookup"><span data-stu-id="7bde1-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="7bde1-107">当数据源刷新失败时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="7bde1-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="7bde1-108">当数据源刷新成功时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="7bde1-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="7bde1-109">当客户细分超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="7bde1-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="7bde1-110">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="7bde1-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="7bde1-111">当业务度量超过阈值时触发的触发器。</span><span class="sxs-lookup"><span data-stu-id="7bde1-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="7bde1-112">此触发器只能在超过阈值时触发。</span><span class="sxs-lookup"><span data-stu-id="7bde1-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="7bde1-113">在完成完全刷新（数据源、客户细分、度量......）时触发。</span><span class="sxs-lookup"><span data-stu-id="7bde1-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="7bde1-114">完成统一过程（映射、匹配、合并）的刷新时触发。</span><span class="sxs-lookup"><span data-stu-id="7bde1-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="7bde1-115">[在 Power Automate 中配置触发器](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。</span><span class="sxs-lookup"><span data-stu-id="7bde1-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="7bde1-116">Power Automate 操作</span><span class="sxs-lookup"><span data-stu-id="7bde1-116">Power Automate actions</span></span>
<span data-ttu-id="7bde1-117">Power Automate 连接器提供的操作与可用触发器不同。</span><span class="sxs-lookup"><span data-stu-id="7bde1-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="7bde1-118">有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)”。</span><span class="sxs-lookup"><span data-stu-id="7bde1-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="7bde1-119">在访问群体见解中创建 Power Automate 流</span><span class="sxs-lookup"><span data-stu-id="7bde1-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="7bde1-120">在访问群体见解中，转到 **管理员** > **系统**。</span><span class="sxs-lookup"><span data-stu-id="7bde1-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="7bde1-121">在 **系统** 页面上，选择 **状态** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7bde1-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="7bde1-122">在 **数据源** 部分中，选择 **流**，然后从下拉列表中选择 **创建流**。</span><span class="sxs-lookup"><span data-stu-id="7bde1-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7bde1-123">![Power Automate 连接器显示“创建流”操作](media/power-automate-connector-create-flow.png "Power Automate 连接器显示“创建流”操作")</span><span class="sxs-lookup"><span data-stu-id="7bde1-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="7bde1-124">在 Power Automate 中，选择一个可用触发器创建首选流。</span><span class="sxs-lookup"><span data-stu-id="7bde1-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="7bde1-125">如果要创建第一个流，您需要首先通过 Power Automate 连接器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="7bde1-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
