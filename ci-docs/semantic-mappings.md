---
title: 语义映射(预览版)
description: 语义映射概述以及如何使用它们。
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183620"
---
# <a name="semantic-mappings-preview"></a>语义映射(预览版)

语义映射使您可以将非活动数据映射到预定义架构。 这些架构可帮助 Customer Insights 更好地了解您的数据属性。 语义映射和提供的数据在 Customer Insights 中实现了新的见解和特征。 要将您的活动数据映射到架构，请查看[活动](activities.md)文档。

**当前已为基于企业客户的环境启用语义映射**。 *ContactProfile* 是目前 Customer Insights 中唯一可用的语义映射类型。

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>定义 ContactProfile 语义实体映射

1. 转到 **数据** > **语义映射（预览版）**。

1. 选择 **添加语义映射** 启动引导式体验。

1. 在 **实体数据** 步骤中，为以下字段设置值：

   - **语义实体映射名称**：语义实体映射的名称。
   - **源实体**：包含联系人数据的实体。
   - **主键**：唯一标识联系人记录的字段。 其中不应包含任何重复值、空值或缺少值。

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="使用名称、源实体和主键设置语义实体映射。":::

1. 选择 **下一步**。

1. 在 **关系** 步骤中，配置详细信息以将您的联系人数据连接到其相应的客户数据。 此步骤显示实体之间的连接。  

   可以实现两种类型的关系路径：**直接关系** 和 **间接关系**。 有关详细信息，请转到[直接和间接关系路径](relationships.md#relationship-paths)。

   1. 选择 **添加关系** 配置关系。
   1. 从您的源实体中选择将您的联系人实体连接到另一个实体的属性。
   1. 选择要将联系人实体连接到的实体。 从 **客户实体** 或 **中间实体** 部分选择实体。 如果选择中间实体，定义第二个关系以连接到目标客户实体。

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="选择客户实体或中间实体。":::

   1. 提供 **关系名称**。 如果实体之间的关系已存在，关系名称为只读。 如果不存在关系，将使用您提供的名称创建新关系。
   1. 选择 **应用** 完成关系配置。

   > [!NOTE]
   > 您可以使用中间实体配置联系人实体和其他客户实体之间的更多关系。
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="各个关系将联系人实体连接到客户实体的可视化。":::

1. 选择 **下一步**。

1. 在 **设置语义类型** 步骤中，选择 **语义类型**。 目前，有一个称为 *ContactProfile* 的 **语义类型**。

1. 将您的联系人 ID 映射到 *ContactProfile* 语义类型 **联系人 ID**。 （可选）映射其他字段，如名、姓、性别或电子邮件。

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="将您的联系人数据属性映射到提供的必填和可选字段。":::

1. 选择 **下一步**。

1. 在 **检查** 步骤中，查看语义映射的配置。 要进行更改，选择相应部分对应的 **编辑**。

1. 选择 **保存**。

1. 要处理语义映射，选择 **运行**。 或选择 **关闭** 保存您的语义映射而不进行处理。 要以后运行，选择语义映射并选择 **刷新**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>管理现有语义映射

转到 **数据** > **语义映射（预览）** 查看您保存的语义映射、它们的源实体、语义类型、映射类型和状态。

:::image type="content" source="media/semantic-mapping-options.png" alt-text="管理语义映射的选项。":::

选择语义映射可查看可用操作。
- **编辑** 当前配置。 选择 **保存** 和 **运行** 以处理更改。
- **刷新** 语义映射以包括最新数据。 更新任何给定的语义映射将更新所有相同类型的语义映射。
- **重命名** 语义映射。 选择 **保存**。
- **删除** 语义映射。 要一次删除多个语义映射，选择语义映射和删除图标。 选择 **删除** 以确认删除。

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>使用 ContactProfile 语义实体映射创建联系人级别的活动

创建 *ContactProfile* 语义实体映射后，可以捕获联系人的活动。 它使您能够在活动时间线中查看由联系人负责每个活动的客户。 大多数步骤都采用典型活动映射配置。

   > [!NOTE]
   > 若要使联系人级别的活动正常工作，活动数据中每个记录都必须具有 **AccountID** 和 **ContactID** 属性。

1. [定义 *ContactProfile* 语义实体映射](#define-a-contactprofile-semantic-entity-mapping)并运行语义映射。

1. 转到 **数据** > **活动**。

1. 选择 **添加活动** 以创建新活动。

1. 命名活动，选择源活动实体，并选择活动实体的主键。

1. 在 **关系** 步骤中，使用您的联系人数据作为中间实体，在您的活动源数据与客户之间创建间接关系。 有关详细信息，请参阅[直接和间接关系路径](relationships.md#relationship-paths)。
   - 名为 *购买* 的活动的示例关系：
      - 属性 **ContactID** 上的 **采购来源活动数据** > **联系人数据**
      - 属性 **AccountID** 上的 **联系人属性** > **客户数据**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="所建立关系示例。":::

1. 建立关系后，选择 **下一步** 并完成您的活动映射配置。 有关创建活动的详细步骤，请参阅[定义活动](activities.md)。

1. 运行活动映射。

1. 联系人级的活动映射运行后，选择 **客户**。 联系人级的活动在客户时间线上显示。

   :::image type="content" source="media/Contact_Activities2.png" alt-text="配置联系人活动后的最终结果":::

### <a name="contact-level-activity-timeline-filtering"></a>联系人级别的活动时间线筛选

客户的活动时间线包括他们所执行活动的 ID 或名称，具体取决于您的 *ContactProfile* 配置。 按时间线中的联系人筛选活动，以查看您感兴趣的特定联系人。 要查看未分配给特定联系人的所有活动，选择 **未映射到联系人的活动**。

:::image type="content" source="media/Contact_Activities3.png" alt-text="适用于联系人级别的活动的筛选选项。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
