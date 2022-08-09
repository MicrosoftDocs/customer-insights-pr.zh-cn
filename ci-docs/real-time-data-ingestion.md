---
title: 实时数据引入（预览版）
description: 有关 Customer Insights 中实时功能的一般信息。
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195647"
---
# <a name="real-time-data-ingestion-preview"></a>实时数据引入（预览版）

近实时功能让您可以在数秒内查看客户与您的产品或服务进行的最近交互。

[计划刷新](system.md#schedule-tab)包括大量记录和几个复杂操作。 首先，从数据源中提取数据。 接下来统一数据，然后使用更多信息进行扩充。 每次运行此过程都可能需要数分钟到数小时时间。

实时功能将立即提供数据以供使用，直到后续计划刷新从数据源中提取此数据。

实时更新有到期时间，此时间之后，更新不再会覆盖数据源中的值。

- 配置文件更新将保留四小时
- 活动将保留 30 天

这些值是您可以更改的 API 调用参数。 它们旨在确保源数据一直充当您的真相来源。 如果您希望实时更新保留更长时间，需要将其添加到数据源，以便在下次计划刷新期间获取它们。

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>统一客户配置文件字段的实时更新

更新的配置文件将在几秒钟内显示在客户卡视图或任何其他可视化中。

因为实时操作在数据统一后进行，所以仅适用于统一客户配置文件。 因此，实施配置文件更改不会更新度量、细分成员资格或扩充。

### <a name="limitations"></a>限制

- 可以更新，但是不能创建或删除客户配置文件。
- 目前不能将实时更新导出到外部系统，如 Power BI。

## <a name="real-time-creation-of-activities"></a>实时创建活动

实时 API 允许您将源系统中的新活动（单个源记录）发布到统一客户配置文件。 新活动将在数秒内在该统一客户配置文件的时间线中以统一活动的形式提供。 您可以在客户卡视图中查看该时间线或您配置的任何其他时间线集成。

> [!NOTE]
>
> - 活动不可变。 一经创建就不会改变。
> - 现在，细分和度量不会根据新活动更新。
> - 导出时不包含仅通过实时 API 添加的活动，所以不会在 PowerBI 中显示此类活动。

可通过两种方法连接到实时 API：

- [间接](#connect-via-the-dynamics-365-customer-insights-connector)，即使用 [Dynamics 365 Customer Insights 连接器](/connectors/customerinsights/)
- [直接 ](#connect-directly-to-the-real-time-api)，即使用代码

这两种方法都需要满足以下先决条件：

- Customer Insights 环境
- 统一客户配置文件
- 配置并运行的活动
- 用于对您的帐户进行身份验证的参与者或管理员权限

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>通过 Dynamics 365 Customer Insights 连接器连接

此实时 API 可以从专用 Power Platform 连接器（[Dynamics 365 Customer Insights 连接器](/connectors/customerinsights/)）引入数据，无需编写和部署任何代码。    
此连接器可以执行与 API 执行的相同实时操作。 需要高级连接器的有效许可证。 有关详细信息，请参阅 [Power Apps 和 Power Automate 许可常见问题解答](/power-platform/admin/powerapps-flow-licensing-faq)。

- Power Platform [Power Apps 和/或 Power Automate](/connectors/)
- Azure [逻辑应用](/azure/connectors/apis-list)

有关创建流的详细信息，请参阅 [Power Automate 文档](/power-automate/)。

## <a name="connect-directly-to-the-real-time-api"></a>直接连接到实时 API

您可以通过生成自己的管道并直接连接到实时 API 来使用实时功能。    
可发布源系统格式或 UnifiedActivity 格式的活动。 请通过对 /api/instances/{instanceId}/manage/entities/UnifiedActivity 进行 API 调用来获取该格式。

可在 [Customer Insights API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)的 **EntityData** 部分中找到此 API 的详细信息（包括参数和响应）。 有关详细信息，请参阅[使用 Customer Insights API](apis.md)。

## <a name="understand-your-real-time-usage-with-telemetry"></a>了解遥测时的实时使用情况

概要介绍实时 API 的请求量以及有关系统可能遇到的问题的信息。 您可以[访问实时遥测数据](system.md#api-usage-tab)。 


[!INCLUDE [footer-include](includes/footer-banner.md)]
