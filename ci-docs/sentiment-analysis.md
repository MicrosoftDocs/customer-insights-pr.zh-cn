---
title: 分析客户反馈中的情绪（预览版）
description: 了解如何在 Dynamics 365 Customer Insights 中对客户反馈使用情绪分析模型。
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055525"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>分析客户反馈中的情绪（预览版）

如今，客户期望高质量的产品、服务和体验。 特别是提供反馈的客户。 对于组织而言，在不降低准确性和增加劳动力成本的情况下分析不断增加的数据量是非常具有挑战性的。 Dynamics 365 Customer Insights 为客户反馈提供情绪分析模型，让组织能够以更低的成本更准确地分析数据。

情绪分析让您能够整合客户情绪并确定哪些业务方面有改进机会。 此 Customer Insights 功能可帮助您了解哪些方面运作良好以及您需要解决哪些问题。 重点关注最相关和最有影响力的业务领域，以改善您的客户体验。 最终，它可以帮助您推动业务行动，实现能够带来高客户满意度和忠诚度的体验。

## <a name="overview"></a>概述

情绪分析功能为每个客户 ID 生成两个派生见解。 情绪分数（-5 到 5）和适用的业务方面（业务领域）列表一起帮助您更好地了解客户反馈。 

此信息可以帮助您实现以下结果： 
- 整体了解客户对品牌或组织的情绪
- 识别具有负面情绪的客户，以专注于您的市场活动和互动，并进行优化以获得更高的回报  
- 确定具有客户指出问题的各个业务方面  
- 根据客户的情绪细分客户，通过有针对性的销售、营销和支持工作开展个性化市场活动
- 通过解决客户提到的问题领域或机会来优化业务运营
- 发现表现良好的业务方面并通过忠诚度和促销计划奖励满意的客户

为确保您可以信任模型的结果，我们提供有关模型如何作决定的透明信息。 您将获得一个影响模型将特定情绪分数或业务方面分配给哪些反馈评论的决定的字词列表。  

我们使用两个 **自然语言处理 (NLP) 模型**：第一个模型为每个反馈评论分配情绪分数。 第二个模型将每个反馈与所有适用的业务方面相关联。 这些模型使用来自社交媒体、零售、餐厅、消费品和汽车行业的公共数据进行训练。    
  
模型将其与反馈数据关联的预定义业务方面包括：
-   帐户管理
-   结帐和付款
-   客户支持
-   店内自取
-   包装装运和检索
-   预订购
-   单价
-   隐私与安全
-   促销和奖励
-   收据和保修
-   返回 Exchange 和取消
-   履行准确性
-   网站/应用质量

> [!NOTE]
> 目前，我们仅支持对英文客户反馈的情绪分析。 未来将支持更多语言。 如果上载了其他语言的反馈，模型仍会返回结果。 但这些结果会不准确。 

## <a name="prerequisites"></a>先决条件

