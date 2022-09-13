---
title: 根据度量建议的客户细分（预览）
description: 让机器学习功能帮助您根据客户属性找到感兴趣的新客户细分。
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170946"
---
# <a name="suggested-segments-based-on-measures-preview"></a>根据度量建议的客户细分（预览）

借助 AI 模型发现感兴趣的客户细分。 这项由机器学习提供支持的功能可根据度量或客户属性建议客户细分。 它可以帮助改善您的关键绩效指标 (KPI) 或更好地了解属性在其他属性的上下文中的影响。

> [!NOTE]
> 建议的客户细分功能使用自动化方法评估数据，然后根据这些数据作出预测。 因此，它能够用作分析方法，因为该术语由一般数据保护条例 (“GDPR”) 定义。 使用此功能处理数据时可能会受到 GDPR 或其他法律或法规的约束。 您有责任确保在使用 Dynamics 365 Customer Insights（包括此功能）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。

:::image type="content" source="media/suggested-segments.png" alt-text="在侧窗格中显示建议详细信息的建议客户细分页面。":::

## <a name="suggested-segments-to-improve-your-kpis"></a>用于改进 KPI 的建议客户细分

如果您使用[创建的度量](measures.md)来帮助跟踪您的 KPI，创建客户细分来查看对 KPI 的影响。 您可以使用此信息来运行具有高度针对性的市场活动。

例如，您可以跟踪一个名为 *TotalSpendPerCustomer* 的度量。 作为一个企业，您喜欢看到此数目增加。 如果选择度量作为主要属性，选择要评估影响力的属性。 假设有 *成员资格层*、*成员资格期间* 和 *职业*。 然后，Customer Insights 可以建议一个客户细分，告诉您谁是该度量的最大影响因素。 例如，作为 *金牌* 成员并且已与您做生意 *至少 5 年* 的 *会计人员* 是 *TotalSpendPerCustomer* 的最大影响者。 对于每个建议，您都会获得一个估计的客户细分大小。 您可以使用此信息为目标受众创建市场活动。

## <a name="understand-what-influences-a-customer-attribute"></a>了解影响客户属性的因素

您可以选择客户属性而不是度量作为主要属性。 根据您选择的影响属性，AI 模型会创建一系列建议，以显示所选属性如何影响主要属性。

例如，您选择 *奖励成员（是/否）* 作为主要属性。 *服务期*、*职业* 和 *支持票证数* 被设置为其他影响属性。 AI 模型可能会建议客户细分，并指明大部分任期在两年以上的 IT 专业人员是奖励成员。 另一个建议可能会强调，任期在一年以上且支持票证少于三张的会计师是奖励会员。

## <a name="artificial-intelligence-usage"></a>人工智能的使用

决策树算法使用主要属性和影响属性建议感兴趣的客户细分。 这些建议基于 AI 算法选择的规则或模式。 系统仅将与普通人群明显不同的客户细分显示为建议。 系统根据所选度量或主要属性与普通人群进行比较。

### <a name="responsible-ai"></a>负责 AI

利用建议的客户细分，您可以选择属性来创建新的客户细分并处理您选择的数据。 在选择属性（包括种族、性取向或性别等敏感属性）时，必须确保可以并且应该处理该数据。 您有责任遵守适用于您组织的任何法律，并遵守组织的原则和隐私政策。

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>具有分类值和数值的主要属性的不同结果

如果您选择数字属性或分类属性作为主要属性，则客户细分建议会有所不同。 类别属性中的值包含两个或更多个类别或类型。 数值属性包含定量数据，并具有与之相关的度量意义。

如果以 *年收入* 或 *成员期间* 之类的数字属性为主要属性，那么系统会建议与所有客户相比该数字属性的平均值较高或较低的客户细分。

如果以分类属性（例如 *客户满意度*）作为主要属性，则会导致所建议客户细分的属于特定类别的客户百分比与属于同一类别的所有客户的百分更高或更低。 例如，*客户满意度* 被选为主要属性，并且它包含三个类别（*低*‘、*中* 和 *高*）。 对于每个类别，将建议客户细分，在这些客户细分中，属于该类别的客户所占的比例与同一类别中占所有客户的比例相比更高或更低。 如果 22% 的所有客户具有 *较高* 满意度，则针对该类别只推荐 *较高* 满意度的客户所占比例比 22% 更高或更低的客户细分。 同样，如果其他类别（*低* 和 *中*）在统计上有意义，则会针对每个这样的类别建议客户细分。

> [!NOTE]
> 当前，我们仅支持最多具有 10 个类别的主要类别属性。 如果您要查看基于具有 10 个以上类别的主要属性的客户细分建议，建议您对某些类别进行分组，以将类别数量减少到 10 个或更少。 此限制仅适用于主要属性。 对于影响类别属性，我们当前最多支持 100 个类别。

## <a name="generate-suggested-segments"></a>生成建议的客户细分

1. 转到 **客户细分**，然后选择 **建议(预览)** 选项卡。

1. 选择 **查找新建议** 并选择 **改进度量/指标**。 选择 **开始**。

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="在建议的客户细分上选择改进度量。":::

1. 选择一个客户属性或度量作为主要属性，然后选择 **下一步**。

1. 选择影响属性并选择 **运行**。

   > [!TIP]
   > 选择多个影响属性可以提高评估它们如何影响主要属性的机率。 不要包括对主要属性没有影响的属性。 例如，如果您的所有客户都来自特定国家/地区，则不要包括 *国家/地区* 属性，因为它不会对输出产生任何影响。

根据客户配置文件和所选属性的数量，可能需要花费几分钟来处理所选属性。

## <a name="manage-suggested-segments"></a>管理建议的客户细分

转到 **客户细分**，选择 **建议（预览）** 选项卡。在 **基于属性的客户细分建议** 部分，选择一个建议的客户细分查看可用操作。

- **查看** 建议的客户细分详细信息和 AI 模型学习的属性值或规则。
- **另存为客户细分** 将建议保存为客户细分。 它显示在 **所有客户细分** 选项卡上，可以[刷新、编辑或删除](segments.md)。
- **编辑属性** 并修改将替换当前建议的配置的属性。
- **刷新建议** 以刷新建议，同时保留配置的属性。

## <a name="limitations"></a>限制

1. 估计的客户细分大小不匹配：如果您选择的主属性包含空值，则会影响客户细分建议中估计的客户细分大小。 保存此类客户细分时，实际客户细分大小可能与原始估计值不同。

2. 布尔类型主要属性不起作用：当前，我们仅支持字符串和数值类型的数据作为主要属性。

3. 建议的客户细分还不够明确：请记住，所选属性和这些属性的值分布会影响结果。 您可以更改影响属性，甚至可以更改主要属性，以获得不同的结果。

[!INCLUDE [footer-include](includes/footer-banner.md)]