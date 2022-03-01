---
title: 将 Customer Insights 数据导出到 Facebook Ads Manager
description: 了解如何配置与 Facebook Ads Manager 的连接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643672"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Facebook Ads Manager 连接器（预览）

将统一客户配置文件的细分导出到 Facebook Ads Manager，以在 Facebook 和 Instagram 上创建市场活动。

## <a name="prerequisites"></a>先决条件

- 您需要有一个包含 [**Facebook 业务帐户**](https://business.facebook.com/)的 [**Facebook 广告帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。
- 您需要是 [**Facebook 广告帐户**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)的管理员。

## <a name="connect-to-facebook-ads-manager"></a>连接到 Facebook Ads Manager

1. 转到 **管理员** > **导出目标**。

1. 在 **Facebook Ads Manager** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

1. 选择 **继续使用 Facebook** 登录到您的 Facebook 广告帐户。

1. 在使用 Facebook 进行身份验证后，允许 **ads_management** 权限。

1. 选择您要使用的 **Facebook 广告帐户**。

1. 从下拉列表中选择 **现有自定义访问群体** 或创建 **新自定义访问群体**。 有关详细信息，请参阅 [**Facebook Ads Manager 中的访问群体**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **选择您的密钥标识符字段** 中，选择 **电子邮件**、**名称和地址** 或 **电话** 以发送到 Facebook Ads Manager。

1. 映射所选密钥标识符的统一客户实体中的相应属性。
   > [提示] 如果选择 **电子邮件** 作为密钥标识符，匹配的最佳机会将出现。 添加其他标识符可以改进匹配。

1. 选择 **添加属性** 来映射其他属性以发送到 Facebook Ads Manager。 Facebook Ads Manager 中的属性映射到以下用户友好名称：**FN** = **名**、**LN** = **姓**、**FI** = **姓氏首字母大写**、**PHONE** = **电话**、**GEN** = **性别**、**DOB** = **出生日期**、**ST** = **省/自治区/直辖市**、**CT** = **市/县**、**ZIP** = **邮政编码**、**COUNTRY** = **国家/地区**

1. 选择想要导出的细分。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Facebook Ads Manager 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Facebook Ads 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
