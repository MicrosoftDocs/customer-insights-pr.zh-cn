---
title: 使用增强型地址更新客户配置文件（包含视频）
description: 使用 Microsoft 模型扩充并标准化客户配置文件的地址信息。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080775"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>使用增强型地址更新客户配置文件

数据中的地址可能无结构、不完整或不正确。 使用 Microsoft 的模型按 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/address)标准化并扩充您的地址，以获得更佳的准确性和见解。

您还可以[扩充数据源上的地址](data-sources-enrichment.md)，以提高数据统一过程中的匹配准确性。 

## <a name="how-we-enhance-addresses"></a>如何增强地址

我们的模型将执行两个步骤来增强地址。 首先，它解析地址以标识其组成部分并使其成为结构化格式。 然后，我们使用 AI 来更正、完成和标准化地址中的值。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>示例

地址信息可能采用非标准格式并且包含拼写错误。 该模型可以在统一客户配置文件中修复这些问题并创建一致的地址。

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>限制

增强的地址仅适用于引入的地址数据中已存在的值。 此模型不会：

1. 验证地址是否有效。
2. 验证任意值（如邮政编码或街道名称）是否有效。
3. 更改它无法识别的值。

该模型使用基于机器学习的技术来增强地址。 与任何基于机器学习的模型一样，不能保证 100% 准确。

## <a name="supported-countries-or-regions"></a>支持的国家或地区

我们当前支持扩充以下国家或地区中的地址：

- 澳大利亚
- 加拿大
- 法国
- 德国
- 意大利
- 日本
- 英国
- 美国

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 **增强的地址** 磁贴上选择 **扩充我的数据**。

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="增强的地址磁贴的屏幕截图。":::

1. 查看概览，然后选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 选择在数据集中设置地址格式的方式。 如果数据中的地址使用单个字段，请选择 **单一属性地址**。 如果数据中的地址使用多个数据字段，请选择 **多属性地址**。

1. 选择 **下一步**，映射您的统一客户实体的地址字段。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="增强的地址字段映射页。":::

   > [!NOTE]
   > 在单一属性和多属性地址中，国家/地区均是必需的。 将不会扩充不包含有效或受支持的国家/地区值的地址。

1. 选择 **下一步** 以完成字段映射。

1. 为扩充和 **输出实体** 提供 **名称**。

1. 在查看您的选择后选择 **保存扩充**。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**按字段扩充的客户数** 可帮助深入了解每个扩充的字段的覆盖范围。

### <a name="overview-card"></a>概览卡

**客户更改概览** 卡显示有关扩充覆盖范围的详细信息：

- **处理和更改的地址**：成功扩充的带地址的客户配置文件数量。
- **已处理但未更改的地址**：已确认但未更改的带地址的客户配置文件数量。 通常发生在输入数据有效且无法通过扩充改进时。
- **未处理且未更改的地址**：未确认的带地址的客户配置文件数量。 通常是指无效或扩充不支持的输入数据。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
