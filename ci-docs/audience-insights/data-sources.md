---
title: 使用数据源引入数据
description: 了解如何从各个数据源导入数据。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 75d597158233f75f0eb5f94389f9dba199d81719f2bbe4e5cc58d2a3afc7dcf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032839"
---
# <a name="data-sources-overview"></a>数据源概述

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights 中的访问群体见解功能可连接到各种来源的数据。 连接到数据源通常称为 *数据引入* 过程。 引入数据后，您可以[统一](data-unification.md)数据并对其执行操作。

## <a name="add-a-data-source"></a>添加数据源

请参阅有关如何添加数据源的详细文章，如何添加具体取决于您选择的选项。

您可以通过以下三种主要方式添加数据源：

- [通过许多 Power Query 连接器](connect-power-query.md)
- [从 Common Data Model 文件夹](connect-common-data-model.md)
- [从您自己的 Microsoft Dataverse 湖](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>添加来自本地数据源的数据

基于 Microsoft Power Platform 数据流支持在访问群体见解中引入本地数据源中的数据。 通过在设置环境时[提供 Microsoft Dataverse 环境 URL](get-started-paid.md)，可以在 Customer Insights 中启用数据流。

将 Dataverse 环境与 Customer Insights 关联后创建的数据源将默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 数据流使用数据网关支持本地连接。 删除并重新创建关联 Dataverse 环境以[使用本地数据网关](/data-integration/gateway/service-gateway-app)之前已存在的数据源。

现有 Power BI 或 Power Apps 环境中的数据网关将可见，您可以在 Customer Insights 中重复使用它们。 数据源页面显示用于转到 Microsoft Power Platform 环境的链接，您可以在该环境中查看和配置本地数据网关。

## <a name="review-ingested-data"></a>查看引入的数据

您将看到每个引入的数据源的名称、它的状态以及上次为该源刷新数据的时间。 您可以按每一列对数据源列表进行排序。

> [!div class="mx-imgBorder"]
> ![已添加数据源。](media/configure-data-datasource-added.png "已添加数据源")

|执行状态  |描述  |
|---------|---------|
|成功   |如果 **已刷新** 列中显示时间，则数据源已成功引入。
|未开始   |数据源尚未引入数据，或仍处于草稿模式。         |
|正在刷新    |正在引入数据。 可以通过选择 **操作** 列中的 **停止刷新** 来取消此操作。 停止刷新数据源将把数据源恢复为上次的刷新状态。       |
|已失败     |数据引入出错。         |

在任意数据源的 **状态** 列中选择值以查看更多详细信息。 在 **进度详细信息** 窗格中，展开 **数据源**。 选择 **查看详细信息** 以查看有关刷新状态的详细信息，包括错误详细信息和下游流程更新。

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
