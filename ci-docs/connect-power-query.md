---
title: 连接到 Power Query 数据源（包含视频）
description: 通过 Power Query 连接器引入数据（包含视频）。
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609865"
---
# <a name="connect-to-a-power-query-data-source"></a>连接到 Power Query 数据源

Power Query 提供一组广泛的连接器来引入数据。 其中大多数连接器都受 Dynamics 365 Customer Insights 支持。

基于 Power Query 连接器添加数据源通常将执行本节概述的步骤。 但是，根据您使用的连接器，需要不同的信息。 要了解详细信息，请参阅 [Power Query 连接器参考](/power-query/connectors/)中有关单个连接器的文档。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>创建新的数据源

1. 转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **Microsoft Power Query**。

1. 为数据源提供 **名称** 和 **说明**（可选），然后选择 **下一步**。

1. 选择一个[可用连接器](#available-power-query-data-sources), 在本示例中，我们选择 **文本/CSV** 连接器。

1. 在所选连接器的 **连接设置** 中输入所需详细信息，然后选择 **下一步** 查看数据预览。

1. 选择 **转换数据**。

1. 在 **Power Query - 编辑查询** 页面查看和优化您的数据。 系统在您的所选数据源中识别出的实体在左侧窗格中显示。

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="编辑查询对话框":::

1. 转换您的数据。 选择要编辑或转换的实体。 使用 Power Query 窗口中的选项应用转换。 每个转换都会列在 **应用的步骤** 下。 Power Query 提供了大量[预构建的转换](/power-query/power-query-what-is-power-query#transformations)选项。

   > [!IMPORTANT]
   > 建议您使用以下转换：
   >
   > - 如果您从 CSV 文件引入数据，第一行通常包含标题。 转到 **转换** 并选择 **使用第一行作为标题**。
   > - 确保数据类型设置正确并与数据匹配。 例如，对于日期字段，请选择日期类型。

1. 若要在 **编辑查询** 对话框中向数据源添加其他实体，请转至 **主页** 并选择 **获取数据**。 重复步骤 5-10，直到您为此数据源添加了所有实体。 如果有其中包含多个数据集的数据库，则每个数据集有自己的实体。

1. 选择 **保存**。 **数据源** 页面将打开，显示处于 **正在刷新** 状态的新数据源。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

加载数据可能需要一些时间。 成功刷新后，可以从 [**实体**](entities.md)页查看引入的数据。

> [!CAUTION]
>
> - 基于 Power Query 的数据源将[在 Dataverse 中创建数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 不要在 Customer Insights 中使用的 Power Platform 管理中心更改数据流的名称。 重命名数据流会导致 Customer Insights 数据源和 Dataverse 数据流之间的引用出现问题。
> - Customer Insights 中 Power Query 数据源的并发评估具有相同的[刷新限制，如 PowerBI.com 中的数据流](/power-query/power-query-online-limits#refresh-limits)。 如果数据刷新因为达到评估限制而失败，我们建议您调整每个数据流的刷新计划，以确保不会同时处理数据源。

### <a name="available-power-query-data-sources"></a>可用 Power Query 数据源

有关可用于将数据导入到 Customer Insights 的连接器列表，请参阅 [Power Query 连接器参考](/power-query/connectors/)。

**Customer Insights（数据流）** 列中带有复选标记的连接器可用于基于 Power Query 创建新数据源。 查看特定连接器的文档了解有关其先决条件、[查询限制](/power-query/power-query-online-limits)和其他详细信息的更多信息。

## <a name="add-data-from-on-premises-data-sources"></a>添加来自本地数据源的数据

基于 Microsoft Power Platform 数据流 (PPDF)，支持从本地数据源引入数据。 通过在设置环境时[提供 Microsoft Dataverse 环境 URL](create-environment.md)，您可以在 Customer Insights 中启用数据流。

将 Dataverse 环境与 Customer Insights 关联后创建的数据源默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 数据流使用数据网关支持本地连接。 您可以删除和重新创建[使用本地数据网关](/data-integration/gateway/service-gateway-app)关联 Dataverse 环境之前就存在的数据源。

来自现有 Power BI 或 Power Apps 环境的数据网关将可见，如果数据网关和 Customer Insights 环境位于同一 Azure 区域，您可以在 Customer Insights 中重复使用它们。 数据源页面显示用于转到 Microsoft Power Platform 环境的链接，您可以在该环境中查看和配置本地数据网关。

> [!IMPORTANT]
> 确保网关更新到最新版本。 您可以直接从网关屏幕上显示的提示安装更新并重新配置网关，或[下载最新版本](https://powerapps.microsoft.com/downloads/)。 如果您不使用最新的网关版本，数据流刷新将失败并显示错误消息，如 **不支持关键字：配置属性。参数名称：关键字**。
>
> Customer Insights 中的本地数据网关出现的错误通常是由配置问题引起的。 有关数据网关故障排除的详细信息，请参阅[本地数据网关故障排除](/data-integration/gateway/service-gateway-tshoot)。

## <a name="edit-power-query-data-sources"></a>编辑 Power Query 数据源

> [!NOTE]
> 可能不能对其中一个应用的进程（如细分或数据统一）正在使用的数据源进行更改。
>
> 在 **设置** 页中，您可以跟踪每个活动进程的进度。 进程完成后，可以回到 **数据源** 页进行更改。

1. 转到 **数据** > **数据源**。

1. 在要更新的数据源旁边，选择 **编辑**。

1. 如 [创建新数据源](#create-a-new-data-source)一节所述，在 **Power Query - 编辑查询** 对话中应用您的更改和转换。

1. 选择 **保存** 应用您的更改并返回到 **数据源** 页面。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>引入错误或数据损坏的常见原因

### <a name="data-type-does-not-match-data"></a>数据类型与数据不匹配

最常见的数据类型不匹配会发生在日期字段未设置为正确的日期格式时。

可以在源位置修复数据，然后重新引入。 或在 Customer Insights 中修复转换。 要修复转换：

1. 转到 **数据** > **数据源**。

1. 在包含损坏数据的数据源旁边，选择 **编辑**。

1. 选择 **下一步**。

1. 选择每个查询，查找在“应用的步骤”中应用的不正确的转换，或尚未用日期格式转换的日期列。

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query - 编辑显示不正确的日期格式":::

1. 更改数据类型以正确匹配数据。

1. 选择 **保存**。 数据源将刷新。

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>解决基于 PPDF Power Query 的数据源刷新问题

如果数据过时或在数据源刷新后收到错误，请执行以下步骤：

1. 导航到 [Power Platform](https://make.powerapps.com)。

1. 为您的 Customer Insights 实例选择 **环境**。

1. 导航到 **数据流**。

1. 对于与 Customer Insights 中的数据源对应的数据流，选择垂直省略号 (&vellip;)，然后选择 **显示刷新历史记录**。

1. 如果数据流的 **状态** 为 **成功**，基于 Power Query 的数据源的所有权可能已更改：

   1. 从刷新历史记录中查看刷新计划。
   1. 设置新负责人的计划并保存设置。

1. 如果数据流的 **状态** 为 **失败**：

   1. 下载刷新历史记录文件。
   1. 查看下载的文件了解失败的原因。
   1. 如果错误无法解决，选择 **?** 打开支持票证。 包括下载的刷新历史文件。


[!INCLUDE [footer-include](includes/footer-banner.md)]
