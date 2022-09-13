---
title: 使用增强的公司数据扩充公司配置文件
description: 使用 Microsoft 的模型扩充并规范公司数据。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054237"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>使用增强的公司数据扩充公司配置文件

使用 Microsoft 的模型和已编译的公司数据更正、补充和标准化您的公司配置文件。 我们将使用 [Common Data Model 格式](/common-data-model/schema/core/applicationcommon/account)，以确保获得更好的准确性和见解。

您还可以[增强数据源上的公司数据](data-sources-enrichment.md)，以提高数据统一过程中的匹配准确性。

对于美国的上市公司，可以获得收入、股票代码、行业等信息。  

## <a name="how-we-enhance-company-data"></a>如何增强公司数据

我们的模型经过双步骤过程来增强公司配置文件。 首先，它会规范公司名称。 例如，*Microsoft Corp* 将被更正并标准化为 *Microsoft Corporation*。 它尝试在 Microsoft 已编译的公司数据中查找匹配项。 如果找到匹配项，我们会用已编译的公司数据中的信息（包括公司名称）来扩充公司配置文件。

### <a name="example"></a>示例

贵公司的信息可能未遵循标准化格式并包含拼写错误。 此模型会尝试修复这些问题并创建一致的信息。

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>限制

此模型不会：

- 确认公司的标识。 我们不验证输入的内容是否为现有组织，也不验证公司是否使用输出作为其标准名称。
- 全局性全面涵盖公司。 Microsoft 的已编译公司数据具有全局涵盖范围，但主要在澳大利亚、加拿大、英国以及美国提供这些数据。
- 全局实现公司地址标准化。 我们当前支持在这些国家或地区中实现地址标准化：澳大利亚、加拿大、法国、德国、意大利、日本、英国和美国。
- 保证数据的准确性或新鲜度。 由于业务信息经常变化，因此我们无法保证所提供的增强型公司数据始终准确或最新。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 **增强的公司数据** 磁贴上选择 **扩充我的数据**。

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="公司数据扩充中心中的扩充磁贴。":::

1. 查看概览，然后选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 选择公司配置文件中的哪类字段要用于与 Microsoft 的已编译公司数据进行匹配。 此选项会影响您可以在下一步中访问的映射字段。

1. 选择 **下一步**。

1. 将您的公司字段映射到 Microsoft 的公司数据。 要获得更高的匹配准确度，请添加更多字段。

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="配置公司扩充时的数据映射步骤。":::

1. 选择 **下一步** 以完成字段映射。

1. 为扩充和 **输出实体** 提供 **名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>概览卡

**客户更改概览** 磁贴显示有关扩充覆盖范围的详细信息

- **处理和更改的公司**：成功扩充的客户公司配置文件的数量。
- **已处理但未更改的公司**：已确认但未更改的公司配置文件的数量。 这通常发生在输入数据有效但无法通过扩充改进时。
- **未处理且未更改的公司**：未确认的客户公司配置文件的数量。 这通常发生在无效或扩充不支持的输入数据上。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]