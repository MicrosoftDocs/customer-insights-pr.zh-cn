---
title: 实体和实体路径之间的关系
description: 创建和管理来自多个数据源的实体之间的关系。
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: db8822aa9e89afb9dc16428af6ca202de789ba1c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355694"
---
# <a name="relationships-between-entities"></a>实体之间的关系

当实体共享一个通用标识符（一个外键）时，关系会关联实体并定义您的数据图表。 此外键可从一个实体引用到另一个实体。 通过连接的实体，可基于多个数据源定义客户细分和度量。

有以下三种类型的关系： 
- 由系统在数据统一过程中创建的不可编辑的系统关系
- 通过引入数据源自动创建的不可编辑的继承关系 
- 由用户创建和配置的可编辑自定义关系

## <a name="non-editable-system-relationships"></a>不可编辑的系统关系

在数据统一过程中，基于智能匹配自动创建系统关系。 这些关系可以帮助将客户配置文件记录与相应记录关联。 下图说明了基于系统的三个关系的创建。 客户实体与其他实体匹配以生成统一的 *客户* 实体。

:::image type="content" source="media/relationships-entities-merge.png" alt-text="具有三个 1-n 关系的客户实体的关系路径图。":::

- 创建了 *客户* 实体与 *联系人* 实体之间的 ***CustomerToContact* 关系**。 *客户* 实体获取了键字段 **Contact_contactID**，以便关联到 *联系人* 实体键字段 **contactID**。
- 创建了 *客户* 实体与 *帐户* 实体之间的 ***CustomerToAccount* 关系**。 *客户* 实体获取了键字段 **Account_accountID**，以便关联到 *帐户* 实体键字段 **accountID**。
- 创建了 *客户* 实体与 *WebAccount* 实体之间的 ***CustomerToWebAccount* 关系**。 *客户* 实体获取了键字段 **WebAccount_webaccountID**，以便关联到 *WebAccount* 实体键字段 **webaccountID**。

## <a name="non-editable-inherited-relationships"></a>不可编辑的继承关系

在数据引入过程中，系统会检查现有关系的数据源。 如果没有关系，系统会自动创建它们。 这些关系也用于下游流程。

## <a name="create-a-custom-relationship"></a>创建自定义关系

关系包括包含外键的 *源实体* 和源实体的外键所指向的 *目标实体*。 

1. 在访问群体见解中，转到 **数据** > **关系**。

2. 选择 **新建关系**。

3. 在 **新建关系** 窗格中，提供以下信息：

   :::image type="content" source="media/relationship-add.png" alt-text="包含空输入字段的新关系侧窗格。":::

   - **关系名称**：反映关系目的的名称。 示例：CustomerToSupportCase。
   - **说明**：关系的说明。
   - **源实体**：在关系中用作来源的实体。 示例：SupportCase。
   - **目标实体**：在关系中用作目标的实体。 示例：客户。
   - **来源基数**：指定来源实体的基数。 基数描述了集中可能的元素的数量。 它始终与目标基数相关。 您可以在 **一个** 和 **多个** 之间做出选择。 仅支持多对一和一对一关系。  
     - 多对一：多个源记录可能与一个目标记录相关。 示例：单个客户的多个支持案例。
     - 一对一：单个源记录与一个目标记录相关。 示例：单个客户的一个忠诚度 ID。

     > [!NOTE]
     > 使用两个多对一关系和一个连接源实体和目标实体的链接实体，可以创建许多到多关系。

   - **目标基数**：选择目标实体记录的基数。 
   - **源键字段**：源实体中的外键字段。 示例：SupportCase 可以使用 CaseID 作为外键字段。
   - **目标键字段**：目标实体的键字段。 示例客户可以使用 **CustomerID** 键字段。

4. 选择 **保存** 以创建自定义关系。

## <a name="set-up-account-hierarchies"></a>设置客户层次结构

配置为使用企业客户作为主要目标访问群体的环境可以为相关企业客户配置客户层次结构。 例如，具有独立业务部门的公司。 

组织创建客户层次结构可以更好地管理客户及其相互之间的关系。 访问群体见解功能支持已存在于引入的客户数据中的父子客户层次结构。 例如，Dynamics 365 Sales 中的客户。 这些层次结构可以在访问群体见解中 **关系** 页面的客户层次结构选项卡下配置。

1. 转到 **数据** > **关系**。
1. 选择 **客户层次结构** 选项卡。
1. 选择 **新建客户层次结构**。 
1. 在 **客户层次结构** 窗格中，为层次结构提供名称。 系统会为输出实体创建名称。 您可以更改输出名称实体的名称。
1. 选择包含客户层次结构的实体。 它通常位于包含客户的同一实体中。
1. 从所选实体中选择 **客户 ID** 和 **客户父 ID** 
1. 选择 **保存** 应用设置并完成客户层次结构。

## <a name="view-relationships"></a>查看视图

“关系”页列出了已创建的所有关系。 每行都表示一种关系，其中还包括有关源实体、目标实体和基数的详细信息。 

:::image type="content" source="media/relationships-list.png" alt-text="关系页操作栏中的关系和选项列表。":::

