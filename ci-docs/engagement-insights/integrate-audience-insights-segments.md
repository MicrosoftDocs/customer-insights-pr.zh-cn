---
title: 使用访问群体见解客户细分筛选参与见解报告
description: 使用访问群体见解对客户网站中参与见解捕获的行为数据进行交互式分析。
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461047"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>使用访问群体见解客户细分筛选参与见解报告

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

借助参与见解，可使用访问群体见解对您的网站中参与见解捕获的行为数据进行交互式分析。

## <a name="prerequisite"></a>先决条件

- 一个参与见解环境，您已在其中将访问群体见解客户细分数据链接到了一个在其中创建了客户细分和客户配置文件的访问群体见解环境。 更多信息：[创建参与见解与访问群体见解之间的链接](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>创建访问群体见解客户细分 

> [!IMPORTANT]
> 若要在参与见解中显示访问群体见解客户细分，首先必须[运行合并和下游流程](../audience-insights/merge-entities.md)。 下游流程非常重要，因为它们生成一个唯一的表，用于准备要与参与见解共享的访问群体见解客户细分。 （如果安排了系统刷新，其将自动包括下游流程。）

可在参与见解的现成报告或您创建的自定义报告中使用访问群体见解客户细分。 有关详细信息，请转到[现成配置文件报告](profile-reports.md)和[创建和编辑自定义报告](custom-reports.md)。

**在参与见解报告中使用访问群体见解客户细分**

1. 在 **工作区** 页面中，选择 **数据**，然后选择 **客户细分** 选项卡。

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="选择客户细分选项卡。":::

   >[!NOTE]
   > 如果选择访问群体见解，将转到访问群体见解，可在这里了解该客户细分是如何根据规则和逻辑创建的。 有关访问群体见解客户细分的详细信息，请参阅[查看和创建客户细分](../audience-insights/segments.md)。

2. 选择一个现成报告，或 [创建一个自定义报告](custom-reports.md)，然后选择 **添加条件**。 （对于本示例，我们选择 **页面视图** 报告。）

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="添加条件。":::

3. 选择 **按客户细分筛选**，展开 **客户细分类型** 列表，然后选择 **人口统计**。

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="选择人口统计客户细分类型。":::

4. 展开 **客户细分名称** 列表，然后选择一个访问群体见解客户细分。

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text=" 选择一个客户细分。":::

5. 您可以应用一个或多个客户细分，包括行为（参与见解）客户细分和人口统计（访问群体见解）客户细分。 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="限制为仅包含美国客户和主页客户细分的页面视图报告。":::

在上图中，已选择 **美国客户** 和 **主页** 客户细分，从而将 **页面视图** 报告限制为仅显示这两个客户细分。 


>[!NOTE]
> 可在参与见解中使用访问群体见解客户细分筛选现成报告、自定义报告和漏斗。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]