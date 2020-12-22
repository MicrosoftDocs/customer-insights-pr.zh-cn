---
title: 将 Customer Insights 数据导出到 Marketo
description: 了解如何配置与 Marketo 的连接。
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570392"
---
# <a name="connector-for-marketo-preview"></a>用于 Marketo 的连接器（预览）

导出统一客户配置文件的客户细分以生成市场活动，提供电子邮件市场营销，并通过 Marketo 使用特定客户组。

## <a name="prerequisites"></a>先决条件

-   您具有 [Marketo 帐户](https://login.marketo.com/)和相应的管理员凭据。
-   Marketo 中有现有列表和相应的 ID。 有关详细信息，请参阅 [Marketo 列表](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)。
-   您已[配置客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="connect-to-marketo"></a>连接到 Marketo

1. 转到 **管理员** > **导出目标**。

1. 在 **Marketo** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

1. 输入您的 **[Marketo 客户端 ID、客户端密码和 REST 终结点主机名](https://developers.marketo.com/rest-api/authentication/)**。

1. 输入您的 **[Marketo 列表 ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. 选择 **我同意** 确认 **数据隐私与合规性**，然后选择 **连接** 以初始化与 Marketo 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

   :::image type="content" source="media/export-connect-marketo.png" alt-text="导出 Marketo 连接的屏幕截图":::

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 

1. 或者，您可以导出 **名**、**姓**、**市/县**、**省/市/自治区** 和 **国家/地区** 作为其他字段，以创建更多个性化的电子邮件。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 Marketo 中。

   :::image type="content" source="media/export-segment-marketo.png" alt-text="选择要导出到 Marketo 的字段和客户细分":::

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。 在 Marketo 中，您现在可以在 [Marketo 列表](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)下找到您的客户细分。

## <a name="known-limitations"></a>已知限制

- 每次最多可以向 Marketo 导出 100 万个配置文件。
- 导出到 Marketo 仅限于客户细分。
- 导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。 
- 可以导出到 Marketo 的配置文件数与 Marketo 的合同相关并受其限制。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Marketo 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Marketo 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
