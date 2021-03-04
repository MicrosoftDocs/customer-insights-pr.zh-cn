---
title: 导出的目标
description: 导出数据和管理导出目标。
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477122"
---
# <a name="export-destinations-preview-overview"></a>导出目标（预览版）概述

**导出目标** 页显示您已设置的要将数据导出到的所有位置。 您还可以为导出添加新目标。 此外，它将显示导出当前可用选项。 获取简要概述、说明，并了解使用每个扩展性选项可以做什么。 将统一的配置文件、度量和细分导出到与您的业务相关的受支持的应用。

转到 **管理** > **导出目标** 来查找以下扩展性选项：

- [Dynamics 365 客户卡加载项](customer-card-add-in.md)
- [Facebook 广告管理器连接器](export-facebook.md)
- [Power Automate 连接器](export-power-automate.md)
- [Power Apps 连接器](export-power-apps.md)
- [Power BI 连接器](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob 存储](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg; 连接器](export-liveramp.md)
- [Microsoft Teams 的机器人](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>添加新的导出目标

若要添加导出目标，您需要具有[管理员权限](permissions.md)。 如果导出到 Microsoft 服务，假设两个服务位于同一个组织中。

1. 转到 **管理员** > **导出目标**。

1. 切换到 **我的导出目标** 选项卡。

1. 选择 **添加目标** 创建新的导出目标。

1. 在 **添加目标** 窗格的下拉列表中，选择导出目标的 **类型**。

1. 提供必需的详细信息，然后选择 **下一步** 创建导出目标。

也可以在 **发现** 选项卡中的磁贴上选择 **设置**。

## <a name="view-export-destinations"></a>查看导出目标

创建导出目标之后，可以在 **我的导出目标** 选项卡上的表中看到这些目标。此表有三列：

- **显示名称**：创建目标时输入的名称。
- **类型**：创建目标时设置的导出目标类型。
- **创建日期**：目标的创建日期。

## <a name="edit-an-export-destination"></a>编辑导出目标

1. 选择要编辑的导出目标的竖省略号。

   > [!div class="mx-imgBorder"]
   > ![竖省略号](media/export-destinations-page-ellipsis.png "竖省略号")

1. 从下拉菜单中选择 **编辑**。

1. 更改需要更新的值，然后选择 **保存**。

## <a name="export-data-on-demand"></a>根据需要导出数据

为导出目标配置连接器之后，将在每次[安排的刷新](system.md#schedule-tab)时运行导出。

若要导出数据但不等待安排的刷新，请转到 **管理** > **导出目标** 中的 **我的导出目标** 选项卡。

> [!div class="mx-imgBorder"]
> ![竖省略号](media/export-destinations-page-ellipsis.png "竖省略号")

- 选择列表上方的 **导出** 同时运行到所有导出目标的导出。
- 选择列表项后的省略号 (...)，然后选择 **导出** 选项为单个导出目标运行导出。

## <a name="remove-an-export-destination"></a>删除导出目标

若要删除导出目标，请从 **导出目标** 主页开始。

1. 选择要删除的导出目标的竖省略号。

   > [!div class="mx-imgBorder"]
   > ![竖省略号](media/export-destinations-page-ellipsis.png "竖省略号")

2. 此下拉菜单中选择 **删除**。

3. 选择确认屏幕中的 **删除** 确认删除。


[!INCLUDE[footer-include](../includes/footer-banner.md)]