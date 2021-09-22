---
title: 漏斗图报表
description: 如何使用漏斗图报表了解访问群体做出决策的方式。
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032244"
---
# <a name="create-and-manage-funnel-reports"></a>创建和管理漏斗图报表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

漏斗图报表通过您的网站或移动设备收集有关客户旅程期间执行的步骤的信息。 它可以帮助您了解访问群体过程的进度并确定放置点。 例如，您可以使用漏斗图报表来确定客户购买之前采用的路径。 漏斗图报表可提供数据来通知决策并确定要优化和进行流程改进的区域。

## <a name="create-a-funnel-report"></a>创建漏斗图报表

要创建漏斗图报表，请指定要包括的步骤以及每个步骤的活动。 活动是代表用户行为的[事件](glossary.md)。 漏斗图报表显示完成每个定义的步骤的用户数。 

1. 转到 **漏斗图** 并选择 **+ 新建漏斗图** 以启动漏斗图报表。

1. 在 **漏斗图编辑器** 中的 **步骤** 下面，选择 **+添加步骤**。 

1. 在 **步骤标题** 中输入名称。

   :::image type="content" source="media/new-funnel-report.png" alt-text="新建漏斗图报表。":::

1. 选择 **活动**。 活动记录了用户查看页面（**查看** 活动）或与内容交互（**操作** 活动）的时间。

1. 使用 **步骤条件** 指定活动的维度。 [维度](dimensions.md)是可用于描述、筛选或分组数据的属性。

1. （可选）您可以配置多条件漏斗图步骤。 选择 **添加条件** 以在步骤中指定更多维度。 其他条件必须使用相同的活动类型。 您可以选择多个条件是使用“与”还是“或”运算符进行连接。

   :::image type="content" source="media/funnel-add-condition.png" alt-text="漏斗图编辑器，显示带多条件步骤的步骤配置。":::

1. 选择 **添加步骤**，直到完成报表中所需的所有步骤。

1. 选择 **保存**，命名报表，然后再次选择 **保存**。 

### <a name="example-fourth-coffee-company-funnel-report"></a>示例：Fourth Coffee 公司漏斗图报表

以下方案演示使用漏斗图报表的一种方式。 Fourth Coffee 公司的分析师希望了解近期促销活动对订阅率的影响。 该分析师创建了一个漏斗图报表以确定客户活动。 此报表从客户到达公司主页时开始，直到他们使用订阅促销代码为止。 该分析师通过以下步骤创建了漏斗图报表：

步骤 1：登陆主页的客户   
步骤 2：进行购买的客户   
步骤 3：使用促销代码获取订阅折扣的客户   
步骤 4：订阅注册   

:::image type="content" source="media/funnel-report-example.png" alt-text="漏斗图报表示例。":::
  
利用此漏斗图，您可以查看一次性购买后使用促销代码注册订阅计划的用户数量。

### <a name="configure-advanced-settings"></a>配置高级设置 

利用漏斗图报表，可以定义对完成漏斗图所需的时间的限制。 例如，可以将完成漏斗图的时间设置为四天。 此设置将仅计算用户在访问主页后四天内进行的成功订阅注册数。

1. 转到 **漏斗图** 以打开 **漏斗图库**。

1. 选择名称以打开报表。 

1. 在 **漏斗图编辑器** 窗格中，选择 **高级设置**。 

1. 将“限制漏斗图完成时间”设置为 **开**。

   :::image type="content" source="media/funnel-limit-time.png" alt-text="漏斗图编辑器，它显示了高级设置和用于限制完成漏斗图的时间的选项。":::

1. 在 **将限制设置为** 下拉列表中选择漏斗图必须完成的时间。

1. 选择 **保存** 以应用您所做的更改。


## <a name="cross-channel-funnel-reports"></a>跨渠道漏斗图报表 

参与见解还可以在您的移动应用上收集行为客户数据。 使用参与见解 [Android SDK](get-started-android.md) 或 [iOS SDK](get-started-ios.md) 检测您的移动应用后，您可以创建跨渠道漏斗图报表。 

### <a name="create-a-cross-channel-funnel-report"></a>创建跨渠道漏斗图报表 

1. 按照以下步骤[创建漏斗图报表](#create-a-funnel-report)。    

1. 若要跟踪您的客户如何跨您的网站和移动应用或多个网站与您的品牌交互，请使用工作区切换器通过其他工作区中的数据创建漏斗图步骤。 在 **漏斗图编辑器** 中，在 **步骤** 下，选择您的漏斗图步骤的数据应该来自哪个工作区。

## <a name="manage-funnel-reports"></a>管理漏斗图报表

您可以查看漏斗图报表以分析数据、跟踪绩效并收集见解。

> [!NOTE]
> - 参与见解漏斗图报表当前支持漏斗图中的所有用户都是匿名用户或所有用户均通过身份验证的方案。 
> - 漏斗图报表中的历史数据适用于最近 30 天。

### <a name="view-funnel-reports"></a>查看漏斗图报表

1. 转到 **漏斗图** 以打开 **漏斗图库**。
1. 选择名称以打开报表。    

### <a name="see-the-data-collected-for-a-report"></a>查看为报表收集的数据   

查看有关阶段的信息

- 指向报表中的步骤。

:::image type="content" source="media/funnel-step-data.png" alt-text="漏斗图数据。":::

### <a name="change-the-date-range-for-the-funnel-report"></a>更改漏斗图报表的日期范围

1. 转到 **漏斗图** 以打开 **漏斗图库**。

1. 选择名称以打开报表。

1. 打开 **时间范围**，然后从列表中选择一个新时间段，或选择 **固定日期范围** 以指定日期范围。

## <a name="edit-or-delete-funnel-reports"></a>编辑或删除漏斗图报表

您可以更改漏斗图报表的名称、删除它或修改此报表中的步骤。

### <a name="rename-or-delete-a-funnel-report"></a>重命名或删除漏斗图报表

1. 转到 **漏斗图** 以打开 **漏斗图库**。 

1. 选择要更改的报表旁边的 **更多**，然后选择 **编辑名称** 或 **删除**。

### <a name="edit-a-funnel-step"></a>编辑漏斗图步骤  

1. 转到 **漏斗图** 以打开 **漏斗图库**。 

1. 选择名称以打开报表。

1. 选择要编辑的步骤。

1. 选择 **编辑**。

1. 在 **漏斗图编辑器** 中，更新要更改的信息。  

1. 选择 **保存**。

### <a name="reorder-a-funnel-step"></a>重新排序漏斗图步骤

1. 转到 **漏斗图** 以打开 **漏斗图库**。 

1. 选择名称以打开报表。

1. 选择要重新排序的步骤。

1. 选择 **移动**，然后选择 **向上**、**向下**、**到顶部** 或 **到底部** 来移动此步骤。

### <a name="delete-a-funnel-step"></a>删除漏斗图步骤

1. 转到 **漏斗图** 以打开 **漏斗图库**。 

1. 选择名称以打开报表。

1. 选择要删除的步骤，然后选择 **删除**。

