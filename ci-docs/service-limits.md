---
title: Customer Insights 中的服务限额
description: 了解 Customer Insights SaaS 服务中的限制和局限。
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940657"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights 中的服务限额

本文介绍 Customer Insights 服务中的内置限制，设计用于确保该服务的可靠性和稳定性。 可以通过[创意论坛](https://go.microsoft.com/fwlink/?linkid=2074172)请求任何更改。

## <a name="customer-insights"></a>Customer Insights

| Area  | 限额  | 注释 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 客户细分、度量和预测 | 300  | 组合后的[客户细分](segments.md)、[度量](measures.md)和[预测](predictions.md)的总数不能超过 300。  |
| 关系 | 实体路径中关系的 20 个深度级别。 | 使用生成器界面创建[客户细分](segments.md)或[度量](measures.md)时，实体路径在起始实体和目标实体之间最多可以有 20 个关系跃点。  |

## <a name="fair-scheduling-of-jobs"></a>合理安排作业

Customer Insights 是一项使用共享 Azure 资源的 SaaS 服务。 客户通常会有不同强度和不同计划的工作负荷。 为了确保对基础资源的合理使用，我们确保系统流程以合理的顺序执行。 系统流程的示例如与数据统一、客户细分更新或度量计算相关的作业。 如果请求的作业数量激增，合理安排可以防止您排队等待资源。 但 Customer Insights 不能保证您加入队列的所有作业都并行处理。

[!INCLUDE [footer-include](includes/footer-banner.md)]
