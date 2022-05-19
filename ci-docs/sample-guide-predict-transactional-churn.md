---
title: 交易流失预测示例指南
description: 使用本示例指南试用现成的交易流失预测模型。
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741308"
---
# <a name="transactional-churn-prediction-sample-guide"></a>交易流失预测示例指南

本指南将向您演示使用下面提供的数据的 Customer Insights 中交易流失预测的端到端示例。 本指南中使用的所有数据都不是真正的客户数据，而是在 Customer Insights 订阅内在 *演示* 环境中找到的 Contoso 数据集的一部分。

## <a name="scenario"></a>方案

Contoso 是一家生产优质咖啡和咖啡机的公司，它们通过 Contoso 咖啡网站销售。 它们的目标是了解通常定期购买其产品的哪些客户在接下来的 60 天内将停止成为活动客户。 了解哪些客户 **可能会流失** 有助于他们将市场营销工作集中在留住这些客户上。

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将 DoB 转换为日期。":::

1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**

1. 保存数据源。

### <a name="ingest-online-purchase-data"></a>引入在线购买数据

1. 将另一个数据集添加到相同的 **电子商务** 数据源中。 再次选择 **文本/CSV** 连接器。

1. 输入 **在线购买** 数据的 URL https://aka.ms/ciadclassonline。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **PurchasedOn**：日期/时间
   - **TotalPrice**：货币
   
1. 在右侧窗格上的 **名称** 字段中，将您的数据源从 **Query** 重命名为 **eCommercePurchases**。

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

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>任务 3 - 配置交易流失预测

建立统一的客户配置文件后，现在可以运行交易流失预测。 有关详细步骤，请参阅[交易流失预测](predict-transactional-churn.md)文章。 

1. 转到 **智能** > **发现** 并选择使用 **客户流失模型**。

1. 选择 **交易** 选项，然后选择 **开始**。

1. 命名模型 **OOB 电子商务交易流失预测** 和输出实体 **OOBeCommerceChurnPrediction**。

1. 定义流失模型的两个条件：

   * **预测时间范围**：**至少 60** 天。 此设置定义未来您想要预测客户流失的程度。

   * **流失定义**：**至少 60** 天。 视为已流失的客户未进行购买的持续时间。

     :::image type="content" source="media/model-levers.PNG" alt-text="选择模型方法预测时间范围和流失定义。":::

1. 选择 **购买历史记录（必需）**，然后针对购买历史记录选择 **添加数据**。

1. 添加 **eCommercePurchases：电子商务** 实体，并将电子商务中的字段映射到模型所需的相应字段。

1. 使用 **eCommerceContacts：电子商务** 加入 **eCommercePurchases：电子商务** 实体。

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="加入电子商务实体。":::

1. 选择 **下一步** 以设置模型计划。

   在引入新数据后，需要定期对模型进行定型以学习新模式。 对于此示例，请选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-4---review-model-results-and-explanations"></a>任务 4 - 审阅模型结果和说明

让模型完成数据的训练和评分。 现在，您可以查看流失模型说明。 有关详细信息，请参阅[审阅预测状态和结果](predict-transactional-churn.md#review-a-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>任务 5 - 创建高流失风险客户的客户细分

运行生产模型将创建一个新实体，您可以在 **数据** > **实体** 中看到该实体。   

您可以基于模型创建的实体创建新的客户细分。

1.  转到 **客户细分**。 选择 **新建**，然后选择 **创建自** > **智能**。 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="使用模型输出创建客户细分。":::

1. 选择 **OOBeCommerceChurnPrediction** 终结点并定义客户细分： 
   - 字段：ChurnScore
   - 运算符：大于
   - 值：0.6

您现在有一个动态更新的客户细分，此客户细分可以识别高流失风险的客户。

有关详细信息，请参阅[创建和管理客户细分](segments.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]
