---
title: 将 Customer Insights 数据导出到 LinkedIn Ads
description: 了解如何配置连接和导出到 LinkedIn Ads。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645954"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>向 LinkedIn Ads 导出客户细分（预览版）

将统一客户配置文件的客户细分导出到 LinkedIn Ads，以创建匹配的访问群体。 将匹配的访问群体用于确定目标公司和目标联系人。

## <a name="prerequisites"></a>先决条件

-   您有一个 [LinkedIn Campaign Manager 帐户](https://business.linkedin.com/marketing-solutions/ads)和相应的管理员凭据。
-   您在 Customer Insights 中具有[配置的客户细分](segments.md)。
-   已导出客户细分中的客户配置文件包含带有电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- Customer Insights 中的客户细分需要包含至少 300 个唯一配置文件。 
- 每次最多可以将 10 万个客户配置文件导出到 LinkedIn Ads。
- 导出到 LinkedIn Ads 仅限于客户细分。
- 向 LinkedIn Ads 导出最多 10 万个客户配置文件最长可能需要 10 分钟完成。 

## <a name="set-up-the-connection-to-linkedin-ads"></a>设置与 LinkedIn Ads 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **LinkedIn Ads** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 [LinkedIn Campaign Manager 帐户 ID](https://www.linkedin.com/help/lms/answer/a424270)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 Campaign Monitor 的连接。

1. 选择 **使用 LinkedIn 进行身份验证**，并为 LinkedIn Campaign Manager 提供您的管理凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 LinkedIn Ads 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选择是要导出数据以在 LinkedIn 中[确定目标联系人](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)还是[确定目标公司](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。 

1. 在 **数据匹配** 部分，对于联系人定位，至少选择一个表示客户的电子邮件地址、Apple 广告 ID、Google 广告 ID、Google 用户 ID 或名字和姓氏的字段。 如果您选择公司定位，至少选择一个表示公司名称、电子邮件域、LinkedIn 页面 URL、股票代码或网站的字段。 还可以选择其他字段来进一步定义导出。 

1. 选择想要导出的细分。 将使用您选择导出的客户细分的名称自动创建 LinkedIn Campaign Manager 中匹配的访问群体。 每个客户细分将产生一个单独的匹配访问群体。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以将数据传输到 LinkedIn Ads 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。 Microsoft 将在您的指示下传输此类数据，但您有责任确保 LinkedIn Ads 履行您可能具有的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来停止使用此功能。
