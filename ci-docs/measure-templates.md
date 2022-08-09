---
title: 通过模板创建度量
description: 使用常见用例的模板定义度量。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170762"
---
# <a name="create-measures-from-templates"></a>通过模板创建度量

使用常用[度量](measures.md)的预定义模板来创建常用度量。 模板建立在 *统一活动* 实体的映射数据的基础上。 因此，在从模板创建量度之前，请确保已配置[客户活动](activities.md)。

度量模板仅在 **个人客户** 环境中受支持。 要创建自定义度量或为企业对企业创建度量，请参阅[使用度量生成器](measure-builder.md)。

可用的度量模板：
- 平均交易值(ATV)
- 总交易值
- 平均每日收入
- 平均每月收入
- 平均每年收入
- 交易计数
- 获得的忠诚度分数
- 兑现的忠诚度分数
- 忠诚度分数余额
- 可用的客户生存期跨度
- 忠诚度成员资格持续时间
- 自最后一次购买以来的时间

## <a name="build-a-new-measure-using-a-template"></a>使用模板生成新度量

1. 转到 **度量**。

1. 选择 **新建**，然后选择 **选择模板**。

   :::image type="content" source="media/measure-use-template.png" alt-text="在创建新度量并在模板上突出显示时的下拉菜单的屏幕截图。":::

1. 查找适合您的需求的模板并选择 **选择模板**。

1. 查看所需数据，如果所有数据都到位，请选择 **开始**。

1. 选择“度量名称”旁边的 **编辑详细信息**。 为度量提供名称。 或者，也可以向度量添加[标记](work-with-tags-columns.md#manage-tags)。

   :::image type="content" source="media/measures_edit_details.png" alt-text="“编辑详细信息”对话框。":::

1. 选择 **完成**。

1. 在 **设置时间段** 部分中，定义数据的期限。 选择是希望新度量通过选择 **所有时间** 覆盖整个数据集，还是希望该度量重点关注 **特定时间段**。

   :::image type="content" source="media/measure-set-time-period.png" alt-text="从模板中配置量度时显示时间段部分的屏幕截图。":::

1. 在下一节中，选择 **添加数据** 来选择活动，并从 *统一活动* 实体中映射相应的数据。

    1. 第 1 步，共 2 步：在 **活动类型** 下，选择要使用的实体类型。 对于 **活动**，选择要映射的实体，然后选择 **下一步**。
    1. 第 2 步，共 2 步：针对公式所要求的组件从 *统一活动* 实体中选择属性。 例如，对于平均交易价值，它是代表交易值的属性。 对于 **活动时间戳**，请从表示活动日期和时间的 *统一活动* 实体中选择属性。
    1. 选择 **保存**。

    数据映射成功后，状态显示 **完成**，映射活动和属性的名称将显示。

1. 选择 **运行** 来计算度量结果。 如果希望保留当前配置并且稍后运行该度量，请选择 **保存草稿**。 **度量** 页将显示。

## <a name="next-step"></a>下一步

使用现有度量创建[客户细分](segments.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
