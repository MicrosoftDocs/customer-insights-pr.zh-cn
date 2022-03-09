---
title: 将 Customer Insights 数据导出到 Mailchimp
description: 了解如何配置连接和导出到 Mailchimp。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226835"
---
# <a name="export-segments-to-mailchimp-preview"></a>将客户细分导出到 Mailchimp（预览版）

将统一客户配置文件的客户细分导出到 Mailchimp 以创建新闻速递和电子邮件市场活动。

## <a name="prerequisites-for-connection"></a>连接的先决条件

-   您具有 [Mailchimp 帐户](https://mailchimp.com/)和相应的管理员凭据。
-   Mailchimp 中有现有访问群体和相应的 ID。 有关详细信息，请参阅 [Mailchimp 访问群体](https://mailchimp.com/help/create-audience/)。
-   您已[配置客户细分](segments.md)
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出到 Mailchimp 最多可导出 100 万个客户配置文件。
- 导出到 Mailchimp 仅限于客户细分。
- 导出包含 100 万个客户配置文件的客户细分最长可能需要三个小时。 
- 您可以导出到 Mailchimp 的客户配置文件数量取决和受限于您与 Mailchimp 的合同。

## <a name="set-up-connection-to-mailchimp"></a>设置与 Mailchimp 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Mailchimp** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 Mailchimp 的连接。

1. 选择 **使用 Mailchimp 进行身份验证** 并提供您的 Mailchimp 凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。 

## <a name="configure-the-connector"></a>配置连接器

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据**> **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Mailchimp 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 输入您的 **[Mailchimp 受众 ID](https://mailchimp.com/help/find-audience-id/)**

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 

1. （可选）您可以导出 **名** 和 **姓** 以创建更个性化的电子邮件。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 Mailchimp 中。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Mailchimp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Mailchimp 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
