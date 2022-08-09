---
title: Power Automate 连接器（预览版）| Microsoft Docs
description: 利用 Dynamics 365 Customer Insights 在 Microsoft Power Automate 中创建流。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196107"
---
# <a name="power-automate-connector-preview"></a>Power Automate 连接器（预览版）

促使特定事件在数据更改时自动发生，并直接在 [Microsoft Power Automate](https://flow.microsoft.com/) 中管理更复杂的流。

## <a name="known-limitations"></a>已知限制

- 每 60 秒最多 100 次调用。 使用 [$skip 参数](/connectors/customerinsights/#get-items-from-an-entity)多次调用 API 终结点。

## <a name="power-automate-triggers"></a>Power Automate 触发器

使用触发器创建云端流并自动执行重复任务，例如发出通知或执行更高级的操作。 在以下情况下使用触发器：

- 数据源刷新失败。
- 数据源刷新成功。
- 客户细分超过阈值。 此触发器只能在超过阈值时触发。
- 业务度量超过阈值。 仅支持没有维度的业务度量。 此触发器只能在超过阈值时触发。
- 计划的整个刷新完成。 此触发器不适用于手动启动的刷新。
- 统一过程的刷新完成。

[在 Power Automate 中配置触发器。](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate 操作

Power Automate 连接器提供的操作与可用触发器不同。 有关详细信息，请参阅“[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)”。

## <a name="create-a-power-automate-flow"></a>创建 Power Automate 流

1. 转到 **管理员** > **连接**。

1. 在 **Power Automate** 磁贴中，选择 **设置**。

1. Power Automate 中的 Customer Insights 连接器（预览版）将会打开。 **登录** 到 Power Automate。

1. 选择可用触发器之一，然后向新流中添加更多步骤。 有关详细信息，请参阅[在 Power Automate 中创建云端流](/power-automate/get-started-logic-flow)。

如何使用流的示例： 
- 如果数据源刷新失败，则将消息发布到 Microsoft Teams 渠道。 
- 超过客户细分阈值时，向数据所有者发送电子邮件。

[!INCLUDE [footer-include](includes/footer-banner.md)]
