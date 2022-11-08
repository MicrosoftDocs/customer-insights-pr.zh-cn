---
title: 将客户细分导出到 MoEngage
description: 了解如何配置连接并导出到 MoEngage。
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725251"
---
# <a name="export-segments-to-moengage-preview"></a>将客户细分导出到 MoEngage（预览）

将统一客户配置文件的客户细分导出到 MoEngage，并在 MoEngage 中将其用于电子邮件市场营销。

## <a name="prerequisites-for-a-connection"></a>连接的先决条件

- [MoEngage 帐户](https://www.moengage.com/)和相应的管理员凭据。
- 来自 MoEngage 中的“设置 > API”的 MoEngage API 密钥。
- Customer Insights 中[配置的客户细分](segments.md)。

## <a name="known-limitations"></a>已知限制

- 不支持专用链接与自带存储 (BYOS) 结合使用。
- 每次导出最多向 MoEngage 导出 100'000 个客户配置文件，最长可能需要 15 分钟。 您可以导出到 MoEngage 的客户配置文件数量取决于您与 MoEngage 的合同。
- 仅客户细分。

## <a name="set-up-connection-to-moengage"></a>设置与 MoEngage 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接**，然后选择 **MoEngage** 配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 [MoEngage 数据 API ID 和 API 密钥](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY)。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化与 MoEngage 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 MoEngage 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 对其他可选字段重复相同步骤。

1. 选择想要导出的细分。 我们将在 **客户细分** > **自定义客户细分** 下创建一个或多个与 MoEngage 中选定客户细分同名的客户细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
