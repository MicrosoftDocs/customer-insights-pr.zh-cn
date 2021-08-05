---
title: 地址增强扩充
description: 使用 Microsoft 模型扩充并标准化客户配置文件的地址信息。
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 65db6ce05f4d6f7f7b08ada172fec057027dd310
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692242"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>使用增强的地址扩充客户配置文件

数据中的地址可能无结构、不完整或不正确。 使用 Microsoft 的模型按 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/address)标准化并扩充您的地址，以获得更佳的准确性和见解。

## <a name="how-we-enhance-addresses"></a>如何增强地址

我们的模型将执行两个步骤来增强地址。 首先，它解析地址以标识其组成部分并使其成为结构化格式。 然后，我们使用 AI 来更正、完成和标准化地址中的值。

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

增强型地址仅适用于引入的地址数据中已经存在的值。 此模型不会： 

1. 验证地址是否有效。
2. 验证任意值（如邮政编码或街道名称）是否有效。
3. 更改它无法识别的值。

该模型使用基于机器学习的技术来增强地址。 虽然我们在模型更改输入值时应用高置信度阈值，但与基于机器学习的任何模型一样，都不能保证 100% 的准确性。

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

地址必须包含国家/地区值。 我们不处理不受支持的国家或地区的地址，也不处理未提供国家或地区的地址。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**。

1. 在 **增强的地址** 磁贴上选择 **扩充我的数据**。

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="增强的地址磁贴的屏幕截图。":::

1. 选择 **客户数据集**，并选择包含要扩充的地址的实体。 您可以选择 *客户* 实体以扩充所有客户配置文件中的地址，也可以选择客户细分实体以仅扩充该客户细分所包含的客户配置文件中的地址。

1. 选择在数据集中设置地址格式的方式。 如果数据中的地址使用单个字段，请选择 **单一属性地址**。 如果数据中的地址使用多个数据字段，请选择 **多属性地址**。

   > [!NOTE]
   > 在单一属性和多属性地址中，国家/地区均是必需的。 将不会扩充不包含有效或受支持的国家/地区值的地址。

1.  映射统一客户实体中的地址字段。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="增强的地址字段映射页。":::

1. 选择 **下一步** 以完成字段映射。

1. 提供扩充和输出实体的名称。

1. 在查看您的选择后选择 **保存扩充**。

## <a name="enrichment-results"></a>扩充结果

要开始扩充过程，请从命令栏中选择 **运行**。 您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间取决于客户数据的大小。

扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

基于扩充的客户数据构建。 创建[细分](segments.md)和[度量](measures.md)，甚至[导出数据](export-destinations.md)，以向客户提供个性化体验。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
