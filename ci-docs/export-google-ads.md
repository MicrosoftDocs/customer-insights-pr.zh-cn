---
title: 向 Google Ads 导出客户细分（预览版）
description: 了解如何配置连接和导出到 Google Ads。
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196567"
---
# <a name="export-segments-to-google-ads-preview"></a>向 Google Ads 导出客户细分（预览版）

将统一客户配置文件的客户细分导出到 Google Ads 访问群体列表，并使用它们在 Google Search、Gmail、YouTube 和 Google Display Network 上投放广告。

## <a name="prerequisites"></a>先决条件

- [Google Ads 帐户](https://ads.google.com/)和相应的管理员凭据。
- [Google Ads 客户 ID](https://support.google.com/google-ads/answer/1704344)。
- 满足 [Customer Match 策略](https://support.google.com/adspolicy/answer/6299717)的要求。
- 满足[重新市场营销列表大小](https://support.google.com/google-ads/answer/7558048)的要求。
- [配置的客户细分](segments.md)。
- 导出的客户细分中的 Unified customer profile 包含表示电子邮件地址、电话、移动广告商 ID、第三方用户 ID 或地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次最多向 Google Ads 导出 100 万个客户配置文件，由于提供商方面的限制，这最长可能需要 30 分钟完成。
- 仅客户细分。
- 在 Google Ads 中匹配可能最长需要 48 小时。

## <a name="set-up-connection-to-google-ads"></a>设置与 Google Ads 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Google Ads**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 Google Ads 客户 ID。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **使用 Google Ads 进行身份验证** 并提供您的 Google Ads 凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Google Ads 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 选择是使用现有访问群体还是创建新访问群体：
   - 要更新现有的 Google Ads 访问群体，请输入您的 [Google Ads 访问群体 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)。
   - 要创建新的访问群体，请将 Google 访问群体 ID 字段留空。 Customer Insights 会自动在您的 Google Ads 帐户中创建一个新的访问群体，使用导出的客户细分的名称。

1. 在 **数据匹配** 部分，选择一个或多个要导出的数据字段，然后选择代表 Customer Insights 中对应数据字段的字段。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
