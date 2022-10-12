---
title: 基于预览模型创建客户细分
description: 基于预测模型输出实体创建客户细分。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610409"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>基于预览模型创建客户细分（预览版）

预测结果有时仅适用于部分客户。 通过根据系统模型的结果创建客户细分，从而提高建议的个性化程度。 例如，您可能想向喜欢某种服务类型的客户提供特定的建议。

## <a name="prerequisites"></a>先决条件

- 至少具有 Customer Insights 中的[参与者权限](permissions.md)。

- 在 Customer Insights 中配置的产品建议、交易流失、订阅流失或客户生存期值模型。 查看设置不同模型的要求：

  - [产品建议模型](predict-product-recommendation.md)
  - [订阅流失模型](predict-subscription-churn.md)
  - [交易流失模型](predict-transactional-churn.md)
  - [客户生存期值模型](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>基于预测创建客户细分

1. 转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。

1. 选择您要查看的模型，然后选择 **查看**。

1. 在结果页上，选择 **创建客户细分**。 有关结果页的详细信息，请查看有关模型的文章。

   :::image type="content" source="media/prediction-create-segment.png" alt-text="预测结果页面的屏幕截图，其中突出显示了“创建客户细分”操作。":::

1. 使用选定模型的输出实体中的属性创建新客户细分。 有关详细信息，请参阅[创建和管理客户细分](segments.md)。

> [!TIP]
> 您还可以通过选择 **新建** 并选择 **创建自** > **智能**，从 **客户细分** 页面为预测模型创建客户细分。 有关详细信息，请参阅[使用快速客户细分创建新客户细分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
