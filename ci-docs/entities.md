---
title: Customer Insights 中的实体
description: 在“实体”页面上查看数据。
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610087"
---
# <a name="entities-in-customer-insights"></a>Customer Insights 中的实体

[配置数据源](data-sources.md)之后，转到 **实体** 页以评估引入的数据的质量。 实体将会视为数据集。 Dynamics 365 Customer Insights 的多个功能基于这些实体生成。 近距离查看它们有助您验证这些功能的输出。

当您在 Customer Insights 中工作，扩充您的数据或创建客户细分、度量和活动时，从这些操作创建的实体会显示在 **实体** 页面上。

## <a name="view-a-list-of-entities"></a>查看实体列表

转到 **数据** > **实体** 查看实体列表。 每个实体将显示以下信息。

- **名称**：实体的名称。 如果看到实体名称旁边有警告符号，说明未成功加载该实体的数据。
- **来源**：引入实体的数据源的类型。
- **更新时间**：上次更新实体的时间。
- **状态**：有关实体上次更新的详细信息。

## <a name="explore-a-specific-entitys-data"></a>浏览特定实体的数据

1. 转到 **数据** > **实体**。
1. 选择实体可以打开详细信息页。  
1. 浏览该实体包含的不同字段和记录。

- 默认情况下，**属性** 选项卡已被选定，显示选定实体的详细信息，如字段名称、数据类型和类型。 **类型** 列显示 Common Data Model 关联的类型，其由系统自动确定，或由用户[手动映射](map-entities.md)。 这些类型是可以与属性的数据类型不同的语义类型。 例如，下面的 *电子邮件* 字段具有 *字符串* 数据类型，但其（语义）Common Data Model 类型可能是 *Email*、*EmailAddress* 或 *Identity.Service.Email*。

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="字段表。":::

   > [!NOTE]
   > 此页只显示实体数据的一个示例。 若要查看完整数据集，请转到 **数据源** 页，选择一个实体，选择 **编辑**，然后按照[数据源](data-sources.md)中的说明使用 Power Query 编辑器查看此实体的数据。

   若要详细了解实体中引入的数据，可通过 **摘要** 列查看某些重要的数据特征，如空、缺少值、唯一值、计数和分发（只要适用于您的数据）。 选择图表图标查看数据的摘要。

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="数据摘要表。":::

- **数据** 选项卡显示有关实体各个记录的详细信息。 列出的详细信息取决于实体的数据类型。

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="选择实体。":::

- **报表** 选项卡（可用于某些实体）使您能够通过创建报表来呈现数据，其包括以下列：

  - **报表名称**：报表的名称。
  - **创建者**：创建实体的用户的名称。
  - **创建时间**：实体的创建日期和时间。
  - **编辑者**：修改实体的用户的名称。
  - **编辑时间**：实体的修改日期和时间。

[!INCLUDE [footer-include](includes/footer-banner.md)]
