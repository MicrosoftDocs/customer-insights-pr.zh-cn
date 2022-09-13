---
title: 使用企业客户
description: 了解 Dynamics 365 Customer Insights 中作为主要目标访问群体的企业客户。
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303905"
---
# <a name="work-with-business-accounts"></a>使用企业客户

Dynamics 365 Customer Insights 让您可以针对不同的主要目标访问群体配置您的环境：个人消费者（企业对客户）和企业客户（企业对企业）。 在企业对客户场景中，数据以个人为中心。 对于企业对企业，主要目标访问群体是客户（组织或公司）和联系人。 本文可帮助您开始使用企业客户环境。 文中根据您的环境焦点列出了 Customer Insights 中功能区域的差异。 有关差异的详细信息，请查看功能区域的文档。 

## <a name="create-an-environment-for-business-accounts"></a>创建企业客户环境

管理员可以[在现有组织中创建环境](create-environment.md)。 创建新环境过程中的一个步骤会要求管理员提供环境的主要目标访问群体。 如果是购买许可证后的初始设置，引导式体验有助于创建第一个环境。

然后，您可以[引入](data-sources.md)企业客户和相关联系人的数据作为所有支持的源的数据源。

 [统一](data-unification.md)您的客户数据，然后统一您的联系人数据来连接联系人和客户实体。

## <a name="switch-between-primary-target-audience"></a>在主要目标访问群体之间切换

如果您的组织为个人客户和企业客户维护环境，您可以使用左窗格中的切换器来选择主要目标访问群体。

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="在个人客户和企业客户之间更改主要目标访问群体的切换器。":::

## <a name="supported-feature-areas"></a>支持的功能区域

- [活动](activities.md)：支持客户和相关联系人创建活动并在时间线中显示活动。
- [关系](relationships.md)：活动向导帮助创建实体之间的关系，让客户视图可以显示联系人的所有活动。 联系人可以向上钻取来查看联系人视图，层次结构可用于客户活动聚合。
- [度量](measures.md)：支持通过一次计算从度量生成器创建的度量。 可选设置允许在创建度量时汇总子客户。
- [客户细分](segments.md)：支持使用客户细分生成器从头创建的客户细分。 客户细分可以基于客户或联系人。
- [数据引入](data-sources.md)：此区域的所有功能对于企业客户和个人客户均相同。
- 企业对企业数据统一与企业对客户数据统一非常相似，只是在客户统一后有一个额外的步骤来统一联系人。 请参阅[企业客户（企业对企业）](data-unification.md)。
- [扩充](enrichment-hub.md)：某些扩充类型仅适用于个人客户场景，而其他扩充类型仅适用于企业客户。
- [预测和现成模型](predictions-overview.md)：交易流失预测包含针对企业客户的额外步骤。 其他预测仅适用于个人客户。
- [激活和导出](export-destinations.md)：导出可用于企业客户和个人客户。 某些导出需要额外的配置以及在基础客户细分中投射的联系信息才能对企业客户有效。
- [系统设置](system.md)和[用户管理](permissions.md)：此区域的所有功能对于企业客户和个人客户均相同。

[!INCLUDE [footer-include](includes/footer-banner.md)]