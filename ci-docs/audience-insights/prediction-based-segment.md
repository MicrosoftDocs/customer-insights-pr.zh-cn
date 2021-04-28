---
title: 基于预测输出的客户细分
description: 基于预测模型输出实体创建客户细分。
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741418"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="3a28e-103">基于预览模型创建客户细分（预览版）</span><span class="sxs-lookup"><span data-stu-id="3a28e-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="3a28e-104">预测结果有时仅适用于部分客户。</span><span class="sxs-lookup"><span data-stu-id="3a28e-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="3a28e-105">通过根据系统模型的结果创建客户细分，从而提高建议的个性化程度。</span><span class="sxs-lookup"><span data-stu-id="3a28e-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="3a28e-106">例如，您可能想向喜欢某种服务类型的客户提供特定的建议。</span><span class="sxs-lookup"><span data-stu-id="3a28e-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3a28e-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="3a28e-107">Prerequisites</span></span>

- <span data-ttu-id="3a28e-108">至少具有 Customer Insights 中的[参与者权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3a28e-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="3a28e-109">在 Customer Insights 中配置的产品建议、交易流失、订阅流失或客户生存期值模型。</span><span class="sxs-lookup"><span data-stu-id="3a28e-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="3a28e-110">查看设置不同模型的要求：</span><span class="sxs-lookup"><span data-stu-id="3a28e-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="3a28e-111">产品建议模型</span><span class="sxs-lookup"><span data-stu-id="3a28e-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="3a28e-112">订阅流失模型</span><span class="sxs-lookup"><span data-stu-id="3a28e-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="3a28e-113">交易流失模型</span><span class="sxs-lookup"><span data-stu-id="3a28e-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="3a28e-114">客户生存期值模型</span><span class="sxs-lookup"><span data-stu-id="3a28e-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="3a28e-115">基于预测创建客户细分</span><span class="sxs-lookup"><span data-stu-id="3a28e-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="3a28e-116">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3a28e-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3a28e-117">选择要查看的模型旁边的垂直省略号，然后选择 **查看**。</span><span class="sxs-lookup"><span data-stu-id="3a28e-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="3a28e-118">在结果页上，选择 **创建客户细分**。</span><span class="sxs-lookup"><span data-stu-id="3a28e-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="3a28e-119">有关结果页的详细信息，请查看有关模型的文章。</span><span class="sxs-lookup"><span data-stu-id="3a28e-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="预测结果页面的屏幕截图，其中突出显示了“创建客户细分”操作。":::

1. <span data-ttu-id="3a28e-121">基于选定模型输出实体创建新客户细分。</span><span class="sxs-lookup"><span data-stu-id="3a28e-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="3a28e-122">有关详细信息，请参阅[创建和管理客户细分](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="3a28e-122">For more information, see [Create and manage segments](segments.md).</span></span>