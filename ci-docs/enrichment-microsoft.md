---
title: 使用来自 Microsoft 的品牌和兴趣数据扩充客户资料
description: 使用 Microsoft 的专有数据通过相似性和配额来扩充您的客户数据。
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953754"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>通过相似性和配额扩充客户配置文件（预览版）

使用 Microsoft 的专有数据通过品牌相似性、兴趣相似性和配额 (SoV) 来扩充您的客户数据。 这些相似性和 SoV 基于人口统计信息与客户相似的用户的数据。 此信息可帮助您针对特定品牌和兴趣根据客户的相似性或 SoV 更好地了解和细分客户。

## <a name="how-we-determine-affinities-and-sov"></a>如何确定相似性和 SoV

我们使用 Microsoft 的联机搜索数据在各个人口统计客户细分（按年龄、性别或位置定义）中查找品牌和兴趣的相似性和 SoV。 品牌或兴趣的联机搜索量构成了确定相似性或 SoV 的基准。 但是，每项内容都提供了一个用于了解客户的不同视角。

- 相似性是跨人口统计客户细分的一项比较。 您可以使用此信息来确定与其他客户细分相比，给定品牌或兴趣相似性最高的人口统计客户细分。

- 配额是在您选择的品牌或兴趣之间进行的一项比较。 您可以使用此信息来确定与您选择的其他品牌或兴趣相比，给定人口统计客户细分的哪个品牌或兴趣具有最高配额。

## <a name="affinity-level-and-score"></a>相似性级别和分数

在每个扩充的客户配置文件中，我们将提供两个相关值：相似性级别和相似性分数。 这些值有助于确定与其他人口统计客户细分相比，该配置文件的人口统计客户细分中品牌或兴趣的相似性强度。

*相似性级别* 由四个级别组成，并且 *相似性分数* 是根据映射到相似性级别的100 分等级计算的。

|相似性级别 |关联分数  |
|---------|---------|
|非常高     | 85-100       |
|高     | 70-84        |
|中     | 35-69        |
|低     | 1-34        |

取决于想要用于测量相似性的粒度，您可以使用相似性级别或分数。 相似性分数使您可以更精确地进行控制。

## <a name="share-of-voice-sov"></a>配额 (SoV)

我们用 100 分量表计算 SoV。 每个已扩充客户配置文件的所有品牌或兴趣的总 SoV 加起来为 100。 与相似性不同，SoV 与您选择的品牌和兴趣相关。 例如，如果所选品牌是 ('Microsoft', 'GitHub') 与 ('Microsoft', 'LinkedIn')，则“Microsoft”的 SoV 值可能不同。

## <a name="supported-countriesregions"></a>支持的国家/地区

目前，我们支持以下国家/地区选项：澳大利亚、加拿大（英语）、法国、德国、英国或美国（英语）。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

   - 要配置品牌相关性和 SoV 扩充，在 **品牌** 磁贴上选择 **扩充我的数据**。

   - 要配置兴趣相关性和 SoV 扩充，在 **兴趣** 磁贴上选择 **扩充我的数据**。

   > [!div class="mx-imgBorder"]
   > ![品牌和兴趣磁贴。](media/BrandsInterest-tile-Hub.png "品牌和兴趣磁贴")

1. 查看概览，然后选择 **下一步**。

1. 要更改您的国家或地区，选择 **国家/地区** 旁边的 **更改**。 在 **国家/地区设置** 窗格中，选择 [支持的国家/地区](#supported-countriesregions)，然后选择 **应用**。

   > [!NOTE]
   > 在选择自己的品牌时，系统会基于所选的国家/地区提供建议。 在选择行业时，您将基于所选国家/地区获得最相关的品牌或兴趣。

1. 使用以下一个或两个选项选择最多五个品牌或兴趣：

   - **行业**：从下拉列表中选择您的行业，然后从该行业的顶部品牌或兴趣中进行选择。
   - **选择您自己的项目**：输入与组织相关的品牌或兴趣，然后从匹配的建议中进行选择。 如果我们未列出您在查找的品牌或兴趣，请使用 **建议** 链接向我们发送反馈。

1. 选择 **下一步**，查看您的默认扩充首选项并根据需要进行更新。

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="扩充首选项窗口的屏幕截图。":::

1. 选择 **下一步**。

1. 选择 **客户数据集**，然后选择您想要使用来自 Microsoft 的数据扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 选择 **下一步**。

1. 将您的字段从您的统一客户实体映射到 Microsoft 数据。

   > [!NOTE]
   > 至少需要出生日期或性别属性。 国家/地区以及至少城市（和省/市/自治区）或邮政编码为必填项。 我们建议在数据引入期间将出生日期转换为日期/时间类型。 或者，可以是采用 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 格式“yyyy-MM-dd”或“yyyy-MM-ddTHH:mm:ss”的字符串。

1. 选择 **下一步** 以完成字段映射。

1. 提供扩充的名称。 **输出实体名称** 会被自动选择。

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="兴趣查看和命名页面。":::

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

   在扩充配置文件时，我们将扩充为其获取选定品牌和兴趣的数据的所有客户配置文件，包括未在选定国家或地区的配置文件。 例如，如果您选择了德国，并且我们有可用于美国中的选定品牌和兴趣的数据，那么我们将扩充位于美国的个人资料。

## <a name="enrichment-results"></a>扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="运行扩充流程后预览结果。":::

结果包括 **相关性级别** 或 **配额** 图表。

从扩充创建的实体将列在 **数据** > **实体** 的 **扩充** 组下。 扩充的品牌数据会进入 **BrandAffinityFromMicrosoft** 和 **BrandShareOfVoiceFromMicrosoft** 实体。 兴趣数据位于 **InterestAffinityFromMicrosoft** 和 **InterestShareOfVoiceFromMicrosoft** 实体中。

## <a name="see-enrichment-data-on-the-customer-card"></a>查看客户卡中的扩充数据

还可以在单个客户卡上查看品牌和兴趣 SoV。 转到 **客户**，然后选择客户配置文件。 在客户卡中，您将根据该客户人口统计配置文件中的用户查找品牌或兴趣 SoV 图表。

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含扩充后数据的客户卡。":::

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
