---
title: 通过 Power Query 连接器引入数据（包含视频）
description: 基于 Power Query 的数据源连接器。
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011646"
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

1. 选择 **转换数据**。 在此步骤中，将向数据源添加实体。 实体是数据集。 如果有其中包含多个数据集的数据库，则每个数据集有自己的实体。

1. **Power Query - 编辑查询** 对话可让您查看和优化数据。 系统在您的所选数据源中识别出的实体在左侧窗格中显示。

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="编辑查询对话框":::

1. 还可以转换数据。 选择要编辑或转换的实体。 使用 Power Query 窗口中的选项应用转换。 每个转换都会列在 **应用的步骤** 下。 Power Query 提供了大量预构建的转换选项。 有关详细信息，请参阅 [Power Query 转换](/power-query/power-query-what-is-power-query#transformations)。

   建议您使用以下转换：

   - 如果您从 CSV 文件引入数据，第一行通常包含标题。 转到 **转换** 并选择 **使用第一行作为标题**。
   - 确保正确设置了数据类型。 例如，对于日期字段，请选择日期类型。

1. 若要在 **编辑查询** 对话框中向数据源添加其他实体，请转至 **主页** 并选择 **获取数据**。 重复步骤 6-10，直到您为此数据源添加了所有实体。

1. 选择 **保存**。 **数据源** 页面将打开，显示处于 **正在刷新** 状态的新数据源。

### <a name="available-power-query-data-sources"></a>可用 Power Query 数据源

有关可用于将数据导入到 Customer Insights 的连接器列表，请参阅 [Power Query 连接器参考](/power-query/connectors/)。

**Customer Insights（数据流）** 列中带有复选标记的连接器可用于基于 Power Query 创建新数据源。 查看特定连接器的文档了解有关其先决条件、[查询限制](/power-query/power-query-online-limits)和其他详细信息的更多信息。

## <a name="add-data-from-on-premises-data-sources"></a>添加来自本地数据源的数据

基于 Microsoft Power Platform 数据流 (PPDF)，支持从本地数据源引入数据。 通过在设置环境时[提供 Microsoft Dataverse 环境 URL](create-environment.md)，您可以在 Customer Insights 中启用数据流。

将 Dataverse 环境与 Customer Insights 关联后创建的数据源默认使用 [Power Platform 数据流](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)。 数据流使用数据网关支持本地连接。 您可以删除和重新创建[使用本地数据网关](/data-integration/gateway/service-gateway-app)关联 Dataverse 环境之前就存在的数据源。

现有 Power BI 或 Power Apps 环境中的数据网关将可见，您可以在 Customer Insights 中重复使用它们。 数据源页面显示用于转到 Microsoft Power Platform 环境的链接，您可以在该环境中查看和配置本地数据网关。

> [!IMPORTANT]
> 确保网关更新到最新版本。 您可以直接从网关屏幕上显示的提示安装更新并重新配置网关，或[下载最新版本](https://powerapps.microsoft.com/downloads/)。 如果您不使用最新的网关版本，数据流刷新将失败并显示错误消息，如 **不支持关键字：配置属性。参数名称：关键字**。

## <a name="edit-power-query-data-sources"></a>编辑 Power Query 数据源

> [!NOTE]
> 可能不能对其中一个应用的进程（如 *细分*、*匹配* 或 *合并*）正在使用的数据源进行更改。
>
> 在 **设置** 页中，您可以跟踪每个活动进程的进度。 进程完成后，可以回到 **数据源** 页进行更改。

1. 转到 **数据** > **数据源**。

1. 在要更新的数据源旁边，选择 **编辑**。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. 如 [创建新数据源](#create-a-new-data-source)一节所述，在 **Power Query - 编辑查询** 对话中应用您的更改和转换。

1. 完成编辑后选择 Power Query 中的 **保存** 保存更改。
