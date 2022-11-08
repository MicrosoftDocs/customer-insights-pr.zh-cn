---
title: 将 Customer Insights 数据导出到 HubSpot
description: 了解如何配置连接和导出到 HubSpot。
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725343"
---
# <a name="export-segments-to-hubspot-preview"></a>将客户细分导出到 HubSpot（预览）

将统一客户配置文件的客户细分导出到 HubSpot，然后将其用于电子邮件市场营销。

## <a name="prerequisites-for-a-connection"></a>连接的先决条件

- [HubSpot 帐户](https://www.hubspot.com/)和相应的管理员凭据。
- 来自 HubSpot 的 [API 密钥](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key)。
- Customer Insights 中[配置的客户细分](segments.md)。

## <a name="known-limitations"></a>已知限制

- 不支持专用链接与自带存储 (BYOS) 结合使用。
- 每次导出到 HubSpot 的客户配置文件最多 100'000 个，最多可能需要 15 分钟完成。 您可以导出到 HubSpot 的客户配置文件数量取决和受限于您与 HubSpot 的合同。
- 仅客户细分。

## <a name="set-up-connection-to-hubspot"></a>设置与 HubSpot 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **HubSpot** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 出现提示时，输入您的 HubSpot 凭据。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化与 HubSpot 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 HubSpot 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 对其他可选字段重复相同步骤。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
