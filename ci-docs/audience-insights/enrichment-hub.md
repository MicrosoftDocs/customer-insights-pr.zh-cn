---
title: 扩充统一的客户配置文件
description: 使用功能扩充您的客户数据。
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597684"
---
# <a name="enrichment-for-customer-profiles-preview"></a>扩充客户配置文件（预览）

使用来自 Microsoft 和其他合作伙伴之类的源的数据来扩充您的客户数据。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="扩充中心页面":::

在访问群体见解中，转到 **数据** > **扩充** 以使用扩充选项。    
您需要具有参与者或管理员权限才能创建或编辑扩充。 有关详细信息，请参阅[权限](permissions.md)。

在 **发现** 选项卡上，您将看到以下扩充：

- 由 Microsoft Graph 提供的[品牌](enrichment-microsoft-graph.md)
- 由 Microsoft Graph 提供的[兴趣](enrichment-microsoft-graph.md)
- Leadspace 提供的[公司数据](enrichment-leadspace.md)
- Experian 提供的[人口统计数据](enrichment-experian.md)
- HERE Technologies 提供的[位置数据](enrichment-here.md)
- 通过安全文件传输协议 (SFTP) [自定义数据](enrichment-SFTP-custom-import.md)

在 **我的扩充** 选项卡上，您可以查看您已配置的扩充并编辑其属性。

## <a name="manage-existing-enrichments"></a>管理现有扩充

转到 **我的扩充** 查看所有已配置的扩充。 每个扩充表示为一行，其中包含有关扩充的其他信息。

选择一个扩充来查看可用选项。 或者，您可以选择列表项上的省略号 (...) 来查看选项。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用于管理扩充列表中的扩充的选项":::

- **查看** 扩充详细信息以及扩充的客户资料的数量。
- **编辑** 扩充配置。
- **运行** 扩充，使用最新数据更新客户配置文件。
- **停用** 现有扩充以阻止其在每次执行计划刷新时自动刷新。 来自上一次成功刷新的数据将继续可用。 **激活** 停用扩充以重新启动在每次执行计划刷新时自动刷新。
- **删除** 扩充。

您可以通过在列表中选择扩充来一次运行或停用多个扩充。 查看和编辑选项不能用作批量操作，一次只能对一个扩充执行。


[!INCLUDE[footer-include](../includes/footer-banner.md)]