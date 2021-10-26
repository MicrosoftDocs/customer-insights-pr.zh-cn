---
title: 将 Customer Insights 数据导出到 Facebook Ads Manager
description: 了解如何配置连接和导出到 Facebook Ads Manager。
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4403c6f535f5dc60919be3717073d52640bbe61a
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619200"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>向 Facebook Ads Manager 导出客户细分列表（预览版）

将统一客户配置文件的细分导出到 Facebook Ads Manager，以在 Facebook 和 Instagram 上创建市场活动。

## <a name="prerequisites-for-connection"></a>连接的先决条件

- 您需要具有一个包含 [**Facebook 业务帐户**](https://business.facebook.com/)的 [**Facebook Ads 帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。
- 您需要成为 [**Facebook Ads 帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)的管理员。

## <a name="known-limitations"></a>已知限制

- 每个导出最多可以将 1000 万个客户配置文件导出到 Facebook Ads Manager。
- 导出到 Facebook Ads Manager 仅限于客户细分。
- 在 Facebook 中仅创建或更新 *客户列表* 类型的自定义受众。
- 导出总计包含 1000 万个客户配置文件的客户细分最长可能需要 90 分钟完成。

## <a name="set-up-connection-to-facebook-ads-manager"></a>设置与 Facebook Ads Manager 的连接

在用户创建导出之前，管理员必须配置与服务的连接，并允许参与者使用该连接。

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Facebook Ads Manager** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 使用 Facebook Ads 进行身份验证： 

   1. 选择 **继续使用 Facebook** 以登录到 Facebook Ads 帐户。

   1. 在使用 Facebook 进行身份验证后，允许 **ads_management** 权限。

   1. 选择您要使用的 **Facebook 广告帐户**。

   1. 从下拉列表中选择 **现有自定义访问群体** 或创建 **新自定义访问群体**。 有关详细信息，请参阅 [**Facebook Ads Manager 中的访问群体**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。
      > [!NOTE]
      > 您在 Facebook 上使用此导出只能创建或更新 *客户列表* 类型的自定义受众。 在某些情况下，您将在下拉列表中看到不同类型的自定义访问群体。 选择不同于 *客户列表* 的类型将导致导出失败。 

1. 查看 **数据隐私和合规性**，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。 

1. 在 **导出连接** 中，从 **Facebook Ads Manager** 部分选择连接。 如果看不到此部分名称，则没有此类型的连接可用。

1. 在 **选择您的密钥标识符字段** 中，选择 **电子邮件**、**名称和地址** 或 **电话** 以发送到 Facebook Ads Manager。 

1. 在 **显示名称** 字段中为连接指定易于识别的名称。

1. 映射所选密钥标识符的统一客户实体中的相应属性。
   > [!TIP]
   > 如果选择 **电子邮件** 作为密钥标识符，匹配的最佳机会将出现。 添加其他标识符可以改进匹配。

1. 选择 **添加属性** 以映射要发送到 Facebook Ads Manager 的更多属性。 Facebook Ads Manager 中的属性映射到以下用户友好名称：**FN** = **名**、**LN** = **姓**、**FI** = **姓氏首字母大写**、**PHONE** = **电话**、**GEN** = **性别**、**DOB** = **出生日期**、**ST** = **省/自治区/直辖市**、**CT** = **市/县**、**ZIP** = **邮政编码**、**COUNTRY** = **国家/地区**

1. 选择想要导出的细分。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 

您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Facebook Ads Manager 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Facebook Ads 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
