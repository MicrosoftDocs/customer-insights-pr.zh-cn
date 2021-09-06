---
title: 扩充统一的客户配置文件
description: 使用功能扩充您的客户数据。
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032517"
---
# <a name="enrichment-for-customer-profiles-preview"></a>扩充客户配置文件（预览）

使用来自 Microsoft 和其他合作伙伴之类的源的数据来扩充您的客户数据。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="扩充中心页面。":::

在访问群体见解中，转到 **数据** > **扩充** 以使用扩充选项。  

您需要具有参与者或管理员权限才能创建或编辑扩充。 有关详细信息，请参阅[权限](permissions.md)。

在 **发现** 选项卡上，您将看到以下扩充：

- Microsoft 提供的[品牌](enrichment-microsoft.md)
- Microsoft 提供的[兴趣](enrichment-microsoft.md)
- Microsoft 提供的[增强地址](enrichment-enhanced-addresses.md)
- Leadspace 提供的[公司数据](enrichment-leadspace.md)
- Experian 提供的[人口统计](enrichment-experian.md)
- HERE Technologies 提供的[位置数据](enrichment-here.md)
- 通过安全文件传输协议 (SFTP) [自定义数据](enrichment-SFTP-custom-import.md)

在 **我的扩充** 选项卡上，您可以查看您已配置的扩充并编辑其属性。

## <a name="manage-existing-enrichments"></a>管理现有扩充

转到 **我的扩充** 选项卡以查看所有配置的扩充。 每个扩充表示为一行，其中包含有关扩充的其他信息。

选择扩充以查看可用选项。 您还可以选择列表项上的椭圆 (...) 以查看选项。 如果您配置了多个扩充，则可以使用搜索框快速找到它。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="用于管理扩充列表中的扩充的选项。":::

- **查看** 扩充详细信息以及扩充的客户资料的数量。
- **编辑** 扩充配置。
- **运行** 扩充，使用最新数据更新客户配置文件。
- **停用** 现有扩充以阻止其在每次执行计划刷新时自动刷新。 来自上一次成功刷新的数据将继续可用。 **激活** 停用扩充以重新启动在每次执行计划刷新时自动刷新。
- **删除** 扩充。

通过在列表中选择多个扩充来同时运行或停用它们。 查看和编辑选项不可用作批量操作。 它们一次只适用于一个扩充。

## <a name="enrichments-and-connections"></a>扩充和连接

使用管理员用凭据设置并且同意进行数据传输的[连接](connections.md)配置了第三方扩充。 然后，管理员和参与者可以使用这些连接配置扩充。  

## <a name="multiple-enrichments-of-the-same-type"></a>相同类型的多项扩充

扩充配置期间已指定了要扩充的实体，这允许您仅扩充配置文件子集。 例如，仅为特定客户细分扩充数据。 您可以配置相同类型的多项扩充并重复使用相同的连接。 某些扩充对可创建的相同类型的扩充数量有限制。 可以在 **扩充** 页面上看到限制和当前使用情况。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
