---
title: 预测概述
description: Dynamics 365 Customer Insights 应用程序涵盖的预测方案和选项。
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610179"
---
# <a name="predictions-overview"></a>预测概述

Dynamics 365 Customer Insights 提供各种选项，这些选项可以利用 AI 和机器学习来预测数据。

## <a name="out-of-box-models"></a>现成模型

开始预测数据的最简单方法是使用预定义的模型（通常称为现成模型）。 它们只需某些数据和结构便可快速生成见解。 以下模型可用：

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

- [客户生存期值](predict-customer-lifetime-value.md)：预测客户在与企业交互的整个期间的潜在收入。
- [产品推荐](predict-product-recommendation.md)：根据购买行为和具有类似购买模式的客户提出一套预测性产品建议。
- [订阅流失](predict-subscription-churn.md)：预测客户是否存在不再使用贵公司的订阅产品或服务的风险的模型。
- [交易流失](predict-transactional-churn.md)：预测单个客户是否会在特定期限内不再购买您的产品或服务。
- [情绪分析](sentiment-analysis.md)：分析客户反馈的情绪并确定经常提及的各个业务方面。

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

- [交易流失](predict-transactional-churn.md)：预测客户是否会在特定期限内不再购买您的产品或服务。

---

> [!TIP]
> 我们建议您定期使用更新的数据刷新现成可用的模型，以确保它们准确地通知您的业务用例。 当系统引入新的或更新的数据源时，数据会临时刷新。 但是，模型在这种情况下只会重新评分，然后继续使用现有的训练数据。
>
> 通过在配置过程中设置模型重新训练计划来配置 **更新计划**。 模型将按此计划重新训练和重新评分，您可以随时更改。

## <a name="azure-machine-learning-integration"></a>Azure 机器学习集成

如果组织已经根据 Azure 机器学习实验使用机器学习方案，则 Customer Insights 中的自定义模型功能有助于将点联系起来。 创建工作流，帮助您选择要从中生成见解的数据，并将结果映射到您的统一客户配置文件。 有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。

## <a name="manage-existing-predictions"></a>管理现有预测

转到 **智能** > **预测** 页面。 在 **我的预测** 选项卡上，查看您创建的预测、预测类型、输出实体名称、状态、上次编辑预测的时间以及上次刷新数据的时间。 您可以按任何列对预测列表进行排序。

选择预测可查看可用操作。

:::image type="content" source="media/predictions.png" alt-text="我的预测页面。":::

- **编辑** 预测以更改其属性。
- [**刷新**](#refresh-a-prediction)预测以包括最新数据。
- **查看** 预测详细信息。
- 用于查看错误、警告和建议的 [**输入数据可用性报表**](#view-the-input-data-usability-report)。
- **删除** 预测。

### <a name="refresh-a-prediction"></a>刷新预测

预测可以按计划自动刷新，也可以根据需要手动刷新。 要手动刷新所有预测，选择 **全部刷新**。 要手动刷新一个预测，选择该预测，然后选择 **刷新**。 若要 [计划自动刷新](schedule-refresh.md)，请转到 **管理** > **系统** > **计划**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>查看输入数据可用性报表

输入数据可用性报告提供了现成预测可能会生成的错误和警告的综合视图。 它还就如何提高模型性能提出了建议。

该报表在模型完成训练过程后可用。 无论是否成功完成训练，系统都将单独为每个模型创建此报表。

在 **我的预测** 选项卡上，选择预测，然后选择 **输入数据可用性报表**。 或者从预测详细信息视图中，选择 **输入数据可用性报表**。

:::image type="content" source="media/input-data-usability-report.png" alt-text="输入数据可用性报表的示例，其中显示了带有错误、警告和建议的表。":::

报表中包括：

- **名称：** 错误、警告或建议的描述性名称。
- **步骤：** 信息所引用的模型阶段、训练或分数。
- **状态：** 信息的严重性（错误、警告、建议）。
- **列名称：** 需要修改以提高模型性能的实体中的列。
- **实体名称：** 需要修改以提高模型性能的实体的名称。
- **详细信息：** 有关错误、警告或建议的详细信息。

[!INCLUDE [footer-include](includes/footer-banner.md)]
