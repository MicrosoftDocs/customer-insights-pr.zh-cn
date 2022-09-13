---
title: 订阅流失预测（包含视频）
description: 预测客户是否存在不再使用贵公司的订阅产品或服务的风险。
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 72aa38242df21181f142833db03c825574455986
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171038"
---
# <a name="subscription-churn-prediction"></a>订阅流失预测

订阅流失预测功能有助于预测客户是否存在不再使用贵公司的订阅产品或服务的风险。 您可以在 **智能** > **预测** 页上创建新的订阅流失预测。 选择 **我的预测** 以查看您已创建的其他预测。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> 请试用使用示例数据的订阅流失预测的教程：[订阅流失预测示例指南](sample-guide-predict-subscription-churn.md)。

## <a name="prerequisites"></a>先决条件

- 至少具有[参与者权限](permissions.md)。
- 具有了解流失对您的业务意味着什么所必需的商业知识。 我们支持基于时间的流失定义，这意味着客户被视为在其订阅结束后已流失了一段时间。
- 有关您的订阅及其历史记录的数据：
    - 用于区分订阅的订阅标识符。
    - 用于使订阅与客户匹配的客户标识符。
    - 订阅事件日期，用于定义开始日期、结束日期和订阅事件发生日期。
    - 用于确定订阅是否是定期订阅及其续订频率的订阅信息。
    - 订阅的语义数据架构需要以下信息：
        - **订阅 ID：** 订阅的唯一标识符。
        - **订阅结束日期：** 客户的订阅到期日期。
        - **订阅开始日期：** 客户的订阅开始日期。
        - **事务日期：** 订阅更改的发生日期。 例如，客户购买或取消订阅的日期。
        - **是否为定期订阅：** 一个布尔型 true/false 字段，用于确定订阅是否将使用同样的订阅 ID 续订而不需要客户干预
        - **重复频率（以月为单位）：** 对于定期订阅，这是订阅续订的时间段。 它用月来表示。 例如，每年自动为客户续订一年的年度订阅的值是 12。
        - （可选）**订阅金额：** 客户为续订订阅而支付的货币金额。 它可以帮助确定不同订阅级别的模式。
- 有关客户活动的数据：
    - 用于区分相同类型的活动的活动标识符。
    - 用于将活动映射到客户的客户标识符。
    - 包含活动的名称和日期的活动信息。
    - 客户活动的语义数据架构包括：
        - **主键：** 活动的唯一标识符。 例如，用于表明客户观看电视节目剧集的网站访问或使用记录。
        - **时间戳：** 主键所标识事件的日期和时间。
        - **事件：** 您要使用的事件的名称。 例如，流视频服务中的一个名为“UserAction”的字段所具有的值可能为“已查看”。
        - **详细信息：** 有关事件的详细信息。 例如，流视频服务中的一个名为“ShowTitle”的字段所具有的值可能是客户观看过的视频。
- 建议的数据特征：
    - 足够的历史数据：订阅数据至少是所选时间窗口数据的两倍。 最好是两到三年的订阅数据。
    - 订阅状态：数据包括每个客户的活动和非活动订阅，因此每个客户 ID 都有多个条目。
    - 客户数量：至少 10 个客户配置文件，最好是超过 1,000 个唯一客户。 该模型将因客户少于 10 个以及历史数据不足而失败。
    - 数据完整性：在提供的实体的数据字段中，缺失值的不足 20%。
   
   > [!NOTE]
   > 您需要要为其计算流失的客户有 50% 至少有两个活动记录。

## <a name="create-a-subscription-churn-prediction"></a>创建订阅流失预测

1. 转到 **智能** > **预测**。
1. 选择 **订阅流失模型** 磁贴并选择 **使用此模型**。
   > [!div class="mx-imgBorder"]
   > ![具有“使用此模型”按钮的订阅流失模型磁贴。](media/subscription-churn-usethismodel.PNG "具有“使用此模型”按钮的订阅流失模型磁贴")

### <a name="name-model"></a>命名模型

