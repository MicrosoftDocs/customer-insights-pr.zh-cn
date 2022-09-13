---
title: Dynamics 365 Customer Insights 入门
description: Customer Insights 可帮助资源快速入门。
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304600"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 入门

Customer Insights 可帮助您更好地了解客户。 连接来自各种事务、行为和观察源的数据以建立 360 度的客户视图。 使用这些见解推动以客户为中心的体验和过程。 统一和理解客户数据，并利用数据来获得智能见解和采取行动。

## <a name="step-1-create-an-environment"></a>步骤 1：创建环境

首先，创造一个工作环境。 如果您的组织已经购买了许可证，请参阅[创建环境](create-environment.md)。 若要开始试用 Customer Insights，请参阅[设置试用环境](trial-signup.md)。

## <a name="step-2-explore-customer-insights"></a>步骤 2：浏览 Customer Insights

首次登录到 Customer Insights 时，配置设置并浏览该产品。

1. 使用 Microsoft Azure Active Directory (AAD) 用户帐户[登录到 Customer Insights](https://home.ci.ai.dynamics.com)。

1. 更改环境以查看演示数据并[了解 Customer Insights](home.md)。

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>步骤 3：引入、统一和设置数据的关系

统一配置文件是获取数据的见解和采取操作的基础。 从各个源中引入数据并运行数据统一过程以合并统一配置文件。 指定所引入实体之间的关系并使用扩充功能将信息添加到配置文件。

1. 通过从多个选项创建数据源来引入数据。 在 [Azure Data Lake Storage（包括 Common Data Model）](connect-common-data-model.md)、[Azure Synapse Analytics](connect-synapse.md)、[Microsoft Dataverse](connect-dataverse-managed-lake.md) 或 [Power Query 连接器](connect-power-query.md)之间进行选择。

1. 通过标识[源字段](map-entities.md)、删除[重复项](remove-duplicates.md)、[匹配条件](match-entities.md)和[统一字段](merge-entities.md)来运行[数据统一流程](data-unification.md)。

1. 熟悉[系统创建的实体](entities.md)并创建[引入的实体之间的关系](relationships.md)。

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>步骤 4：通过预测、活动和度量增强统一配置文件

通过设置统一的配置文件，增强您的数据并进一步增加它们提供的信息。

1. 在不断扩大的扩充提供商库中进行选择以[扩充客户数据](enrichment-hub.md)。

1. 使用[现成模型](predictions-overview.md)预测流失可能性或预期收入。

1. 根据引入的数据[配置活动](activities.md)，并在按时间排序的时间线中可视化与客户之间的交互。

1. [生成度量](measures.md)以衡量业务目标和 KPI。

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>步骤 5：通过各种导出选项创建客户细分和激活数据

现在，您的数据是完整的并且包含有关您的客户的大量信息，请寻找对这些数据采取操作的方法。

1. [创建客户细分](segments.md)（即客户数据的子集），以确保操作与目标客户有关。

1. 浏览不断扩大的[导出选项](export-destinations.md)目录， 可在这些选项中使用客户数据。 例如，可以使用数据管理促销和与数字市场营销联系。

1. 查看集成选项，例如与具有[客户卡加载项](customer-card-add-in.md)的其他 Dynamics 365 应用集成的选项。  


[!INCLUDE [footer-include](includes/footer-banner.md)]