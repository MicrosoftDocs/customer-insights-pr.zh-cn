---
title: Power BI 连接器（预览版）
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 连接器。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196659"
---
# <a name="power-bi-connector-preview"></a>Power BI 连接器（预览版）

使用 Microsoft Power BI Desktop 为数据创建可视化效果。 使用您的统一客户数据生成更多见解和构建报告。

## <a name="prerequisites"></a>先决条件

- 统一客户配置文件。
- 您的计算机上安装了最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)。 [了解有关 Power BI Desktop 的更多信息](/power-bi/desktop-what-is-desktop)。

## <a name="configure-the-connector-for-power-bi"></a>配置适用于 Power BI 的连接器

1. 在 Power BI Desktop 中，选择 **文件** > **获取数据**。

1. 选择 **查看更多**，然后搜索 **Dynamics 365 Customer Insights**

1. 选择 **连接**。

1. 使用用于 Customer Insights 的相同组织帐户 **登录**，然后选择 **连接**。
   > [!NOTE]
   > 您在此步骤中指定的帐户用于从 Customer Insights 获取数据，不需要与您登录 Power BI 所使用的帐户相同。 若要重置用于数据提取的帐户，请打开 Power BI，然后转到 **文件** > **选项** > **设置** > **数据源设置**。 在数据源列表中，选择 **Dynamics 365 Customer Insights 登录**，然后选择 **清除权限**。  

1. 在 **导航器** 对话框中，查看您有权访问的所有环境的列表。 展开环境并打开任何文件夹（实体、度量、客户细分、扩充）。 例如，打开 **实体** 文件夹，查看可导入的所有实体。

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI 连接器导航器。":::

1. 选中要包含的实体旁边的复选框，然后 **加载**。 可以从多个环境选择多个实体。

   加载实体时会显示加载对话框。 在已加载所有选择的实体后，使用 Power BI 的功能可视化数据。

## <a name="large-data-sets"></a>大型数据集

Power BI 的 Customer Insights 连接器用于最多包含 100 万个客户配置文件的数据集。 导入较大数据集时可能有效，但需要很长时间，且可能由于 Power BI 限制而超时。 有关详细信息，请参阅 [Power BI：针对大型数据集的建议](/power-bi/admin/service-premium-what-is#large-datasets)。

### <a name="work-with-a-subset-of-data"></a>使用数据的子集

考虑使用数据的子集。 例如，创建[客户细分](segments.md)，而不是将所有客户记录导出到 Power BI。

## <a name="troubleshooting"></a>疑难解答​​

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights 环境不会显示在 Power BI 中

在 Customer Insights 中的两个相同实体之间定义了多种[关系](relationships.md)的环境在 Power BI 连接器中将不可用。

标识和删除重复的关系。

1. 针对 Power BI 中缺少的环境转到 **数据** > **关系**。
1. 识别重复关系：
   - 检查是否在这两个实体之间定义了多种关系。
   - 检查在统一过程中都包含的两个实体之间是否创建了关系。 在统一过程中包括的所有实体之间定义了隐式关系。
1. 删除标识的任何重复关系。

在删除重复的关系后，尝试再次配置 Power BI 连接器。

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>在 Power BI Desktop 中加载实体时出现日期字段错误

加载包含日期格式（如 MM/DD/YYYYY）的字段的实体时，您可能会因区域设置格式不匹配而遇到错误。 当您的 Power BI Desktop 文件设置为英语（美国）以外的其他区域设置时，会出现此不匹配的情况，因为 Customer Insights 中的日期字段以美国格式保存。

Power BI Desktop 文件具有在检索数据时应用的单个区域设置。 要修复日期错误，[将 .BPI 文件的区域设置](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop)设置为英语（美国）。

[!INCLUDE [footer-include](includes/footer-banner.md)]
