---
title: 基于 Power Query 的数据源的增量刷新
description: 刷新基于 Power Query 的大型数据源的新数据和更新数据。
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: d204228f8d6881cbf0e7fac6609bf50dd5296610
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377823"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>基于 Power Query 的数据源的增量刷新

对数据源进行增量刷新具有以下优点：

- **刷新速度更快** - 仅刷新已更改的数据。 例如，可以仅刷新过去五天的历史数据集。
- **提高可靠性** - 因为刷新量较小，所以无需长时间与不稳定源系统保持连接，从而可以降低连接问题风险。
- **减少资源消耗** - 仅刷新所有数据中的一小部分，从而更有效地使用计算资源和降低对环境的破坏。

## <a name="configure-incremental-refresh"></a>配置增量刷新

访问群体见解允许对通过支持增量引入的 Power Query 导入的数据源进行增量刷新。 例如，具有日期和时间字段的 Azure SQL 数据库，这些字段指示数据记录的上次更新时间。

1. [创建新的基于 Power Query 的数据源](connect-power-query.md)。

1. 为该数据源提供名称。

1. 选择支持增量刷新的数据源，如 Azure SQL 数据库。

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