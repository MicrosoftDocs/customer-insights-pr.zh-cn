---
title: 实体和数据集
description: 在“实体”页面上查看数据。
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553964"
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

## <a name="explore-a-specific-entitys-data"></a>浏览特定实体的数据

选择实体以浏览该实体中包含的不同字段和记录。

> [!div class="mx-imgBorder"]
> ![选择实体。](media/data-manager-entities-data.png "选择实体")

- **数据** 选项卡显示一个表，其中列出了有关实体各个记录的详细信息。

> [!div class="mx-imgBorder"]
> ![字段表。](media/data-manager-entities-fields.PNG "字段表")

- 默认情况下，**属性** 选项卡已被选定，并且会显示一个表，用于查看选定实体的详细信息，例如字段名称、数据类型和类型。 **类型** 列显示 Common Data Model 关联的类型，其由系统自动确定，或由用户[手动映射](map-entities.md)。 这些类型是可以与属性的数据类型不同的语义类型。 例如，下面的 *电子邮件* 字段具有 *文本* 数据类型，但其（语义）Common Data Model 类型可能是 *电子邮件* 或 *EmailAddress*。

> [!NOTE]
> 这两个表都仅显示您的实体的数据的一个示例。 若要查看完整数据集，请转到 **数据源** 页，选择一个实体，选择 **编辑**，然后按照[数据源](data-sources.md)中的说明使用 Power Query 查看此实体的数据。

若要详细了解实体中引入的数据，可通过 **摘要** 列查看数据的某些重要特征，如空、缺少值、唯一值、计数和分发（如果适用于您的数据）。

选择图表图标查看数据的摘要。

> [!div class="mx-imgBorder"]
> ![摘要符号。](media/data-manager-entities-summary.png "数据摘要表")

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
- 如果存在 datetime/date/datetimeoffset 列，并且未遵循标准 ISO 格式，则需要在模型中指定它们的格式。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
