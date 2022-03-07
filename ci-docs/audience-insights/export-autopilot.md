---
title: 将 Customer Insights 数据导出到 Autopilot
description: 了解如何配置与 Autopilot 的连接。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269227"
---
# <a name="connector-for-autopilot-preview"></a>用于 Autopilot 的连接器（预览版）

将统一客户配置文件的客户细分导出到 Autopilot，并在 Autopilot 中将其用于电子邮件市场营销。 

## <a name="prerequisites"></a>先决条件

-   您具有 [Autopilot 帐户](https://www.autopilothq.com/)和相应的管理员凭据。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="connect-to-autopilot"></a>连接到 Autopilot

1. 转到 **管理员** > **导出目标**。

1. 在 **Autopilot** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 连接的配置窗格。":::

1. 输入您的 **Autopilot API 密钥** [Autopilot API 密钥](https://autopilot.docs.apiary.io/#)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 Autopilot 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 对于其他可选字段（例如名 **名** 和 **姓**），请重复相同的步骤。

1. 选择想要导出的细分。 我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 Autopilot。 

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。

## <a name="known-limitations"></a>已知限制

- 您总共可以将最多 100'000 个客户配置文件导出到 Autopilot 中。
- 导出到 Autopilot 仅限于客户细分。
- 将多达 100'000 个配置文件导出到 Autopilot 可能需要几个小时才能完成。 
- 可以导出到 Autopilot 的配置文件数与 Autopilot 的合同相关并受其限制。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Autopilot 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Autopilot 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]