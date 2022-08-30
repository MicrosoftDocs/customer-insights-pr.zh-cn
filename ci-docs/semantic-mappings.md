---
title: 语义映射(预览版)
description: 语义映射概述以及如何使用它们。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303865"
---
# <a name="semantic-mappings-preview"></a>语义映射(预览版)

> [!NOTE]
> **语义映射** 页面只能用于已使用此页面创建联系人配置文件的企业环境（企业对企业）。 您可以使用 **语义映射** 页面继续创建和管理各个联系人配置文件。 或者，[统一您的联系人数据](data-unification-contacts.md)，删除重复项、识别实体间的匹配项并创建一个统一的联系人配置文件。 然后，您可以使用统一的联系人配置文件来创建联系人级别的活动。

语义映射使您可以将非活动数据映射到预定义架构。 这些架构可帮助 Customer Insights 更好地了解您的数据属性。 语义映射和提供的数据在 Customer Insights 中实现了新的见解和特征。 要将您的活动数据映射到架构，请查看[活动](activities.md)文档。

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
