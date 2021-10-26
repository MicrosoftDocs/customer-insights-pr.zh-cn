---
title: 使用来自 Microsoft 的数据扩充客户配置文件
description: 使用来自 Microsoft 的专有数据用品牌和兴趣相似性扩充客户配置文件。
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 51b150cbf5d9cfb3a5df42e680bcfa57ec5496cb
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617866"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>使用品牌和兴趣相似性扩充客户配置文件（预览版）

使用 Microsoft 的专有数据用品牌和兴趣相似性扩充客户配置文件。 这些相似性基于使用人口统计信息与客户相似的用户的数据。 这些信息可帮助您根据客户在特定品牌和兴趣方面的相似性更好地了解和细分客户。

在访问群体见解中，转到 **数据** > **扩充** 以[配置和查看扩充](enrichment-hub.md)。

若要配置品牌相似性扩充，请转到 **发现** 选项卡，并选择 **品牌** 磁贴上的 **扩充我的数据**。

若要配置兴趣相似性扩充，请转到 **发现** 选项卡，并选择 **兴趣** 磁贴上的 **扩充我的数据**。

   > [!div class="mx-imgBorder"]
   > ![品牌和兴趣磁贴。](media/BrandsInterest-tile-Hub.png "品牌和兴趣磁贴")

## <a name="how-we-determine-affinities"></a>我们如何确定相似性

我们使用 Microsoft 的在线搜索数据来查找不同人口统计细分市场（按年龄、性别或位置定义）的品牌和兴趣相似性。 品牌或兴趣的联机搜索量决定人口统计细分与其他细分相比在该品牌或兴趣方面的相似程度。

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

## <a name="supported-countriesregions"></a>支持的国家/地区

目前，我们支持以下国家/地区选项：澳大利亚、加拿大（英语）、法国、德国、英国或美国（英语）。

若要选择国家或地区，请打开 **品牌扩充** 或 **兴趣扩充**，然后选择 **国家/地区** 旁边的 **更改**。 在 **国家/地区设置** 窗格中，选择一个选项，然后选择 **应用**。

### <a name="implications-related-to-country-selection"></a>与国家/地区选择相关的含义

- 在[选择自己的品牌](#define-your-brands-or-interests)时，系统会基于所选的国家/地区提供建议。

- 在[选择行业](#define-your-brands-or-interests)时，您将基于所选国家/地区获得最相关的品牌或兴趣。

- 在[扩充配置文件](#refresh-enrichment)时，我们将扩充为其获取选定品牌和兴趣的数据的所有客户配置文件，包括未在选定国家或地区的配置文件。 例如，如果您选择了德国，并且我们有可用于美国中的选定品牌和兴趣的数据，那么我们将扩充位于美国的个人资料。

## <a name="configure-enrichment"></a>配置扩充

引导式体验可帮助您完成扩充配置。 

### <a name="define-your-brands-or-interests"></a>定义您的品牌或兴趣

使用以下一个或两个选项选择最多五个品牌或兴趣：

- **行业**：从下拉列表中选择您的行业，然后从该行业的顶部品牌或兴趣中进行选择。
- **选择您自己的项目**：输入与组织相关的品牌或兴趣，然后从匹配的建议中进行选择。 如果我们未列出您在查找的品牌或兴趣，请使用 **建议** 链接向我们发送反馈。

### <a name="review-enrichment-preferences"></a>查看扩充首选项

查看默认扩充首选项，然后根据需要更新这些首选项。

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="扩充首选项窗口的屏幕截图。":::

### <a name="select-entity-to-enrich"></a>选择要扩充的实体

选择 **扩充的实体**，然后选择您希望利用 Microsoft 提供的公司数据扩充的数据集。 您可以选择客户实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。

### <a name="map-your-fields"></a>映射字段

映射来自统一客户实体的字段，以定义希望系统用于扩充客户数据的人口统计客户细分。 映射国家/地区，并至少映射“出生日期”或“性别”属性。 此外，必须至少映射一个市/县（和省/市/自治区）或邮政编码。 选择 **编辑** 以定义字段的映射，然后在完成后选择 **应用**。 选择 **保存** 完成字段映射。

支持下列格式和值（值不区分大小写）：

- **出生日期**：我们建议在数据引入期间将出生日期转换为日期/时间类型。 或者，可以是采用 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 格式“yyyy-MM-dd”或“yyyy-MM-ddTHH:mm:ss”的字符串。
- **性别**：男、女、未知。
- **邮政编码**：美国五位数的邮政编码，其他国家或地区的标准邮政编码。
- **市/县**：英文的市/县名称。
- **州/省**：美国和加拿大的两个字母的缩写。 澳大利亚的两个或三个字母的缩写。 不适用于法国、德国或英国。
- **国家/地区**：

  - US：United States of America、United States、USA、US、America
  - CA：Canada、CA
  - GB：United Kingdom、UK、Great Britain、GB、United Kingdom of Great Britain and Northern Ireland、United Kingdom of Great Britain
  - AU：澳大利亚、AU、澳大利亚英联邦
  - FR：France、FR、French Republic
  - DE：Germany、German、Deutschland、Allemagne、DE、Federal Republic of Germany、Republic of Germany

## <a name="review-and-name-the-enrichment"></a>查看并命名扩充

最后，您可以针对扩充查看信息并提供名称。

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="兴趣查看和命名页面。":::

## <a name="refresh-enrichment"></a>刷新扩充

为人口统计数据配置品牌、兴趣和字段映射之后运行扩充。 若要启动此流程，请在品牌或兴趣配置页上选择 **运行**。 此外，还可以让系统在执行计划的刷新期间自动运行扩充。

根据客户数据的大小，可能需要几分钟，扩充才能运行完成。

> [!TIP]
> 对于任务/流程，有[六种类型的状态](system.md#status-types)。 此外，大多数流程[取决于其他下游流程](system.md#refresh-policies)。 可以选择流程状态以查看有关整个作业的进度的详细信息。 针对一个作业任务选择 **查看详细信息** 后，您将找到其他信息：处理时间、上次处理日期以及与该任务关联的所有错误和警告。

## <a name="enrichment-results"></a>扩充结果

运行扩充流程之后，转到 **我的扩充**，以在扩充后的客户配置文件中查看扩充的客户总数和品牌或兴趣明细。

:::image type="content" source="media/my-enrichments.png" alt-text="运行扩充流程后预览结果。":::

通过在图表中选择 **查看扩充的数据** 查看扩充的数据。 扩充的品牌数据将进入 **BrandAffinityFromMicrosoft** 实体。 兴趣的数据位于 **InterestAffinityFromMicrosoft** 实体中。 还可以发现 **数据** > **实体** 中的 **扩充** 组内列出了这些实体。

您将看到一个图表，其中显示一段时间扩充的一些客户配置文件和扩充后实体的预览。 在预览磁贴中选择 **详细显示** 可查看扩充后的实体。

## <a name="see-enrichment-data-on-the-customer-card"></a>查看客户卡中的扩充数据

也可以在各客户卡中查看品牌和兴趣相似度。 转到 **客户**，然后选择客户配置文件。 在客户卡中，您会找到品牌或兴趣的图表，此图表反映了该客户的人口统计特征中人们具有的品牌或兴趣相似性。

:::image type="content" source="media/enrichment-customer-card.png" alt-text="包含扩充后数据的客户卡。":::

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
