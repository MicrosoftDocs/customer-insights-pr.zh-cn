---
title: 使用数据源引入数据
description: 了解如何从各个数据源导入数据。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>数据源概述



Dynamics 365 Customer Insights 中的访问群体见解功能可连接到各种来源的数据。 连接到数据源通常称为 *数据引入* 过程。 引入数据后，您可以[统一](data-unification.md)数据并对其执行操作。

## <a name="add-a-data-source"></a>添加数据源

请参阅详细文章以了解如何根据选择的选项添加数据源。

您可以添加以下数据源：

- [Power Query 连接器](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse 湖](connect-dataverse-managed-lake.md)

> [!NOTE]
> 如果您使用的是试用版，则导入方法部分包含 **Customer Insights 数据库** 选项。 选择此选项可选择适用于各个行业的示例数据集。 有关详细信息，请参阅 [Dynamics 365 Customer Insights 试用版](../trial-signup.md)。

## <a name="add-data-from-on-premises-data-sources"></a>添加来自本地数据源的数据

基于 Microsoft Power Platform 数据流支持在访问群体见解中引入本地数据源中的数据。 通过在设置环境时[提供 Microsoft Dataverse 环境 URL](create-environment.md)，您可以在 Customer Insights 中启用数据流。

将 Dataverse 环境与 Customer Insights 关联后创建的数据源默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 数据流使用数据网关支持本地连接。 您可以删除和重新创建[使用本地数据网关](/data-integration/gateway/service-gateway-app)关联 Dataverse 环境之前就存在的数据源。

现有 Power BI 或 Power Apps 环境中的数据网关将可见，您可以在 Customer Insights 中重复使用它们。 数据源页面显示用于转到 Microsoft Power Platform 环境的链接，您可以在该环境中查看和配置本地数据网关。

## <a name="review-ingested-data"></a>查看引入的数据

您将看到每个引入的数据源的名称、它的状态以及上次为该源刷新数据的时间。 您可以按每一列对数据源列表进行排序。

> [!div class="mx-imgBorder"]
> ![已添加数据源。](media/configure-data-datasource-added.png "已添加数据源")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

加载数据可能需要一些时间。 成功刷新后，可以从 **实体** 页查看引入的数据。 有关详细信息，请参阅[实体](entities.md)。

## <a name="refresh-a-data-source"></a>刷新数据源

数据源可以按计划自动刷新，也可以根据需要手动刷新。 

转到 **管理员** > **系统** > [**计划**](system.md#schedule-tab)以配置所有引入数据源的计划刷新。

若要根据需要刷新数据源，请执行以下步骤：

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择您要更改刷新的数据源旁边的垂直省略号，然后从下拉列表中选择 **刷新**。

3. 现在，将为数据源触发手动刷新。 刷新数据源将更新数据源中指定的所有实体的实体架构和数据。

4. 如果要取消现有刷新，请选择 **停止刷新**，数据源将还原到上次刷新状态。

## <a name="delete-a-data-source"></a>删除数据源

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择您要删除的数据源旁边的垂直省略号，然后从下拉菜单中选择 **删除**。

3. 确认删除。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
