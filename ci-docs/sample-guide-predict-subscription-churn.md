---
title: 订阅流失预测示例指南
description: 使用本示例指南试用现成的订阅流失预测模型。
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741400"
---
# <a name="subscription-churn-prediction-sample-guide"></a>订阅流失预测示例指南

我们将向您演示使用下面提供的示例数据的订阅流失预测的端到端示例。 

## <a name="scenario"></a>方案

Contoso 是一家生产优质咖啡和咖啡机的公司，它们通过 Contoso 咖啡网站销售。 他们最近为定期购买咖啡的客户启动了一项订阅业务。 他们的目标是了解哪些订阅客户可能会在接下来的几个月内取消订阅。 了解哪些客户 **可能会流失** 有助于他们将市场营销工作集中在留住这些客户上。

## <a name="prerequisites"></a>先决条件

- 至少具有 Customer Insights 中的[参与者权限](permissions.md)。
- 我们建议您[在新环境中](manage-environments.md)实施以下步骤。

## <a name="task-1---ingest-data"></a>任务 1 - 引入数据

专门查看[关于数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)的文章。 以下信息假设您大致了解如何引入数据。 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>从电子商务平台中引入客户数据

1. 创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**

1. 保存数据源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。

1. 保存数据源。

### <a name="ingest-subscription-information"></a>引入订阅信息

1. 创建名为 **SubscriptionHistory** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadchurnsubscriptionhistory。

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

1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **SubscriptionHistory**。

1. 保存数据源。

### <a name="ingest-customer-data-from-website-reviews"></a>从网站评价中引入客户数据

1. 创建名为 **网站** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasswebsite。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **ReviewRating**：整数
   - **ReviewDate**：日期

1. 在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **webReviews**。

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>任务 3 - 配置订阅流失预测

有了统一的客户配置文件，我们现在可以运行订阅流失预测。 有关详细步骤，请参阅[订阅流失预测](predict-subscription-churn.md)文章。 

1. 转到 **智能** > **发现** 并选择使用 **客户流失模型**。

1. 选择 **订阅** 选项，然后选择 **开始**。

1. 命名模型 **OOB 订阅流失预测** 和输出实体 **OOBSubscriptionChurnPrediction**。

1. 定义流失模型的两个条件：

   * **订阅结束后的天数**：**至少 60** 天。 如果客户在其订阅结束后的此期间内未续订订阅，他们将会视为已流失。 

   * **流失定义**：**至少 93** 天。 模型预测哪些客户可能流失的持续时间。 您所查看的将来时间越长，结果的精度越低。

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="选择模型方法预测时间范围和流失定义。":::

1. 选择 **添加必需数据**，然后针对订阅历史记录选择 **添加数据**。

1. 添加 **订阅：SubscriptionHistory** 实体，并将电子商务中的字段映射到模型所需的相应字段。

1. 使用 **eCommerceContacts：电子商务** 加入 **订阅：SubscriptionHistory** 实体，命名关系 **eCommerceSubscription**。

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="加入电子商务实体。":::

1. 在客户活动下，添加 **webReviews：网站** 实体，并将 webReviews 中的字段映射到模型所需的相应字段。 
   - 主键：ReviewId
   - 时间戳：ReviewDate
   - 事件：ReviewRating

1. 为网站评价配置活动。 选择活动 **评价** 并使用 **eCommerceContacts：电子商务** 加入 **webReviews：网站** 实体。

1. 选择 **下一步** 以设置模型计划。

   在引入新数据后，需要定期对模型进行定型以学习新模式。 对于此示例，请选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-4---review-model-results-and-explanations"></a>任务 4 - 审阅模型结果和说明

让模型完成数据的训练和评分。 您现在可以审阅订阅流失模型说明。 有关详细信息，请参阅[审阅预测状态和结果](predict-subscription-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>任务 5 - 创建高流失风险客户的客户细分

运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。   

您可以基于模型创建的实体创建新的客户细分。

1.  转到 **客户细分**。 选择 **新建**，然后选择 **创建自** > **智能**。 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型输出创建客户细分。":::

1. 选择 **OOBSubscriptionChurnPrediction** 终结点并定义客户细分： 
   - 字段：ChurnScore
   - 运算符：大于
   - 值：0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="设置订阅流失客户细分。":::

现在，您已具有将动态更新的客户细分，可用于确定此订阅业务的高流失风险客户。

有关详细信息，请参阅[创建和管理客户细分](segments.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]