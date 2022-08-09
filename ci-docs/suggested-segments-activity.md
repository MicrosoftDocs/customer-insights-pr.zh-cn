---
title: 根据活动建议的客户细分（预览版）
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170578"
---
# <a name="suggested-segments-based-on-activity-preview"></a>根据活动建议的客户细分（预览版）

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
如果您提供公共医疗服务，您的目标是尽量减少患者的费用，您可以尝试通过尽可能少的就诊次数提供可用的最佳医疗服务来减少重复就诊。 在这种情况下，您的目标就是保持访问频率较低，并将患者经常性成本降到最低。 或者，您可以确定约会频繁且经常性成本高的患者的客户细分，并分析这些情况以改善个人治疗。

## <a name="required-data"></a>所需数据

系统根据选定的输入数据生成建议。

- 客户配置文件：特定客户细分的所有客户或成员。

- 时间段：上个月、去年或任何自定义期限。

- 活动类型：购买、零售交易、联机交易、客户支持案例、订阅等。  

- Customer Insights 中包含活动数据的实体：UnifiedActivity 实体或特定活动的实体。

- 要包含的维度：最近数据、频率或货币维度，具体取决于业务要求。

## <a name="generate-suggested-segments"></a>生成建议的客户细分

1. 转到 **客户细分**，然后选择 **建议(预览)** 选项卡。

1. 选择 **查找新建议** 并选择 **查看或预计客户行为**。 选择 **开始**。

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="基于活动的建议细分的配置向导的第一步。":::

1. 提供所需的输入数据并选择 **下一步**。

   - 选择客户：包括所有客户或特定客户细分。
   - 选择活动：选择活动类型和描述该活动的实体。
   - 首选项：设置要考虑的时间段和建议的因素，并映射属性。

1. 检查您的输入并选择 **运行** 以运行模型并生成建议。

根据客户配置文件和所选活动的数量，可能需要几分钟才能完成。

在生成建议后，可以按您最感兴趣的维度或值筛选建议。

## <a name="manage-suggested-segments"></a>管理建议的客户细分

转到 **客户细分**，选择 **建议（预览）** 选项卡。在 **基于活动的建议** 部分，选择一个建议的客户细分查看可用操作。

- **查看建议** 以查看该客户细分的详细信息，如与目标组比较的每个维度的范围。 它还突出显示该客户细分中潜在成员的数量以及占总客户数的对应百分比。
- **创建客户细分** 来将建议保存为客户细分。 它显示在 **所有客户细分** 选项卡上，可以[刷新或删除](segments.md)。 您无法编辑客户细分详细信息。 但是，您可以更改建议的输入条件并生成不同的建议。
- **编辑建议** 以修改将替换当前建议的配置的属性。
- **刷新建议** 以刷新建议，同时保留配置的属性。

[!INCLUDE [footer-include](includes/footer-banner.md)]
