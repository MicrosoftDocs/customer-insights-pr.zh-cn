---
title: 使用数据源引入数据
description: 了解如何从各个数据源导入数据。
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645592"
---
# <a name="data-sources-overview"></a>数据源概述



Dynamics 365 Customer Insights 连接到来自一组广泛来源的数据。 连接到数据源通常称为 *数据引入* 过程。 引入数据后，您可以[统一](data-unification.md)数据并对其执行操作。

## <a name="add-a-data-source"></a>添加数据源

请参阅详细文章以了解如何根据选择的选项添加数据源。

您可以添加以下数据源：

- [通过许多 Power Query 连接器](connect-power-query.md)
- [从 Common Data Model 文件夹](connect-common-data-model.md)
- [从您自己的 Microsoft Dataverse 湖](connect-dataverse-managed-lake.md)
- [从 Azure Synapse Analytics 数据库](connect-synapse.md)

> [!NOTE]
> 如果您使用的是试用版，则导入方法部分包含 **Customer Insights 数据库** 选项。 选择此选项可选择适用于各个行业的示例数据集。 有关详细信息，请参阅 [Dynamics 365 Customer Insights 试用版](trial-signup.md)。

## <a name="add-data-from-on-premises-data-sources"></a>添加来自本地数据源的数据

基于 Microsoft Power Platform 数据流，支持从本地数据源引入数据。 通过在设置环境时[提供 Microsoft Dataverse 环境 URL](create-environment.md)，您可以在 Customer Insights 中启用数据流。

将 Dataverse 环境与 Customer Insights 关联后创建的数据源默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 数据流使用数据网关支持本地连接。 您可以删除和重新创建[使用本地数据网关](/data-integration/gateway/service-gateway-app)关联 Dataverse 环境之前就存在的数据源。

现有 Power BI 或 Power Apps 环境中的数据网关将可见，您可以在 Customer Insights 中重复使用它们。 数据源页面显示用于转到 Microsoft Power Platform 环境的链接，您可以在该环境中查看和配置本地数据网关。

> [!IMPORTANT]
> 确保网关更新到最新版本。 您可以直接从网关屏幕上显示的提示安装更新并重新配置网关，或[下载最新版本](https://powerapps.microsoft.com/downloads/)。 如果您不使用最新的网关版本，数据流刷新将失败并显示错误消息，如 **不支持关键字：配置属性。参数名称：关键字**。

## <a name="review-ingested-data"></a>查看引入的数据
如果您的环境包含 Power Platform 数据流，**数据源** 页面会列出三个部分： 
- **共享**：可由所有 Customer Insights 管理员管理的数据源。 Power BI 数据流、您自己的存储帐户以及附加到 Dataverse 托管的数据湖是共享数据源的示例。
- **由我管理**：Power Platform 数据流被创建，只能由您管理。 其他 Customer Insights 管理员只能查看这些数据流，不能编辑、刷新或删除它们。
- **由其他人管理**：由其他管理员创建的 Power Platform 数据流。 您只能查看这些数据流。 其中将列出数据流的负责人，可以向其寻求帮助。
> [!NOTE]
> 其他用户可以查看和使用所有实体。 用户上下文仅适用于数据源，不适用于这些数据流产生的实体。

如果没有使用 Power Platform 数据流，您将看不到任何组或部分。 **数据源** 页面仅包含所有数据源的列表。

您将看到每个引入的数据源的名称、它的状态以及上次为该源刷新数据的时间。 您可以按每一列对数据源列表进行排序。

> [!div class="mx-imgBorder"]
> ![已添加数据源。](media/configure-data-datasource-added.png "已添加数据源")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

加载数据可能需要一些时间。 成功刷新后，可以从 **实体** 页查看引入的数据。 有关详细信息，请参阅[实体](entities.md)。

## <a name="refresh-a-data-source"></a>刷新数据源

数据源可以按计划自动刷新，也可以根据需要手动刷新。 

转到 **管理员** > **系统** > [**计划**](system.md#schedule-tab)以配置所有引入数据源的计划刷新。

若要根据需要刷新数据源，请执行以下步骤：

1. 转到 **数据** > **数据源**。

2. 选择您要更改刷新的数据源旁边的垂直省略号，然后从下拉列表中选择 **刷新**。

3. 现在，将为数据源触发手动刷新。 刷新数据源将更新数据源中指定的所有实体的实体架构和数据。

4. 如果要取消现有刷新，请选择 **停止刷新**，数据源将还原到上次刷新状态。

## <a name="delete-a-data-source"></a>删除数据源

1. 转到 **数据** > **数据源**。

2. 选择您要删除的数据源旁边的垂直省略号，然后从下拉菜单中选择 **删除**。

3. 确认删除。


[!INCLUDE [footer-include](includes/footer-banner.md)]
