---
title: LiveRamp 连接器
description: 了解如何配置连接和导出到 LiveRamp。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035634"
---
# <a name="export-segments-to-liverampreg-preview"></a>将细分市场导出到 LiveRamp&reg;（预览版）

在 LiveRamp 中激活您的数据，以在数字、社交和 TV 中与 500 多个平台进行连接。 在 LiveRamp 中处理数据以便为广告市场活动设置目标，隐藏广告市场活动和个性化广告市场活动。

## <a name="prerequisites-for-a-connection"></a>连接的先决条件

- 需要 LiveRamp 订阅才能使用此连接器。
- 若要获取订阅，请直接[联系 LiveRamp](https://liveramp.com/contact/)。 [详细了解 LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="set-up-connection-to-liveramp"></a>设置与 LiveRamp 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **LiveRamp** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 为 LiveRamp Secure FTP (SFTP) 帐户提供 **用户名** 和 **密码**。
这些凭据可能与您的 LiveRamp Onboarding 凭据不同。

1. 选择 **验证** 以测试与 LiveRamp 之间的连接。

1. 验证成功之后，选中 **我同意** 复选框同意 **数据隐私和合规性**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 LiveRamp 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 在 **选择密钥标识符** 字段中，选择要发送到 LiveRamp 以进行身份识别的 **电子邮件**、**姓名和地址** 或 **电话**。
   > [!div class="mx-imgBorder"]
   > ![具有属性映射的 LiveRamp 连接器。](media/export-liveramp-segments.png "具有属性映射的 LiveRamp 连接器")

1. 映射所选密钥标识符的统一客户实体中的相应属性。

1. 选择 **添加属性** 以映射要发送到 LiveRamp 的更多属性。

   > [!TIP]
   > 向 LiveRamp 发送更多密钥标识符属性可提高匹配率。

1. 选择要导出到 LiveRamp 的细分。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Liveramp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Liveramp 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
