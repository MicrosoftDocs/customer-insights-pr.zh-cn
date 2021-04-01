---
title: 将 Customer Insights 数据导出到 SendGrid
description: 了解如何配置与 SendGrid 的连接。
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597270"
---
# <a name="connector-for-sendgrid-preview"></a>用于 SendGrid 的连接器（预览版）

将统一客户配置文件的客户细分导出到 SendGrid 联系人列表，并在 SendGrid 中将其用于市场活动和电子邮件市场营销。 

## <a name="prerequisites"></a>先决条件

-   您具有 [SendGrid 帐户](https://sendgrid.com/)和相应的管理员凭据。
-   SendGrid 中已有联系人列表和相应的 ID。 有关详细信息，请参阅 [SendGrid - 管理联系人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="connect-to-sendgrid"></a>连接到 SendGrid

1. 转到 **管理员** > **导出目标**。

1. 在 **SendGrid** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid 导出配置窗格。":::

1. 输入您的 **SendGrid API 密钥** [SendGrid API 密钥](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。

1. 输入您的 **[SendGrid 列表 ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 SendGrid 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 对于其他可选字段（例如 **名**、**姓**、**国家/地区**、**省/自治区/直辖市**、**市/县** 和 **邮政编码**），请重复相同的步骤。

1. 选择想要导出的细分。 我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 SendGrid。 

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。

## <a name="known-limitations"></a>已知限制

- 总共最多可以将 100'000 个配置文件导出到 SendGrid。
- 导出到 SendGrid 仅限于客户细分。
- 将多达 100'000 个配置文件导出到 SendGrid 可能需要几个小时才能完成。 
- 可以导出到 SendGrid 的配置文件数与 SendGrid 的合同相关并受其限制。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 SendGrid 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 SendGrid 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]