---
title: 产品建议预测示例指南
description: 使用本示例指南试用产品建议预测模型。
ms.date: 02/10/2021
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
ms.openlocfilehash: 8ba54cfd466049c8df99c15f34626ab1914234f1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354636"
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

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscontacts。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

5. 在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**

6. **保存** 数据源。

### <a name="ingest-online-purchase-data"></a>引入在线购买数据

1. 将另一个数据集添加到相同的 **电子商务** 数据源中。 再次选择 **文本/CSV** 连接器。

1. 输入 **在线购买** 数据的 URL https://aka.ms/ciadclassonline。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **PurchasedOn**：日期/时间
   - **TotalPrice**：货币

1. 在侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommercePurchases**。

1. **保存** 数据源。


### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建名为 **LoyaltyScheme** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **loyCustomers**。

1. **保存** 数据源。

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

在引入数据后，我们现在开始进行数据统一流程，以创建统一的客户配置文件。 有关详细信息，请参阅[数据统一](data-unification.md)。

### <a name="map"></a>映射

1. 引入数据后，将联系人从电子商务和忠诚度数据映射到常见数据类型。 转到 **数据** > **统一** > **映射**。

2. 选择表示客户配置文件的实体 – **eCommerceContacts** 和 **loyCustomers**。

   ![统一电子商务和忠诚度数据源。](media/unify-ecommerce-loyalty.png)

3. 选择 **ContactId** 作为 **eCommerceContacts** 的主键，选择 **LoyaltyID** 作为 **loyCustomers** 的主键。

   ![统一 LoyaltyId 作为主键。](media/unify-loyaltyid.png)

### <a name="match"></a>匹配项

1. 转到 **匹配** 选项卡并选择 **设置顺序**。

2. 在 **主要** 下拉列表中，选择 **eCommerceContacts : eCommerce** 作为主要源并包括所有记录。

3. 在 **实体 2** 下拉列表中，选择 **loyCustomers : LoyaltyScheme** 并包括所有记录。

   ![统一匹配电子商务和忠诚度。](media/unify-match-order.png)

4. 选择 **创建新规则**

5. 使用 FullName 添加您的第一个条件。

   - 对于 eCommerceContacts，在下拉列表中选择 **FullName**。
   - 对于 loyCustomers，在下拉列表中选择 **FullName**。
   - 选择 **标准化** 下拉列表，然后选择 **类型（电话、名称、地址......）**。
   - 设置 **精度级别**：**基本** 和 **值**：**高**。

6. 为新规则输入名称 **全名、电子邮件**。

   - 通过选择 **添加条件** 为电子邮件地址添加第二个条件
   - 对于实体 eCommerceContacts，在下拉列表中选择 **电子邮件**。
   - 对于实体 loyCustomers，在下拉列表中选择 **电子邮件**。
   - 将“标准化”留空。
   - 设置 **精度级别**：**基本** 和 **值**：**高**。

   ![统一名称和电子邮件的匹配规则。](media/unify-match-rule.png)

7. 选择 **保存** 和 **运行**。

### <a name="merge"></a>合并​​

1. 转到 **合并** 选项卡。

1. 在 **loyCustomers** 实体的 **ContactId** 上，将显示名称更改为 **ContactIdLOYALTY** 以将其与引入的其他 ID 区分开。

   ![从忠诚度 ID 中重命名 contactid。](media/unify-merge-contactid.png)

1. 选择 **保存** 和 **运行** 以启动合并流程。

## <a name="task-3---configure-product-recommendation-prediction"></a>任务 3 - 配置产品建议预测

有了统一的客户配置文件，我们现在可以运行订阅流失预测。

1. 转到 **智能** > **预测**，选择 **产品建议**。

1. 选择 **开始**。

1. 将模型命名为 **OOB 产品建议模型预测**，将输出实体命名为 **OOBProductReendationModelPrediproduct**。

1. 定义模型的三个条件：

   - **产品数量**：将此值设置为 **5**。 此设置定义要推荐给客户的产品数。

   - **重复预期的购买**：选择 **是** 以表示您希望将客户以前购买过的产品包含在建议中。

   - **回看窗口：** 至少选择 **365 天**。 此设置定义模型回溯客户活动的时长以将其用作建议输入。
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="产品建议模型的模型首选项。":::

1. 选择 **必需数据**，然后针对购买历史记录选择 **添加数据**。

1. 添加 **eCommercePurchases：电子商务** 实体，并将电子商务中的字段映射到模型所需的相应字段。

1. 使用 **eCommerceContacts：电子商务** 加入 **eCommercePurchases：电子商务** 实体。

   ![加入电子商务实体。](media/model-purchase-join.png)

1. 选择 **下一步** 以设置模型计划。

   在引入新数据后，需要定期对模型进行定型以学习新模式。 对于此示例，请选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。


## <a name="task-4---review-model-results-and-explanations"></a>任务 4 - 审阅模型结果和说明

让模型完成数据的训练和评分。 您现在可以审阅产品建议模型说明。 有关详细信息，请参阅[审阅预测状态和结果](predict-subscription-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>任务 5 - 创建热销产品的客户细分

运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。

您可以基于模型创建的实体创建新的客户细分。

1. 转到 **客户细分**。 选择 **新建**，然后选择 **创建自** > **智能**。

   ![使用模型输出创建客户细分。](media/segment-intelligence.png)

1. 选择 **OOBProductRecommendationModelPrediction** 终结点并定义客户细分：

   - 字段：ProductID
   - 运算符：值
   - 值：选择前三个产品 ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="利用模型结果创建客户细分。":::

您现在具有一个动态更新的客户细分，它确定更愿意购买这三种推荐度最高的产品的客户 

有关详细信息，请参阅[创建和管理客户细分](segments.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
