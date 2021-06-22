---
title: Microsoft Dataverse 中的 Customer Insights 数据
description: 使用 Customer Insights 实体作为 Microsoft Dataverse 中的表。
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259180"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>使用 Microsoft Dataverse 中的 Customer Insights 数据

Customer Insights 提供了使输出实体在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md) 中可用的选项。 这种集成通过低代码/无代码方法实现了轻松的数据共享和自定义开发。 输出实体将可用作 Dataverse 中的表。 这些表通过 Power Apps 支持一些方案，如[通过 Power Automate 实现的自动工作流](/power-automate/getting-started)、[模型驱动应用](/powerapps/maker/model-driven-apps/)和[画布应用](/powerapps/maker/canvas-apps/)。 您可以将数据用于基于 Dataverse 表的任何其他应用程序。 当前实施主要支持可以针对给定客户 ID 提取可用访问群体见解实体数据的查找。

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>将 Dataverse 环境附加到 Customer Insights

**具有现有 Dataverse 环境的组织**

当管理员设置访问群体见解时，已经使用 Dataverse 的组织可以[使用他们现有的 Dataverse 环境之一](manage-environments.md#create-an-environment-in-an-existing-organization)。 通过提供 Dataverse 环境 URL，它将附加到其新访问群体见解环境。 为了确保可能的最佳性能，Customer Insights 和 Dataverse 环境必须托管在同一区域。

要附加 Dataverse 环境，请在创建访问群体见解环境时扩展 **高级设置**。 提供 **Microsoft Dataverse 环境 URL** 并选择相应复选框以 **启用数据共享**。

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

**新建组织**

如果您在设置 Customer Insights 时创建了一个新组织，您将自动获得新的 Dataverse 环境。

> [!NOTE]
> 如果您的组织已经在其租户中使用 Dataverse，请务必记住，[Dataverse 环境创建由管理员控制](/power-platform/admin/control-environment-creation.md)。例如，如果您正在使用组织帐户设置新的访问群体见解环境，并且管理员已禁止为除管理员以外的所有人创建 Dataverse 试用环境，则无法创建新的试用环境。
> 
> 在 Customer Insights 中创建的 Dataverse 试用环境具有不计入租户总容量的 3 GB 存储空间。  通过付费订阅，可以获得 15 GB 数据库和 20 GB 文件存储空间的 Dataverse 权利。

## <a name="output-entities"></a>输出实体

一些来自访问群体见解的输出实体可在 Dataverse 中用作表格。 下面的部分描述了这些表格的预期架构。

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [扩充](#enrichment)
- [预测](#prediction)


### <a name="customerprofile"></a>CustomerProfile

此表包含来自 Customer Insights 的统一客户配置文件。 统一客户配置文件的架构取决于合并过程中使用的实体和属性。 客户配置文件架构通常包含来自 [CustomerProfile Common Data Model 定义](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)的属性子集。

### <a name="alternatekey"></a>AlternateKey

AlternateKey 表包含参与统一流程的实体的键。

|Column  |Type  |描述  |
|---------|---------|---------|
|DataSourceName    |String         | 数据源的名称。 例如: `datasource5`        |
|EntityName        | String        | 访问群体见解中的实体的名称。 例如: `contact1`        |
|AlternateValue    |String         |映射到客户 ID 的备用 ID。 示例: `cntid_1078`         |
|KeyRing           | 多行文本        | JSON 值  </br> 示例：[{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | 统一客户配置文件的 ID。         |
|AlternateKeyId     | GUID         |  基于 msdynci_identifier 的 AlternateKey 确定性 GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> 示例：`testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

此表包含 Customer Insights 中可用的用户活动。

| Column            | Type        | 描述                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | 客户配置文件 ID                                                                      |
| ActivityId        | String      | 客户活动的内部 ID（主键）                                       |
| SourceEntityName  | String      | 源实体的名称                                                                |
| SourceActivityId  | String      | 源实体的主键                                                       |
| ActivityType      | String      | 语义活动类型或自定义活动的名称                                        |
| ActivityTimeStamp | 日期/时间    | 活动时间戳                                                                      |
| 职务             | String      | 活动的标题或名称                                                               |
| 描述       | String      | 活动说明                                                                     |
| URL               | String      | 特定于活动的外部 URL 的链接                                         |
| SemanticData      | JSON 字符串 | 包括特定于活动类型的语义映射字段的键值对列表 |
| RangeIndex        | String      | 用于排序活动时间线和有效范围查询的 Unix 时间戳 |
| mydynci_unifiedactivityid   | GUID | 客户活动的内部 ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

此表包含基于客户属性的度量输出数据。

| Column             | Type             | 描述                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | 客户配置文件 ID        |
| 度量           | JSON 字符串      | 包括给定客户的度量名称和值的键值对列表 | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | 客户配置文件 ID |


### <a name="enrichment"></a>扩充

此表包含扩充流程的输出。

| Column               | Type             |  描述                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | 客户配置文件 ID                                 |
| EnrichmentProvider   | String           | 扩充的提供程序的名称                                  |
| EnrichmentType       | String           | 扩充的类型                                      |
| 值               | JSON 字符串      | 扩充流程产生的属性列表 |
| msdynci_enrichmentid | GUID             | 通过 msdynci_identifier 产生的确定性 GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>预测

此表包含模型预测的输出。

| Column               | Type        | 描述                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | 客户配置文件 ID                                  |
| ModelProvider        | String      | 模型的提供程序的名称                                      |
| 模型                | String      | 模型名称                                                |
| 值               | JSON 字符串 | 模型产生的属性列表 |
| msdynci_predictionid | GUID        | 通过 msdynci_identifier 产生的确定性 GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
