---
title: 客户生存期值 (CLV) 预测示例指南
description: 使用此示例指南试用客户生存期值模型。
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051626"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>客户生存期值 (CLV) 预测示例指南

本指南将使用示例数据逐步向您解释 Customer Insights 中的客户生存期值 (CLV) 预测端到端示例。

## <a name="scenario"></a>场景

Contoso 是一家生产高品质咖啡和咖啡机的公司。 他们通过 Contoso Coffee 网站销售产品。 公司希望了解客户在未来 12 个月内可以产生的价值（收入）。 了解客户在未来 12 个月的预期价值将有助于他们将营销工作转向高价值客户。

## <a name="prerequisites"></a>先决条件

- 至少具有 Customer Insights 中的[参与者权限](permissions.md)。
- 我们建议您[在新环境中](manage-environments.md)实施以下步骤。

## <a name="task-1---ingest-data"></a>任务 1 - 引入数据

查看[关于数据引入](data-sources.md)和[使用 Power Query 连接器导入数据源](connect-power-query.md)的文章。 以下信息假设您大致了解如何引入数据。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>从电子商务平台中引入客户数据

1. 创建名为 **电子商务** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **CreatedOn**：日期/时间/区域

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="将出生日期转换为日期。":::

1. 在右侧窗格上的“名称”字段中，将您的数据源从 **Query** 重命名为 **eCommerceContacts**

1. **保存** 数据源。

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

### <a name="ingest-customer-data-from-website-reviews"></a>从网站评价中引入客户数据

1. 创建名为 **网站** 的数据源，选择导入选项，然后选择 **文本/CSV** 连接器。

1. 输入电子商务联系人的 URL https://aka.ms/CI-ILT/WebReviews。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：

   - **ReviewRating**：十进制数
   - **ReviewDate**：日期

1. 在右侧窗格上的“名称”字段中，将您的数据源从 **查询** 重命名为 **审核**。

1. **保存** 数据源。

## <a name="task-2---data-unification"></a>任务 2 - 数据统一

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>任务 3 - 配置客户生存期值预测

部署了统一客户配置文件后，我们现在可以运行客户生存期值预测。 有关详细步骤，请参阅[客户生存期值预测](predict-customer-lifetime-value.md)。

1. 转到 **智能**  > **预测** 并选择 **客户生存期值模型**。

1. 浏览侧窗格中的信息并选择 **开始**。

1. 将模型命名为 **OOB 电子商务 CLV 预测**，将输出实体命名为 **OOBeCommerceCLVPrediction**。

1. 定义 CLV 模型的模型首选项：
   - **预测时间段**：**12 个月或 1 年**。 此设置定义了未来要预测客户生存期值多久。
   - **活跃客户**：指定活跃客户对您业务的意义。 设置客户必须在其中至少有一笔交易才能被视为活跃客户的历史期限。 该模型将只预测活跃客户的 CLV。 在让模型根据历史交易数据计算时间段与提供特定期限之间进行选择。 在此示例指南中，我们 **让模型计算购买间隔**，这是默认选项。
   - **高价值客户**：将高价值客户定义为最高付费客户的百分位数。 该模型使用此输入提供符合您的高价值客户定义的结果。 您可以选择让模型定义高价值客户。 它使用一种启发式规则来得出此百分位数。 您还可以将高价值客户定义为将来最高付费客户的百分位数。 在此示例指南中，我们将高价值客户手动定义为 **前 30% 的主动付费客户**，并选择 **下一步**。

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 模型的引导式体验中的首选项步骤。":::

1. 在 **所需数据** 步骤中，选择 **添加数据** 以提供交易历史记录数据。

1. 添加 **eCommercePurchases：电子商务** 实体并映射模型所需的属性：
   - 交易 ID：eCommerce.eCommercePurchases.PurchaseId
   - 交易日期：eCommerce.eCommercePurchases.PurchasedOn
   - 交易金额：eCommerce.eCommercePurchases.TotalPrice
   - 产品 ID：eCommerce.eCommercePurchases.ProductId

1. 选择 **下一步**。

1. 在 **eCommercePurchases：电子商务** 实体与 **eCommerceContacts：电子商务** 之间建立关系。

1. **附加数据（可选）** 步骤允许您添加更多客户活动数据。 这些数据可以帮助获得更多关于客户与企业之间的交互的见解，这可能对 CLV 有影响。 添加关键客户交互（如 Web 日志、客户服务日志或奖励计划历史记录）可以提高预测的准确性。 选择 **添加数据** 以包含更多客户活动数据。

1. 添加客户活动实体，将其字段名称映射到模型所需的相应字段：
   - 客户活动实体：Reviews:Website
   - 主键：Website.Reviews.ReviewId
   - 时间戳：Website.Reviews.ReviewDate
   - 事件（活动名称）：Website.Reviews.ActivityTypeDisplay
   - 详细信息（金额或价值）：Website.Reviews.ReviewRating

1. 选择 **下一步** 并配置活动以及交易数据与客户数据之间的关系：  
   - 活动类型：选择现有项
   - 活动标签：审核
   - 相应的标签：Website.Reviews.UserId
   - 客户实体：eCommerceContacts:eCommerce
   - 关系：WebsiteReviews

1. 选择 **下一步** 以设置模型计划。

   当存在引入的新数据时，模型需要定期训练以学习新模式。 对于本示例，选择 **每月**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-4---review-model-results-and-explanations"></a>任务 4 - 审阅模型结果和说明

让模型完成数据的训练和评分。 接下来，您可以查看 CLV 模型的结果和解释。 有关详细信息，请参阅[审阅预测状态和结果](predict-customer-lifetime-value.md#review-prediction-status-and-results)。

## <a name="task-5---create-a-segment-of-high-value-customers"></a>任务 5 - 创建高价值客户的客户细分

运行模型可创建一个新实体，该实体列在 **数据** > **实体** 上。 您可以根据模型创建的实体创建新客户细分。

1. 转到 **客户细分**。 

1. 选择 **新建**，然后选择 **创建自** > **智能**。

   ![使用模型输出创建客户细分。](media/segment-intelligence.png)

1. 选择 **OOBeCommerceCLVPrediction** 实体并定义客户细分：
  - 字段：CLVScore
  - 运算符：大于
  - 值：1500

1. 选择 **审核** 并 **保存** 客户细分。

您现在有一个客户细分，该客户细分可识别预计在未来 12 个月内产生超过 1500 美元收入的客户。 如果引入更多数据，将动态更新此客户细分。

有关详细信息，请参阅[创建和管理客户细分](segments.md)。
