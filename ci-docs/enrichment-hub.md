---
title: 数据扩充（预览版）概述
description: 使用 Microsoft 和其他第三方服务的功能来扩充客户数据。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053853"
---
# <a name="data-enrichment-preview-overview"></a>数据扩充（预览版）概述

使用来自 Microsoft 和其他合作伙伴之类的源的数据来扩充您的客户数据。 使用管理员用凭据设置并且同意进行数据传输的[连接](connections.md)配置了第三方扩充。 管理员和参与者可以使用这些连接来配置扩充。  

## <a name="multiple-enrichments-of-the-same-type"></a>相同类型的多项扩充

扩充配置期间已指定了要扩充的实体，这允许您仅扩充配置文件子集。 例如，仅为特定客户细分扩充数据。 您可以配置相同类型的多项扩充并重复使用相同的连接。 某些扩充对可创建的相同类型的扩充数量有限制。 限制和当前使用情况可以在 **扩充** 页面 **发现** 选项卡上的每个磁贴上看到。

## <a name="enrich-data-sources-before-unification"></a>在统一之前扩充数据源

您可以在数据统一之前扩充您的客户数据，以帮助提高数据匹配的质量。 有关详细信息，请参阅[数据源扩充](data-sources-enrichment.md)。

## <a name="create-an-enrichment"></a>创建扩充

您需要具有参与者或管理员[权限](permissions.md)才能创建或编辑扩充。

转到 **数据** > **扩充**。 **发现** 选项卡会显示所有支持的扩充选项。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="扩充中心页面。":::

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

- LiveRamp AbiliTec 提供的 [AbiliTec 标识](enrichment-liveramp.md)
- Microsoft 提供的[品牌](enrichment-microsoft.md)
- Experian 提供的[人口统计](enrichment-experian.md)
- Microsoft 提供的[增强地址](enrichment-enhanced-addresses.md)
- Microsoft 提供的[兴趣](enrichment-microsoft.md)
- Microsoft Azure Maps 提供的[位置数据](enrichment-azure-maps.md)
- HERE Technologies 提供的[位置数据](enrichment-here.md)
- 通过安全文件传输协议 (SFTP) 提供的 [SFTP 自定义数据](enrichment-SFTP-custom-import.md)

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

- Microsoft 提供的[帐户参与数据](enrichment-office.md)
- Dun & Bradstreet 提供的[公司数据](enrichment-dnb.md)
- Leadspace 提供的[公司数据](enrichment-leadspace.md)
- Microsoft 提供的[增强地址](enrichment-enhanced-addresses.md)
- Microsoft 提供的[增强型公司数据](enrichment-enhanced-company-data.md)
- Microsoft Azure Maps 提供的[位置数据](enrichment-azure-maps.md)
- HERE Technologies 提供的[位置数据](enrichment-here.md)
- 通过安全文件传输协议 (SFTP) 提供的 [SFTP 自定义数据](enrichment-SFTP-custom-import.md)

---

## <a name="manage-existing-enrichments"></a>管理现有扩充

转到 **数据** > **扩充**。 在 **我的扩充** 选项卡上，查看配置的扩充、其状态、扩充的客户数以及上次刷新数据的时间。 您可以按任何列对扩充列表进行排序，或使用搜索框查找要管理的扩充。

选择扩充以查看可用操作。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用于管理扩充列表中的扩充的选项。":::

- **查看** 扩充详细信息以及扩充的客户资料的数量。
- **编辑** 扩充配置。
- [**运行**](#run-or-refresh-enrichments)扩充 ，以使用最新数据更新客户配置文件。 通过在列表中选择多个扩充来同时运行多个扩充。
- **激活** 或 **停用** 扩充。  在[计划的刷新](system.md#schedule-tab)期间不会刷新停用的扩充。
- **删除** 扩充。

您还可以从扩充项创建[客户细分](segments.md)或[度量](measures.md)。

## <a name="run-or-refresh-enrichments"></a>运行或刷新扩充

运行后，可以按自动计划刷新扩充，也可以按需手动刷新。

1. 若要手动刷新一个或多个扩充，请选择它们并选择 **运行**。 若要 [计划自动刷新](system.md#schedule-tab)，请转到 **管理** > **系统** > **计划**。 处理时间取决于客户数据的大小。

1. （可选）[查看扩充过程的进度](#see-the-progress-of-the-enrichment-process)。

1. 扩充过程完成后，转到 **我的扩充** 查看新扩充的客户资料数据、上次更新的时间和扩充资料的数量。

1. 选择扩充查看[扩充结果](#view-enrichment-results)。

### <a name="see-the-progress-of-the-enrichment-process"></a>查看扩充过程的进度

可以找到有关扩充处理的详细信息，包括其在刷新时或刷新完成后的状态和潜在问题。 了解刷新活动涉及哪些进程以及运行这些进程需要的时间。 Experian、Leadspace、HERE Technologies、SFTP Import 和 Azure Maps 支持扩充状态。

1. 转到 **数据** > **扩充**。
1. 在 **我的扩充** 选项卡中，选择扩充的状态打开侧窗格。
1. 在 **进度详细信息** 窗格中，展开 **扩充** 部分。
1. 在要查看其进度的扩充下，选择 **查看详细信息**。
1. 在 **任务详细信息** 窗格中，选择 **显示详细信息** 以查看更新窗口及其状态时涉及的进程。

## <a name="view-enrichment-results"></a>查看扩充结果

完成扩充运行后，查看扩充结果。

1. 转到 **数据** > **扩充**。
1. 在 **我的扩充** 选项卡中，选择您要查看的扩充。

所有扩充都显示基本信息，如已扩充资料的数量以及随着时间的推移完成扩充的资料的数量。 **扩充的客户预览** 磁贴显示生成的扩充实体的示例。 要查看详细视图，选择 **查看更多**，然后选择 **数据** 选项卡。

:::image type="content" source="media/enrichments-results.png" alt-text="扩充结果页面。":::

如果显示，**按字段扩充的客户数** 可帮助深入了解每个扩充的字段的覆盖范围。

一些扩充还显示特定于扩充类型的信息。 有关详细信息，请参阅相关文档。

[!INCLUDE [footer-include](includes/footer-banner.md)]
