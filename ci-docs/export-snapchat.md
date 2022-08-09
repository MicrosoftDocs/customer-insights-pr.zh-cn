---
title: 将客户细分导出到 Snapchat（预览版）
description: 了解如何配置连接和导出到 Snapchat。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195371"
---
# <a name="export-segments-to-snapchat-preview"></a>将客户细分导出到 Snapchat（预览版）

将统一客户配置文件的客户细分导出到 Snapchat，并将其用于广告。

## <a name="prerequisites"></a>先决条件

- [Snapchat 业务帐户](https://business.snapchat.com/)、一个 [Snapchat 广告帐户](https://ads.snapchat.com/)以及相应的管理员凭据。 您必须至少是组织帐户的成员和特定广告帐户的数据管理员。
- 在 SAM（快速访问群体匹配）类型的 Snapchat 访问群体管理器中至少有一个访问群体。
- [Snapchat 客户细分/访问群体 ID](https://businesshelp.snapchat.com/s/article/custom-audiences)。 受众的 ID 可以在 Snapchat 受众管理器中选择受众后在 URL 中找到。
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 最多导出 100 万个客户配置文件，最长可能需要 15 分钟完成。
- 仅客户细分。

## <a name="set-up-connection-to-snapchat"></a>设置与 Snapchat 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Snapchat**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **使用 Snapchat 进行身份验证**，并为 Snapchat 提供您的管理凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Snapchat 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 输入 **Snapchat 客户细分/访问群体 ID**。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
