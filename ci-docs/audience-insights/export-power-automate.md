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
# <a name="power-automate-connector-preview"></a>Power Automate 连接器（预览版）

促使特定事件在数据更改时自动发生，并直接在 [Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。

## <a name="power-automate-triggers"></a>Power Automate 触发器

您可以使用允许创建流以自动执行重复性任务（如通知或更高级的操作）的多种触发器。 

- 当数据源刷新失败时触发的触发器。 
- 当数据源刷新成功时触发的触发器。
- 当客户细分超过阈值时触发的触发器。 此触发器只能在超过阈值时触发。
- 当业务度量超过阈值时触发的触发器。 此触发器只能在超过阈值时触发。
- 在完成完全刷新（数据源、客户细分、度量......）时触发。
- 完成统一过程（映射、匹配、合并）的刷新时触发。

[在 Power Automate 中配置触发器](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。

## <a name="power-automate-actions"></a>Power Automate 操作
Power Automate 连接器提供的操作与可用触发器不同。 有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)”。

## <a name="create-a-power-automate-flow-in-audience-insights"></a>在访问群体见解中创建 Power Automate 流

1. 在访问群体见解中，转到 **管理员** > **系统**。

1. 在 **系统** 页面上，选择 **状态** 选项卡。

1. 在 **数据源** 部分中，选择 **流**，然后从下拉列表中选择 **创建流**。
   > [!div class="mx-imgBorder"]
   > ![Power Automate 连接器显示“创建流”操作](media/power-automate-connector-create-flow.png "Power Automate 连接器显示“创建流”操作")

1. 在 Power Automate 中，选择一个可用触发器创建首选流。 如果要创建第一个流，您需要首先通过 Power Automate 连接器的身份验证。
