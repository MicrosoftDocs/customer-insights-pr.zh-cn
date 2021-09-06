---
title: 有关支持的预测方案的概述
description: Dynamics 365 Customer Insights 应用程序涵盖的预测方案和选项。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035998"
---
# <a name="predictions-overview"></a>预测概述

Dynamics 365 Customer Insights 提供各种选项，这些选项可以利用 AI 和机器学习来预测数据。 

## <a name="out-of-box-models"></a>现成模型

开始预测数据的最简单方法是使用预定义的模型（通常称为现成模型）。 它们只需某些数据和结构便可快速生成见解。 目前，以下模型可用： 
- [客户生存期值](predict-customer-lifetime-value.md)：预测客户在与企业交互的整个期间的潜在收入。 
- [产品推荐](predict-product-recommendation.md)：根据购买行为和具有类似购买模式的客户提出一套预测性产品建议。
- [订阅流失](predict-subscription-churn.md)：预测客户是否存在不再使用贵公司的订阅产品或服务的风险的模型。
- [交易流失](predict-transactional-churn.md)：预测客户是否会在特定期限内不再购买您的产品或服务。

## <a name="azure-machine-learning-integration"></a>Azure 机器学习集成

如果组织已经根据 Azure 机器学习实验使用机器学习方案，则 Customer Insights 中的自定义模型功能有助于将点联系起来。 创建工作流，帮助您选择要从中生成见解的数据，并将结果映射到您的统一客户配置文件。 有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。

## <a name="ai-builder-prediction"></a>AI Builder 预测

有时，数据集不完整，缺少某些值。 Customer Insights 可以帮助预测客户实体和客户细分的缺失值。 有关更多信息，请参阅[使用预测完成部分数据](predictions.md)。
