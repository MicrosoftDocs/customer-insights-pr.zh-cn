---
title: 数据源扩充
description: 在经过数据统一流程之前扩充数据源。
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376568"
---
# <a name="enrichment-for-data-sources-preview"></a>数据源扩充（预览）

在进行数据统一之前，使用来自 Microsoft 和其他合作伙伴等来源的数据扩充您的客户数据。 数据源扩充有助于提高数据完整性和质量，可以帮助在您统一数据后获得更好的结果。 例如，使用规范化和标准化的地址格式可以提高匹配结果的质量。 要获取支持的扩充的列表，请参阅[支持的数据源扩充选项](#supported-data-source-enrichments)。

## <a name="enrich-a-data-source"></a>扩充数据源

您必须具有参与者或管理员权限才能创建或编辑扩充。 有关详细信息，请参阅[权限](permissions.md)。  

1. 转到 **数据** > **统一**。 选择要扩充的实体，然后选择一个属性作为实体的主键。 有关详细信息，请参阅[选择主键](map-entities.md#select-primary-key-and-semantic-type-for-attributes)。

1. 转到 **数据** > **数据源**。
 
1. 选择要扩充的数据源旁边的垂直省略号，然后选择 **扩充**。

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="数据源扩充页面。":::

   **发现** 选项卡显示[支持的数据源扩充选项](#supported-data-source-enrichments)。

1. 选择 **扩充我的数据** 配置数据源扩充。 将自动填充输出实体名称。

## <a name="supported-data-source-enrichments"></a>支持的数据源扩充

以下扩充当前可用于数据源。 查看扩充的详细步骤，了解如何对其进行配置。

- [增强的地址](enrichment-enhanced-addresses.md)
- [增强的公司数据](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>管理现有数据源扩充

转到 **我的扩充** 选项卡以查看所有配置的扩充。

选择扩充以查看可用选项。 您还可以选择列表项上的椭圆 (...) 以查看选项。 如果您配置了多个扩充，则可以使用搜索框快速找到它。

您可以查看、编辑、运行或删除数据源扩充。 有关详细信息，请参阅[管理现有扩充](enrichment-hub.md)。
