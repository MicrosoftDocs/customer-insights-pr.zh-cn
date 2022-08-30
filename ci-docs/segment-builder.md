---
title: 使用客户细分生成器创建复杂客户细分
description: 使用客户细分生成器通过根据各种属性对客户进行分组来创建复杂的客户细分。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304738"
---
# <a name="create-complex-segments-with-segment-builder"></a>使用客户细分生成器创建复杂客户细分

围绕着统一客户或统一联系人及其相关实体定义复杂筛选器。 每个客户细分在处理后都将创建一组客户或联系人记录，您可以导出和处理这组记录。

> [!TIP]
> 基于 **个人客户** 的客户细分自动包含客户细分成员的可用联系信息。 在 **企业客户** 中，如果您[统一](data-unification.md)客户和联系人，请选择客户细分是基于客户还是基于企业联系人。 要导出到需要联系人信息的目标，请使用联系人客户细分。 要导出到需要客户信息的目标，请使用客户的客户细分。

## <a name="segment-builder"></a>客户细分生成器

下图演示客户细分生成器的各个方面。 其中显示的一个客户细分将生成一组客户。 客户在特定期限内订购商品并获得奖励积分或花费一定金额。

:::image type="content" source="media/segment-builder-overview.png" alt-text="客户细分生成器的元素。" lightbox="media/segment-builder-overview.png":::

1. 使用规则和子规则组织您的客户细分。 每个规则或子规则都由条件构成。 使用逻辑运算符组合条件。

1. 选择应用于规则的实体之间的[关系路径](relationships.md)。 关系路径决定条件中可使用哪些属性。

1. 管理规则和子规则。 更改规则的位置或删除规则。

1. 使用子规则添加条件和创建适当的嵌套级别。

1. 为相连规则应用集运算。

1. 使用属性窗格添加可用实体属性或基于属性创建条件。 此窗格根据所选关系路径显示所选规则的可用实体和属性的列表。

1. 基于属性向现有规则和子规则添加条件，或向新规则添加条件。

1. 创建客户细分时撤消和恢复更改。

上面的示例显示客户细分功能。 我们为在线上至少购买了 500 美元商品 *并且* 对软件开发有兴趣的客户定义了一个客户细分。

## <a name="create-a-new-segment-with-segment-builder"></a>使用客户细分生成器创建新客户细分

1. 转到 **客户细分**。

