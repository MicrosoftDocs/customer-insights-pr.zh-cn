---
title: 通过 Leadspace 扩充公司配置文件（预览版）
description: 有关 Leadspace 第三方扩充的常规信息。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237939"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>通过 Leadspace 扩充公司配置文件（预览版）

Leadspace 是一个提供企业对企业客户数据平台的数据科学公司。 它使具有基于客户的统一客户配置文件的环境能够扩充数据。 使用公司规模、位置或行业等属性扩充 *客户配置文件*。 使用职务、角色或电子邮件验证等属性扩充 *联系人配置文件*。

## <a name="prerequisites"></a>先决条件

- 有效的 Leadspace 许可证。
- 基于客户的 [Unified customer profile](customer-profiles.md)。
- Leadspace [连接](connections.md)已由管理员[配置](#configure-the-connection-for-leadspace)。 直接联系 [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/)，了解有关其产品的详细信息。

## <a name="configure-the-connection-for-leadspace"></a>针对 Leadspace 配置连接

您必须是 Customer Insights 中的 [管理员](permissions.md#admin)并具有“永久密钥”（称为 **Leadspace 令牌**）。

1. 配置扩充时选择 **添加连接**，或转到 **管理员** > **连接**，然后在 Leadspace 磁贴上选择 **设置**。

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 连接配置页面。":::

1. 为连接输入名称并输入有效的 Leadspace 令牌。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **验证** 验证配置，然后选择 **保存**。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 Leadspace 磁贴的 **公司数据** 上选择 **扩充我的数据**。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 磁贴的屏幕截图。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接。 如果没有连接可用，请联系管理员。

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 Leadspace 的公司数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. 定义统一资料中用于匹配的字段类型：主要和/或辅助地址。 您可以为两个地址指定字段映射，并分别扩充这两个地址的配置文件。 例如，家庭地址和公司地址。 选择 **下一步**。

1. 将您的字段映射到 Leadspace 的公司数据。 **公司名称** 字段是必需的。 为了使匹配精度更高，可添加最多两个其他字段：**公司网站** 和 **公司位置**。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 字段映射窗格。":::

1. 选择 **下一步** 以完成字段映射。

1. 如果您有要扩充的 *联系人配置文件*，请选中此复选框。 Customer Insights 将自动映射必填字段。

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace 联系人记录扩充。":::

1. 选择 **下一步**。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

有关详细信息，请参阅 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]