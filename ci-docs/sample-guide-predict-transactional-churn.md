---
title: 交易流失预测示例指南
description: 使用本示例指南试用现成的交易流失预测模型。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609673"
---
# <a name="transactional-churn-prediction-sample-guide"></a>交易流失预测示例指南

本指南将向您演示使用示例数据的交易流失预测的端到端示例。 我们建议您[在新环境中](manage-environments.md)试用此预测。

## <a name="scenario"></a>场景

Contoso 是一家生产高品质咖啡和咖啡机的公司。 他们通过 Contoso Coffee 网站销售产品。 它们的目标是了解通常定期购买其产品的哪些客户在接下来的 60 天内将停止成为活动客户。 了解哪些客户 **可能会流失** 有助于他们将市场营销工作集中在留住这些客户上。

## <a name="prerequisites"></a>先决条件

- 至少具有[参与者权限](permissions.md)。

## <a name="task-1---ingest-data"></a>任务 1 - 引入数据

查看[关于数据引入](data-sources.md)和[连接到 Power Query 数据源](connect-power-query.md)的文章。 以下信息假设您大致了解如何引入数据。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>从电子商务平台中引入客户数据

1. 创建一个名为 **eCommerce** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将 DoB 转换为日期。":::

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **eCommerceContacts**

1. 保存数据源。

### <a name="ingest-online-purchase-data"></a>引入在线购买数据

1. 将另一个数据集添加到相同的 **电子商务** 数据源中。 再次选择 **文本/CSV** 连接器。

1. 输入在线购买数据的 URL https://aka.ms/ciadclassonline。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **PurchasedOn**：日期/时间
   - **TotalPrice**：货币

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **eCommercePurchases**。

1. 保存数据源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建一个名为 **LoyaltyScheme** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **loyCustomers**。

1. 保存数据源。

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

查看[关于数据统一](data-unification.md)的文章。 以下信息假设您大致了解数据统一。

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>任务 3 - 创建交易历史记录活动

查看[关于客户活动](activities.md)的文章。 以下信息假设您大致了解如何创建活动。

1. 使用 *eCommercePurchases:eCommerce* 实体及其主键 **PurchaseId** 创建一个名为 **eCommercePurchases** 的活动。

1. 在 *eCommercePurchases:eCommerce* 和 *eCommerceContacts:eCommerce* 之间创建关系，将 **ContactID** 作为连接两个实体的外键。

1. 对于 **EventActivity**，选择 **TotalPrice**，对于 **TimeStamp**，选择 **PurchasedOn**。

1. 为 **活动类型** 选择 **SalesOrderLine**，并在语义上映射活动数据。

1. 运行活动。

## <a name="task-4---configure-transaction-churn-prediction"></a>任务 4 - 配置交易流失预测

建立统一的客户配置文件并创建活动后，运行交易流失预测。

1. 转到 **智能** > **预测**。

1. 在 **创建** 选项卡上，在 **客户流失模型** 上选择 **使用模型**。

1. 选择 **交易** 作为流失类型，然后选择 **开始**。

1. 命名模型 **OOB 电子商务交易流失预测** 和输出实体 **OOBeCommerceChurnPrediction**。

1. 选择 **下一步**。

1. 定义模型首选项：

   - **预测窗口**：**60** 天，定义未来您想要预测客户流失的时间。

   - **流失定义**：**60** 天，表示视为已流失的客户未进行购买的持续时间。

     :::image type="content" source="media/model-levers.PNG" alt-text="选择模型首选项预测窗口和流失定义。":::

1. 选择 **下一步**。

1. 选择 **购买历史记录（必需）**，然后针对购买历史记录选择 **添加数据**。

1. 选择 **SalesOrderLine** 和 eCommercePurchases 实体，然后选择 **下一步**。 所需数据会从活动自动填入。 选择 **保存**，然后选择 **下一步**。

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="加入电子商务实体。":::

1. 跳过 **其他数据（可选）** 步骤。

1. 在 **数据更新** 步骤中，为模型计划选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-5---review-model-results-and-explanations"></a>任务 5 - 审阅模型结果和说明

让模型完成数据的训练和评分。 查看流失模型说明。 有关详细信息，请参阅[查看预测结果](predict-transactional-churn.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>任务 6 - 创建高流失风险客户的客户细分

运行生产模型可创建一个新实体，该实体列在 **数据** > **实体** 上。 您可以基于模型创建的实体创建新的客户细分。

1. 在结果页上，选择 **创建客户细分**。

1. 使用 **OOBeCommerceChurnPrediction** 实体创建规则并定义客户细分：
   - **字段**：ChurnScore
   - **运算符**：大于
   - **值**：0.6

1. 选择 **保存** 并 **运行** 客户细分。

您现在有一个动态更新的客户细分，此客户细分可以识别高流失风险的客户。 有关详细信息，请参阅[创建和管理客户细分](segments.md)。

> [!TIP]
> 您还可以通过选择 **新建** 并选择 **创建自** > **智能**，从 **客户细分** 页面为预测模型创建客户细分。 有关详细信息，请参阅[使用快速客户细分创建新客户细分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