1. 选择 **新建** > **创建自己的内容**。 在客户细分生成器页上，您可以定义或编写规则。 规则由定义一组客户的一个或多个条件组成。

   > [!NOTE]
   > 对于基于企业客户的环境，请根据您要创建的客户细分类型选择 **新建** > **客户的客户细分** 或 **联系人的客户细分（预览）**。 如果已定义 [客户层次结构](relationships.md#set-up-account-hierarchies)，并且您想要创建规则来根据父子关系筛选数据，选择 **使用层次结构?(预览)**，选择层次结构，然后 **应用**。
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="客户细分选择客户层次结构窗格。":::

1. 选择“无标题的客户细分”旁边的 **编辑详细信息**。 为客户细分提供名称，然后更新为客户细分建议的 **输出实体名称**。 （可选）向客户细分中添加说明和[标记](work-with-tags-columns.md#manage-tags)。

   :::image type="content" source="media/segments_edit_details.png" alt-text="“编辑详细信息”对话框。":::

1. 在 **规则 1** 部分，选择筛选客户所要依据的实体的属性。 可通过两种方法选择属性。
   - 在 **添加到规则** 窗格中查看可用实体和属性的列表，然后选择要添加的属性旁边的 **+** 图标。 选择要将属性添加到现有规则中，还是将其用于创建新规则。
   - 在规则部分中键入属性的名称，以查看匹配的建议。

1. 选择运算符以指定条件的匹配值。 属性可以具有四种数据类型之一作为值：数值、字符串、日期或布尔值。 根据属性的数据类型，可以使用不同的运算符来指定条件。

1. 选择 **添加添加** 向规则添加更多条件。 若要在当前规则下创建规则，请选择 **添加子规则**。

1. 如果规则使用 *Customer* 实体（或企业对企业的 *ContactProfile* 实体）以外的其他实体，选择 **设置关系路径** 将所选实体映射到统一的客户实体。 如果仅有一个可能的关系路径，系统将自动选择该关系路径。 不同的[关系路径](relationships.md#relationship-paths)可能产生不同的结果。 每个规则都可以有自己的关系路径。

   :::image type="content" source="media/relationship-path.png" alt-text="根据映射到统一客户实体的实体创建规则时的潜在关系路径。":::

1. 如果一个规则中包含多个条件，选择连接这些条件的逻辑运算符。  
   - **AND** 运算符：必须满足所有条件才能在客户细分中包含记录。 如果要为不同实体定义条件，使用此选项。
   - **OR** 运算符：必须满足其中一个条件才能在客户细分中包含记录。 如果要为同一个实体定义多个条件，使用此选项。

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="包含两个 AND 条件的规则。":::

   如果使用 OR 运算符，则所有条件必须基于关系路径中包含的实体。

1. 要创建不同的客户记录集，请创建多个规则。 要包括业务案例所需的客户，合并组。 具体来说，如果由于指定的关系路径的缘故而无法在规则中包含实体，则创建新规则以从中选择属性。

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="向客户细分添加新规则，然后选择 set 运算符。":::

   1. 选择 **添加规则**。
   1. 选择一个设置的运算符：**并集**、**交集** 或 **排除**。

      - **联合** 用于联合两个组。
      - **相交** 用于重叠两个组。 只有这两个组所 *共有* 的数据才会保留在统一组中。
      - **除外** 用于合并两个组。 只保留组 A 中有但在组 B 中 *不常见* 的数据。

1. 默认情况下，输出实体会自动包含与所定义筛选器匹配的客户配置文件的所有属性。 在企业对企业中，使用 *ContactProfile* 实体时，会自动包含客户 ID。 如果客户细分基于 *Customer* 实体以外的其他实体或要包含 *ContactProfile* 中的更多属性，选择 **项目属性** 将这些实体的更多属性添加到输出实体。
 
   例如：客户细分基于包含与 *Customer* 实体相关的购买数据的实体。 此客户细分查找今年购买了商品的所有西班牙客户。 可以选择向输出实体中的所有匹配的客户记录追加商品价格或购买日期之类属性。 若要分析季节与总支出之间的关系，此信息可能非常有用。

   :::image type="content" source="media/segments-project-attributes.png" alt-text="侧窗格中选择了要添加到输出实体的预测属性的示例。":::
 
   基于具有预计联系人属性的业务客户的客户细分示例输出如下所示：

   |ID  |客户名称  |收入  |联系人姓名  | 联系人角色|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100K | [Abbie Moss、Ruth Soto]  | [CEO、采购经理]

   > [!NOTE]
   > - **项目属性** 仅适用于与 *Customer* 或 *ContactProfile* 实体具有一对多关系的实体。 例如，一个客户可以具有多个订阅。
   > - 如果您要投射的属性与关系定义的 *Customer* 或 *ContactProfile* 实体相距不止一个跃点，则应在您正在构建的客户细分查询的每个规则中使用该属性。
   > - 如果您要投射的属性距离 *Customer* 或 *ContactProfile* 实体仅一个跃点，该属性则不需要出现在您正在构建的客户细分查询的每个规则中。
   > - 在使用设置的运算符时，会将 **预测属性** 考虑在内。

1. 选择 **运行** 创建客户细分。 如果希望保留当前配置并且稍后运行客户细分，选择 **保存**。 **客户细分** 页将显示。

### <a name="segment-builder-tips"></a>客户细分生成器提示

使用客户细分生成器创建客户细分时，请记住以下提示：

- 在为条件设置运算符时，客户细分生成器不会建议实体中的有效值。 您可以转到 **数据** > **实体**，然后下载实体数据以查看哪些值可用。
- 基于日期的条件让您可以在固定日期与浮动日期范围之间切换。
- 如果您的客户细分有多个规则，您正在编辑的规则旁边会显示一条垂直的蓝线。
- 可以将规则和条件移动到客户细分定义中的其他位置。 选择规则或条件旁边的竖省略号 (&vellip;)，并选择其移动方法和位置。
- 命令栏中的 **撤消** 和 **恢复** 控件可让您回滚更改。
- 创建客户细分后，某些客户细分允许您[跟踪客户细分的使用情况](segments.md#track-usage-of-a-segment)。

## <a name="next-steps"></a>后续步骤

[导出客户细分](export-destinations.md)和浏览 [Customer Card 集成](customer-card-add-in.md)，以便在其他应用程序中使用客户细分。

[!INCLUDE [footer-include](includes/footer-banner.md)]
