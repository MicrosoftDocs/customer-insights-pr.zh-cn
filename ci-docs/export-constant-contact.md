---
title: 将客户细分导出到 Constant Contact（预览版）
description: 了解如何配置连接和导出到 Constant Contact。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196475"
---
# <a name="export-segments-to-constant-contact-preview"></a>将客户细分导出到 Constant Contact（预览版）

将统一客户配置文件的客户细分导出到 Constant Contact，并将其用于市场营销活动。

## <a name="prerequisites"></a>先决条件

- [Constant Contact 帐户](https://www.constantcontact.com/account-home)和相应的管理员凭据。
- [Constant Contact 列表 ID](https://app.constantcontact.com/pages/contacts/ui#lists)。 在 Constant Contact 中打开列表以查找 URL 中的列表 ID。
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 一次导出最多向 Constant Contact 导出 100 万个客户配置文件，最长可能需要一个小时完成。 您可以导出到 Constant Contact 的客户配置文件数量取决于您与 Constant Contact 的合同。
- 仅客户细分。

## <a name="set-up-connection-to-constant-contact"></a>设置与 Constant Contact 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Constant Contact**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **通过 Constant Contact 进行身份验证**，并提供您的 Constant Contact 管理员凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Constant Contact 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 输入 **Constant Contact 列表 ID**。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。

1. （可选）导出 **名** 和 **姓** 作为其他字段，以创建更多个性化的电子邮件。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
