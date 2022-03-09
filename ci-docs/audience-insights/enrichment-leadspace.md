---
title: 通过第三方扩充 Leadspace 扩充公司配置文件
description: 有关 Leadspace 第三方扩充的常规信息。
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f89ef6842c21cf6b78154586f818beffbcdcffb9
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230623"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>通过 Leadspace 扩充公司配置文件（预览）

Leadspace 是一个提供企业对企业客户数据平台的数据科学公司。 它使具有基于客户的统一客户配置文件的环境能够扩充数据。 使用公司规模、位置或行业等属性扩充 *客户配置文件*。 使用职务、角色或电子邮件验证等属性扩充 *联系人配置文件*。

## <a name="prerequisites"></a>先决条件

要配置 Leadspace，必须满足以下先决条件：

- 您有一个可用的 Leadspace 许可证。
- 您有基于客户的[统一客户配置文件](customer-profiles.md)。
- 管理员已配置 Leadspace 连接，或者您拥有 [管理员](permissions.md#administrator)权限和“永久密钥”（称为 **Leadspace 令牌**）。 直接联系 [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/)，了解有关其产品的详细信息。

## <a name="configure-the-enrichment"></a>配置扩充

1. 在访问群体见解中，转到 **数据** > **扩充**。

1. 在 Leadspace 磁贴上选择 **扩充我的数据**，然后选择 **开始**。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 磁贴的屏幕截图。":::

1. 从下拉列表中选择[连接](connections.md)。 如果没有连接可用，请联系管理员。 如果您是管理员，则可以通过选择 **添加连接** 并选择 **Leadspace** 来创建连接。 

1. 选择 **连接到 Leadspace** 以确认连接。

1. 选择 **下一步**，然后选择您希望利用 Leadspace 提供的公司数据扩充的 **客户数据集**。 您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. 选择 **下一步**，并定义应使用统一配置文件中的哪些字段来查找来自 Leadspace 的匹配公司数据。 **公司名称** 字段是必需的。 为了使匹配精度更高，可添加最多两个其他字段：**公司网站** 和 **公司位置**。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 字段映射窗格。":::

1. 选择 **下一步** 以完成字段映射。

1. 如果您有要扩充的 *联系人配置文件*，请选中此复选框。 访问群体见解将自动映射必需字段。

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace 联系人记录扩充。":::
 
1. 提供扩充的名称，并在查看您的选择后选择 **保存扩充**。


## <a name="configure-the-connection-for-leadspace"></a>针对 Leadspace 配置连接 

您必须是管理员才能配置连接。 配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在 Leadspace 磁贴上选择 **设置**。

1. 选择 **开始**。 

1. 在 **显示名称** 框中输入连接的名称。

1. 提供有效的 Leadspace 令牌。

1. 通过选择 **我同意**，查看并同意 **数据隐私与合规性**。

1. 选择 **验证** 以验证配置。

1. 完成验证后，选择 **保存**。
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 连接配置页面。":::

## <a name="enrichment-results"></a>扩充结果

刷新扩充后，您可以在[我的扩充](enrichment-hub.md)下查看新扩充的公司数据。 您可以查找上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

有关详细信息，请参阅 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)。

## <a name="next-steps"></a>后续步骤


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Leadspace 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Leadspace 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
