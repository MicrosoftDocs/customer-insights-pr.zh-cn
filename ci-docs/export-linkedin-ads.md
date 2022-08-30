---
title: 向 LinkedIn Ads 导出客户细分（预览版）
description: 了解如何配置连接和导出到 LinkedIn Ads。
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304692"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>向 LinkedIn Ads 导出客户细分（预览版）

将统一客户配置文件的客户细分导出到 LinkedIn Ads，以创建匹配的访问群体。 将匹配的访问群体用于确定目标公司和目标联系人。

## <a name="prerequisites"></a>先决条件

- [LinkedIn Campaign Manager 帐户](https://business.linkedin.com/marketing-solutions/ads)和相应的管理员凭据。
- [LinkedIn Campaign Manager 帐户 ID](https://www.linkedin.com/help/lms/answer/a424270)。
- Customer Insights 中[配置的客户细分](segments.md)。
- 导出的客户细分至少需要一个特定字段，具体取决于您在 LinkedIn 上选择[联系人定位](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)还是[公司定位](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。 [配置导出](#configure-an-export)时的 **数据匹配** 步骤中列出了可能的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出最多向 LinkedIn Ads 导出 100,000 个客户配置文件，最长可能需要 10 分钟完成。
- 仅客户细分。 一个客户细分必须至少包含 300 个唯一配置文件。

## <a name="set-up-connection-to-linkedin-ads"></a>设置与 LinkedIn Ads 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **LinkedIn Ads**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 LinkedIn Campaign Manager 帐户 ID。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **连接** 以初始化连接。

1. 选择 **使用 LinkedIn 进行身份验证**，并为 LinkedIn Campaign Manager 提供您的管理凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 LinkedIn Ads 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 选择是要导出数据以在 LinkedIn 中[确定目标联系人](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)还是[确定目标公司](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)。

1. 在 **数据匹配** 部分，对于联系人定位，至少选择一个表示客户的电子邮件地址、Apple 广告 ID、Google 广告 ID、Google 用户 ID 或名字和姓氏的字段。 如果您选择公司定位，至少选择一个表示公司名称、电子邮件域、LinkedIn 页面 URL、股票代码或网站的字段。

1. （可选）添加字段以进一步定义您的导出。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。 将使用您选择导出的客户细分的名称自动创建 LinkedIn Campaign Manager 中匹配的访问群体。 每个客户细分将产生一个单独的匹配访问群体。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
