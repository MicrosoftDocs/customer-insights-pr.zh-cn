---
title: Dynamics 365 Customer Insights 中的服务限制
description: 了解限制和局限。
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350396"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights 功能中的服务限额

本文介绍 Customer Insights 服务中的内置限制，设计用于确保该服务的可靠性和稳定性。 可以通过[创意论坛](https://go.microsoft.com/fwlink/?linkid=2074172)请求任何更改。 

## <a name="audience-insights"></a>访问群体见解

| Area  | 限额  | 注释 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客户细分、度量和预测 | 300  | 组合后的[客户细分](audience-insights/segments.md)、[度量](audience-insights/measures.md)和[预测](audience-insights/predictions.md)的总数不能超过 300。  |
| 关系 | 实体路径中关系的 20 个深度级别。 | 使用生成器界面创建[客户细分](audience-insights/segments.md)或[度量](audience-insights/measures.md)时，实体路径在起始实体和目标实体之间最多可以有 20 个关系跃点。  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
