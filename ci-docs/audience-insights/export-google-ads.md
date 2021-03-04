---
title: 将 Customer Insights 数据导出到 Google Ads
description: 了解如何配置与 Google Ads 的连接。
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268951"
---
# <a name="connector-for-google-ads-preview"></a>用于 Google Ads 的连接器（预览）

将统一客户配置文件的客户细分导出到 Google Ads 访问群体列表，并使用它们在 Google Search、Gmail、YouTube 和 Google Display Network 上投放广告。 

## <a name="prerequisites"></a>先决条件

-   您具有 [Google Ads 帐户](https://ads.google.com/)和相应的管理员凭据。
-   Google Ads 中有现有访问群体和相应的 ID。 有关详细信息，请参阅 [Google Ads 访问群体](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)。
-   您已[配置客户细分](segments.md)
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址、名和姓的字段

## <a name="connect-to-google-ads"></a>连接到 Google Ads

1. 转到 **管理员** > **导出目标**。

1. 在 **Google Ads** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

1. 输入您的 **[Google Ads 客户 ID](https://support.google.com/google-ads/answer/1704344)**。

1. 输入您的 **[Google Ads 审批的开发人员令牌](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 输入您的 **[Google Ads 访问群体 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**，然后选择 **连接** 以初始化与 Google Ads 的连接。

1. 选择 **使用 Google Ads 进行身份验证** 并提供您的 Google Ads 凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="导出 Google Ads 连接的屏幕截图":::

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 对**名**和 **姓** 字段重复相同的步骤。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 Google Ads 中。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。 在 Google Ads 中，您现在可以在 [Google Ads 访问群体](https://support.google.com/google-ads/answer/7558048?hl=en/)下找到您的客户细分。

## <a name="known-limitations"></a>已知限制

- 每次最多可以向 Google Ads 导出 100 万个配置文件。
- 导出到 Google Ads 仅限于客户细分。
- 由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 5 分钟。 
- 在 Google Ads 中匹配可能最多需要 48 个小时。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Google Ads 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Google Ads 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]