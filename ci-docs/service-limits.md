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
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641751"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights 中的服务限额

本文介绍 Customer Insights 服务中的内置限制，设计用于确保该服务的可靠性和稳定性。 可以通过[创意论坛](https://go.microsoft.com/fwlink/?linkid=2074172)请求任何更改。 

## <a name="customer-insights"></a>Customer Insights

| Area  | 限额  | 注释 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客户细分、度量和预测 | 300  | 组合后的[客户细分](segments.md)、[度量](measures.md)和[预测](predictions.md)的总数不能超过 300。  |
| 关系 | 实体路径中关系的 20 个深度级别。 | 使用生成器界面创建[客户细分](segments.md)或[度量](measures.md)时，实体路径在起始实体和目标实体之间最多可以有 20 个关系跃点。  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
