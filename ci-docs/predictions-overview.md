---
title: 预测概述
description: Dynamics 365 Customer Insights 应用程序涵盖的预测方案和选项。
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080957"
---
# <a name="predictions-overview"></a>预测概述

Dynamics 365 Customer Insights 提供各种选项，这些选项可以利用 AI 和机器学习来预测数据。 

## <a name="out-of-box-models"></a>现成模型

开始预测数据的最简单方法是使用预定义的模型（通常称为现成模型）。 它们只需某些数据和结构便可快速生成见解。 目前，以下模型可用： 

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

- [客户生存期值](predict-customer-lifetime-value.md)：预测客户在与企业交互的整个期间的潜在收入。
- [产品推荐](predict-product-recommendation.md)：根据购买行为和具有类似购买模式的客户提出一套预测性产品建议。
- [订阅流失](predict-subscription-churn.md)：预测客户是否存在不再使用贵公司的订阅产品或服务的风险的模型。
- [交易流失](predict-transactional-churn.md)：预测客户是否会在特定期限内不再购买您的产品或服务。
- [情绪分析](sentiment-analysis.md)：分析客户反馈的情绪并确定经常提及的各个业务方面。

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

- [交易流失](predict-transactional-churn.md)：预测客户是否会在特定期限内不再购买您的产品或服务。

---

> [!TIP]
> 我们建议您定期使用更新的数据刷新现成可用的模型，以确保它们准确地通知您的业务用例。 当系统引入新的或更新的数据源时，数据会临时刷新。 但是，模型在这种情况下只会重新评分，然后继续使用现有的训练数据。
> 
> 您可以通过在配置体验中设置模型重新训练计划来配置 **更新计划**。 模型将按此计划重新训练和重新评分，您可以随时更改。


## <a name="azure-machine-learning-integration"></a>Azure 机器学习集成

如果组织已经根据 Azure 机器学习实验使用机器学习方案，则 Customer Insights 中的自定义模型功能有助于将点联系起来。 创建工作流，帮助您选择要从中生成见解的数据，并将结果映射到您的统一客户配置文件。 有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。

## <a name="ai-builder-prediction"></a>AI Builder 预测

有时，数据集不完整，缺少某些值。 Customer Insights 可以帮助预测客户实体和客户细分的缺失值。 有关更多信息，请参阅[使用预测完成部分数据](predictions.md)。
