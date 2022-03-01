---
title: 语义映射（预览）
description: 语义映射概述以及如何使用它们。
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622924"
---
# <a name="semantic-mappings"></a>语义映射

语义映射使您可以将非活动数据映射到预定义架构。 这些架构可帮助访问群体见解更好地了解您的数据属性。 语义映射和提供的数据在访问群体见解中实现了新的见解和特征。 要将您的活动数据映射到架构，请查看[活动](activities.md)文档。

**当前已为基于企业客户的环境启用语义映射**。 *ContactProfile* 是目前访问群体见解中唯一可用的语义映射类型。

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>定义 ContactProfile 语义实体映射

1. 在访问群体见解中，转到 **数据** > **语义映射(预览)**。

1. 选择 **添加语义映射** 启动引导式体验。

1. 在 **实体数据** 步骤中，为以下字段设置值：

   - **语义实体映射名称**：为语义实体映射提供名称。
   - **源实体**：选择包含联系人数据的实体。
   - **主键**：选择唯一标识联系人记录的字段。 其中不应包含任何重复值、空值或缺少值。

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="使用名称、源实体和主键设置语义实体映射。":::

1. 选择 **下一步** 继续操作。

1. 在 **关系** 步骤中，配置详细信息以将您的联系人数据连接到其相应的客户数据。 此步骤显示实体之间的连接。  

   可以实现两种类型的关系路径：**直接关系** 和 **间接关系**。 有关详细信息，请转到[直接和间接关系路径](relationships.md#relationship-paths)。

   1. 选择 **添加关系** 配置关系。
   1. 从您的源实体中选择将您的联系人实体连接到另一个实体的属性。
   1. 选择要将联系人实体连接到的实体。 您可以从 **客户实体** 或 **中间实体** 部分选择实体。 如果选择中间实体，您需要定义第二个关系以连接到目标客户实体。

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="选择客户实体或中间实体。":::

   1. 提供 **关系名称**。 如果实体之间的关系已存在，关系名称为只读。 如果不存在关系，将使用您提供的名称创建新关系。
   1. 选择 **应用** 完成关系配置。

   > [!NOTE]
   > 您可以使用中间实体配置联系人实体和其他客户实体之间的更多关系。
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="各个关系将联系人实体连接到客户实体的可视化。":::

1. 完成关系配置后，选择 **下一步**。

1. 在 **设置语义类型** 步骤中，选择 **语义类型**。 目前，有一个称为 *ContactProfile* 的 **语义类型**。

1. 将您的数据映射到所显示字段的 *ContactProfile* **语义类型**。
   - 必填字段：联系人 ID
   - 可选字段：名、姓、出生日期、性别、主要电子邮件和主要电话

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="将您的联系人数据属性映射到提供的必填和可选字段。":::

1. 选择 **下一步** 继续操作。

1. 在 **检查** 步骤中，查看语义映射的配置。 选择相应部分对应的 **编辑** 进行更改。

1. 选择 **保存** 保存新的 **语义映射**。

1. 保存后，您可以选择 **运行** 处理语义映射，或者可以选择 **关闭** 保存语义映射，不进行处理。

1. 要稍后运行语义映射，选择语义映射并选择 **刷新**。

> [!TIP]
> 对于任务/流程，有[六种类型的状态](system.md#status-types)。 此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。 可以选择流程状态以查看有关整个作业的进度的详细信息。 在选择一个作业任务的 **查看详细信息** 后，您会发现其他信息：处理时间、上次处理日期以及与该任务相关的所有错误和警告。

## <a name="manage-existing-semantic-mappings"></a>管理现有语义映射

在 **数据** > **语义映射(预览)** 上，您可以查看所有保存的语义映射，并对其进行管理。 每个语义映射由单独一行表示。 您将找到有关源实体、语义类型、映射类型及其状态的详细信息。

:::image type="content" source="media/semantic-mapping-options.png" alt-text="管理语义映射的选项。":::

- **编辑**：在检查步骤中打开语义映射设置的配置。 您可以更改当前配置。 选择 **保存** 和 **运行** 以处理更改。

- **更新**：使用来自属于其配置一部分的实体的最新数据更新选定的语义映射。 更新任何给定的语义映射将更新所有相同类型的语义映射。

- **重命名**：打开一个对话，您可以在其中为选定的语义映射输入不同的名称。 选择 **保存** 以应用您所做的更改。

- **删除**：打开一个对话以确认删除选定的语义映射。 您还可以通过选择语义映射和删除图标一次删除多个语义映射。 选择 **删除** 以确认删除。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
