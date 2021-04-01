---
title: Power Automate 连接器 | Microsoft Docs
description: 利用 Dynamics 365 Customer Insights 在 Microsoft Power Automate 中创建流。
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597914"
---
# <a name="power-automate-connector-preview"></a>Power Automate 连接器（预览版）

促使特定事件在数据更改时自动发生，并直接在 [Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。

## <a name="power-automate-triggers"></a>Power Automate 触发器

使用触发器创建云端流并自动执行重复任务，例如发出通知或执行更高级的操作。 

- 当数据源刷新失败时触发的触发器。 
- 当数据源刷新成功时触发的触发器。
- 当客户细分超过阈值时触发的触发器。 此触发器只能在超过阈值时触发。
- 当业务度量超过阈值时触发的触发器。 此触发器只能在超过阈值时触发。
- 在完成完全刷新（数据源、客户细分、度量......）时触发。
- 完成统一过程（映射、匹配、合并）的刷新时触发。

[在 Power Automate 中配置触发器](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。

## <a name="power-automate-actions"></a>Power Automate 操作
Power Automate 连接器提供的操作与可用触发器不同。 有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)”。

## <a name="create-a-power-automate-flow"></a>创建 Power Automate 流

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **Power Automate** 磁贴中，选择 **设置**。

1. Power Automate 中的 Customer Insights 连接器（预览版）将会打开。 **登录** 到 Power Automate。

1. 选择可用触发器之一，然后向新流中添加更多步骤。 有关详细信息，请参阅[在 Power Automate 中创建云端流](/power-automate/get-started-logic-flow)。

关于如何使用流的示例： 
- 如果数据源刷新失败，则将消息发布到 Microsoft Teams 渠道。 
- 超过客户细分阈值时，向数据所有者发送电子邮件。



[!INCLUDE[footer-include](../includes/footer-banner.md)]