---
title: 将 Customer Insights 数据导出到 SendGrid
description: 了解如何配置连接和导出到 SendGrid。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: da3da5ea68d178deab3b9ab31dd810dee610f607
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617820"
---
# <a name="export-segments-to-sendgrid-preview"></a>将客户细分导出到 SendGrid（预览版）

将统一客户配置文件的客户细分导出到 SendGrid 联系人列表，并在 SendGrid 中将其用于市场活动和电子邮件市场营销。 

## <a name="prerequisites-for-a-connection"></a>连接的先决条件

-   您具有 [SendGrid 帐户](https://sendgrid.com/)和相应的管理员凭据。
-   SendGrid 中已有联系人列表和相应的 ID。 有关详细信息，请参阅 [SendGrid - 管理联系人](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 总计最多可将 100'000 个客户配置文件导出到 SendGrid。
- 导出到 SendGrid 仅限于客户细分。
- 向 SendGrid 导出最多 100'000 个客户配置文件最长可能需要几个小时完成。 
- 您可以导出到 SendGrid 的客户配置文件数量取决和受限于您与 SendGrid 的合同。

## <a name="set-up-connection-to-sendgrid"></a>设置与 SendGrid 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **SendGrid** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 **SendGrid API 密钥** [SendGrid API 密钥](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 SendGrid 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 SendGrid 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 输入您的 **[SendGrid 列表 ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 对于其他可选字段（例如 **名**、**姓**、**国家/地区**、**省/自治区/直辖市**、**市/县** 和 **邮政编码**），请重复相同的步骤。

1. 选择想要导出的细分。 我们强烈 **建议不要将总共超过 100'000 个客户配置文件导出** 到 SendGrid。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 SendGrid 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 SendGrid 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
