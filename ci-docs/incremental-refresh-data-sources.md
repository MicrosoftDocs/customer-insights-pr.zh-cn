---
title: Power Query 和 Azure Data Lake 数据源的增量刷新
description: 刷新基于 Power Query 或 Azure Data Lake 数据源的大型数据源的新数据和更新数据。
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012014"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Power Query 和 Azure Data Lake 数据源的增量刷新

本文讨论如何为基于 Power Query 或 Azure Data Lake 的数据源配置增量刷新。

对数据源进行增量刷新具有以下优点：

- **刷新速度更快** - 仅刷新已更改的数据。 例如，可以仅刷新过去五天的历史数据集。
- **提高可靠性** - 因为刷新量较小，所以无需长时间与不稳定源系统保持连接，从而可以降低连接问题风险。
- **减少资源消耗** - 仅刷新所有数据中的一小部分，从而更有效地使用计算资源和降低对环境的破坏。

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>为基于 Power Query 的数据源配置增量刷新

Customer Insights 允许对通过 Power Query 导入且支持增量引入的数据源进行增量刷新。 例如，具有日期和时间字段的 Azure SQL 数据库，这些字段指示数据记录的上次更新时间。

1. [创建基于 Power Query 的新数据源](connect-power-query.md)。

1. 选择支持增量刷新的数据源，如 [Azure SQL 数据库](/power-query/connectors/azuresqldatabase)。

1. 选择要引入的实体或表。

1. 完成传输步骤，然后选择 **下一步**。

1. 在 **设置增量刷新** 对话框中，选择 **设置** 打开 **增量刷新设置**。 如果选择 **跳过**，数据源将刷新整个数据集。
   > [!TIP]
   > 也可以在以后通过编辑现有数据源来应用增量刷新。

1. 在 **增量刷新设置** 中，为创建数据源时选择的所有实体配置增量刷新。

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="配置增量刷新设置。":::

1. 选择实体，然后提供以下详细信息：

   - **定义主键**：选择实体或表的主键。
   - **定义“上次更新时间”字段**：此字段将仅显示类型为日期或时间的属性。 选择用于指示记录的上次更新时间的属性。 它将用于标识在增量刷新期限内的记录。
   - **更新检查频率**：指定所需的增量刷新时间范围长度。

1. 选择 **保存** 完成数据源的创建。 数据的初始刷新为完全刷新。 之后，将按照上一步中的配置进行数据增量刷新。

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>为 Azure Data Lake 数据源配置增量刷新

Customer Insights 允许增量刷新连接到 Azure Data Lake Storage 的数据源。 要对实体使用增量引入和刷新，请在添加 Azure Data Lake 数据源时或稍后在编辑数据源时配置该实体。 实体数据文件夹必须包含以下文件夹：

- **FullData**：具有包含初始记录的数据文件的文件夹
- **IncrementalData**：具有包含增量更新的 **yyyy/mm/dd/hh** 格式的日期/时间层次结构文件夹的文件夹。 **hh** 表示更新的 UTC 小时，其中包含 **Upserts** 和 **Deletes** 文件夹。 **Upserts** 包含具有对现有记录的更新或新记录的数据文件。 **Deletes** 包含具有要删除记录的数据文件。

1. 添加或编辑数据源时，导航到实体的 **属性** 窗格。

1. 查看属性。 确保使用 *日期/时间* **数据格式** 和 *Calendar.Date* **语义类型** 设置创建或上次更新日期属性。 如有必要，编辑属性，然后选择 **完成**。

1. 在 **选择实体** 窗格中，编辑实体。 将选中 **增量引入** 复选框。

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="配置数据源中的实体以进行增量刷新。":::

   1. 浏览到包含完整数据、增量数据插入和增量数据删除的 .csv 或 .parquet 文件的根文件夹。
   1. 输入完整数据和两个增量文件（\.csv 或 \.parquet）的扩展名。
   1. 选择 **保存**。

1. 对于 **上次更新时间**，选择日期时间戳属性。

1. 如果未选择 **主键**，选择主键。 主键是实体所特有的属性。 若要使属性成为有效主键，它不应包括重复值、缺少值或 null 值。 支持将字符串、整数和 GUID 数据类型属性作为主键。

1. 选择 **关闭** 保存并关闭窗格。

1. 继续添加或编辑数据源。

[!INCLUDE [footer-include](includes/footer-banner.md)]
