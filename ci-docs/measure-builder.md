---
title: 使用度量生成器创建度量
description: 从头开始生成度量以分析有关业务的关键指标。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170838"
---
# <a name="create-measures-with-measure-builder"></a>使用度量生成器创建度量

度量生成器允许您使用算术运算符、聚合函数和筛选器定义计算。 使用与统一 *客户* 实体相关的实体中的属性定义度量。

在企业对客户和企业对企业环境中创建度量采用同样的方法。 但是，如果您的企业对企业环境[使用具有层次结构的客户](relationships.md#set-up-account-hierarchies)，选择是否跨相关子客户聚合度量。

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

在个人客户级别（客户属性、客户度量）或企业/组织级别（业务度量）创建度量。 客户属性和客户度量使您能够跟踪每个客户的绩效。 例如，每个客户所花费的总时间。 业务度量跟踪每个企业的绩效。 例如，公司的总收入。

- 客户属性：生成输出作为新属性，该属性在名为 *Customer_Measure* 的系统生成实体中另存为新列。 刷新客户属性时，会同时刷新此 *Customer_Measure* 实体中的所有其他客户属性。 此外，客户属性显示在客户配置文件卡中。 一旦运行或保存，就无法将客户属性更改为客户度量。

- 客户度量：生成输出作为其自己的实体，并且一旦运行或保存，就不能将输出更改为客户属性。 客户度量不会显示在客户配置文件卡中。

- 业务度量：生成输出作为其自己的实体，并显示在 Customer Insights 环境的主页上。

1. 转到 **度量**。

1. 选择 **新建** > **创建自己的内容**。

   :::image type="content" source="media/measure-b2c.png" alt-text="企业对客户度量的空配置屏幕。" lightbox="media/measure-b2c.png":::

1. 选择“无标题的度量”旁边的 **编辑详细信息**。 为度量提供名称。 或者，也可以向度量添加[标记](work-with-tags-columns.md#manage-tags)。

   :::image type="content" source="media/measures_edit_details.png" alt-text="“编辑详细信息”对话框。":::

1. 选择 **完成**。

1. 要跟踪业务级别的绩效，请将 **度量类型** 切换为 **业务级别**。 默认情况下选中了 **客户级别**。 **客户级别** 会将 *CustomerId* 属性自动添加到维度，而 **业务级别** 则会自动删除它。

1. 在配置区域中，从 **选择函数** 下拉菜单中选择聚合函数。 聚合函数包括：
   - **Sum**
   - **平均值**
   - **计数**
   - **唯一计数**
   - **最大值**
   - **Min**
   - **第一个**：采用数据记录的第一个值
   - **最后一个**：采用添加到数据记录的最后一个值
   - **ArgMax**：从目标函数中查找给出最大值的数据记录
   - **ArgMin**：从目标函数中查找给出最小值的数据记录

1. 选择 **添加属性** 以选择数据创建此度量。

   1. 选择 **属性** 选项卡。
   1. 数据实体：选择包括要度量的属性的实体。
   1. 数据属性：选择要在聚合函数中用于计算度量的属性。 一次只能选择一个属性。
   1. （可选）选择 **度量** 选项卡从现有度量中选择数据属性，或搜索实体或度量名称。
   1. 选择 **添加**。

1. 若要生成更复杂的度量，添加更多属性或在度量函数中使用数学运算符。

1. 若要添加筛选器，请在配置区域中选择 **筛选器**。 如果应用筛选器，则将只使用与筛选器匹配的记录来计算度量。
  
   1. 在 **筛选器** 窗格的 **添加属性** 部分中，选择要用于创建筛选器的属性。
   1. 设置筛选器运算符，以为每个所选属性定义筛选器。
   1. 选择 **应用**。

1. 选择 **维度** 以选择作为列添加到度量输出实体中的更多字段。

   1. 选择 **编辑维度** 以添加要作为度量值分组依据的数据属性。 例如，市/县或性别。
      > [!TIP]
      > 如果选择了 **客户级别** 作为 **度量类型**，则已经添加了 *CustomerId* 属性。 如果删除属性，则 **度量类型** 会切换至 **业务级别**。
   1. 选择 **完成**。

1. 如果必须用整数替换数据中的值，选择 **规则**。 配置规则并确保您只选择整数作为替换值。 例如，将 *null* 替换为 *0*。

1. 如果所映射的数据实体与 *客户* 实体之间有多个路径，选择其中一个标识的[实体关系路径](relationships.md)。 根据所选路径的不同，度量结果可能有所不同。

   1. 选择 **关系路径**，然后选择应用于识别度量值的实体路径。 如果只有一个指向 *客户* 实体的路径，则不会显示此控件。
   1. 选择 **完成**。

1. 若要为度量添加更多计算，请选择 **新建计算**。 应只在同一实体路径上使用实体进行新计算。 更多计算将在度量输出实体中显示为新列。 （可选）选择 **编辑名称** 为计算创建名称。

1. 选择计算上的竖省略号 (&vellip;) **复制** 或 **删除** 度量中的计算。

1. 在 **预览** 区域中，您将看到度量输出实体的数据架构，包括筛选器和维度。 预览会动态响应配置中的更改。

1. 选择 **运行** 以计算已配置度量的结果。 如果希望保留当前配置并且稍后运行该度量，请选择 **保存并关闭**。 **度量** 页将显示。

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

在个人客户级别（客户度量）或全部客户级别（业务度量）创建度量。

- 客户度量：生成输出作为其自己的实体。 客户度量不会显示在客户配置文件卡中。

- 业务度量：生成输出作为其自己的实体，并显示在 Customer Insights 环境的主页上。

1. 转到 **度量**。

1. 选择 **新建**。

   :::image type="content" source="media/measure-b2b.png" alt-text="企业对企业度量的空配置屏幕。":::

1. 选择“无标题的度量”旁边的 **编辑详细信息**。 为度量提供名称。 或者，也可以向度量添加[标记](work-with-tags-columns.md#manage-tags)。 
   :::image type="content" source="media/measures_edit_details.png" alt-text="“编辑详细信息”对话框。":::

1. 选择 **完成**。

1. 在配置区域中，从 **选择函数** 下拉菜单中选择聚合函数。 聚合函数包括：
   - **Sum**
   - **平均值**
   - **计数**
   - **唯一计数**
   - **最大值**
   - **Min**
   - **第一个**：采用数据记录的第一个值
   - **最后一个**：采用添加到数据记录的最后一个值

1. 选择 **添加属性** 以选择数据创建此度量。

   1. 选择 **属性** 选项卡。
   1. 数据实体：选择包括要度量的属性的实体。
   1. 数据属性：选择要在聚合函数中用于计算度量的属性。 一次只能选择一个属性。
   1. （可选）选择 **度量** 选项卡从现有度量中选择数据属性，或搜索实体或度量名称。
   1. 选择 **添加** 以将所选属性添加到度量中。

1. 若要生成更复杂的度量，添加更多属性或在度量函数中使用数学运算符。

1. 若要添加筛选器，请在配置区域中选择 **筛选器**。 如果应用筛选器，则将只使用与筛选器匹配的记录来计算度量。
  
   1. 在 **筛选器** 窗格的 **添加属性** 部分中，选择要用于创建筛选器的属性。
   1. 设置筛选器运算符，以为每个所选属性定义筛选器。
   1. 选择 **应用** 以将筛选器添加到度量中。

1. 选择 **维度** 以选择作为列添加到度量输出实体中的更多字段。

   1. 选择 **编辑维度** 以添加要作为度量值分组依据的数据属性。 例如，市/县或性别。
      > [!TIP]
      > *CustomerId* 属性已添加，指示这是客户级度量类型。 如果删除属性，度量类型将变为业务级别。
   1. 选择 **完成** 以将维度添加到度量中。

1. 如果必须用整数替换数据中的值，选择 **规则**。 配置规则并确保您只选择整数作为替换值。 例如，将 *null* 替换为 *0*。

1. 如果您 **使用具有层次结构的客户**，请查看[汇总子客户](relationships.md#set-up-account-hierarchies)。
   - 如果此切换设置为 **关**，将为每个客户计算度量值。 每个客户将获得自己的结果。
   - 如果设置为 **开**，选择 **编辑** 来根据引入的层次结构选择客户层次结构。 此度量将只生成一个结果，因为它将与子客户聚合。

1. 如果所映射的数据实体与 *客户* 实体之间有多个路径，选择其中一个标识的[实体关系路径](relationships.md)。 根据所选路径的不同，度量结果可能有所不同。

   1. 选择 **关系路径**，然后选择应用于识别度量值的实体路径。 如果只有一个指向 *客户* 实体的路径，则不会显示此控件。
   1. 选择 **完成** 以应用您的选择。

1. 选择计算上的竖省略号 (&vellip;) **复制** 或 **删除** 度量中的计算。

1. 在 **预览** 区域中，您将看到度量输出实体的数据架构，包括筛选器和维度。 预览会动态响应配置中的更改。

1. 选择 **运行** 以计算已配置度量的结果。 如果希望保留当前配置并且稍后运行该度量，请选择 **保存并关闭**。 **度量** 页将显示。

---

## <a name="next-step"></a>下一步

使用现有度量创建[客户细分](segments.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]