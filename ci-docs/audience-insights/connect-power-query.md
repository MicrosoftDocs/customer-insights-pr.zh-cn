---
title: 通过 Power Query 连接器引入数据（包含视频）
description: 基于 Power Query 的数据源连接器。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934967"
---
# <a name="connect-to-a-power-query-data-source"></a>连接到 Power Query 数据源

Power Query 提供一组广泛的连接器来引入数据。 其中大多数连接器都受 Dynamics 365 Customer Insights 支持。 

基于 Power Query 连接器添加数据源通常将执行本节概述的步骤。 但是，根据您使用的连接器，需要不同的信息。 要了解详细信息，请参阅 [Power Query 连接器参考](/power-query/connectors/)中有关单个连接器的文档。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>创建新的数据源

1. 在访问群体见解中，转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **Microsoft Power Query**，然后选择 **下一步**。

1. 为数据源提供 **名称**，然后选择 **下一步** 创建数据源。

1. 选择一个[可用连接器](#available-power-query-data-sources), 在本示例中，我们选择 **文本/CSV** 连接器。

1. 在所选连接器的 **连接设置** 中输入所需详细信息，然后选择 **下一步** 查看数据预览。

1. 选择 **转换数据**。 在此步骤中，将向数据源添加实体。 实体是数据集。 如果有其中包含多个数据集的数据库，则每个数据集有自己的实体。

1. **Power Query - 编辑查询** 对话可让您查看和优化数据。 系统在您的所选数据源中识别出的实体在左侧窗格中显示。

   > [!div class="mx-imgBorder"]
   > ![编辑查询对话框。](media/data-manager-configure-edit-queries.png "编辑查询对话框")

1. 还可以转换数据。 选择要编辑或转换的实体。 使用 Power Query 窗口中的选项应用转换。 每个转换在 **应用的步骤** 下列出。 Power Query 提供了大量预构建的转换选项。 有关详细信息，请参阅 [Power Query 转换](/power-query/power-query-what-is-power-query#transformations)。

1. 可以通过选择 **编辑查询** 对话框中的 **获取数据** 向数据源添加更多实体。

   建议您使用以下转换：

   - 如果您从 CSV 文件引入数据，第一行通常包含标题。 转到 **转换表**，选择 **使用标题作为第一行**。
   - 确保正确设置了数据类型。

1. 选择 Power Query 窗口底部的 **保存** 保存转换。 保存后，您将在 **数据** > **数据源** 中找到您的数据源。

1. 在 **数据源** 页上，您会注意到新数据源处于 **正在刷新** 状态。

## <a name="available-power-query-data-sources"></a>可用 Power Query 数据源

有关可用于将数据导入到 Customer Insights 的连接器列表，请参阅 [Power Query 连接器参考](/power-query/connectors/)。 

**Customer Insights（数据流）** 列中带有复选标记的连接器可用于基于 Power Query 创建新数据源。 查看特定连接器的文档，了解有关其先决条件、限制和其他详细信息的详细信息。

## <a name="edit-power-query-data-sources"></a>编辑 Power Query 数据源

> [!NOTE]
> 可能不能对其中一个应用的进程（如 *细分*、*匹配* 或 *合并*）正在使用的数据源进行更改。 
>
> 在 **设置** 页中，您可以跟踪每个活动进程的进度。 进程完成后，可以回到 **数据源** 页进行更改。

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择您要更改的数据源旁边的垂直省略号，然后从下拉菜单中选择 **编辑**。

   > [!div class="mx-imgBorder"]
   > ![编辑选项。](media/edit-option-data-sources.png "编辑选项")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. 如 [创建新数据源](#create-a-new-data-source)一节所述，在 **Power Query - 编辑查询** 对话中应用您的更改和转换。

4. 完成编辑后选择 Power Query 中的 **保存** 保存更改。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
