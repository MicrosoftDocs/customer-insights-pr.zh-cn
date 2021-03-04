---
title: 将 Customer Insights 数据导出到 Mailchimp
description: 了解如何配置与 Mailchimp 的连接。
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267162"
---
# <a name="connector-for-mailchimp-preview"></a>用于 Mailchimp 的连接器（预览）

将统一客户配置文件的客户细分导出到 Mailchimp 以创建新闻速递和电子邮件市场活动。

## <a name="prerequisites"></a>先决条件

-   您具有 [Mailchimp 帐户](https://mailchimp.com/)和相应的管理员凭据。
-   Mailchimp 中有现有访问群体和相应的 ID。 有关详细信息，请参阅 [Mailchimp 访问群体](https://mailchimp.com/help/create-audience/)。
-   您已[配置客户细分](segments.md)
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="connect-to-mailchimp"></a>连接到 Mailchimp

1. 转到 **管理员** > **导出目标**。

1. 在 **Mailchimp** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 输入您的 **[Mailchimp 访问群体 ID](https://mailchimp.com/help/find-audience-id/)**，然后选择 **连接** 以初始化与 Mailchimp 的连接。

1. 选择 **使用 Mailchimp 进行身份验证** 并提供您的 Mailchimp 凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="导出 Mailchimp 连接的屏幕截图":::

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 

1. 或者，您可以导出 **名** 和 **姓** 作为其他字段，以创建更多个性化的电子邮件。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 Mailchimp 中。

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="选择要导出到 Mailchimp 的字段和客户细分":::

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。 在 Mailchimp 中，您现在可以在 [Mailchimp 访问群体](https://mailchimp.com/help/create-audience/)下找到您的客户细分。

## <a name="known-limitations"></a>已知限制

- 每次最多可以向 Mailchimp 导出 100 万个配置文件。
- 导出到 Mailchimp 仅限于客户细分。
- 由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要三个小时。 
- 可以导出到 Mailchimp 的配置文件数与 Mailchimp 的合同相关并受其限制。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Mailchimp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Mailchimp 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]