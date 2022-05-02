---
title: 了解和管理度量
description: 了解度量如何帮助分析和反映您的业务绩效。
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645637"
---
# <a name="measures-overview"></a>度量概述

措施有助于您更好地了解客户行为和业务绩效。 他们从[统一配置文件](data-unification.md)中查看相关值。 例如，企业希望查看 *每个客户的总支出* 以了解单独客户的购买历史记录，或度量 *公司的总销售额* 以了解整个企业的聚合级别收入。  

度量是[使用度量生成器](measure-builder.md)（具有各种运算符和简单映射选项的数据查询平台）创建的。 它允许您筛选数据、对结果进行分组、检测[实体关系路径](relationships.md)和预览输出。 您可以[使用预定义的模板](measure-templates.md)有效地配置常用度量。

使用度量生成器通过查询客户数据来规划业务活动并提取见解。 例如，创建 *每个客户所花费的总费用* 和 *每个客户的总回报* 的度量有助于确定一组花费高但回报也高的客户。 您可以基于这些度量[创建一个客户细分](segments.md)，以推动下一批最佳操作。

## <a name="manage-your-measures"></a>管理度量

您可以在 **度量** 页面上找到度量列表。

您将找到有关度量类型、创建者、创建日期、状况和状态的信息。 当您从列表中选择度量时，您可以预览输出并下载 CSV 文件。

:::image type="content" source="media/measures-actions.png" alt-text="用于管理单个度量的操作。"lightbox="media/measures-actions.png":::

当您选择某个度量时，可以使用以下操作：

- **编辑** 度量的配置。
- **重复** 度量。 您可以选择立即编辑其属性或只是保存重复项。
- 根据最新数据 **刷新** 度量。 若要同时刷新所有度量，请选择所有度量，然后选择 **刷新**。
- **重命名** 度量。
- **激活** 或 **停用**。 停用的度量在[计划刷新](system.md#schedule-tab)期间不会刷新。
- 用于针对客户细分 [管理标记](work-with-tags-columns.md#manage-tags)的 **标记**。
- **删除** 度量。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>下一步

您可以使用现有度量创建[客户细分](segments.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
