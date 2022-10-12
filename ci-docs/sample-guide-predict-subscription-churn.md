---
title: 订阅流失预测示例指南
description: 使用本示例指南试用现成的订阅流失预测模型。
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609995"
---
# <a name="subscription-churn-prediction-sample-guide"></a>订阅流失预测示例指南

本指南将向您演示使用示例数据的订阅流失预测的端到端示例。 我们建议您[在新环境中](manage-environments.md)试用此预测。

## <a name="scenario"></a>场景

Contoso 是一家生产高品质咖啡和咖啡机的公司。 他们通过 Contoso Coffee 网站销售产品。 他们最近为定期购买咖啡的客户启动了一项订阅业务。 他们的目标是了解哪些订阅客户可能会在接下来的几个月内取消订阅。 了解哪些客户 **可能会流失** 有助于他们将市场营销工作集中在留住这些客户上。

## <a name="prerequisites"></a>先决条件

- 至少具有 Customer Insights 中的[参与者权限](permissions.md)。

## <a name="task-1---ingest-data"></a>任务 1 - 引入数据

查看[关于数据引入](data-sources.md)和[连接到 Power Query 数据源](connect-power-query.md)的文章。 以下信息假设您大致了解如何引入数据。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>从电子商务平台中引入客户数据

1. 创建一个名为 **eCommerce** 的 Power query 数据源，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **eCommerceContacts**

1. 保存数据源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建一个名为 **LoyaltyScheme** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入会员客户的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **loyCustomers**。

1. 保存数据源。

### <a name="ingest-subscription-information"></a>引入订阅信息

1. 创建一个名为 **SubscriptionHistory** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入订阅的 URL https://aka.ms/ciadchurnsubscriptionhistory。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **SubscriptioID**：整数
   - **SubscriptionAmount**：货币
   - **SubscriptionEndDate**：日期/时间
   - **SubscriptionStartDate**：日期/时间
   - **TransactionDate**：日期/时间
   - **IsRecurring**：True/False
   - **Is_auto_renew**：True/False
   - **RecurringFrequencyInMonths**：整数

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **SubscriptionHistory**。

1. 保存数据源。

### <a name="ingest-customer-data-from-website-reviews"></a>从网站评价中引入客户数据

1. 创建一个名为 **Website** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入网站评论的 URL https://aka.ms/ciadclasswebsite。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **ReviewRating**：整数
   - **ReviewDate**：日期

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **webReviews**。

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

查看[关于数据统一](data-unification.md)的文章。 以下信息假设您大致了解数据统一。

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>任务 3 - 创建交易历史记录活动

查看[关于客户活动](activities.md)的文章。 以下信息假设您大致了解如何创建活动。

1. 使用 *Subscription* 实体及其主键 **CustomerId** 创建一个名为 **SubscriptionHistory** 的活动。

1. 在 *SubscriptionHistory:Subscription* 和 *eCommerceContacts:eCommerce* 之间创建关系，将 **CustomerID** 作为连接两个实体的外键。

1. 对于 **EventActivity**，选择 **SubscriptionType**，对于 **TimeStamp**，选择 **SubscriptionEndDate**。

1. 为 **活动类型** 选择 **Subscription**，并在语义上映射活动数据。

1. 运行活动。

1. 添加另一个活动并将其字段名称映射到相应的字段：
   - 客户活动实体：Reviews:Website
   - 主键：Website.Reviews.ReviewId
   - 时间戳：Website.Reviews.ReviewDate
   - 事件（活动名称）：Website.Reviews.ActivityTypeDisplay
   - 详细信息（金额或价值）：Website.Reviews.ReviewRating

1. 运行活动。

## <a name="task-4---configure-the-subscription-churn-prediction"></a>任务 4 - 配置订阅流失预测

有了统一的客户配置文件并创建了活动后，运行订阅流失预测。 有关详细步骤，请参阅[订阅流失预测](predict-subscription-churn.md)。

1. 转到 **智能** > **预测**。

1. 在 **创建** 选项卡上，在 **客户流失模型** 磁贴上选择 **使用模型**。

1. 选择 **订阅** 作为流失类型，然后选择 **开始**。

1. 命名模型 **OOB 订阅流失预测** 和输出实体 **OOBSubscriptionChurnPrediction**。

1. 定义模型首选项：
   - **订阅结束后的天数**：**60** 天，表示客户在其订阅结束后的此期间内未续订订阅，将被视为已流失。
   - **预测将来以预测客户流失的天数**：**93** 天，即模型预测哪些客户可能流失的持续时间。 您所查看的将来时间越长，结果的精度越低。

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="选择模型首选项和流失定义。":::

1. 选择 **下一步**。

1. 在 **所需数据** 步骤中，选择 **添加数据** 提供订阅历史记录。

1. 选择 **订阅** 和 SubscriptionHistory 实体，然后选择 **下一步**。 所需数据会从活动自动填入。 选择 **保存**。

1. 在“客户活动”下，选择 **添加数据**。

1. 对于本示例，添加 Web 评论活动。

1. 选择 **下一步**。

1. 在 **数据更新** 步骤中，为模型计划选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-5---review-model-results-and-explanations"></a>任务 5 - 审阅模型结果和说明

让模型完成数据的训练和评分。 查看订阅流失模型说明。 有关详细信息，请参阅[查看预测结果](predict-subscription-churn.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>任务 6 - 创建高流失风险客户的客户细分

运行模型可创建一个新实体，该实体列在 **数据** > **实体** 上。 您可以基于模型创建的实体创建新的客户细分。

1. 在结果页上，选择 **创建客户细分**。

1. 使用 **OOBSubscriptionChurnPrediction** 实体创建规则并定义客户细分：
   - **字段**：ChurnScore
   - **运算符**：大于
   - **值**：0.6

1. 选择 **保存** 并 **运行** 客户细分。

现在，您已具有将动态更新的客户细分，可用于确定此订阅业务的高流失风险客户。 有关详细信息，请参阅[创建和管理客户细分](segments.md)。

> [!TIP]
> 您还可以通过选择 **新建** 并选择 **创建自** > **智能**，从 **客户细分** 页面为预测模型创建客户细分。 有关详细信息，请参阅[使用快速客户细分创建新客户细分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
