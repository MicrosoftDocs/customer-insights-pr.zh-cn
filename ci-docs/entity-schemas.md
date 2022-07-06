---
title: Common Data Model 中的实体架构
description: 使用 Common Data Model 中的实体。
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 92d37fc0950fefcb5c2a5d26214a469d3693980d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054743"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model 中的实体架构

[Common Data Model](/common-data-model/) 声明性规范，也是代表跨多种企业和生产力应用程序的常用概念和活动的标准实体的定义。 此模型也将延伸到观察数据和分析数据。 Common Data Model 提供明确定义、模块化和可扩展的业务实体（例如帐户、业务部门、用例、联系人、潜在客户、机会和产品），还提供与供应商、员工和客户之间的交互（例如活动和服务级别协议）。 任何人都可以生成和扩展 Common Data Model 定义以捕获更多特定于业务的观点。

此共享数据模型可供应用程序和数据集成者通过提供统一的数据定义来进行协作。 Common Data Model 中包含丰富的元数据系统和标准实体、关系、层次结构、特征等。 其源自 Dynamics 365 应用，具有 260 多个标准实体，并在 GitHub 上开源。 内部和外部合作伙伴构成的大型系统为 Common Data Model 贡献了业界专有的概念。

现在，多个系统和平台实施了 Common Data Model，包括 Power BI 数据流和 Azure 数据服务。 Microsoft Dataverse、Dynamics 365、Power Apps、Power BI 和即将推出的 Azure 数据服务中已对其提供了支持，直接增长了[开放数据方案](https://dynamics.microsoft.com/en-us/open-data-initiative/)的价值。

## <a name="customer-insights-entity-schemas"></a>Customer Insights 实体架构

为了建立 360 度的客户视图和在 Common Data Model 中提供 Customer Insights 模型以进行扩展，我们发布了以下实体架构：

| 实体 | 说明 |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | 用户执行且具有业务的观察价值的活动。 |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | 执行了业务活动或有潜力参与业务活动的人员或组织。 |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | 无或多个维度划分的 KPI（如月度活跃用户、客户总开支、平均获客成本）的定义 |
|[细分](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | 定义一组具有共同特征的成员。 |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | 参与给定细分的成员。 |

有关详细信息，请参阅有关 [Common Data Model 中的 Customer Insights 实体架构](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)的文档。

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>使用 Common Data Model 实体导航器查看实体

您可以在 [Common Data Model 实体导航器中](https://microsoft.github.io/CDM/)查看实体。 从“Insights 应用程序”部分选择一个实体，以便获取 Customer Insights 实体的列表及其定义。
> [!div class="mx-imgBorder"]
> ![CDM 实体导航器，其中显示了 CustomerActivity 实体。](media/CDM-entity-navigator.png "CDM 实体导航器，其中显示了 CustomerActivity 实体")


[!INCLUDE [footer-include](includes/footer-banner.md)]
