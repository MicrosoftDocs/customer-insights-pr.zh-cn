---
title: 基于活动的建议客户细分。
description: 让机器学习功能根据客户活动帮助您查找新客户细分和感兴趣的客户细分。
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645851"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>基于活动数据的建议客户细分（预览版）

根据引入到 Customer Insights 的客户活动数据发现感兴趣的客户细分。 活动数据的示例包括交易、支持通话持续时间、购买或退货。 为了建议客户细分，将分析活动数据以了解最近情况、频率和货币值（或持续时间）。 或者，您可以生成[建议的客户细分以改进度量或更好地了解是什么对属性产生了影响](suggested-segments.md)。

:::image type="content" source="media/suggested-segments-tab.png" alt-text="建议的客户细分选项卡，显示了基于活动和基于属性的客户细分的客户细分建议。":::

## <a name="categorize-customers-by-activity"></a>按活动对客户分类

通过 Customer Insights 中可用的[活动数据](activities.md)，我们可以生成表示客户组的建议：

- 最活跃的客户 
- 购买最多的客户 
- 创造收入最多的客户 
- 最近没有活动的客户 
- 经常与您的公司交互的客户  

如果您有零售业务，您可以找出哪些客户创造的收入最高并奖励他们优惠券。 或者，您可以识别临时客户并提议他们加入奖励计划，以便他们更频繁地访问您的公司。
如果您任职于提供公共医疗保健服务的医疗保健公司，并且您的目标是最大程度地减少单个患者的费用。 这样做的一个方法可能是在尽可能少的访问中提供最佳护理来减少重复访问。 在这种情况下，您的目标就是保持访问频率较低，并将患者经常性成本降到最低。 或者，您可以确定约会频繁且经常性成本高的患者的客户细分，并分析这些情况以改善个人治疗。 

## <a name="required-data"></a>所需数据

系统根据选定的输入数据生成建议。 

- 客户配置文件：特定客户细分的所有客户或成员。 

- 时间段：上个月、去年或任何自定义期限。

- 活动类型：购买、零售交易、联机交易、客户支持案例、订阅等。  

- Customer Insights 中包含活动数据的实体：UnifiedActivity 实体或特定活动的实体。 

- 要包含的维度：最近数据、频率或货币维度，具体取决于业务要求。

## <a name="generate-suggested-segments"></a>生成建议的客户细分

1. 转到 **客户细分**。

1. 选择 **建议（预览版）** 选项卡。

1. 选择 **查找新建议** 并选择 **查看或预计客户行为**。 选择 **开始** 以运行引导式体验。

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="基于活动的建议细分的配置向导的第一步。":::

1. 提供所需的输入数据并选择 **下一步** 继续。

   - 选择客户：包括所有客户或特定客户细分。
   - 选择活动：选择活动类型和描述该活动的实体。
   - 首选项：设置要考虑的时间段和建议的因素，并映射属性。

1. 检查您的输入并选择 **运行** 以运行模型并生成建议。

1. 根据客户配置文件和所选活动的数量，可能需要几分钟才能完成。 

在生成建议后，可以按您最感兴趣的维度或值筛选建议。 

## <a name="view-details-of-a-suggested-segment"></a>查看建议的客户细分详细信息

生成建议之后，在 **基于活动的建议** 部分中，您将会发现 **客户细分** > **建议（预览）** 中列出了这些建议。

:::image type="content" source="media/suggested-segments-details.png" alt-text="展开的侧窗格，其中显示了建议的客户细分的详细数据。":::

针对建议的客户细分选择 **查看建议**，以查看该客户细分的详细信息。 侧窗格提供了与目标组比较的每个维度范围等详细信息。 它还突出显示该客户细分中潜在成员的数量以及占总客户数的对应百分比。 如果要将建议保留为客户细分，请选择 **创建客户细分**。    

## <a name="save-a-suggestion-as-a-segment"></a>将建议另存为客户细分

1. 转到 **客户细分** > **建议（预览版）**。

1. 选择要保存的客户细分。 

1. 在侧窗格中，选择 **创建客户细分**。 

1. 保存客户细分后，它将显示在 **所有客户细分** 选项卡上的客户细分列表中。可以[像刷新或删除任何其他客户细分那样刷新或删除](segments.md)该客户细分。 您无法编辑客户细分详细信息。 但是，您可以更改建议的输入条件并生成不同的建议。

## <a name="refresh-or-edit-a-set-of-suggestions"></a>刷新或编辑一组建议

1. 转到 **客户细分** > **建议（预览版）**，在 **基于活动的建议** 部分中查找客户细分。

1. 选择 **刷新建议** 以刷新建议，同时保留配置的属性。 或者选择 **编辑建议** 以修改配置的属性。 系统将重新运行该流程，根据最新数据生成客户细分建议，并替换当前的建议。

[!INCLUDE [footer-include](includes/footer-banner.md)]
