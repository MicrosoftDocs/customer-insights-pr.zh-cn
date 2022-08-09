---
title: 将细分市场导出到 Marketo（预览版）
description: 了解如何配置连接和导出到 Marketo。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195233"
---
# <a name="export-segments-to-marketo-preview"></a>将细分市场导出到 Marketo（预览版）

导出统一客户配置文件的客户细分以生成市场活动，提供电子邮件市场营销，并通过 Marketo 使用特定客户组。

## <a name="prerequisites"></a>先决条件

- [Marketo 帐户](https://login.marketo.com/)和相应的管理员凭据。
- [Marketo 客户端 ID、客户端密码和 REST 终结点主机名](https://developers.marketo.com/rest-api/authentication/)。
- [Marketo 中的现有列表](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)和相应的 ID。
- [配置的客户细分](segments.md)。
- 导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出最多向 Marketo 导出 100 万个客户配置文件，最长可能需要 3 小时。 您可以导出到 Marketo 的客户配置文件数量取决于您与 Marketo 的合同。
- 仅客户细分。

## <a name="set-up-connection-to-marketo"></a>设置与 Marketo 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Marketo**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 **Marketo 客户端 ID、客户端密码和 REST 终结点主机名**。 REST 终结点主机名是纯主机名，不带 https://。 示例：xyz-abc-123.mktorest.com。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Marketo 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 输入您的 **Marketo 列表 ID**。 列表 ID 是一个纯数值。 例如，如果 Marketo 列表 ID 为 ST12345A7，请删除数字之前和之后的字符，并输入 *12345*。

1. 在 **数据匹配** 部分，选择至少一个代表客户的电子邮件地址或客户的 Marketo ID 的字段。

1. （可选）导出 **名**、**姓**、**市/县**、**省/市/自治区** 和 **国家/地区** 以创建更个性化的电子邮件。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

在 Marketo 中，在 [Marketo 列表](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)下找到您的客户细分。

[!INCLUDE [footer-include](includes/footer-banner.md)]