情绪分析基于经过[数据统一过程](data-unification.md)的文本反馈数据。 我们强烈建议您事先[将反馈数据实体配置为语义类型的活动实体](map-entities.md#select-primary-key-and-semantic-type-for-attributes)（反馈类型）。 

要配置情绪分析模型，您至少需要有[参与者权限](permissions.md)。

Customer Insights 最多可以为单个模型运行处理 1000 万条反馈记录。 模型最多可以分析 128 个字词的反馈评论。 如果反馈评论更长，分析仅考虑前 128 个字词。

### <a name="data-requirements"></a>数据要求
  
需要以下数据属性：
- 统一客户 ID (UCID) 将文本反馈数据记录与单个客户匹配。 此 ID 是[数据统一过程](data-unification.md)的结果。
- 反馈 ID
- 反馈时间戳
- 反馈文本   

> [!TIP]
> 情绪分析需要客户的文本反馈。 当前只能配置一个反馈实体。 如果有多个反馈实体，您可以在数据引入开始之前将它们合并到 Power Query 中。

## <a name="configure-a-sentiment-analysis"></a>配置情绪分析 

1. 在 Customer Insights 中，转到 **智能** > **预测**。

1. 在 **客户情绪分析** 磁贴上，选择 **使用模型**。

1. 在 **客户情绪分析（预览）** 窗格中，选择 **开始**。

1. 在 **模型名称** 步骤中，为您的分析提供一个 **名称**。 

1. 提供 **业务方面输出实体名称** 和 **情绪分数输出实体名称**，然后选择 **下一步**。

1. 在 **所需数据** 步骤中，选择 **添加数据**。

   :::image type="content" source="media/sentiment-add-data.png" alt-text="在情绪分析模型中添加数据流。":::

1. 在 **添加数据** 窗格中，从列表中选择语义类型的 **反馈**。

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="选择反馈活动以用于情绪分析的配置步骤。":::

1. 选择要用于此情绪分析的活动，然后选择 **下一步**。
 
1. 将数据中的属性映射到模型属性。 选择 **保存** 以应用您的选择。 

1. 您将看到数据映射的状态。 选择 **下一步** 继续操作。 

1. 在 **查看模型详细信息** 步骤中，验证情绪分析的配置。 您可以返回到预测配置的任何部分。 选择 **保存并运行** 开始分析。 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="查看显示所有已配置项的情绪模型的步骤。":::

1. 选择 **完成** 退出配置体验。 此过程可能需要几个小时完成，具体取决于使用的数据量。 

## <a name="review-analysis-status"></a>查看分析状态

1.  转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。
2.  选择要查看的预测。
- **预测名称**：创建时提供的预测的名称。
- **预测类型**：用于预测的模型的类型。
- **输出实体**：用于存储预测输出的实体的名称。 转到 **数据** > **实体** 以查找具有此名称的实体。
- **预测字段**：仅针对某些类型的预测填充此字段，而不在客户生存期值预测中使用它。
- **状态**：预测运行的状态。
  - **已排队**：预测正在等待其他流程完成。
  - **刷新**：预测当前正在运行，以创建将流入输出实体的结果。
  - **失败**：预测运行已失败。 有关更多详细信息，请查看日志。
  - **已成功**：预测已成功。 选择垂直省略号下面的视图，以查看预测结果。
- **已编辑**：预测配置的更改日期。
- **上次刷新时间**：预测在输出实体中获得刷新结果的日期。

## <a name="manage-sentiment-analysis"></a>管理情绪分析

您可以优化、刷新或删除预测或解决预测相关问题。 查看输入数据可用性报告，了解如何更快、更可靠地进行预测。 有关详细信息，请参阅[管理预测](manage-predictions.md)。

## <a name="review-analysis-results"></a>查看分析结果
 
1. 转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。 
1. 选择您要查看其结果的预测名称。 在此例中，选择您要查看的情绪分析。 

### <a name="summary-tab"></a>“摘要”标签页

在结果页中，有四个主要的数据部分。 

- **平均情绪分数**：帮助您了解所有客户的整体情绪。 情绪分数分为三类： 
  1.    负面 (-5 > 2)
  2.    中性 (-1 > 1)
  3.    正面 (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="整体客户情绪的可视表示。":::

- **按情绪分数划分客户**：根据客户的情绪分数将客户分为负面、中性和正面组。 将鼠标悬停在直方图中的条形上查看每组的客户数量和平均情绪分数。 这些数据可以帮助您根据客户的情绪分数[创建客户细分](segments.md)。  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="显示三个情绪组的客户情绪的条形图。":::

- **随时间发展的平均情绪分数**：客户情绪可能会随着时间发生变化。 我们提供数据时间范围内客户情绪的发展趋势。 此视图可以帮助您衡量季节性促销、产品发布或其他有时限的干预措施对客户情绪的影响。 从下拉菜单中选择感兴趣的年份来查看图表。 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="以线条表示的随时间发展的情绪分数变化历史图表。":::
 
- **业务方面的情绪**：此表列出了跨各个业务方面的平均情绪。 可以帮助您衡量业务的哪些方面已经满足客户要求或哪些方面需要更多关注。 与任何受支持业务方面都不相符的反馈记录归类在 **其他** 下。 默认情况下，此表按字母顺序排序。 您可以选择表标头来修改排序。

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="包含相关情绪值和提及它的客户数量的业务方面列表。":::
 
  选择业务方面的名称可以查看模型如何识别业务方面的其他信息。 此窗格有两个部分： 

  - **影响字词**：显示对 AI 模型在客户反馈中识别业务方面影响最大的的字词。 
    **显示冒犯性词语**：允许您在来自原始客户反馈数据的列表中包含冒犯性词语。 默认情况下，此部分处于关闭状态。  冒犯性字词屏蔽由 AI 模型提供支持，可能无法检测到所有冒犯性字词。 我们会继续迭代和训练分类器以获得最佳性能。 如果您检测到未按预期过滤掉的冒犯性字词，请告诉我们。 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="带有显示或隐藏冒犯性字词的切换的影响字词列表。":::
 
  - **反馈示例**：在数据中显示实际反馈记录。 字词根据它们对识别业务方面的影响进行颜色编码。 


### <a name="influential-words-analysis-tab"></a>影响字词分析选项卡

有三个介绍其他信息的部分解释情绪模型的工作原理。
  
1. **引发正面情绪的主要字词**：显示影响 AI 模型识别客户反馈中正面情绪的主要字词。  
2. **引发负面情绪的主要字词**：显示影响 AI 模型识别客户反馈中负面情绪的主要字词。  
3. **反馈示例**：显示实际反馈记录，一条带有负面情绪，一条带有正面情绪。 反馈记录中的字词会根据它们对指定情绪分数的贡献突出显示。 对正面情绪分数有贡献的字词以绿色突出显示。 对负面分数有贡献的字词以红色突出显示。
   选择 **查看更多** 可以加载更多反馈示例，将会提供有关情绪模型工作原理的更多信息和上下文。
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="有关客户反馈的情绪分析示例。":::
 
**显示冒犯性词语**：允许您在来自原始客户反馈数据的列表中包含冒犯性词语。 默认情况下，此部分处于关闭状态。  冒犯性字词屏蔽由 AI 模型提供支持，可能无法检测到所有冒犯性字词。 我们会继续迭代和训练分类器以获得最佳性能。 如果您检测到未按预期过滤掉的冒犯性字词，请告诉我们。 

## <a name="act-on-analysis-results"></a>对分析结果采取行动

选择模型结果页面顶部的 **创建客户细分**，您可以轻松地开始从情绪分析结果页面创建新客户细分。

:::image type="content" source="media/create-segment-model.png" alt-text="带有预测模型选项的命令栏。":::
 
## <a name="potential-bias"></a>潜在偏差

与使用预测性人工智能的任何功能一样，您应该注意用于预测客户情绪的数据中的潜在偏差。 例如，如果您仅以数字方式收集反馈，您可能会错过主要与您当面开展业务的客户的反馈，这可能会影响功能的输出。

由于此功能使用自动化方式来评估数据并根据该数据进行预测，因此它能够用作分析方法，该条款由通用数据保护条例（“GDPR”）定义。 使用此功能处理数据时可能会受到 GDPR 或其他法律或法规的约束。 您负责确保您对 Dynamics 365 Customer Insights 的使用（包括情绪分析）遵守所有适用的法律和法规，包括与隐私、个人数据、生物识别数据、数据保护和通信保密性相关的法律。

[!INCLUDE [footer-include](includes/footer-banner.md)]
