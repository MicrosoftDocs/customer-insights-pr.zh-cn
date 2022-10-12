---
title: 客户生存期值 (CLV) 预测示例指南
description: 使用此示例指南试用客户生存期值模型。
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609627"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>客户生存期值 (CLV) 预测示例指南

本指南将使用示例数据逐步向您解释 Customer Insights 中的客户生存期值 (CLV) 预测端到端示例。 我们建议您[在新环境中](manage-environments.md)试用此预测。

## <a name="scenario"></a>场景

Contoso 是一家生产高品质咖啡和咖啡机的公司。 他们通过 Contoso Coffee 网站销售产品。 公司希望了解客户在未来 12 个月内可以产生的价值（收入）。 了解客户在未来 12 个月的预期价值将有助于他们将营销工作转向高价值客户。

## <a name="prerequisites"></a>先决条件

- 至少具有[参与者权限](permissions.md)。

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

1. **保存** 数据源。

### <a name="ingest-online-purchase-data"></a>引入在线购买数据

1. 将另一个数据集添加到相同的 **电子商务** 数据源中。 再次选择 **文本/CSV** 连接器。

1. 输入 **在线购买** 数据的 URL https://aka.ms/ciadclassonline。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **PurchasedOn**：日期/时间
   - **TotalPrice**：货币

1. 在侧窗格上的 **名称** 字段中，将您的数据源重命名为 **eCommercePurchases**。

1. **保存** 数据源。

### <a name="ingest-customer-data-from-loyalty-schema"></a>从忠诚度架构中引入客户数据

1. 创建一个名为 **LoyaltyScheme** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入会员客户的 URL https://aka.ms/ciadclasscustomerloyalty。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **DateOfBirth**：日期
   - **RewardsPoints**：整数
   - **CreatedOn**：日期/时间

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **loyCustomers**。

1. **保存** 数据源。

### <a name="ingest-customer-data-from-website-reviews"></a>从网站评价中引入客户数据

1. 创建一个名为 **Website** 的数据源，然后选择 **文本/CSV** 连接器。

1. 输入网站评论的 URL https://aka.ms/CI-ILT/WebReviews。

1. 编辑数据时，选择 **转换**，然后选择 **使用第一行作为标题**。

1. 更新下面列出的列的数据类型：
   - **ReviewRating**：十进制数
   - **ReviewDate**：日期

1. 在右侧窗格上的 **名称** 字段中，将您的数据源重命名为 **Reviews**。

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

1. 添加另一个活动并将其字段名称映射到相应的字段：
   - **活动实体**：Reviews:Website
   - **主键**：ReviewId
   - **时间戳**：ReviewDate
   - **事件活动**：ActivityTypeDisplay
   - **其他详细信息**：ReviewRating
   - **活动类型**：Review

1. 运行活动。

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>任务 4 - 配置客户生存期值预测

部署了统一客户配置文件并创建了活动后，运行客户生存期值 (CLV) 预测。 有关详细步骤，请参阅[客户生存期值预测](predict-customer-lifetime-value.md)。

1. 转到 **智能** > **预测**。

1. 在 **创建** 选项卡上，在 **客户生存期值** 磁贴上选择 **使用模型**。

1. 选择 **开始**。

1. 将模型命名为 **OOB 电子商务 CLV 预测**，将输出实体命名为 **OOBeCommerceCLVPrediction**。

1. 定义模型首选项：
   - **预测时间段**：**12 个月或 1 年**，定义要预测 CLV 的未来时长。
   - **活跃客户**：**让模型计算购买间隔**，限定客户在此期间必须至少有一笔交易才会被视为活跃的期限。
   - **高价值客户**：手动将高价值客户定义为 **排名在前 30% 的活跃客户**。

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 模型的引导式体验中的首选项步骤。":::

1. 选择 **下一步**。

1. 在 **所需数据** 步骤中，选择 **添加数据** 以提供交易历史记录数据。

    :::image type="content" source="media/clv-model-required.png" alt-text="在 CLV 模型的引导式体验中添加所需的数据步骤。":::

1. 选择 **SalesOrderLine** 和 eCommercePurchases 实体，然后选择 **下一步**。 所需数据会从活动自动填入。 选择 **保存**，然后选择 **下一步**。

1. **其他数据（可选）** 步骤允许您添加更多客户活动数据以获得更多客户交互方面的见解。 对于本示例，选择 **添加数据**，添加 Web 评论活动。

1. 选择 **下一步**。

1. 在 **数据更新** 步骤中，为模型计划选择 **每月**。

1. 选择 **下一步**。

1. 在查看所有详细信息后，选择 **保存并运行**。

## <a name="task-5---review-model-results-and-explanations"></a>任务 5 - 审阅模型结果和说明

让模型完成数据的训练和评分。 查看 [CLV 模型结果和说明](predict-customer-lifetime-value.md#view-prediction-results)。

## <a name="task-6---create-a-segment-of-high-value-customers"></a>任务 6 - 创建高价值客户的客户细分

运行模型可创建一个新实体，该实体列在 **数据** > **实体** 上。 您可以根据模型创建的实体创建新客户细分。

1. 在结果页上，选择 **创建客户细分**。

1. 使用 **OOBeCommerceCLVPrediction** 实体创建规则并定义客户细分：
   - **字段**：CLVScore
   - **运算符**：大于
   - **值**：1500

1. 选择 **保存** 并 **运行** 客户细分。

您现在有一个客户细分，该客户细分可识别预计在未来 12 个月内产生超过 1500 美元收入的客户。 如果引入更多数据，将动态更新此客户细分。 有关详细信息，请参阅[创建和管理客户细分](segments.md)。

> [!TIP]
> 您还可以通过选择 **新建** 并选择 **创建自** > **智能**，从 **客户细分** 页面为预测模型创建客户细分。 有关详细信息，请参阅[使用快速客户细分创建新客户细分](segment-quick.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