此页面为现有和新关系提供了一组选项： 
- **新关系**：[创建自定义关系](#create-a-custom-relationship)。
- **可视化工具**：[探索关系可视化工具](#explore-the-relationship-visualizer)，查看现有关系及其基数的网络图表。
- **筛选依据**：选择列表中要显示的关系类型。
- **搜索关系**：对关系属性使用基于文本的搜索。

### <a name="explore-the-relationship-visualizer"></a>探索关系可视化工具

关系可视化工具会显示已连接实体及其基数之间的现有关系的网络图表。 它还可以可视化关系路径。

要自定义视图，您可以通过将框拖到画布上来更改框的位置。

:::image type="content" source="media/relationship-visualizer.png" alt-text="关系可视化工具网络图的屏幕截图，其中包括相关实体之间的连接。":::

可用选项： 
- **导出为图像**：将当前视图保存为图像文件。
- **更改为水平/垂直布局**：更改实体和关系的对齐。
- **编辑**：更新编辑窗格中自定义关系的属性并保存更改。

## <a name="relationship-paths"></a>关系路径

关系路径描述通过源实体和目标实体之间的关系连接的实体。 其使用场景为：要创建的客户细分或度量中包含的实体是非统一配置文件实体，并且可通过多个选项到达统一配置文件实体。 

关系路径通知系统通过哪些关系来访问统一配置文件实体。 不同的关系路径可能产生不同的结果。

例如，实体 *eCommerce_eCommercePurchases* 与统一配置文件 *Customer* 实体之间的关系如下：

- eCommerce_eCommercePurchases > Customer
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Customer
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Customer 

关系路径确定在为度量或客户细分创建规则时可以使用哪些实体。 如果选择关系路径最长的选项，产生的结果较少，因为匹配记录需要是所有实体的其中一部分。 在此示例中，一位客户必须已通过 e-commerce(eCommerce_eCommercePurchases) 在销售点 (POS_posPurchases) 购买了货物，并且参加了我们的忠诚度计划 (loyaltyScheme_loyCustomers)。 如果选择第一个选项，可能会获得更多结果，因为客户只需要存在于一个附加实体中。

### <a name="direct-relationship"></a>直接关系

当源实体与目标实体仅通过一种关系相关时，关系被归类为 **直接关系**。

例如，如果名为 *eCommerce_eCommercePurchases* 的活动实体仅通过 *ContactId* 连接到目标实体 *eCommerce_eCommerceContacts*，那么这是直接关系。

:::image type="content" source="media/direct_Relationship.png" alt-text="源实体直接连接到目标实体。":::

#### <a name="multi-path-relationship"></a>多路径关系

**多路径关系** 是一种特殊类型的直接关系，它将源实体连接到多个目标实体。

例如，如果名为 *eCommerce_eCommercePurchases* 的活动实体与 *eCommerce_eCommerceContacts* 和 *loyaltyScheme_loyCustomers* 这两个目标实体相关，那么这是一种多路径关系。

:::image type="content" source="media/multi-path_relationship.png" alt-text="源实体通过多跃点关系直接连接到多个目标实体。":::

### <a name="indirect-relationship"></a>间接关系

当源实体在与目标实体相关之前与一个或多个其他实体相关时，关系被归类为 **间接关系**。

#### <a name="multi-hop-relationship"></a>多跃点关系

*多跃点关系* 是一种 *间接关系*，它允许您通过一个或多个其他中间实体将源实体连接到目标实体。

例如，如果名为 *eCommerce_eCommercePurchasesWest* 的活动实体连接到名为 *eCommerce_eCommercePurchasesEast* 的中间实体，然后连接到名为 *eCommerce_eCommerceContacts* 的目标实体，则这是多跃点关系。

:::image type="content" source="media/multi-hop_relationship.png" alt-text="源实体通过中间实体直接连接到目标实体。":::

### <a name="multi-hop-multi-path-relationship"></a>多跃点、多路径关系

多跃点和多路径关系可一起用于创建 **多跃点、多路径关系**。 此特殊类型将合并 **多跃点** 和 **多路径关系** 功能。 它使您能够在使用中间实体时连接到多个目标实体。

例如，如果名为 *eCommerce_eCommercePurchasesWest* 的活动实体连接到名为 *eCommerce_eCommercePurchasesEast* 的中间实体，然后连接到 *eCommerce_eCommerceContacts* 和 *loyaltyScheme_loyCustomers* 这两个目标实体，则这是多跃点、多路径关系。

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="源实体直接连接到一个目标实体并通过中间实体连接到另一个目标实体。":::

## <a name="manage-existing-relationships"></a>管理现有关系 

在“关系”页上，每个关系都由行来表示。 

选择关系并选择以下选项之一： 
 
- **编辑**：更新编辑窗格中自定义关系的属性并保存更改。
- **删除**：删除自定义关系。
- **视图**：查看系统创建和继承的关系。 

## <a name="next-step"></a>下一步

系统和自定义关系用于基于不再孤立的多个数据源[创建客户细分](segments.md)和[度量](measures.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
