---
title: Power BI 连接器
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 连接器。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477077"
---
# <a name="connector-for-power-bi-preview"></a>适用于 Power BI 的连接器（预览版）

使用 Power BI Desktop 为您的数据创建可视化。 使用您的统一客户数据生成更多见解和构建报告。

## <a name="prerequisites"></a>先决条件

- 您具有统一的客户配置文件。
- 您的计算机上已安装最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)。 [了解有关 Power BI Desktop 的更多信息](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)。

## <a name="configure-the-connector-for-power-bi"></a>配置适用于 Power BI 的连接器

1. 在 Power BI Desktop 中，选择 **文件** > **获取数据**。

1. 选择 **查看更多**，然后搜索 **Dynamics 365 Customer Insights**

1. 选择 **连接**。

1. 使用用于 Customer Insights 的相同组织帐户 **登录**，然后选择 **连接**。
   > [!NOTE]
   > 您在此步骤中指定的帐户用于从 Customer Insights 获取数据，不需要与您登录 Power BI 所使用的帐户相同。 若要重置用于数据提取的帐户，请打开 Power BI，然后转到 **文件** > **选项** > **设置** > **数据源设置**。 在数据源列表中，选择 **Dynamics 365 Customer Insights 登录**，然后选择 **清除权限**。  

1. 在 **导航器** 对话框中。 您将看到有权访问的所有环境的列表。 展开环境并打开任何文件夹（实体、度量、客户细分、扩充）。 例如，打开 **实体** 文件夹，查看可导入的所有实体。

   ![Power BI连接器导航器](media/power-bi-navigator.png "Power BI 连接器导航器")

1. 选中要包含的实体旁边的复选框，然后 **加载**。 可以从多个环境选择多个实体。

1. 加载实体时，您将看到“正在加载”对话框。 在已加载所有选择的实体后，您可以使用 Power BI 的功能可视化数据。

## <a name="large-data-sets"></a>大型数据集

Power BI 的 Customer Insights 连接器用于最多包含 100 万个客户配置文件的数据集。 导入更大的数据集可能会运行，但需要花费较长时间。 而且，此过程还可能由于 Power BI 限制而超时。 有关详细信息，请参阅 [Power BI：针对大型数据集的建议](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)。 

### <a name="work-with-a-subset-of-data"></a>使用数据的子集

考虑使用数据的子集。 例如，您可以创建[客户细分](segments.md)，而不是将所有客户记录导出到 Power BI。

## <a name="troubleshooting"></a>疑难解答​​

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights 环境不会显示在 Power BI 中

在访问群体见解中的两个相同实体之间定义了多种[关系](relationships.md)的环境在 Power BI 连接器中不可用。

您可以标识和删除重复的关系。

1. 在访问群体见解中，在 Power BI 中缺少的环境上转到 **数据** > **关系**。
2. 识别重复关系：
   - 检查是否在这两个实体之间定义了多种关系。
   - 检查在统一过程中都包含的两个实体之间是否创建了关系。 在统一过程中包括的所有实体之间定义了隐式关系。
3. 删除标识的任何重复关系。

在删除重复的关系后，尝试再次配置 Power BI 连接器。 该环境现在应该可用了。

[!INCLUDE[footer-include](../includes/footer-banner.md)]

