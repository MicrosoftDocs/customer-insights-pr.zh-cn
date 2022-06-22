---
title: 通过第三方扩充 Experian 进行的扩充
description: 有关 Experian 第三方扩充的常规信息。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954076"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>使用 Experian 中的人口统计信息扩充客户配置文件（预览）

Experian 是消费者和企业信用报告以及市场营销服务领域的全球领先者。 使用 Experian 的数据扩充服务，您可以通过使用人口统计数据（例如家庭规模、收入等）扩充客户配置文件，以进一步了解您的客户。

## <a name="supported-countriesregions"></a>支持的国家/地区

我们当前仅支持在美国扩充客户配置文件。

## <a name="prerequisites"></a>先决条件

- 有效的 Experian 订阅。 若要获取订阅，请直接[与 Experian 联系](https://www.experian.com/marketing-services/contact)。 [了解有关 Experian 数据扩充的详细信息](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- Experian [连接](connections.md)已由管理员[配置](#configure-the-connection-for-experian)。

- Experian 为您创建的启用 SSH 的安全传输 (ST) 帐户的 Experian 用户 ID、参与方 ID 和型号。

## <a name="configure-the-connection-for-experian"></a>配置 Experian 的连接

您必须是 Customer Insights 中的[管理员](permissions.md#admin)，并具有 Experian 用户 ID、参与方 ID 和型号。

1. 当配置扩充时选择 **添加连接**，或者转到 **管理员** > **连接**，然后在 Experian 磁贴上选择 **设置**。

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 连接配置窗格。":::

1. 为连接输入名称，并输入您的 Experian 安全传输帐户的有效用户 ID、参与方 ID 和型号。

1. 通过选择 **我同意**，查看并同意[数据隐私与合规性](#data-privacy-and-compliance)。

1. 选择 **验证** 验证配置，然后选择 **保存**。

### <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当启用 Dynamics 365 Customer Insights 将数据传输到 Experian 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。 Microsoft 将根据您的指示传输此类数据，但您负责确保 Experian 满足您可能承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。 您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 Experian 磁贴的 **人口统计** 上选择 **扩充我的数据**。

   :::image type="content" source="media/experian-tile.png" alt-text="扩充概览页面的 Experian 磁贴。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接。 如果连接不可用，请联系管理员。

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 Experian 的人口统计数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. 定义统一资料中的哪些字段类型用于匹配 Experian 的人口统计数据。 至少需要 **名称和地址**、**电话** 或 **电子邮件** 中的一个字段。 要获得更高的匹配准确度，请添加其他字段。 选择 **下一步**。

1. 将字段映射到 Experian 的人口统计数据。

1. 选择 **下一步** 以完成字段映射。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="enrichment-results"></a>扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**按字段扩充的客户数** 可帮助深入了解每个扩充的字段的覆盖范围。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
