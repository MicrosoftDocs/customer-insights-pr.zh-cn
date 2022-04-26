---
title: Microsoft Dataverse 中的 Customer Insights 数据
description: 使用 Customer Insights 实体作为 Microsoft Dataverse 中的表。
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547615"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>使用 Microsoft Dataverse 中的 Customer Insights 数据

Customer Insights 提供了使输出实体在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) 中可用的选项。 这种集成通过低代码/无代码方法实现了轻松的数据共享和自定义开发。 [输出实体](#output-entities)可用作 Dataverse 环境中的表。 您可以基于 Dataverse 表将数据用于任何其他应用程序。 这些表支持通过 Power Automate 执行自动工作流或使用 Power Apps 生成应用等方案。 当前的实施主要支持查找，通过这些查找，可以为给定的客户 ID 提取来自可用 Customer Insights 实体的数据。

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>将 Dataverse 环境附加到 Customer Insights

**现有组织**

管理员可以在创建 Customer Insights 环境时将 Customer Insights 配置为[使用现有 Dataverse 环境](create-environment.md)。 通过提供 Dataverse 环境 URL，它将附加到其新访问群体见解环境。 Customer Insights 和 Dataverse 环境必须托管在同一区域。 

如果不希望使用现有 Dataverse 环境，则系统会为租户中的 Customer Insights 数据创建新环境。 

> [!NOTE]
> 如果您的组织已经在其租户中使用 Dataverse，请务必记住，[Dataverse 环境创建由管理员控制](/power-platform/admin/control-environment-creation)。例如，如果您正在使用组织帐户设置新的访问群体见解环境，并且管理员已禁止为除管理员以外的所有人创建 Dataverse 试用环境，则无法创建新的试用环境。
> 
> 在 Customer Insights 中创建的 Dataverse 试用环境具有不计入租户总容量的 3 GB 存储空间。  通过付费订阅，可以获得 15 GB 数据库和 20 GB 文件存储空间的 Dataverse 权利。

**新建组织**

如果您在设置 Customer Insights 时创建新组织，则系统会自动在您的组织中为您创建一个新的 Dataverse 环境。

## <a name="output-entities"></a>输出实体

一些来自访问群体见解的输出实体可在 Dataverse 中用作表格。 下面的部分描述了这些表格的预期架构。

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [扩充](#enrichment)
- [预测](#prediction)
- [客户细分成员身份](#segment-membership)


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

### <a name="segment-membership"></a>客户细分成员身份

此表包含客户配置文件的客户细分成员身份信息。

| Column        | 类型​​ | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | 客户配置文件 ID        |
| SegmentProvider      | String       | 发布客户细分的应用。 默认：访问群体见解         |
| SegmentMembershipType | String       | 此客户细分成员身份记录的客户类型。 支持多种类型，例如顾客、联系人或客户。 默认：客户  |
| 客户细分       | JSON 字符串  | 客户配置文件所属的独特客户细分的列表      |
| msdynci_identifier  | String   | 客户细分成员身份记录的唯一标识符。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | 从 `msdynci_identifier` 中生成的确定 GUID          |
