---
title: 实体和数据集
description: 在“实体”页面上查看数据。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 00c5ee50fb9f0906622c91699852ffba0acb5c15
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900416"
---
# <a name="entities-in-audience-insights"></a>访问群体见解中的实体

[配置数据源](data-sources.md)之后，转到 **实体** 页以评估引入的数据的质量。 实体将会视为数据集。 Dynamics 365 Customer Insights 的多个功能基于这些实体生成。 近距离查看它们有助您验证这些功能的输出。

**实体** 页列出了实体并包含以下列：

- **名称**：数据实体的名称。 如果看到实体名称旁边有警告符号，说明未成功加载该实体的数据。
- **来源**：引入实体的数据源的类型。
- **更新时间**：上次更新实体的时间。
- **状态**：有关实体上次更新的详细信息。

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>浏览特定实体的数据

1. 在访问群体见解中，转到 **数据** > **实体**。
1. 在 **实体** 页中，选择一个实体以打开详细信息页。  
1. 浏览该实体包含的不同字段和记录。

- 默认情况下，**属性** 选项卡已被选定，并且会显示一个表，用于查看选定实体的详细信息，例如字段名称、数据类型和类型。 **类型** 列显示 Common Data Model 关联的类型，其由系统自动确定，或由用户[手动映射](map-entities.md)。 这些类型是可以与属性的数据类型不同的语义类型。 例如，下面的 *电子邮件* 字段具有 *文本* 数据类型，但其（语义）Common Data Model 类型可能是 *电子邮件* 或 *EmailAddress*。

> [!div class="mx-imgBorder"]
> ![字段表。](media/data-manager-entities-fields.PNG "字段表")

> [!NOTE]
> 此页只显示实体数据的一个示例。 若要查看完整数据集，请转到 **数据源** 页，选择一个实体，选择 **编辑**，然后按照[数据源](data-sources.md)中的说明使用 Power Query 查看此实体的数据。

若要详细了解实体中引入的数据，可通过 **摘要** 列查看数据的某些重要特征，如空、缺少值、唯一值、计数和分发（如果适用于您的数据）。 选择图表图标查看数据的摘要。

> [!div class="mx-imgBorder"]
> ![摘要符号。](media/data-manager-entities-summary.png "数据摘要表")

- **数据** 选项卡显示一个表，其中列出了有关实体各个记录的详细信息。 列出的详细信息取决于实体的数据类型。

> [!div class="mx-imgBorder"]
> ![选择实体。](media/data-manager-entities-data.png "选择实体")

- **报表** 选项卡（可用于某些实体）使您能够通过创建报表来呈现数据，并且包括以下列：

  - **报表名称**：报表的名称。
  - **创建者**：创建实体的用户的名称。
  - **创建时间**：实体的创建日期和时间。
  - **编辑者**：修改实体的用户的名称。
  - **编辑时间**：实体的修改日期和时间。 

## <a name="entity-specific-information"></a>实体特定信息

以下部分提供有关一些系统创建的实体的信息。

### <a name="corrupted-data-sources"></a>损坏的数据源

引入的数据源的字段可能包含损坏的数据。 系统创建的实体中公开了字段损坏的记录。 了解损坏的记录有助于您确定要在源系统上查看和更新哪些数据。 在下一次刷新数据源后，更正的记录被引入到 Customer Insights 中并传递到下游流程。 

例如，“生日”列的数据类型已被设置为“日期”。 客户记录中生日被输入为“01/01/19777”。 系统会将此记录标记为已损坏。 现在，某人可以将源系统中的生日更改为“1977”。 自动刷新数据源后，该字段现在具有有效格式，并且将从损坏的实体中删除记录。 

转到 **数据** > **实体**，在 **系统** 部分中查找损坏的实体。 损坏的实体的命名架构：“DataSourceName_EntityName_corrupt”。

Customer Insights 仍会处理损坏的记录。 但是，使用统一数据时，它们可能会导致问题。

对引入的数据运行了以下检查以显示损坏的记录： 

- 字段的值与其列的数据类型不匹配。
- 字段包含导致列与预期架构不匹配的字符。 例如：格式不正确的引号、未转义的引号或换行符。
- 如果存在日期时间/日期/datetimeoffset 列，则需要在模型中指定其格式（如果它没有遵循标准的 ISO 格式）。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
