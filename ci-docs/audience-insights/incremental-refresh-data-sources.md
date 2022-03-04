---
title: 基于 Power Query 的数据源的增量刷新
description: 刷新基于 Power Query 的大型数据源的新数据和已更新数据。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353670"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>基于 Power Query 的数据源的增量刷新

本文讨论如何为基于 Power Query 的数据源配置增量刷新。

对数据源进行增量刷新具有以下优点：

- **刷新速度更快** - 仅刷新已更改的数据。 例如，可以仅刷新过去五天的历史数据集。
- **提高可靠性** - 因为刷新量较小，所以无需长时间与不稳定源系统保持连接，从而可以降低连接问题风险。
- **减少资源消耗** - 仅刷新所有数据中的一小部分，从而更有效地使用计算资源和降低对环境的破坏。

## <a name="configure-incremental-refresh"></a>配置增量刷新

访问群体见解允许对通过 Power Query 导入且支持增量引入的数据源进行增量刷新。 例如，具有日期和时间字段的 Azure SQL 数据库，这些字段指示数据记录的上次更新时间。

1. [创建基于 Power Query 的新数据源](connect-power-query.md)。

1. 为该数据源提供 **名称**。

1. 选择支持增量刷新的数据源，如 [Azure SQL 数据库](/power-query/connectors/azuresqldatabase)。

1. 选择要引入的实体或表。

1. 完成传输步骤，然后选择 **下一步**。

1. 在 **设置增量刷新** 对话框中，选择 **设置** 打开 **增量刷新设置**。 如果选择 **跳过**，数据源将刷新整个数据集。
   > [!TIP]
   > 也可以在以后通过编辑现有数据源来应用增量刷新。

1. 在 **增量刷新设置** 中，为创建数据源时选择的所有实体配置增量刷新。

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="配置数据源中的实体以进行增量刷新。":::

1. 选择实体，然后提供以下详细信息：

   - **定义主键**：选择实体或表的主键。
   - **定义“上次更新时间”字段**：此字段将仅显示类型为日期或时间的属性。 选择用于指示记录的上次更新时间的属性。 它将用于标识在增量刷新期限内的记录。
   - **更新检查频率**：指定所需的增量刷新时间范围长度。

1. 选择 **保存** 完成数据源的创建。 数据的初始刷新为完全刷新。 之后，将按照上一步中的配置进行数据增量刷新。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
