---
title: 通过 Power Query 连接器引入数据
description: 基于 Power Query 的数据源的连接器。
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: ab6edc3f33ebacb81f55c0882a78c5827b4384ed
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643483"
---
# <a name="connect-to-a-power-query-data-source"></a>连接到 Power Query 数据源

Power Query 提供大量用于插入数据的连接器。 其中大多数连接器都受 Dynamics 365 Customer Insights 支持。 添加基于 Power Query 连接器的数据源通常要执行下一节中概述的步骤。 但是，根据您使用的连接器，需要不同的信息。 有关详细信息，请参阅 [Power Query 连接器参考](/power-query/connectors/)中各个连接器的相关文档。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>创建新的数据源

1. 在访问群体见解中，转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **导入数据** 方法，然后选择 **下一步**。

1. 为数据源提供 **名称**，然后选择 **下一步** 创建数据源。 名称准则： 
   - 以字母开头。
   - 只能使用字母和数字。 不允许使用特殊字符和空格。
   - 使用 3 至 64 个字符。

1. 选择一个[可用连接器](#available-power-query-data-sources), 在本例中，我们选择 **文本/CSV** 连接器。

1. 在所选连接器的 **连接设置** 中输入所需详细信息，然后选择 **下一步** 查看数据预览。

1. 选择 **转换数据**。 在此步骤中，将向数据源添加实体。 实体是数据集。 如果有其中包含多个数据集的数据库，则每个数据集有自己的实体。

1. 利用 **Power Query - 编辑查询** 对话框，您可以查看和优化数据。 系统在您的所选数据源中识别出的实体在左侧窗格中显示。

   > [!div class="mx-imgBorder"]
   > ![编辑查询对话框。](media/data-manager-configure-edit-queries.png "编辑查询对话框")

1. 还可以转换数据。 选择要编辑或转换的实体。 使用 Power Query 窗口中的选项应用转换。 每个转换在 **应用的步骤** 下列出。 Power Query 提供了很多预建的转换选项。 有关详细信息，请参阅 [Power Query 转换](/power-query/power-query-what-is-power-query#transformations)。

1. 可以通过选择 **编辑查询** 对话框中的 **获取数据** 向数据源添加更多实体。

   强烈建议进行以下转换：

   - 如果您从 CSV 文件引入数据，第一行通常包含标题。 转到 **转换表**，选择 **使用标题作为第一行**。
   - 确保正确设置了数据类型。

1. 选择 Power Query 窗口底部的 **保存** 保存转换。 保存后，您将在 **数据** > **数据源** 中找到您的数据源。

1. 在 **数据源** 页上，您会注意到新数据源处于 **正在刷新** 状态。

## <a name="available-power-query-data-sources"></a>可用 Power Query 数据源

请参阅 [Power Query 连接器参考](/power-query/connectors/)，获取您可以选择用来将数据导入 Customer Insights 的连接器的最新列表。 

**Customer Insights (数据流)** 列中带有复选标记的连接器可用于创建新的基于 Power Query 的数据源。 查看特定连接器的文档，了解有关其先决条件、限制和其他详细信息的详细信息。

## <a name="edit-power-query-data-sources"></a>编辑 Power Query 数据源

> [!NOTE]
> 可能不能对其中一个应用的进程（如 *细分*、*匹配* 或 *合并*）正在使用的数据源进行更改。 
>
> 可以使用 **设置** 页跟踪每个活动进程的进度。 进程完成后，可以回到 **数据源** 页进行更改。

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择您要更改的数据源旁边的垂直省略号，然后从下拉菜单中选择 **编辑**。

   > [!div class="mx-imgBorder"]
   > ![编辑选项。](media/edit-option-data-sources.png "编辑选项")

3. 按照 [创建新数据源](#create-a-new-data-source)一节中所述，在 **Power Query - 编辑查询** 对话框中应用更改和转换。

4. 完成编辑后，在 Power Query 中选择 **保存** 保存所作的更改。


[!INCLUDE[footer-include](../includes/footer-banner.md)]