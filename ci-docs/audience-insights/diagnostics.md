---
title: 使用 Azure Monitor 审核 Dynamics 365 Customer Insights
description: 了解如何将日志发送到 Microsoft Azure Monitor。
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354361"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>使用 Azure Monitor 在 Dynamics 365 Customer Insights 中转发日志（预览版）

Dynamics 365 Customer Insights 提供与 Azure Monitor 的直接集成。 利用 Azure Monitor 资源日志，可以监视日志并将其发送到 [Azure 存储](https://azure.microsoft.com/services/storage/)、[Azure 日志分析](/azure/azure-monitor/logs/log-analytics-overview)，或将它们流式传输至 [Azure 事件中心](https://azure.microsoft.com/services/event-hubs/)。

Customer Insights 将发送以下事件日志：

- **审核事件**
  - **APIEvent** - 启用通过 Dynamics 365 Customer Insights UI 完成的更改跟踪。
- **操作事件**
  - **WorkflowEvent** - 此工作流允许设置[数据源](data-sources.md)、[统一](data-unification.md)和[扩充](enrichment-hub.md)数据，并最终将数据[导出](export-destinations.md)到其他系统。 所有这些步骤都可以单独完成（例如，触发单个导出）或协调完成（例如，刷新来自触发统一过程的数据源的数据，此统一过程将引入其他扩充，并且在完成后会将数据导出到另一个系统）。 有关更多详细信息，请参阅 [WorkflowEvent 架构](#workflow-event-schema)。
  - **APIEvent** - 到 Dynamics 365 Customer Insights 的所有客户实例 API 调用。 有关更多详细信息，请参阅 [APIEvent 架构](#api-event-schema)。

## <a name="set-up-the-diagnostic-settings"></a>设置诊断设置

### <a name="prerequisites"></a>先决条件

要在 Customer Insights 中配置诊断，必须满足以下先决条件：

- 您有有效的 [Azure 订阅](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)。
- 您在 Customer Insights 中具有[管理员](permissions.md#administrator)权限。
- 您在 Azure 上的目标资源上拥有 **参与者** 和 **用户访问管理员** 角色。 该资源可以是 Azure 存储帐户、Azure 事件中心或 Azure Log Analytics 工作区。 有关详细信息，请参阅[使用 Azure 门户添加或删除 Azure 角色分配](/azure/role-based-access-control/role-assignments-portal)。
- 满足 Azure 存储、Azure 事件中心或 Azure 日志分析的[目标要求](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements)。
- 您在资源所属的资源组中至少具有 **读者** 角色。

### <a name="set-up-diagnostics-with-azure-monitor"></a>使用 Azure Monitor 设置诊断

1. 在 Customer Insights 中，选择 **系统** > **诊断** 以查看为此实例配置的诊断目标。

1. 选择 **添加目标**。

   > [!div class="mx-imgBorder"]
   > ![诊断连接](media/diagnostics-pane.png "诊断连接")

1. 在 **诊断目标的名称** 中提供名称。

1. 选择具有目标资源的 Azure 订阅的 **租户** 并选择 **登录**。

1. 选择 **资源类型**（存储帐户、事件中心或日志分析）。

1. 针对目标资源选择 **订阅**。

1. 针对目标资源选择 **资源组**。

1. 选择 **资源**。

1. 确认 **数据隐私与合规性** 声明。

1. 选择 **连接到系统** 以连接到目标资源。 如果 API 已在使用中并生成事件，则 15 分钟后日志开始显示在目标中。

### <a name="remove-a-destination"></a>删除目标

1. 转到 **系统** > **诊断**。

1. 在列表中选择诊断目标。

1. 在 **操作** 列中，选择 **删除** 图标。

1. 确认删除以停止日志转发。 Azure 订阅上的资源将不会被删除。 您可以选择 **操作** 列中的链接，以针对所选资源打开 Azure 门户并删除所选资源。

## <a name="log-categories-and-event-schemas"></a>记录类别和事件架构

目前[支持 API 事件](apis.md)和工作流事件，并且会应用以下类别和架构。
日志架构遵循 [Azure Monitor 通用架构](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)。

### <a name="categories"></a>类别

Customer Insights 提供以下两个类别：

- **审核事件**：[API 事件](#api-event-schema)，用于跟踪服务的配置更改。 `POST|PUT|DELETE|PATCH` 操作属于此类别。
- **操作事件**：使用服务时生成的 [API 事件](#api-event-schema)或[工作流事件](#workflow-event-schema)。  例如，工作流的 `GET` 请求或执行事件。

## <a name="configuration-on-the-destination-resource"></a>目标资源配置

根据您的资源类型选择，将自动应用下列步骤：

### <a name="storage-account"></a>Storage account

Customer Insights 服务主体获得对所选资源的 **存储帐户参与者** 权限，并在所选命名空间下创建两个容器：

- 包含 **审核事件** 的 `insight-logs-audit`
- 包含 **操作事件** 的 `insight-logs-operational`

### <a name="event-hub"></a>事件中心

Customer Insights 服务主体获得对资源的 **Azure 事件中心数据责任人** 权限，并将在所选命名空间下面创建两个事件中心：

- 包含 **审核事件** 的 `insight-logs-audit`
- 包含 **操作事件** 的 `insight-logs-operational`

### <a name="log-analytics"></a>Log Analytics

Customer Insights 服务主体获取对资源的 **日志分析参与者** 权限。 将在所选 Log Analytics 工作区的 **日志** > **表** > **日志管理** 下提供日志。 展开 **日志管理** 解决方案并查找 `CIEventsAudit` 和 `CIEventsOperational` 表。

- 包含 **审核事件** 的 `CIEventsAudit`
- 包含 **操作事件** 的 `CIEventsOperational`

在 **查询** 窗口下，展开 **审核** 解决方案并查找通过搜索 `CIEvents` 提供的示例查询。

## <a name="event-schemas"></a>事件架构

API 事件和工作流事件虽然不同，但它们具有通用的结构和详细信息，请参阅 [API 事件架构](#api-event-schema)或[工作流事件架构](#workflow-event-schema)。

### <a name="api-event-schema"></a>API 事件架构

| 字段             | DataType  | 必需/可选 | Description       | 示例        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | 时间戳 | 需要          | 事件的时间戳 (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | 需要          | 发出事件的实例的 ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | 需要          | 此事件表示的操作的名称。                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | 需要          | 事件的日志类别。 是 `Operational` 或者 `Audit`。 所有 POST/PUT/PATCH/DELETE HTTP 请求都标有 `Audit`，其他所有请求都标有 `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | 需要          | 事件的状态。 `Success`、`ClientError`、`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | 可选          | 事件的结果状态。 如果该操作对应于一个 REST API 调用，则它是 HTTP 状态代码。        | `200`             |
| `durationMs`      | Long      | 可选          | 操作的持续时间（以毫秒为单位）。     | `133`     |
| `callerIpAddress` | String    | 可选          | 调用方 IP 地址（如果操作对应于来自公开可用的 IP 地址的 API 调用）。                                                 | `144.318.99.233`         |
| `identity`        | String    | 可选          | 描述执行该操作的用户或应用程序的标识的 JSON 对象。       | 请参阅[标识](#identity-schema)部分。     |  |
| `properties`      | String    | 可选          | 具有更多特定事件类别属性的 JSON 对象。      | 请参阅[属性](#api-properties-schema)部分。    |
| `level`           | String    | 需要          | 事件的严重性级别。    | `Informational`、`Warning`、`Error` 或 `Critical`。           |
| `uri`             | String    | 可选          | 绝对请求 URI。    |               |

#### <a name="identity-schema"></a>标识架构

`identity` JSON 对象具有以下结构

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| 字段                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | 为用户或应用分配的角色。 有关详细信息，请参阅[用户权限](permissions.md)。                                     |
| `Authorization.RequiredRoles` | 执行该操作所需的角色。 允许 `Admin` 角色执行所有操作。                                                    |
| `Claims`                      | 用户或应用 JSON Web 令牌 (JWT) 的声明。 声明属性因组织和 Azure Active Directory 配置而异。 |

#### <a name="api-properties-schema"></a>API 属性架构

[API 事件](apis.md)具有以下属性。

| 字段                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | 始终为 `ApiEvent`，将日志事件标记为 API 事件。                                                                 |
| `properties.userAgent`       | 发送请求的浏览器代理或 `unknown`。                                                                        |
| `properties.method`          | HTTP 方法：`GET/POST/PUT/PATCH/HEAD`。                                                                                |
| `properties.path`            | 请求的相对路径。                                                                                          |
| `properties.origin`          | 指示 Fetch 来源的 URI 或 `unknown`。                                                                  |
| `properties.operationStatus` | `Success`（适用于 HTTP 状态代码 < 400） <br> `ClientError`（适用于 HTTP 状态代码 < 500） <br> `Error`（适用于 HTTP 状态 >= 500） |
| `properties.tenantId`        | 组织 ID                                                                                                        |
| `properties.tenantName`      | 组织的名称。                                                                                              |
| `properties.callerObjectId`  | 调用方的 Azure Active Directory ObjectId。                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>工作流事件架构

工作流包含多个步骤。 [引入数据源](data-sources.md)、[统一](data-unification.md)、[扩充](enrichment-hub.md)和[导出](export-destinations.md)数据。 通过以下过程，所有这些步骤都可以单独完成或协调完成。 

#### <a name="operation-types"></a>操作类型

| OperationType     | 组合                                     |
| ----------------- | ----------------------------------------- |
| 引入         | [数据源](data-sources.md)           |
| DataPreparation   | [数据源](data-sources.md)           |
| 映射               | [数据统一](data-unification.md)   |
| 匹配项             | [数据统一](data-unification.md)   |
| 合并​​             | [数据统一](data-unification.md)   |
| ProfileStore      | [客户配置文件](customer-profiles.md) |
| 搜索            | [客户配置文件](customer-profiles.md) |
| 活动          | [活动](activities.md)                  |
| AttributeMeasures | [客户细分和度量](segments.md)      |
| EntityMeasures    | [客户细分和度量](segments.md)      |
| 度量          | [客户细分和度量](segments.md)      |
| 分段      | [客户细分和度量](segments.md)      |
| 扩充        | [扩充](enrichment-hub.md)                                          |
| 智能      | [预测](predictions-overview.md)                                          |
| AiBuilder         | [预测](predictions-overview.md)                                          |
| 见解          | [预测](predictions-overview.md)                                          |
| Export            | [导出](export-destinations.md)                                          |
| ModelManagement   | [预测](custom-models.md)                                           |
| 关系      | [数据统一](relationships.md)                                           |

#### <a name="field-description"></a>字段说明

| 字段           | DataType  | 必需/可选 | Description                                                                                                                                                   | 示例                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | 时间戳 | 需要          | 事件的时间戳 (UTC)。                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | 需要          | 发出事件的实例的 ResourceId。                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | 需要          | 此事件表示的操作的名称。 `{OperationType}.[WorkFlow|Task][Started|Completed]`。 请参阅供参考的[操作类型 ](#operation-types)。 | `Segmentation.WorkflowStarted`，<br> `Segmentation.TaskStarted`， <br> `Segmentation.TaskCompleted`， <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | 需要          | 事件的日志类别。 对于工作流事件，始终为 `Operational`                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | 需要          | 事件的状态。 `Running`、`Skipped`、`Successful`、`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | 可选          | 操作的持续时间（以毫秒为单位）。                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | 可选          | 具有更多特定事件类别属性的 JSON 对象。                                                                                        | 请参阅[工作流属性](#workflow-properties-schema)子部分                                                                                                       |
| `level`         | String    | 需要          | 事件的严重性级别。                                                                                                                                  | `Informational`、`Warning` 或 `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>工作流属性架构

工作流事件具有以下属性。

| 字段              | Workflow | 任务 | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | 是      | 是  | 始终为 `WorkflowEvent`，将事件标记为工作流事件。                                                                                                                                                                                                |
| `properties.workflowJobId`                   | 是      | 是  | 工作流运行的标识符。 工作流执行中的所有工作流和任务事件都具有相同的 `workflowJobId`。                                                                                                                                   |
| `properties.operationType`                   | 是      | 是  | 操作标识符，请参阅[操作类型].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | 是      | No   | 仅工作流。 工作流触发的任务数。                                                                                                                                                                                                       |
| `properties.submittedBy`                     | 是      | No   | 可选。 仅工作流事件。 触发工作流的 Azure Active Directory [用户的 objectId](/azure/marketplace/find-tenant-object-id#find-user-object-id)，另请参阅 `properties.workflowSubmissionKind`。                                   |
| `properties.workflowType`                    | 是      | No   | `full` 或 `incremental` 刷新。                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | 是      | No   | `OnDemand` 或 `Scheduled`。                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | 是      | No   | `Running` 或 `Successful`。                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | 是      | 是  | UTC 时间戳`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | 是      | 是  | UTC 时间戳`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | 是      | 是  | UTC 时间戳`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | 是      | 是  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | 是  | - 对于 OperationType = `Export`，此标识符是导出配置的 guid。 <br> - 对于 OperationType = `Enrichment`，它是扩充的 guid <br> - 对于 OperationType `Measures` 和 `Segmentation`，此标识符是实体名称。 |
| `properties.friendlyName`                    | No       | 是  | 处理的导出或实体的用户友好名称。                                                                                                                                                                                           |
| `properties.error`                           | No       | 是  | 可选。 包含更多详细信息的错误消息。                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | 是  | 可选。 仅适用于 OperationType `Export`。 标识导出的类型。 有关详细信息，请参阅[导出目标概述](export-destinations.md)。                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | 是  | 可选。 仅适用于 OperationType `Export`。 在导出中包含已配置实体的列表。                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | 是  | 可选。 仅适用于 OperationType `Export`。 导出的详细消息。                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | 是  | 可选。 仅适用于 OperationType `Segmentation`。 指示此客户细分具有的成员总数。                                                                                                                                                    |
