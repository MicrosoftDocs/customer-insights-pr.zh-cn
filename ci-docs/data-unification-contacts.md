---
title: 创建统一的联系人配置文件（预览）
description: 完成数据统一过程来创建单个联系人主数据集。
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305007"
---
# <a name="create-a-unified-contact-profile-preview"></a>创建统一的联系人配置文件（预览）

[统一企业客户](map-entities.md)后，您可以选择统一这些客户的联系人并将统一的联系人链接到统一客户。 联系人统一过程映射来自多个数据源的联系人数据、删除重复项、跨实体匹配数据、设置语义映射、在联系人和客户之间创建关系，然后创建统一的联系人配置文件。

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

前几个步骤与统一客户步骤相同。

## <a name="prerequisites"></a>先决条件

客户和联系人记录必须具有连接它们的唯一键（称为外键）。 例如，存在于将客户和联系人关联在一起的客户记录和联系人记录中的客户 ID。

## <a name="preview-limitations"></a>预览限制

- 没有客户链接的联系人将被删除。
- 如果对某客户进行了重复数据删除，将根据合并首选项识别赢单者记录。 丢单者记录未被选择，因此被删除。 与丢单记录关联的联系人将被删除。
- 一个客户可以有多个联系人，但一个联系人将链接到一个客户。
- 在语义映射步骤中映射的联系人属性是唯一可以显示在客户卡上的属性。 但是，有 17 个属性。

## <a name="select-source-fields"></a>选择源字段

1. 在 **统一联系人（预览）** 下，选择 **开始**。

1. 为您的联系人数据源[选择实体和字段](map-entities.md)，包括主键和属性类型。

1. 选择 **下一步**。

## <a name="remove-duplicate-records"></a>删除重复记录

1. 或者，为您选择的实体[定义重复数据删除规则](remove-duplicates.md)。

1. 选择 **下一步**。

## <a name="match-conditions"></a>匹配条件

1. 为跨实体匹配[定义匹配顺序和规则](match-entities.md)。

1. 选择 **下一步**。

## <a name="unify-contact-fields"></a>统一联系人字段

1. [合并和排除联系人字段](merge-entities.md)。

1. 选择 **下一步**。

## <a name="define-the-semantic-fields-for-unified-contacts"></a>定义统一联系人的语义字段

统一过程中的此步骤将您的统一联系人字段映射到语义类型。 在企业对企业中，客户卡显示客户。 选择卡后，将显示与该客户关联的所有联系人。 您在此步骤中映射的字段是将显示在卡上的字段。

1. 选择映射到每个统一字段的语义类型。 如果语义类型不可用，选择 **无**。

   :::image type="content" source="media/semantic_mapping.png" alt-text="定义语义类型的语义字段页面的屏幕截图。" lightbox="media/semantic_mapping.png":::

1. 映射所有统一字段后，选择 **下一步**。

## <a name="set-the-relationship-between-contacts-and-accounts"></a>设置联系人与客户之间的关系

统一过程中的此步骤将您的联系人数据连接到其相应的客户数据。

1. 对于每个实体，输入以下信息：

   - **联系人实体中的外键**：选择将您的联系人实体连接到客户的属性。
   - **目标客户实体**：选择与联系人关联的客户实体。

   :::image type="content" source="media/contact_relationship.png" alt-text="连接联系人和客户实体的关系页面的屏幕截图。":::

1. 选择 **下一步**。

## <a name="review-contact-unification"></a>查看联系人统一

查看更改摘要、创建统一配置文件并查看结果。

### <a name="review-and-create-contact-profiles"></a>查看和创建联系人配置文件

统一过程中的最后一步显示该过程中的步骤的摘要，并提供了一个在创建统一联系人配置文件之前进行更改的机会。

:::image type="content" source="media/b2b_review_contacts.png" alt-text="“查看和创建联系人配置文件”的屏幕截图。":::

1. 在任何联系人统一步骤中选择 **编辑** 查看并进行任何更改。

1. 如果您对选择感到满意，请选择 **创建联系人配置文件**。 在创建统一的联系人配置文件时，将显示 **统一** 页面。
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="包含显示“已排队”或“正在刷新”的磁贴的统一联系人页面的屏幕截图。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

统一算法需要一些时间才能完成，并且在完成之前您无法更改配置。

### <a name="view-the-results-of-contact-unification"></a>查看联系人统一的结果

统一完成后，**数据** > **统一** 页将显示统一的联系人配置文件的数量。 统一过程中每个步骤的结果都显示在每个磁贴上。 例如，**源字段** 显示已映射属性（字段）的数量，而 **重复记录** 显示找到的重复记录数。

:::image type="content" source="media/unified_contacts.png" alt-text="联系人统一后的“数据统一”页面的屏幕截图。":::

> [!TIP]
> 仅在选择多个实体时才会显示 **匹配条件** 磁贴。

我们建议您查看结果，尤其是[匹配规则](data-unification-update.md#manage-match-rules)的质量，并在必要时对其进行改进。

如果需要，[更改联系人统一设置](data-unification-update.md)，然后重新运行统一配置文件。

### <a name="verify-output-entities-from-data-unification"></a>验证数据统一的输出实体

转到 **数据** > **实体** 验证输出实体。

称为 *ContactProfile* 的统一联系人配置文件实体显示在 **语义实体** 部分。 第一次成功运行统一时，会创建统一的 *ContactProfile* 实体。 所有后续运行均会展开该实体。

*ContactsCustomer* 实体（预览）已创建并显示在 **配置文件** 部分。 此实体包含联系人数据，没有指向客户的链接。 此实体用作联系人统一的语义映射和关系步骤的输入。

重复数据删除和合并实体将创建并显示在 **系统** 部分。 将为每个源实体创建一个已删除重复项的实体，名称为 **Deduplication_DataSource_Entity**。 **ContactsConflationMatchPairs** 实体包含有关跨实体匹配的信息。

删除重复输出实体包含以下信息：
- ID/键
  - 主键和备用 ID 字段。 备用 ID 字段由为记录标识的所有备用 ID 组成。
  - Deduplication_GroupId 字段显示在实体中标识的组或群集，该组或群集根据指定的删除重复字段将所有相似记录归组。 它用于系统处理目的。 如果没有指定手动删除重复规则并且系统定义的删除重复规则适用，则您可能在重复删除输出实体中找不到此字段。
  - Deduplication_WinnerId：此字段包含标识的组或群集中的获胜者 ID。 如果 Deduplication_WinnerId 与记录的主键值相同，则这意味着该记录是入选记录。
- 用于定义删除重复规则的字段。
- “规则”和“分数”字段，分别用于表示所应用的删除重复规则以及匹配算法返回的分数。

## <a name="next-step"></a>下一步

配置[活动](activities.md)、[扩充](enrichment-hub.md)或[关系](relationships.md)，以便加深对联系人的了解。
