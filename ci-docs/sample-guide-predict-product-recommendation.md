---
title: 产品建议预测示例指南
description: 使用本示例指南试用产品建议预测模型。
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762675"
---
# <a name="product-recommendation-prediction-sample-guide"></a>产品建议预测示例指南

我们将向您演示使用下面提供的示例数据的产品建议预测的端到端示例。

## <a name="scenario"></a>方案

Contoso 是一家生产优质咖啡和咖啡机的公司，它们通过 Contoso 咖啡网站销售。 他们的目标是了解应该向定期客户推荐哪些产品。 通过了解客户更 **有可能购买** 哪些产品，可以将主要精力放在特定项目上来节省市场营销工作。

## <a name="prerequisites"></a>先决条件

- 至少具有 Customer Insights 中的[参与者权限](permissions.md)。
- 我们建议您[在新环境中](manage-environments.md)实施以下步骤。

## <a name="task-1---ingest-data"></a>任务 1 - 引入数据

专门查看[关于数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)的文章。 以下信息假设您大致了解如何引入数据。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>从电子商务平台中引入客户数据

1. 创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL：[https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. 在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**

1. **保存** 数据源。

### <a name="ingest-online-purchase-data"></a>引入在线购买数据

1. 将另一个数据集添加到相同的 **电子商务** 数据源中。 再次选择 **文本/CSV** 连接器。

1. 输入 **在线购买** 数据的 URL [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline)。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **PurchasedOn**：日期/时间
   - **TotalPrice**：货币

1. 在侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommercePurchases**。

1. **保存** 数据源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty)。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。

1. **保存** 数据源。

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>任务 3 - 配置产品建议预测

建立统一的客户配置文件后，现在可以运行产品建议预测。

1. 转到 **智能** > **预测**，选择 **产品建议**。

1. 选择 **开始**。

1. 将模型命名为 **OOB 产品建议模型预测**，将输出实体命名为 **OOBProductReendationModelPrediproduct**。

1. 定义模型的三个条件：

   - **产品数量**：将此值设置为 **5**。 此设置定义要推荐给客户的产品数。

   - **重复预期的购买**：选择 **是** 以表示您希望将客户以前购买过的产品包含在建议中。

   - **回看窗口：** 至少选择 **365 天**。 此设置定义模型回溯客户活动的时长以将其用作建议输入。

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="产品建议模型的模型首选项。":::

1. 在 **添加所需数据** 步骤中，选择 **添加数据**。

1. 在 **添加数据** 窗格中，选择 **SalesOrderLine** 作为购买历史记录实体。 目前，尚未配置它。 打开此窗格中的链接，按照以下步骤创建活动：
   1. 输入 **活动名称**，并选择 *eCommercePurchases:eCommerce* 作为 **活动实体**。 **主键** 为 *PurchaseId*。
   1. 定义关系并将其命名为 *eCommerceContacts:eCommerce 实体*，然后选择 **ContactId** 作为外键。
   1. 对于活动统一，将 **事件活动** 设置为 *TotalPrice*，将时间戳设置为  *PurchasedOn*。 您可以指定[客户活动](activities.md)中概述的更多字段。
   1. 对于 **活动类型**，请选择 *SalesOrderLine*。 映射以下活动字段：
      - 订单行 ID：PurchaseId
      - 订单 ID：PurchaseId
      - 订单数据：PurchasedOn
      - 产品 ID: ProductId
      - 金额：TotalPrice
   1. 在返回模型配置之前，查看并完成活动。

1. 返回 **选择活动** 步骤，在 **活动** 部分中选择新创建的活动。 选择 **下一步**，属性映射已填写。选择 **保存**。

1. 在此示例指南中，我们跳过了 **添加产品信息** 和 **产品筛选器** 设置，因为我们还没有产品信息数据。

1. 在 **数据更新** 步骤中，设置模型计划。

   在引入新数据后，需要定期对模型进行定型以学习新模式。 对于此示例，请选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。 第一次运行模型需要几分钟的时间。

## <a name="task-4---review-model-results-and-explanations"></a>任务 4 - 审阅模型结果和说明

让模型完成数据的训练和评分。 您现在可以审阅产品建议模型说明。 有关详细信息，请参阅[审阅预测状态和结果](predict-transactional-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>任务 5 - 创建热销产品的客户细分

运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。

您可以基于模型创建的实体创建新的客户细分。

1. 转到 **客户细分**。 选择 **新建**，然后选择 **通过智能功能创建**。

   ![使用模型输出创建客户细分。](media/segment-intelligence.png)

1. 选择 **OOBProductRecommendationModelPrediction** 终结点并定义客户细分：

   - 字段：ProductID
   - 值：选择前三个产品 ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="利用模型结果创建客户细分。":::

您现在有一个动态更新的客户细分，此客户细分标识可能有兴趣购买三种最推荐产品的客户。

有关详细信息，请参阅[创建和管理客户细分](segments.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
