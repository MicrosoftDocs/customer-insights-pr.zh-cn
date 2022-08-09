---
title: 通过 Dun & Bradstreet 扩充公司配置文件（预览版）
description: 有关 Dun & Bradstreet 第三方扩充的一般信息。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196015"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>通过 Dun & Bradstreet 扩充公司配置文件（预览版）

Dun & Bradstreet 为企业提供商业数据、分析和见解。 它使那些具有公司统一客户配置文件的客户能够扩充其数据。 扩充包括 DUNS 编号、公司规模、位置、行业等属性。

## <a name="prerequisites"></a>先决条件

- 有效的 [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) 许可证。
- 适用于公司的 [Unified customer profile](customer-profiles.md)。
- 设置了一个 Dun & Bradstreet [项目](#set-up-your-dun--bradstreet-project)。
- Dun & Bradstreet [连接](connections.md)已由管理员[配置](#configure-a-connection-for-dun--bradstreet)。

## <a name="set-up-your-dun--bradstreet-project"></a>设置您的 Dun & Bradstreet 项目

作为 Dun & Bradstreet 的许可用户，您可以在 [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) 中设置项目。

1. 登录到 [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)。 若要检索凭据，请[还原密码](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)。

1. 下载[我的们 csv 模板文件](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)，该文件将用于将 Customer Insights 字段映射到相应的 Dun & Bradstreet 字段。

1. 在 Dun & Bradstreet 项目创建体验的 **上传数据** 步骤中上传文件。

1. 在新创建的 Dun & Bradstreet 项目中选择相关 **来源** 下的水平点以查看可用选项。

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet 项目中的点的屏幕截图。":::

1. 选择 **获取 S3 详细信息**。 将此信息存储在安全位置。 您将需要它以在 Customer Insights 中[为扩充设置连接](#configure-a-connection-for-dun--bradstreet)。

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="在 Dun & Bradstreet 项目中选择 s3 信息的屏幕截图。":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>配置 Dun & Bradstreet 连接

您必须是 Customer Insights 中的[管理员](permissions.md#admin)，并具有 Dun & Bradstreet Connect 的凭据。

1. 配置扩充时选择 **添加连接**，或转到 **管理员** > **连接**，在 Dun & Bradstreet 磁贴上选择 **设置**。

1. 为连接输入名称。

1. 提供有效的 Dun & Bradstreet 凭据和 Dun & Bradstreet 项目详细信息 *区域、放置文件夹路径和放置文件夹名称*。 您可以从 Dun & Bradstreet 项目中[获取此信息](#set-up-your-dun--bradstreet-project)。

1. 通过选择 **我同意**，查看并同意[数据隐私与合规性](#data-privacy-and-compliance)。

1. 选择 **验证** 验证配置，然后选择 **保存**。

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet 连接配置页面。":::

### <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Dun & Bradstreet 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 Dun & Bradstreet 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。

## <a name="supported-countries-or-regions"></a>支持的国家或地区

我们目前支持以下国家/地区选项：加拿大（英语）或美国（英语）。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 Dun & Bradstreet 磁贴的 **公司数据** 上选择 **扩充我的数据**。

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet 磁稍的屏幕截图。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接并确认。 如果没有连接可用，请联系管理员。

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 Dun & Bradstreet 的公司数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 定义统一资料中的哪些字段类型用于匹配 Dun & Bradstreet 的公司数据。 至少需要 **名称和地址**、**电话** 或 **电子邮件** 中的一个字段。

1. 选择 **下一个**

1. 将您的字段映射到 Dun & Bradstreet 的公司数据。 必须填写 **DUNS 编码** 或 **公司的名称** 和 **国家/地区** 字段。

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet 字段映射窗格。":::

1. 选择 **下一步** 以完成字段映射。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
