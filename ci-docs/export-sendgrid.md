---
title: 将客户细分导出到 SendGrid（预览版）
description: 了解如何配置连接和导出到 SendGrid。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724837"
---
# <a name="export-segments-to-sendgrid-preview"></a>将客户细分导出到 SendGrid（预览版）

将统一客户配置文件的客户细分导出到 SendGrid 联系人列表，并在 SendGrid 中将其用于市场活动和电子邮件市场营销。

## <a name="prerequisites"></a>先决条件

- [SendGrid 帐户](https://sendgrid.com/)和相应的管理员凭据。
- [SendGrid 中的现有联系人列表](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)和相应的 ID。
- [SendGrid API 密钥](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)。
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 不支持专用链接与自带存储 (BYOS) 结合使用。
- 总计最多向 SendGrid 导出 100,000 个客户配置文件，最长可能需要几个小时完成。 您可以导出到 SendGrid 的客户配置文件数量取决于您与 SendGrid 的合同。
- 仅客户细分。

## <a name="set-up-connection-to-sendgrid"></a>设置与 SendGrid 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **SendGrid**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入 **SendGrid API 密钥**。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 SendGrid 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 输入您的 **SendGrid 列表 ID**。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。

1. （可选）选择字段，如 **名**、**姓**、**国家/地区**、**省/自治区/直辖市**、**市/县** 和 **邮政编码**。

1. 选择要按照已知限制导出的客户细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
