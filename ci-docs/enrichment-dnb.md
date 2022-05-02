---
title: 通过 Dun & Bradstreet 扩充公司配置文件
description: 有关 Dun & Bradstreet 第三方扩充的一般信息。
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653697"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>通过 Dun & Bradstreet 扩充公司配置文件（预览版）

Dun & Bradstreet 为企业提供商业数据、分析和见解。 它使那些具有公司统一客户配置文件的客户能够扩充其数据。 扩充包括 DUNS 编号、公司规模、位置、行业等属性。

## <a name="prerequisites"></a>先决条件

要配置 Dun & Bradstreet 扩充，必须满足以下先决条件：

- 您必须有可用的 [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) 许可证。
- 您具有公司[统一客户配置文件](customer-profiles.md)。
- Dun & Bradstreet [连接](connections.md)由管理员配置。 如果您拥有[管理员](permissions.md#admin)权限和 Dun & Bradstreet Connect 的凭据，则可以创建它。 

## <a name="setting-up-your-dun--bradstreet-project"></a>设置您的 Dun & Bradstreet 项目

作为 Dun & Bradstreet 的许可用户，您可以在 [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) 中设置项目。 


1. 登录到 [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)。 若要检索凭据，请[还原密码](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)。

1. 下载[我的们 csv 模板文件](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)，该文件将用于将访问群体见解字段映射到相应的 Dun & Bradstreet 字段。 

1. 在 Dun & Bradstreet 项目创建体验的 **上传数据** 步骤中上传文件。 

1. 在新创建的 Dun & Bradstreet 项目中选择相关 **来源** 下的水平点以查看可用选项。

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet 项目中的点的屏幕截图。":::

1. 选择 **获取 S3 详细信息**。 将此信息存储在安全位置。 您将需要它以在访问群体见解中[为扩充设置连接](#configure-a-connection-for-dun--bradstreet)。 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="在 Dun & Bradstreet 项目中选择 s3 信息的屏幕截图。":::



## <a name="configure-the-enrichment"></a>配置扩充

1. 在访问群体见解中，转到 **数据** > **扩充**。

1. 在 Dun & Bradstreet 磁贴上选择 **扩充我的数据**，然后选择 **开始使用**。

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet 磁稍的屏幕截图。":::

1. 从下拉列表中选择[连接](connections.md)。 如果没有连接可用，请联系管理员。 如果您是管理员，则可以创建连接。 选择 **添加连接** 并选择 **Dun & Bradstreet**。 

1. 选择 **连接到 Dun & Bradstreet** 以确认连接。

1. 选择 **下一步**，然后选择您要使用 Dun & Bradstreet 中的公司数据扩充的 **客户数据集**。 您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的 Unified customer profile。

1. 选择 **下一步**，并确定统一配置文件中的哪些字段用于查找来自 Dun & Bradstreet 的匹配公司数据。 必须填写 **DUNS 编码** 或 **公司的名称** 和 **国家/地区** 字段。 国家/地区字段支持[二或三字母的国家代码](https://www.iso.org/iso-3166-country-codes.html)、英文国家/地区名称、母语国家/地区名称、电话前缀。 一些常见国家/地区变体包括：

   * US：United States of America、United States、USA、America。
   * CA：Canada。
   * GB：United Kingdom、UK、Great Britain、GB、United Kingdom of Great Britain and Northern Ireland、United Kingdom of Great Britain。
   * AU：Australia、Commonwealth of Australia。
   * FR：France、French Republic。
   * DE：Germany、German、Deutschland、Allemagne、Federal Republic of Germany、Republic of Germany。

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet 字段映射窗格。":::

1. 选择 **下一步** 以完成字段映射。

1. 提供扩充的名称，并在查看您的选择后选择 **保存扩充**。


## <a name="configure-a-connection-for-dun--bradstreet"></a>配置 Dun & Bradstreet 连接 

您必须是管理员才能配置连接。 配置扩充时选择 **添加连接**，*或* 转到 **管理** > **连接**，在 Dun & Bradstreet 磁贴上选择 **设置**。

1. 选择 **开始**。 

1. 在 **显示名称** 框中输入连接的名称。

1. 提供有效的 Dun & Bradstreet 凭据和 Dun & Bradstreet 项目详细信息 *区域、放置文件夹路径和放置文件夹名称*。 您可以从 Dun & Bradstreet 项目中[获取此信息](#setting-up-your-dun--bradstreet-project)。

1. 通过选择 **我同意**，查看并同意 **数据隐私与合规性**。

1. 选择 **验证** 以验证配置。

1. 完成验证后，选择 **保存**。
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet 连接配置页面。":::

## <a name="enrichment-results"></a>扩充结果

刷新扩充后，您可以在[我的扩充](enrichment-hub.md)下查看新扩充的公司数据。 您可以查找上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Dun & Bradstreet 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 Dun & Bradstreet 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。


[!INCLUDE[footer-include](includes/footer-banner.md)]
