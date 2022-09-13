---
title: 将客户细分导出到 AdRoll（预览版）
description: 了解如何配置连接和导出到 AdRoll。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195739"
---
# <a name="export-segments-to-adroll-preview"></a>将客户细分导出到 AdRoll（预览版）

将统一客户配置文件的客户细分导出到 AdRoll 中，并使用它们投放广告。

## <a name="prerequisites"></a>先决条件

- [AdRoll 帐户](https://www.adroll.com/)和相应的管理员凭据。
- [AdRoll 广告厂商 ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出最多向 AdRoll 导出 250,000 个客户配置文件，最长可能需要 10 分钟完成。 您可以导出到 AdRoll 的客户配置文件数量取决于您与 AdRoll 的合同。
- 仅客户细分。 一个客户细分必须至少包含 100 个客户配置文件。

## <a name="set-up-connection-to-adroll"></a>设置与 AdRoll 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **AdRoll**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **使用 AdRoll 进行身份验证** 并提供您的 AdRoll 管理员凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 AdRoll 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 输入您的 **AdRoll 广告厂商 ID**。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]