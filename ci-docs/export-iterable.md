---
title: 将客户细分导出到 Iterable（预览版）
description: 了解如何配置连接并导出到 Iterable。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195418"
---
# <a name="export-segments-to-iterable-preview"></a>将客户细分导出到 Iterable（预览版）

将 Unified customer profile 的客户细分导出到 Iterable，然后将其用于市场营销活动。

## <a name="prerequisites"></a>先决条件

- [Iterable 帐户](https://iterable.com/)和相应的管理员凭据。
- [Iterable API 密钥](https://support.iterable.com/hc/en-us/articles/360043464871)
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 最多向 Iterable 导出 100 万个客户配置文件，最长可能需要 30 分钟完成。 您可以导出到 Iterable 的客户配置文件数量取决于您与 Iterable 的合同。
- 仅客户细分。

## <a name="set-up-connection-to-iterable"></a>设置与 Iterable 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Iterable**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 Iterable API 密钥继续登录。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Iterable 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 在 Iterable 中创建的列表将具有与您在 Dynamics 365 Customer Insights 中的客户细分名称完全相同的名称。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
