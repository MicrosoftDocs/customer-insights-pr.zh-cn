---
title: 了解和管理度量
description: 了解度量如何帮助分析和反映您的业务绩效。
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359762"
---
# <a name="measures-overview"></a>度量概述

措施有助于您更好地了解客户行为和业务绩效。 他们从[统一配置文件](data-unification.md)中查看相关值。 例如，企业希望查看 *每个客户的总支出* 以了解单独客户的购买历史记录，或度量 *公司的总销售额* 以了解整个企业的聚合级别收入。  

度量是[使用度量生成器](measure-builder.md)（具有各种运算符和简单映射选项的数据查询平台）创建的。 它允许您筛选数据、对结果进行分组、检测[实体关系路径](relationships.md)和预览输出。 您可以[使用预定义的模板](measure-templates.md)有效地配置常用度量。

使用度量生成器通过查询客户数据来规划业务活动并提取见解。 例如，创建 *每个客户所花费的总费用* 和 *每个客户的总回报* 的度量有助于确定一组花费高但回报也高的客户。 您可以基于这些度量[创建一个客户细分](segments.md)，以推动下一批最佳操作。 

## <a name="manage-your-measures"></a>管理度量

您可以在 **度量** 页面上找到度量列表。

您将找到有关度量类型、创建者、创建日期、状况和状态的信息。 当您从列表中选择度量时，您可以预览输出并下载 CSV 文件。

若要同时刷新所有度量，请在不选择特定度量的情况下选择 **全部刷新**。

:::image type="content" source="media/measure-actions.png" alt-text="用于管理单个度量的操作。":::

针对以下选项从列表中选择度量：

- 选择度量名称以查看其详细信息。
- **编辑** 度量的配置。
- 根据最新数据 **刷新** 度量。
- **重命名** 度量。
- **删除** 度量。
- **激活** 或 **停用**。 停用的度量在[计划刷新](system.md#schedule-tab)期间不会刷新。

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>下一步

您可以使用现有度量创建[客户细分](segments.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
