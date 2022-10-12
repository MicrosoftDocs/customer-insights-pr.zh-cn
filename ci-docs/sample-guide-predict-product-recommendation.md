---
title: 产品建议预测示例指南
description: 使用本示例指南试用产品建议预测模型。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610133"
---
# <a name="product-recommendation-prediction-sample-guide"></a>产品建议预测示例指南

本指南将向您演示使用示例数据的产品建议预测的端到端示例。 我们建议您[在新环境中](manage-environments.md)试用此预测。

## <a name="scenario"></a>场景

Contoso 是一家生产高品质咖啡和咖啡机的公司。 他们通过 Contoso Coffee 网站销售产品。 他们的目标是了解应该向定期客户推荐哪些产品。 通过了解客户更 **有可能购买** 哪些产品，可以将主要精力放在特定项目上来节省市场营销工作。

## <a name="prerequisites"></a>先决条件

- 至少具有 Customer Insights 中的[参与者权限](permissions.md)。

## <a name="task-1---ingest-data"></a>任务 1 - 引入数据

查看[关于数据引入](data-sources.md)和[连接到 Power Query 数据源](connect-power-query.md)的文章。 以下信息假设您大致了解如何引入数据。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>从电子商务平台中引入客户数据

1. 创建一个名为 **eCommerce** 的 Power query 数据源，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL：https://aka.ms/ciadclasscontacts。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **eCommerceContacts**。

1. **保存** 数据源。

### <a name="ingest-online-purchase-data"></a>引入在线购买数据

1. 将另一个数据集添加到相同的 **电子商务** 数据源中。 再次选择 **文本/CSV** 连接器。

1. 输入在线购买数据的 URL https://aka.ms/ciadclassonline。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **PurchasedOn**：日期/时间
   - **TotalPrice**：货币

1. 在侧窗格上的 **名称** 字段中，将您的数据源重命名为 **eCommercePurchases**。

1. **保存** 数据源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建一个名为 **LoyaltyScheme** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入忠诚客户的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **loyCustomers**。

1. **保存** 数据源。

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

## <a name="task-4---configure-product-recommendation-prediction"></a>任务 4 - 配置产品建议预测

建立统一的客户配置文件并创建活动后，运行产品建议预测。

1. 转到 **智能** > **预测**。

1. 在 **创建** 选项卡上，在 **产品建议（预览）** 磁贴上选择 **使用模型**。

1. 选择 **开始**。

1. 将模型命名为 **OOB 产品建议模型预测**，将输出实体命名为 **OOBProductReendationModelPrediproduct**。

1. 选择 **下一步**。

1. 定义模型首选项：
   - **产品数量**：**5**，定义要推荐给客户的产品数。
   - **重复预期的购买**：**是**，在建议中包括以前购买的产品。
   - **回看窗口**：**365 天**，定义在再次推荐某个产品之前，模型回顾的时间。

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="产品建议模型的模型首选项。":::

1. 选择 **下一步**。

1. 在 **添加购买历史记录** 步骤中，选择 **添加数据**。

1. 选择 **SalesOrderLine** 和 eCommercePurchases 实体，然后选择 **下一步**。 所需数据会从活动自动填入。 选择 **保存**，然后选择 **下一步**。

1. 跳过 **添加产品信息** 和 **产品筛选器** 步骤，因为我们还没有产品信息数据。

1. 在 **数据更新** 步骤中，为模型计划选择 **每月**。

1. 选择 **下一步**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-5---review-model-results-and-explanations"></a>任务 5 - 审阅模型结果和说明

让模型完成数据的训练和评分。 查看[产品建议模型说明](predict-transactional-churn.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>任务 6 - 创建热销产品的客户细分

运行模型可创建一个新实体，该实体列在 **数据** > **实体** 上。 您可以基于模型创建的实体创建新的客户细分。

1. 在结果页上，选择 **创建客户细分**。

1. 使用 **OOBProductRecommendationModelPrediction** 实体创建规则并定义客户细分：
   - **字段**：ProductID
   - **值**：选择前三个产品 ID

1. 选择 **保存** 并 **运行** 客户细分。

您现在有一个动态更新的客户细分，此客户细分标识可能有兴趣购买五种推荐最多的产品的客户。 有关详细信息，请参阅[创建和管理客户细分](segments.md)。

> [!TIP]
> 您还可以通过选择 **新建** 并选择 **创建自** > **智能**，从 **客户细分** 页面为预测模型创建客户细分。 有关详细信息，请参阅[使用快速客户细分创建新客户细分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
