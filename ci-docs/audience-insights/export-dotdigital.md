---
title: 将 Customer Insights 数据导出到 DotDigital
description: 了解如何配置与 DotDigital 的连接。
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644437"
---
# <a name="connector-for-dotdigital-preview"></a>用于 DotDigital 的连接器（预览）

将统一客户配置文件的客户细分导出到 DotDigital 通讯簿，并将其用于市场活动、电子邮件市场营销和使用 DotDigital 生成客户细分。 

## <a name="prerequisites"></a>先决条件

-   您具有 [DotDigital 帐户](https://dotdigital.com/)和相应的管理员凭据。
-   DotDigital 中有现有通讯簿和相应的 ID。 当您选择并打开通讯簿时，可以在 URL 中找到 ID。 有关详细信息，请参阅 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="connect-to-dotdigital"></a>连接到 DotDigital

1. 转到 **管理员** > **导出目标**。

1. 在 **DotDigital** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="用于 DotDigital 导出的配置窗格。":::

1. 输入您的 **DotDigital 用户名和密码**。

1. 输入您的 **[DotDigital 通讯簿 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 DotDigital 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 对于其他可选字段（例如 **名**、**姓**、**全名**、**性别** 和 **邮政编码**），请重复相同的步骤。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 DotDigital 中。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。 在 DotDigital 中，您现在可以在 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)中找到您的客户细分。

## <a name="known-limitations"></a>已知限制

- 每次最多可以向 DotDigital 导出 100 万个配置文件。
- 导出到 DotDigital 仅限于客户细分。
- 由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。 
- 可以导出到 DotDigital 的配置文件数与 DotDigital 的合同相关并受其限制。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 DotDigital 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 DotDigital 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
