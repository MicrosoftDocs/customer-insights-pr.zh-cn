---
title: 度量概述
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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170809"
---
# <a name="measures-overview"></a>度量概述

措施有助于您更好地了解客户行为和业务绩效。 他们从[统一配置文件](data-unification.md)中查看相关值。 例如，企业希望查看 *每个客户的总支出* 以了解单独客户的购买历史记录，或度量 *公司的总销售额* 以了解整个企业的聚合级别收入。

创建度量以通过查询客户数据来规划业务活动并提取见解。 例如，创建 *每个客户所花费的总费用* 和 *每个客户的总回报* 的度量来帮助确定一组花费高但回报也高的客户。 然后，基于这些度量[创建一个客户细分](segments.md)，以推动下一批最佳操作。

## <a name="create-a-measure"></a>创建度量

选择如何根据您的目标访问群体创建度量。

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

- 使用度量生成器从头开始：[生成您自己的度量](measure-builder.md)。
- 从常用度量：[使用预定义模板](measure-templates.md)。

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

使用度量生成器从头开始：[生成您自己的度量](measure-builder.md)。

---

## <a name="manage-existing-measures"></a>管理现有度量

转到 **度量** 页面查看您创建的度量、度量的状态、度量类型以及上次刷新数据的时间。 您可以按任何列对度量列表进行排序，或使用搜索框查找要管理的度量。

在度量旁边选择可以查看可用操作。 选择度量名称可以预览输出并下载 CSV 文件。

:::image type="content" source="media/measures-actions.png" alt-text="用于管理单个度量的操作。"lightbox="media/measures-actions.png":::

- **编辑** 度量以更改其属性。
- **刷新** 度量以包括最新数据。
- **重命名** 度量。
- **激活** 或 **停用** 度量。 停用度量不会在 [计划刷新](system.md#schedule-tab)时刷新，会将 **状态** 列为 **已跳过**，指示还没有尝试刷新。
- 用于针对度量 [管理标记](work-with-tags-columns.md#manage-tags)的 **标记**。
- **删除** 度量。
- 用于 [自定义显示的列](work-with-tags-columns.md#customize-columns)的 **列**。
- 用于 [按标记筛选](work-with-tags-columns.md#filter-on-tags)的 **筛选器**。
- 用于按度量名称进行搜索的 **搜索名称**。

## <a name="refresh-measures"></a>刷新度量

度量可以按计划自动刷新，也可以根据需要手动刷新。 若要手动刷新一个或多个度量，请选择它们并选择 **刷新**。 若要 [计划自动刷新](system.md#schedule-tab)，请转到 **管理** > **系统** > **计划**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
