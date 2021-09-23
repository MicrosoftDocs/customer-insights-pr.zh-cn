---
title: 使用人口统计维度拆分行为数据（策划的维度）
description: 使用统一配置文件策划的维度启用访问群体见解客户配置文件属性。
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466337"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>使用人口统计维度拆分行为数据

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解用户可使用统一配置文件人口统计维度访问访问群体见解配置文件属性。 然后，可在对行为数据（包括参与见解在您的网站或移动应用中捕获的数据）进行交互式分析时使用这些属性。

>[!NOTE]
> 参与见解包含事件属性的现成维度。 更多信息：[查看和创建维度](dimensions.md)

## <a name="prerequisite"></a>先决条件

- 一个参与见解环境，您已在其中将客户配置文件数据链接到了一个在其中创建了客户细分和客户配置文件的访问群体见解环境。 更多信息：[创建参与见解与访问群体见解之间的链接](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> 创建访问群体见解环境与参与见解环境之间的链接之后，您可能只需要特定于客户配置文件属性的数据，这在参与见解中充当维度时可能非常有用。 有关详细信息，请转到[启用访问群体见解统一配置文件属性和客户细分](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments)。

## <a name="create-a-new-custom-report"></a>创建新的自定义报表

1. 在左窗格中，选择 **自定义** > **新建报表**，然后选择所需指标。 （对于本示例，我们选择 **按小时的页面视图**。）

    :::image type="content" source="media/curated-dimensions1.png" alt-text="选择指标。":::

2. 在可视化效果编辑器中，选择 **维度**，然后在 **维度类型** 下拉菜单中选择 **人口统计**。

    :::image type="content" source="media/curated-dimensions2.png" alt-text="选择人口统计。":::

3. 选择 **Signal.Customer.*xxx*** 维度。 （此示例将显示 Signal.Customer.Country。）

    :::image type="content" source="media/curated-dimensions3.png" alt-text="选择维度。":::
  
## <a name="limitations"></a>限制

目前只能将人口统计维度用于拆分行为数据。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
