---
title: 将客户细分导出到 Microsoft Advertising（预览版）
description: 了解如何配置连接和导出到 Microsoft Advertising。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196521"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>将客户细分导出到 Microsoft Advertising（预览版）

将 Customer Insights 客户细分导出到 Microsoft Advertising，以创建客户匹配访问群体。 将这些访问群体用于您的广告市场活动。

## <a name="prerequisites"></a>先决条件

- [Microsoft Advertising 帐户](https://ads.microsoft.com/)和相应的管理员凭据。
- Microsoft Advertising 客户 ID 和帐户 ID。 当您登录 Microsoft Advertising 时，在 URL 的参数中查找客户 ID (`cid`) 和帐户 ID (`aid`)。
- 已接受 Customer Match 使用条款。
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出最多向 Microsoft Advertising 导出 500,000 个客户配置文件，最长可能需要 10 分钟。
- 仅客户细分。

## <a name="set-up-connection-to-microsoft-advertising"></a>设置与 Microsoft Advertising 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Microsoft Advertising**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认为管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入 **Microsoft Advertising 客户 ID**。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **使用 Microsoft Advertising 进行身份验证**，并为 Microsoft Advertising 提供您的管理凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Microsoft Advertising 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 选择要导出的客户细分。 会使用为导出选择的客户细分的名称自动创建 Microsoft Advertising 中的客户匹配访问群体。 每个客户细分将产生一个单独的客户匹配访问群体。

1. 输入您的 **Microsoft Advertising 客户 ID 和帐户 ID**。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择包含客户电子邮件地址的字段。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
