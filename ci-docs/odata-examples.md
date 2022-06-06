---
title: Dynamics 365 Customer Insights API 的 OData 示例
description: 用于查询 Customer Insights API 以查看数据的 Open Data Protocol (OData) 的常用示例。
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808450"
---
# <a name="odata-query-examples"></a>OData 查询示例

Open Data Protocol (OData) 是一种基于 HTTP 等核心协议构建的数据访问协议。 它使用普遍接受的方法，例如适用于 Web 的 REST。 有多种库和工具可用于使用 OData 服务。

本文列出了一些经常请求的示例查询，以帮助您根据 [Customer Insights API](apis.md) 生成您自己的实施。

您必须修改查询示例，使其在目标环境中能够正常工作： 

- {serviceRoot}：`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}`，其中 {instanceId} 是您要查询的 Customer Insights 环境的 GUID。 通过 [ListAllInstances 操作](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)，您可以找到您有权访问的 {InstanceId}。
- {CID}：统一客户记录的 GUID。 示例：`ce759201f786d590bf2134bff576c369`。
- {AlternateKey}：数据源中客户记录的主键标识符。 示例: `CNTID_1002`
- {DSname}：带有被引入到 Customer Insights 的数据源的实体名称的字符串。 示例：`Website_contacts`。
- {SegmentName}：带有 Customer Insights 中客户细分的输出实体名称的字符串。 示例：`Male_under_40`。

## <a name="customer"></a>客户

下表包含一组有关 *客户* 实体的示例查询。

|查询类型 |示例  | 备注  |
|---------|---------|---------|
|单个客户 ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|备用键    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  备用键保留在统一客户实体中       |
|选择   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|于    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|备用键 + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|搜索  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   返回搜索字符串的前 10 个结果      |
|客户细分成员身份  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | 从分段实体返回预设数量的行。      |

## <a name="unified-activity"></a>统一活动

下表包含一组有关 *UnifiedActivity* 实体的示例查询。

|查询类型 |示例  | 备注  |
|---------|---------|---------|
|CID 的活动     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | 列出特定客户配置文件的活动 |
|活动期限    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  期限内的客户配置文件的活动       |
|活动类型    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|按显示名称列出的活动     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|活动排序    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  按升序或降序对活动排序       |
|从客户细分成员身份扩展的活动  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>其他示例

下表包含一组有关其他实体的示例查询。

|查询类型 |示例  | 备注  |
|---------|---------|---------|
|CID 的度量    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|CID 的扩充品牌    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID 的扩充兴趣    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In 子句 + 展开     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>不支持的 OData 查询

Customer Insights 不支持以下查询：

- 针对引入的源实体的 `$filter`。 您只能对 Customer Insights 创建的系统实体运行 $filter 查询。
- `$search` 查询中的 `$expand`。 示例: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$select` 中的 `$expand`（如果只选择了属性的子集）。 示例: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` 扩充了给定客户的品牌或兴趣相似性。 示例: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- 通过备用键查询预测模型输出实体。 示例: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
