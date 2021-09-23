---
title: Dynamics 365 Customer Insights 中的服务限制
description: 了解限制和局限。
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483647"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights 功能中的服务限额

本文介绍 Customer Insights 服务中的内置限制，设计用于确保该服务的可靠性和稳定性。 可以通过[创意论坛](https://go.microsoft.com/fwlink/?linkid=2074172)请求任何更改。 

## <a name="audience-insights"></a>访问群体见解

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 访问群体见解功能中的服务限制

| 地区  | 限额  | 备注 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客户细分和度量 | 100 个客户细分或度量。 | 组合的活动[客户细分](audience-insights/segments.md)和[度量](audience-insights/measures.md)的总数不能超过 100。  |
| 关系 | 实体路径中关系的 20 个深度级别。 | 使用生成器界面创建[客户细分](audience-insights/segments.md)或[度量](audience-insights/measures.md)时，实体路径在起始实体和目标实体之间最多可以有 20 个关系跃点。  |


## <a name="engagement-insights"></a>参与见解

### <a name="workspace-and-event-quotas"></a>工作区和事件配额

参与见解是一款可缩放性高的应用程序，每秒可支持数百万个事件。 在公开预览版期间，事件具有卷阈值。 对组织中的工作区数量也有限制。

### <a name="engagement-insights-limits"></a>参与见解限制

- 每个工作区的最大事件数 = 每秒 100 个事件

- 每个组织的最大工作区数 = 100

当事件超出阈值时，可能会导致基于这些事件的报表丢失数据。 您可以[与支持人员联系](https://go.microsoft.com/fwlink/?linkid=2145734)，以在超出限制之前请求增加数量。 我们将同您一起确定数量增加需求，并支持您的请求。


[!INCLUDE[footer-include](includes/footer-banner.md)]