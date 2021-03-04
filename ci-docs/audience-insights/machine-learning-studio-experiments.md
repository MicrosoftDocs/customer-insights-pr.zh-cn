---
title: 机器学习工作室（经典）试验
description: 在 Dynamics 365 Customer Insights 中使用机器学习工作室（经典）模型。
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 8a861d62bdfee6a3a82468fe1ab4a3fbbdad43d4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270193"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>基于 Azure 机器学习工作室（经典）使用模型

Dynamics 365 Customer Insights 中的统一数据是构建可生成其他业务见解的机器学习模型的来源。 Customer Insights 与机器学习工作室（经典）集成以使用您自己的自定义模型。 若要了解在 Azure 机器学习中开发的模型如何与 Customer Insights 集成，请参阅 [Azure 机器学习试验](azure-machine-learning-experiments.md)。

## <a name="prerequisites"></a>先决条件

- Customer Insights 访问权限
- 有效的 Azure Enterprise 订阅
- [统一客户配置文件](data-unification.md)
- [实体导出到 Azure Blob 存储](export-azure-blob-storage.md)设置

## <a name="set-up-machine-learning-studio-classic"></a>设置机器学习工作室（经典）

在第一步中，我们需要创建工作区并打开机器学习工作室（经典）。

1. 转到 [https://www.portal.azure.com](https://www.portal.azure.com/) 并登录。

1. 选择 **创建资源**。

1. 搜索 **机器学习工作室工作区**，然后选择 **创建**。

1. 输入[创建工作区](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace)所需的详细信息。 基于您计划导入的数据量选择 **Web 服务计划定价层**。 为了获得最佳性能，请选择地理位置最靠近您的 **位置**。

1. 创建资源后，将显示机器学习工作室工作区仪表板。 选择 **启动机器学习工作室**。

   ![Azure 机器学习工作室用户界面](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>使用 Azure 机器学习工作室

现在，您可以创建一个新试验，或从示例库导入现有试验模板。 以下是用于三种标准场景的试验示例：

- [流失预测](#churn-analysis)

- [客户生命周期值](#customer-lifetime-value-prediction)

- [产品建议或下一个最佳操作](#productrecommendation-or-next-best-action)

1. 如果您从图库创建新试验或使用试验模板，则需要配置 **导入数据** 属性。 使用引导式体验或直接提供详细信息以访问包含您的数据的 Azure Blob 存储。  

   ![Azure 机器学习工作室试验](media/azure-machine-learning-studio-experiment.png)

1. 现在，您可以构建自定义处理管道来清理和预处理数据、提取特征，以及训练合适的模型。

1. 测试和优化模型性能。

1. 当您对模型的质量感到满意时，选择 **设置 Web 服务** > **预测性 Web 服务**。 此选项将训练后的模型和特征化管道从训练试验导入到预测性服务。 预测性服务可以采用训练试验中使用的架构获取另一组输入数据，来进行预测。

   ![设置预测性 Web 服务](media/predictive-webservice-control.png)

1. 预测性 Web 服务试验成功后，您可以将其部署为进行自动计划。 要使 Web 服务与 Customer Insights 一起使用，请选择 **部署 Web 服务** > **部署 Web 服务[新]预览**。 [了解有关部署 Web 服务的详细信息](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service)。

   ![部署预测性 Web 服务](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>库中的模型示例

在本文中，我们将使用虚拟的 Contoso 酒店场景作为模型。 Contoso 酒店收集以下数据：

- 由酒店住宿活动组成的 CRM 数据。 此数据集包含有关每个注册客户的入住日期的信息。 还包含有关预订、房间类型、支出明细等信息。 数据跨度为四年，从 2014 年 1 月到 2018 年 1 月。
- 酒店来宾的客户资料。 这些资料包含有关每个客户的信息，包括他们的姓名、生日、邮政地址、性别和电话号码。
- 对酒店提供服务的使用情况，如水疗中心、洗衣房、WiFi 或快递。 将为每个注册客户记录此信息。 通常，服务的使用与住宿相关。 在某些情况下，客户不入住酒店也可以使用服务。

## <a name="churn-analysis"></a>流失分析

流失分析适用于不同的业务领域。 在此示例中，我们将专门在酒店服务上下文中查看服务流失，如上所述。 它提供端到端模型管道的工作示例，可用作任何其他类型的流失模型的起点。

### <a name="definition-of-churn"></a>定义流失

流失的定义可能会因场景而异。 在此示例中，过去一年未来过酒店的来宾应标记为已流失。  

试验模板可以从库中导入。 首先，请确保从 Azure Blob 存储导入 **酒店住宿活动**、**客户数据** 和 **服务使用数据** 的数据。

   ![为流失模型导入数据](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>特征化

根据流失的定义，我们首先确定将影响此标签的原始特征。 然后，我们将这些原始特征处理为可在机器学习模型中使用的数字特征。 在 Customer Insights 中进行数据集成，以便我们可以使用 *客户 ID* 加入这些表。

   ![联接导入的数据](media/join-imported-data.png)

生成流失分析模型的特征化可能有些棘手。 此数据是一个时间函数，每天记录新的酒店活动。 在特征化期间，我们想要从动态数据生成静态特征。 在此情况下，我们通过一年的滑动窗口从酒店活动生成多个特征。 我们还使用一次性编码将房间类型或预订类型等分类特征扩展为单独特征。  

最后的特征列表：

| **编号**  | **Original_Column**          | **派生特征**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | 房间类型                    | RoomTypeLargeCount、RoomTypeSmallCount                                                                                                    |
| 2           | 预订类型                 | BookingTypeOnlineCount、BookingTypePhoneCallCount                                                                                         |
| 3           | 旅行类别              | TravelCategoryBusinessCount、TravelCategoryLeisureCount                                                                                   |
| 4           | 支出金额                | TotalDollarSpent                                                                                                                          |
| 5           | 入住和退房日期  | StayDayCount、StayDayCount2016、StayDayCount2015、StayDayCount2014、StayCount、StayCount2016。 StayCount2015、StayCount2014                |
| 6           | 服务用户                | UsageTenure、ConciergeUsage、CourierUsage、DryCleaningUsage、GymUsage、PhoneUsage、RestaurantUsage、SpaUsage、TelevisionUsage、WifiUsage  |

### <a name="model-selection"></a>模型选择

现在，我们需要选择要使用的最佳算法。 在此例中，大多数特征基于分类特征。 通常，基于决策树的模型效果较好。 如果仅存在数字特征，神经网络可能是更好的选择。 在这种情况下，支持向量机 (SVM) 也很适合；但是，需要进行大量调整才能获得最佳性能。 我们选择的第一个模型是 **两类提升决策树**，第二个模型是 **两类 SVM**。 Azure 机器学习工作室可让您进行 A/B 测试，因此从两个模型而不是一个模型开始是有好处的。

下图显示了 Azure 机器学习工作室的模型训练和评估管道：

![Azure 机器学习工作室中的流失模型](media/azure-machine-learning-model.png)

我们还应用称为 **排列特征重要性** 的技术，这是模型优化的重要方面。 内置模型几乎看不到任何特定特征对最终预测的影响。 特征重要性计算器使用自定义算法来计算单个特征对特定模型结果的影响。 特征重要性标准化为 +1 到 -1 的值。 负面影响意味着相应的特征对结果具有与直觉相反的影响，应从模型中删除。 正面影响表明该特征对预测有重大贡献。 这些值不是相关系数，因为它们是不同的指标。 有关详细信息，请参阅[排列特征重要性](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance)。

整个[流失试验在 Azure AI 库中提供](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp)。

## <a name="customer-lifetime-value-prediction"></a>客户生命周期值预测

客户生命周期价值 (CLTV) 计算是企业可用来评估和细分客户的关键指标之一。 对于酒店企业而言，了解客户至关重要。 例如，了解构成良好客户的因素是至关重要的信息。 它可以帮助酒店管理层评估他们需要重点关注和改进的特征，以让高消费客户满意。 这些决策可能直接影响销售和收益。  

### <a name="definition-of-cltv"></a>定义 CLTV

对于此示例，我们将客户的 CLTV 定义为期望客户在接下来的 365 天内支出的总金额。 我们将使用过去三年所有客户的数据来预测此值。

### <a name="featurization"></a>特征化

在此例中，特征化与流失场景很相似。 但是，标签和预测值与上面定义的不同。

### <a name="model-selection"></a>模型选择

由于预测值是一个正连续变量，因此预测 CLTV 是一个回归问题。 根据特征属性，我们选择 **提升决策树回归** 作为训练模型的一种算法，选择 **神经网络回归** 作为另一种算法。

## <a name="product-recommendation-or-next-best-action"></a>产品建议或下一个最佳操作

酒店场景中的产品建议被解释为酒店向客户提供的建议服务。 目的是为客户选择适当的服务，以最大程度地增加他们对服务的使用。 这类似于针对视频流服务用户的电影推荐。

### <a name="definition-of-product-recommendation-or-next-best-action"></a>定义产品建议或下一个最佳操作

我们将目标定义为通过根据酒店客户的兴趣向他们提供最匹配的服务，来最大程度地提高使用服务的支出金额。

### <a name="featurization"></a>特征化

与流失模型一样，我们将酒店 ServiceCustomerID 与 CustomerID 联接，以按照 CustomerID 一致地生成建议。

![建议模型的特征化](media/azure-machine-learning-model-featurization.png)

数据源自三个不同的实体，特征从这些实体中派生。 与流失或 CLTV 场景相比，建议问题的特征化有所不同。 建议模型需要以三组特征的形式输入数据。

### <a name="model-selection"></a>模型选择

我们使用称为 **训练 Matchbox 推荐器** 的算法来训练建议模型，从而预测产品或服务。

![产品建议算法](media/azure-machine-learning-model-recommendation-algorithm.png)

**训练 Matchbox 推荐器** 模型的三个输入端口获取培训服务使用数据、客户描述（可选）和服务描述。 有三种不同的模型评分方法。 一种用于模型评估，其计算标准化折扣累积收益 (NDCG) 分数来对评级项目进行排名。 在此试验中，我们的 NDCG 分数为 0.97。 另外两个选项是在整个可建议服务目录上对模型进行评分，或仅对用户之前未使用过的项目评分。

进一步查看建议在整个服务目录上的分布情况，我们注意到，电话、WiFi 和快递是要建议的几个排名最靠前的服务。 这与我们从服务使用数据的分布中发现的一致：

![建议模型输出](media/azure-machine-learning-model-output.png)

整个[产品建议试验可在 Azure AI 库中访问。](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>集成自定义模型

若要在 Customer Insights 中使用这些预测，您需要 **导出** 预测以及客户 ID。 [将其导出到相同的 Azure Blob 存储位置](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs)，您要向该位置导出元数据。 可以将预测性 Web 服务计划为定期运行，然后更新分数。

自定义模型生成的数据可用于进一步扩充您的客户数据。 有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]