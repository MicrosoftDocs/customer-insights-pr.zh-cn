---
title: 查看和创建维度
description: 如何创建、编辑和删除维度。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623621"
---
# <a name="view-and-create-dimensions"></a>查看和创建维度

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

维度是事件的属性，可用于描述和筛选数据或对数据进行分组。 如果您正在网站中运行市场营销促销，您可以使用维度按新用户和回访用户对访客进行排序。  

参与见解包含事件属性的现成 (OOB) 维度。 示例包括：

- 浏览器名称
- 页面名称
- 设备型号
- 操作系统
- 国家/地区

## <a name="view-dimensions"></a>查看维度

维度基于现有事件属性。 当您使用参与见解的跟踪代码时，将自动创建系统维度。

1. 在左侧导航窗格中，转到 **数据**。 
1. 选择 **维度** 以查看工作区中所有维度的列表。 
   > [!NOTE]
   > 系统生成的维度是只读维度。 您无法编辑它们。 您只能创建和编辑自定义维度。

## <a name="create-a-dimension"></a>创建维度

除了系统生成的维度外，环境和工作区管理员还可以创建自定义的维度。 自定义的维度基于基本事件的默认属性，或者可以使用[事件的自定义属性](advanced-SDK-implementation.md)。

1. 转到 **数据** > **维度**。
1. 选择 **新维度**。

   :::image type="content" source="media/add-dimension.png" alt-text="向事件添加维度。":::

1. 在 **创建维度** 窗格中，选择维度要基于的属性。 属性列表将显示工作区中未分配给维度的所有属性。
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="创建新维度。":::
      
3. 在 **显示名称** 框中，输入名称。 （可选）您可以添加 **说明**。
4. 选择 **创建** 以保存维度。 可能最多需要一分钟的时间才能在[自定义报表](custom-reports.md)或[客户细分](segments.md)中使用此维度。 

## <a name="edit-a-dimension"></a>编辑维度

您可以更改维度的名称和说明。 您只能编辑用户创建的维度，不能编辑系统维度。


1. 转到 **数据** > **维度**。
1. 选择要删除的维度。
1. 在 **编辑维度** 窗格中，更新维度。
1. 选择 **应用** 以保存所做的更改。

## <a name="delete-a-dimension"></a>删除维度

您只能删除用户创建的维度，但不能删除系统维度。

删除维度是永久性操作。 使用已删除维度的报表和客户细分将不再有效。 

1. 转到 **数据** > **维度**。
1. 选择要删除的维度。
1. 在 **编辑维度** 窗格中，选择 **删除维度**。

   :::image type="content" source="media/delete-dimension.png" alt-text="删除事件中的维度。":::

1. 输入 **确认删除**（全部大写）以确认删除。 
1. 选择 **删除**。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
