---
title: 服务限制
description: 了解限制和局限。
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604358"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 访问群体见解功能中的服务限制

本文介绍 Customer Insights 服务中的内置限制，设计用于确保该服务的可靠性和稳定性。 可以通过[创意论坛](https://go.microsoft.com/fwlink/?linkid=2074172)请求任何更改。 
 
| 面积  | 限额  | 备注 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客户细分和度量 | 100 个客户细分或度量。 | 组合的活动[客户细分](segments.md)和[度量](measures.md)的总数不能超过 100。  |
| 关系 | 实体路径中关系的 20 个深度级别。 | 使用生成器界面创建[客户细分](segments.md)或[度量](measures.md)时，实体路径在起始实体和目标实体之间最多可以有 20 个关系跃点。  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]