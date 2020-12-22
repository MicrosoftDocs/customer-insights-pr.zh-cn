---
title: 实体和数据集
description: 在“实体”页面上查看数据。
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405191"
---
# <a name="entities-in-audience-insights"></a>访问群体见解中的实体

[配置数据源](data-sources.md)之后，转到 **实体** 页以评估引入的数据的质量。 实体将会视为数据集。 Dynamics 365 Customer Insights 的多个功能基于这些实体生成。 近距离查看它们有助您验证这些功能的输出。

**实体** 页列出实体，并且有多列：

- **名称**：数据实体的名称。 如果看到实体名称旁边有警告符号，说明未成功加载该实体的数据。
- **源**：引入的实体的数据源类型
- **创建者**：创建实体的用户的名称
- **创建时间**：实体的创建日期和时间
- **更新者**：更新实体的用户的名称
- **上次更新时间**：实体的上次更新日期和时间
- **上次刷新时间**：上次刷新数据的日期和时间

## <a name="exploring-a-specific-entitys-data"></a>浏览特定实体的数据

选择实体以浏览该实体中包含的不同字段和记录。

> [!div class="mx-imgBorder"]
> ![选择实体](media/data-manager-entities-data.png "选择实体")

- **数据** 选项卡默认已选中，并显示一个表，其中列出了有关实体的各记录的详细信息。

> [!div class="mx-imgBorder"]
> ![字段表](media/data-manager-entities-fields.PNG "字段表")

- **字段** 选项卡显示一个表，用于查看所选实体的详细信息，如字段名称、数据类型和类型。 **类型** 列显示 Common Data Model 关联的类型，其由系统自动确定，或由用户[手动映射](map-entities.md)。 这些是可能与属性的数据类型不同的语义类型 — 例如，下面的 *电子邮件* 字段的数据类型为 *文本*，但是，其（语义）的 Common Data Model 类型可能未 *电子邮件* 或 *电子邮件地址*。

> [!NOTE]
> 这两个表都仅显示您的实体的数据的一个示例。 若要查看完整数据集，请转到 **数据源** 页，选择一个实体，选择 **编辑**，然后按照[数据源](data-sources.md)中的说明使用 Power Query 查看此实体的数据。

若要详细了解实体中引入的数据，可通过 **摘要** 列查看数据的某些重要特征，如空、缺少值、唯一值、计数和分发（如果适用于您的数据）。

选择图表图标查看数据的摘要。

> [!div class="mx-imgBorder"]
> ![摘要符号](media/data-manager-entities-summary.png "数据摘要表")

### <a name="next-step"></a>下一步

请参阅 [统一](data-unification.md)状态了解如何 *映射*、*匹配* 和 *合并* 引入的数据。
