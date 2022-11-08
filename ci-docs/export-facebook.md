---
title: 将客户细分导出到 Facebook 广告管理器（预览版）（包含视频）
description: 了解如何配置连接和导出到 Facebook Ads Manager。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724572"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>将客户细分导出到 Facebook 广告管理器（预览版）

将统一客户配置文件的细分导出到 Facebook Ads Manager，以在 Facebook 和 Instagram 上创建市场活动。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>先决条件

- 包含 [Facebook 业务帐户](https://business.facebook.com/)的 [Facebook 广告帐户](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)。
- [Facebook 广告帐户](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)的管理员特权。
- 在 Customer Insights 中设置连接的用户需要接受自定义访问群体条款。

## <a name="known-limitations"></a>已知限制

- 每次导出最多向 Facebook Ads Manager 导出 1000 万个客户配置文件，最长可能需要 90 分钟。
- 仅客户细分。
- Facebook 广告集成不支持有超过 25 个广告帐户的用户。
- 仅 [自定义访问群体](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)中的 Facebook *客户列表* 类型。
  > [!NOTE]
  > 在某些情况下，您可能会在下拉列表中看到不同类型的自定义访问群体。 如果您选择 *客户列表* 以外的其他类型，导出将失败。

## <a name="set-up-connection-to-facebook-ads-manager"></a>设置与 Facebook Ads Manager 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Facebook Ads Manager**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. [允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 使用 Facebook Ads 进行身份验证：

   1. 选择 **继续使用 Facebook** 以登录到 Facebook Ads 帐户。

   1. 在使用 Facebook 进行身份验证后，允许 **ads_management** 权限。

   1. 选择您要使用的 **Facebook 广告帐户**。

   1. 从下拉列表中选择 **现有自定义访问群体** 或创建 **新自定义访问群体**。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Facebook Ads Manager 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 在 **连接数据** 字段中，选择 **电子邮件**、**名称和地址** 或 **电话** 以发送到 Facebook Ads Manager。

1. 映射所选密钥标识符的统一客户实体中的相应属性。
   > [!TIP]
   > 如果选择 **电子邮件** 作为密钥标识符，匹配的最佳机会将出现。 添加其他标识符可以改进匹配。

1. 选择 **添加属性** 以映射要发送到 Facebook Ads Manager 的更多属性。 Facebook Ads Manager 中的属性映射到以下用户友好名称：**FN** = **名**、**LN** = **姓**、**FI** = **姓氏首字母大写**、**PHONE** = **电话**、**GEN** = **性别**、**DOB** = **出生日期**、**ST** = **省/自治区/直辖市**、**CT** = **市/县**、**ZIP** = **邮政编码**、**COUNTRY** = **国家/地区**

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
