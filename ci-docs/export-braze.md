---
title: 将客户细分导出到 Braze（预览版）
description: 了解如何配置连接并导出到 Braze。
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725205"
---
# <a name="export-segments-to-braze-preview"></a>将客户细分导出到 Braze（预览版）

将 Unified customer profile 的客户细分导出到 Braze，然后将其用于市场营销活动。

## <a name="prerequisites"></a>先决条件

- [Braze 帐户](https://www.braze.com/)和相应的管理员凭据。
- [Braze API 密钥](https://www.braze.com/docs/api/basics/)
- 您的 [Braze REST 终结点](https://www.braze.com/docs/api/basics/#api-definitions) 
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分中的 Unified customer profile 包含一个表示电子邮件地址和 Braze 客户 ID 的字段。

## <a name="known-limitations"></a>已知限制

- 不支持专用链接与自带存储 (BYOS) 结合使用。
- 向 Braze 导出最多 100 万个客户配置文件，最长可能需要 40 分钟完成。 您可以导出到 Braze 的客户配置文件数量取决于您与 Braze 的合同。
- 仅客户细分。
- Braze 导出不支持 Azure 专用链接。

## <a name="set-up-connection-to-braze"></a>设置与 Braze 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Braze**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 Braze API 密钥继续登录。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Braze 部分选择连接。 如果没有连接可用，请联系管理员。

1. 在 **主机名** 字段中按以下格式输入 REST 终结点：`rest.iad-03.braze.com`。

1. 为导出输入名称。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 在 **客户 ID** 字段中，选择代表客户的 Braze ID 的字段。 Braze 中的客户细分将使用与 Dynamics 365 Customer Insights 中的客户细分相同的名称创建。 您可以选择更多可选字段来匹配数据。

1. 选择要导出的实体或客户细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