1. 为模型提供一个名称，以区别于其他模型。
1. 仅使用字母和数字（不使用任何空格）为输出实体提供名称。 这是模型实体将使用的名称。 然后选择 **下一步**。

### <a name="define-customer-churn"></a>定义客户流失

1. 输入导致您的企业认为客户将处于流失状态的 **自订阅结束以来的天数**。 这段时间通常与报价或其他试图防止失去客户的市场营销工作等业务活动相关。
1. 输入 **预测将来以预测客户流失的天数** 来设置一个预测客户流失的窗口。 例如，预测您的客户在未来 90 天内流失的风险，以与您的市场营销保留工作保持一致。 根据您的特定业务要求，预测更长或更短时间的流失风险可能会使您难以解决流失风险配置文件中的因素。 选择 **下一步** 继续操作
   >[!TIP]
   > 您可以随时选择 **保存草稿**，将预测保存为草稿。 您可以在 **我的预测** 选项卡中查找草稿预测以继续操作。

### <a name="add-required-data"></a>添加所需数据

1. 针对 **订阅历史记录** 选择 **添加数据**，然后选择提供订阅历史记录信息的实体，如[先决条件](#prerequisites)中所述。
1. 如果未填充下面的字段，请配置您的订阅历史记录实体与客户实体之间的关系。
    1. 选择 **订阅历史记录实体**。
    1. 选择用于在订阅历史记录实体中标识客户的 **字段**。 它需要与您的客户实体的主要客户 ID 相关。
    1. 选择与您的主要客户实体相匹配的 **客户实体**。
    1. 输入一个用于描述关系的名称。
       > [!div class="mx-imgBorder"]
       > ![显示如何创建客户关系的“订阅历史记录”页。](media/subscription-churn-subscriptionhistoryrelationship.PNG "显示如何创建客户关系的“订阅历史记录”页")
1. 选择 **下一步**。
1. 将语义字段映射到订阅历史记录实体内的属性并选择 **保存**。 有关字段的说明，请查看[先决条件](#prerequisites)。
   > [!div class="mx-imgBorder"]
   > ![订阅历史记录页面显示了映射到所选订阅历史记录实体中的字段的语义属性。](media/subscription-churn-subscriptionhistorymapping.PNG "订阅历史记录页面显示了映射到所选订阅历史记录实体中的字段的语义属性")
1. 针对 **客户活动** 选择 **添加数据**，然后选择提供客户活动信息的实体，如先决条件中所述。
1. 选择与您要配置的客户活动类型匹配的活动类型。  如果未看到与所需活动类型匹配的选项，请选择 **新建** 并提供名称。
1. 您需要配置客户活动实体与客户实体之间的关系。
    1. 选择在客户活动表中标识客户的字段，此字段可以直接与客户实体的主要客户 ID 相关。
    1. 选择与您的主要客户实体相匹配的客户实体
    1. 输入一个用于描述关系的名称。
1. 选择 **下一步**。
1. 将语义字段映射到客户活动实体内的属性并选择 **保存**。 有关字段的说明，请查看[先决条件](#prerequisites)。
1. （可选）如果您有想要包括的任何其他客户活动，请重复上述步骤。
   > [!div class="mx-imgBorder"]
   > ![定义实体关系。](media/subscription-churn-customeractivitiesmapping.PNG "客户活动页面显示了映射到所选客户活动实体中的字段的语义属性")
1. 选择 **下一步**。

### <a name="set-schedule-and-review-configuration"></a>设置计划与查看配置

1. 设置频率以重新训练您的模型。 此设置对于更新预测的准确性很重要，因为在 Customer Insights 中引入了新数据。 大多数企业每个月可以重新进行一次训练，并取得良好的预测准确度。
1. 选择 **下一步**。
1. 查看配置。 通过在显示的值下面选择 **编辑**，可以返回到预测配置的任意部分。 或者，您也可以从进度指示器中选择配置步骤。
1. 如果正确配置了所有值，请选择 **保存并运行** 以开始预测过程。 在 **我的预测** 选项卡上，您可以查看预测的状态。 完成该过程可能需要几个小时，具体取决于预测中使用的数据量。

## <a name="review-a-prediction-status-and-results"></a>查看预测状态和结果

1. 在 **智能** > **预测** 上转到 **我的预测** 选项卡。
   > [!div class="mx-imgBorder"]
   > ![“我的预测”页面视图。](media/subscription-churn-mypredictions.PNG "“我的预测”页面视图")
1. 选择要查看的预测。
   - **预测名称：** 创建预测时提供的预测名称。
   - **预测类型：** 用于预测的模型类型
   - **输出实体：** 用于存储预测输出的实体的名称。 您可以在 **数据** > **实体** 中查找具有此名称的实体。    
     在输出实体中，*ChurnScore* 是预测的流失概率，*IsChurn* 是基于 *ChurnScore* 的二进制标签，阈值为 0.5。 默认阈值可能不适合您的方案。 使用首选阈值[创建新客户细分](segments.md#create-a-segment)。
   - **预测字段：** 系统仅为某些类型的预测填充此字段，此字段不用于订阅流失预测。
   - **状态：** 预测运行的当前状态。
        - **已排队：** 预测当前正在等待其他流程运行。
        - **刷新：** 预测当前运行到“评分”处理阶段以生成将流入输出实体的结果。
        - **失败：** 预测已失败。 选择 **日志** 以了解更多详细信息。
        - **已成功：** 预测已成功完成。 在垂直省略号下选择 **查看** 以查看预测
   - **已编辑：** 预测配置的更改日期。
   - **上次刷新**：预测刷新输出实体中的结果的日期。
1. 选择要查看其结果的预测旁边的垂直省略号并选择 **查看**。
   > [!div class="mx-imgBorder"]
   > ![预测的垂直省略号菜单中的选项视图，包括编辑、刷新、查看、日志和删除。](media/subscription-churn-verticalellipses.PNG "预测的垂直省略号菜单中的选项视图，包括编辑、刷新、查看、日志和删除")
1. 结果页中有三个主要部分的数据：
    1. **训练模型的性能：** A、B 或 C 为可能的分数。 此分数指示预测的性能，并可帮助您做出关于使用输出实体中存储的结果的决策。
        - 根据以下规则确定分数：
            - **A** 模型能够准确预测总预测的至少 50%，以及对流失客户的准确预测百分比至少超过历史平均流失率的 10%。
            - **B** 模型能够准确预测总预测的至少 50%，以及对流失客户的准确预测百分比最高可超过比历史平均流失率 10%。
            - **C** 模型准确预测不到总预测的 50%，或者对流失客户的准确预测百分比低于历史平均流失率时。
               > [!div class="mx-imgBorder"]
               > ![模型性能结果视图。](media/subscription-churn-modelperformance.PNG "模型性能结果视图")
    1. **流失的可能性（客户数量）：** 基于预测的客户流失风险的客户组。 如果您要创建具有高流失风险的客户细分，此数据可以在以后为您提供帮助。 此类客户细分有助于了解客户细分成员资格应在何处截止。
       > [!div class="mx-imgBorder"]
       > ![显示流失结果（已分成 0-100% 的范围）分布情况的图形。](media/subscription-churn-resultdistribution.PNG "显示流失结果（已分成 0-100% 的范围）分布情况的图形")
    1. **最具影响力的因素：** 创建预测时考虑了许多因素。 系统针对模型创建的汇总预测计算了每个因素的重要性。 您可以使用这些因素帮助验证预测结果。 或者，您也可以在以后使用该信息[创建客户细分](segments.md)，这些客户细分可能有助于影响客户流失风险。
       > [!div class="mx-imgBorder"]
       > ![显示影响因素及其在预测流失结果方面的重要性的列表。](media/subscription-churn-influentialfactors.PNG "显示影响因素及其在预测流失结果方面的重要性的列表")

## <a name="manage-predictions"></a>管理预测

可以对预测进行优化、排除故障、刷新或删除。 查看输入数据可用性报告，了解如何更快、更可靠地进行预测。 有关详细信息，请参阅[管理预测](manage-predictions.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]