---
title: 使用 HERE Technologies 扩充客户配置文件（预览版）
description: 有关 HERE Technologies 第三方扩充的常规信息。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237847"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>使用 HERE Technologies 扩充客户配置文件（预览版）

HERE Technologies 是一家位置平台公司，可提供以位置为中心的数据和服务。 HERE Technologies 的数据扩充服务可提高客户位置信息的精确度。 它提供地址标准化、纬度和经度提取等。

## <a name="prerequisites"></a>先决条件

- 有效的 HERE Technologies 订阅。 要获取订阅，请[在此处注册](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)或直接[联系 HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。 [了解有关 HERE Technologies 位置扩充的详细信息。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [连接](connections.md)已由管理员[配置](#configure-the-connection-for-here-technologies)。

## <a name="configure-the-connection-for-here-technologies"></a>为 HERE Technologies 配置连接

您必须是 Customer Insights 中的[管理员](permissions.md#admin)，并且具有有效的 HERE Technologies API 密钥。

1. 配置扩充时选择 **添加连接**，或转到 **管理员** > **连接**，然后在 HERE Technologies 磁贴上选择 **设置**。

1. 为连接输入名称并输入有效的 HERE Technologies API 密钥。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **验证** 验证配置，然后选择 **保存**。

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies 连接配置页面。":::

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 HERE Technologies 地图磁贴的 **位置** 上选择 **扩充我的数据**。

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies 磁贴。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接。 如果没有连接可用，请联系管理员。

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 HERE Technologies 的人口统计数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 定义统一资料中用于匹配的字段类型：主要和/或辅助地址。 您可以为两个地址指定字段映射，并分别扩充这两个地址的配置文件。 例如，家庭地址和公司地址。 选择 **下一步**。

1. 将字段映射到 HERE Technologies 的数据。 必须为所选的主要和/或辅助地址指定 **街道 1** 和 **邮政编码** 字段。 要获得更高的匹配准确度，请添加更多字段。

1. 选择 **下一步** 以完成字段映射。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**按字段扩充的客户数** 可帮助深入了解每个扩充的字段的覆盖范围。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
