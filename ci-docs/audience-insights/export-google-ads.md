---
title: 将 Customer Insights 数据导出到 Google Ads
description: 了解如何配置连接和导出到 Google Ads。
ms.date: 09/27/2021
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28e2b35c5a47a025b8cdcccdb3f61c79878bf056
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226999"
---
# <a name="export-segments-to-google-ads-preview"></a>向 Google Ads 导出客户细分（预览版）

将统一客户配置文件的客户细分导出到 Google Ads 访问群体列表，并使用它们在 Google Search、Gmail、YouTube 和 Google Display Network 上投放广告。 

> [!IMPORTANT]
> 目前，仅当您已经拥有批准的 Google Ads 开发人员令牌时，才能创建新连接并将数据导出到 Google Ads。 由于政策发生了变更，我们将很快更新 Google Ads 导出并提供不需要开发人员令牌的导出选项，以确保体验的连续性并简化导出到 Google Ads 的过程。 我们建议不要与 Google Ads 建立更多连接，以便更轻松地切换到新的导出选项。

## <a name="prerequisites-for-connection"></a>连接的先决条件

-   您具有 [Google Ads 帐户](https://ads.google.com/)和相应的管理员凭据。
-   您有一个[批准的 Google Ads 开发人员令牌](https://developers.google.com/google-ads/api/docs/first-call/dev-token)。 
-   您满足[客户匹配策略](https://support.google.com/adspolicy/answer/6299717)的要求。
-   您满足[重新市场营销列表大小](https://support.google.com/google-ads/answer/7558048)的要求。
-   Google Ads 中有现有访问群体和相应的 ID。 有关详细信息，请参阅 [Google Ads 访问群体](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。
-   您已[配置客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址、名和姓的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出到 Google Ads 最多可导出 100 万个客户配置文件。
- 导出到 Google Ads 仅限于客户细分。
- 由于提供商方面的限制，导出总计包含 100 万个客户配置文件的客户细分最长可能需要 5 分钟时间。 
- 在 Google Ads 中匹配可能最多需要 48 个小时。

## <a name="set-up-connection-to-google-ads"></a>设置与 Google Ads 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Google Ads** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 **[Google Ads 客户 ID](https://support.google.com/google-ads/answer/1704344)**。

1. 输入您的 **[Google Ads 审批的开发人员令牌](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **使用 Google Ads 进行身份验证** 并提供您的 Google Ads 凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。 

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Google Ads 部分选择连接。 如果看不到此部分名称，则没有此类型的连接可用。

1. 输入您的 **[Google Ads 访问群体 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**，然后选择 **连接** 以初始化与 Google Ads 的连接。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 Google Ads 中。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 

您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Google Ads 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Google Ads 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
