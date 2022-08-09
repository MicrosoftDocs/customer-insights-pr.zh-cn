---
title: 使用 LiveRamp 的标识数据扩充客户资料（预览）
description: 使用 LiveRamp 数据扩充客户资料。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196337"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>使用 LiveRamp 的标识数据扩充客户资料（预览）

LiveRamp 提供确定性的离线标识解析和客户数据整合。 您可以将客户数据中的个人标识符映射到 AbiliTec 标识图形，然后接收 AbiliTec ID。 然后，您可以使用这些 ID 更好地统一您的客户数据。

## <a name="supported-countriesregions"></a>支持的国家/地区

我们目前仅支持在美国使用 LiveRamp 数据扩充客户资料。

## <a name="prerequisites"></a>先决条件

- 有效的 LiveRamp 订阅。 要获取订阅，请联系您的 LiveRamp 客户团队或 [dynamics@liveramp.com](mailto:dynamics@liveramp.com) 了解更多信息。

- 具有客户端 ID 和机密的有效 AbiliTec 订阅，用于访问 API。 有关详细信息，请参阅 [AbiliTec API 开发人员中心](https://developers.liveramp.com/abilitec-api/)。

- LiveRamp [连接](connections.md)已由管理员[配置](#configure-the-connection-for-liveramp)。

## <a name="configure-the-connection-for-liveramp"></a>配置 LiveRamp 的连接

您必须是 Customer Insights 中的[管理员](permissions.md#admin)，并具有有效的 LiveRamp 客户端 ID 和密码。

1. 配置扩充时选择 **添加连接**，或转到 **管理员** > **连接**，在 LiveRamp 磁贴上选择 **设置**。

   :::image type="content" source="media/liveramp-connection.png" alt-text="用于设置与 LiveRamp AbiliTec 服务的连接的配置窗格。":::

1. 为连接输入名称和有效的 LiveRamp 客户端 ID 和密码。

1. 通过选择 **我同意**，查看并同意[数据隐私与合规性](#data-privacy-and-compliance)。

1. 选择 **验证** 验证配置，然后选择 **保存**。

### <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 LiveRamp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 LiveRamp 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请查看 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。 您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 LiveRamp 磁贴的 **标识** 上选择 **扩充我的数据**。

   :::image type="content" source="media/liveramp-tile.png" alt-text="扩充概览页面的标识磁贴。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接。 如果没有连接可用，请联系管理员。

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 LiveRamp 的标识数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 定义统一资料中的哪些字段类型用于匹配 LiveRamp 的标识数据。 **姓名和地址**、**电子邮件** 或 **电话** 字段中至少有一个是必填项。 要获得更高的匹配准确度，请添加其他字段。 选择 **下一步**。

1. 将您的字段映射到 LiveRamp 的标识数据。

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp 扩充的数据映射选项。":::

1. 选择 **下一步** 以完成字段映射。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**按字段扩充的客户数** 可帮助深入了解每个扩充的字段的覆盖范围。

## <a name="next-steps"></a>后续步骤

基于扩充的客户数据构建。 使用 AbiliTec ID 将客户资料整合到基于个人的视图中。
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
