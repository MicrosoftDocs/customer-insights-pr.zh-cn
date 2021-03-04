---
title: LiveRamp 连接器
description: 了解如何将数据导出到 LiveRamp。
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270147"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; 连接器（预览版）

在 LiveRamp 中激活数据，以便跨数字、社交和 TV 生态系统与超过 500 个平台连接。 在 LiveRamp 中处理数据以便为广告市场活动设置目标，隐藏广告市场活动和个性化广告市场活动。

## <a name="prerequisites"></a>先决条件

- 需要 LiveRamp 订阅才能使用此连接器。
- 若要获取订阅，请直接[联系 LiveRamp](https://liveramp.com/contact/)。 [详细了解 LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="connect-to-liveramp"></a>连接到 LiveRamp

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **LiveRamp** 磁贴中，选择 **设置**。

1. 在 **显示名称** 字段中为目标指定易于识别的名称。

1. 为 LiveRamp Secure FTP (SFTP) 帐户提供 **用户名** 和 **密码**。
这些凭据可能与您的 LiveRamp Onboarding 凭据不同。

1. 选择 **验证** 以测试与 LiveRamp 之间的连接。

1. 验证成功之后，选中 **我同意** 复选框同意 **数据隐私和合规性**。

1. 选择 **下一步** 设置 LiveRamp 连接器。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **选择密钥标识符** 字段中，选择要发送到 LiveRamp 以进行身份识别的 **电子邮件**、**姓名和地址** 或 **电话**。

1. 映射所选密钥标识符的统一客户实体中的相应属性。

1. 选择 **添加属性** 映射要发送到 LiveRamp 的更多属性。

   > [!TIP]
   > 向 LiveRamp 发送更多密钥标识符属性可提高匹配率。

1. 选择要导出到 LiveRamp 的细分。

1. 选择 **保存**。

> [!div class="mx-imgBorder"]
> ![具有属性映射的 LiveRamp 连接器](media/export-liveramp-segments.png "具有属性映射的 LiveRamp 连接器")

## <a name="export-the-data"></a>导出数据

如果满足所有导出必要条件，很快将开始导出。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。
成功完成导出之后，可以登录 LiveRamp Onboarding 激活和分发数据。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Liveramp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Liveramp 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]