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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095689"
---
# <a name="predictions-overview"></a><span data-ttu-id="d8f90-103">预测概述</span><span class="sxs-lookup"><span data-stu-id="d8f90-103">Predictions overview</span></span>

<span data-ttu-id="d8f90-104">Dynamics 365 Customer Insights 提供各种选项，这些选项可以利用 AI 和机器学习来预测数据。</span><span class="sxs-lookup"><span data-stu-id="d8f90-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="d8f90-105">现成模型</span><span class="sxs-lookup"><span data-stu-id="d8f90-105">Out-of-box models</span></span>

<span data-ttu-id="d8f90-106">开始预测数据的最简单方法是使用预定义的模型（通常称为现成模型）。</span><span class="sxs-lookup"><span data-stu-id="d8f90-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="d8f90-107">它们只需某些数据和结构便可快速生成见解。</span><span class="sxs-lookup"><span data-stu-id="d8f90-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="d8f90-108">目前，以下模型可用：</span><span class="sxs-lookup"><span data-stu-id="d8f90-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="d8f90-109">[客户生存期值](predict-customer-lifetime-value.md)：预测客户在与企业交互的整个期间的潜在收入。</span><span class="sxs-lookup"><span data-stu-id="d8f90-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="d8f90-110">[产品推荐](predict-product-recommendation.md)：根据购买行为和具有类似购买模式的客户提出一套预测性产品建议。</span><span class="sxs-lookup"><span data-stu-id="d8f90-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="d8f90-111">[订阅流失](predict-subscription-churn.md)：预测客户是否存在不再使用贵公司的订阅产品或服务的风险的模型。</span><span class="sxs-lookup"><span data-stu-id="d8f90-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="d8f90-112">[交易流失](predict-transactional-churn.md)：预测客户是否会在特定期限内不再购买您的产品或服务。</span><span class="sxs-lookup"><span data-stu-id="d8f90-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="d8f90-113">Azure 机器学习集成</span><span class="sxs-lookup"><span data-stu-id="d8f90-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="d8f90-114">如果组织已经根据 Azure 机器学习实验使用机器学习方案，则 Customer Insights 中的自定义模型功能有助于将点联系起来。</span><span class="sxs-lookup"><span data-stu-id="d8f90-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="d8f90-115">创建工作流，帮助您选择要从中生成见解的数据，并将结果映射到您的统一客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="d8f90-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="d8f90-116">有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。</span><span class="sxs-lookup"><span data-stu-id="d8f90-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="d8f90-117">AI Builder 预测</span><span class="sxs-lookup"><span data-stu-id="d8f90-117">AI Builder prediction</span></span>

<span data-ttu-id="d8f90-118">有时，数据集不完整，缺少某些值。</span><span class="sxs-lookup"><span data-stu-id="d8f90-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="d8f90-119">Customer Insights 可以帮助预测客户实体和客户细分的缺失值。</span><span class="sxs-lookup"><span data-stu-id="d8f90-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="d8f90-120">有关更多信息，请参阅[使用预测完成部分数据](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="d8f90-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
