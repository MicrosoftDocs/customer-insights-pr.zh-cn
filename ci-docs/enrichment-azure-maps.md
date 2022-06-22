---
title: 使用 Azure Maps 中的位置数据扩充客户配置文件
description: 有关 Azure Maps 第一方扩充的常规信息。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953617"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>使用 Azure Maps（预览版）扩充客户配置文件

Azure Maps 提供以位置为中心的数据和服务，以提供基于具有内置位置智能的地理空间数据的体验。 Azure Maps 数据扩充服务可以提高有关客户位置的信息的精度。 其为 Dynamics 365 Customer Insights 提供地址标准化和经纬度提取之类功能。

## <a name="prerequisites"></a>先决条件

- 有效的 Azure Maps 订阅。 要获取订阅，[注册或获取免费试用版](https://azure.microsoft.com/services/azure-maps/)。

- Azure Maps [连接](connections.md)由管理员[配置](#configure-the-connection-for-azure-maps)。

## <a name="configure-the-connection-for-azure-maps"></a>为 Azure Maps 配置连接

您必须是 Customer Insights 中的[管理员](permissions.md#admin)，并且具有有效的 Azure Maps API 密钥。

1. 当配置扩充时选择 **添加连接**，或者转到 **管理** > **连接**，然后在 Azure Maps 磁贴上选择 **设置**。

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps 连接配置页。":::

1. 为连接输入名称并输入有效的 Azure Maps API 密钥。

1. 通过选择 **我同意**，查看并同意[数据隐私与合规性](#data-privacy-and-compliance)。

1. 选择 **验证** 验证配置，然后选择 **保存**。

### <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当启用 Dynamics 365 Customer Insights 将数据传输到 Azure Maps 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 Azure Maps 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请转到 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 Microsoft Azure Maps 磁贴的 **位置** 上选择 **扩充我的数据**。

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps 磁贴。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接。 如果没有连接可用，请联系管理员。

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 Microsoft 的数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 定义统一资料中用于匹配的字段类型：主要和/或辅助地址。 您可以为两个地址指定字段映射，并分别扩充这两个地址的配置文件。 例如，家庭地址和公司地址。 选择 **下一步**。

1. 将字段映射到 Azure Maps 中的位置数据。 必须为所选的主要和/或辅助地址指定 **街道 1** 和 **邮政编码** 字段。 要获得更高的匹配准确度，请添加更多字段。

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps 属性映射。":::

1. 选择 **下一步** 以完成字段映射。

1. 查看 **高级设置**，它为处理高级用例提供了最大的灵活性。 但是，通常不需要更改以下默认值。

   - **地址类型**：最佳地址匹配返回，即使不完整。 若要仅获取完整地址 &mdash; 例如，包含住宅编号的地址 &mdash; 请清除除 **点地址** 之外的所有复选框。
   - **语言**：地址基于地址区域使用的语言返回。 若要应用标准化地址语言，请从下拉菜单中选择该语言。 例如，选择 **英语** 将返回 **Copenhagen, Denmark** 而不是 **København, Danmark**。
   - **最大结果数**：每个地址的结果数。

1. 选择 **下一步**。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="enrichment-results"></a>扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**按字段扩充的客户数** 可帮助深入了解每个扩充的字段的覆盖范围。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
