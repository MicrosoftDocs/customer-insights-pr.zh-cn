---
title: 将参与见解中的 Web 数据与访问群体见解集成
description: 将参与见解中有关客户的 Web 信息引入到访问群体见解中。
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305007"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>将参与见解中的 Web 数据与访问群体见解集成

客户通常使用网站在线进行日常交易。 Dynamics 365 Customer Insights 中的参与见解（预览）功能是用于将 Web 数据作为源集成的有用解决方案。 除了查看交易、人口统计或行为数据，我们还可以在统一客户配置文件中查看 Web 上的活动。 我们可以使用这些配置文件获得访问群体激活的其他见解，例如客户细分、度量或预测。

本文介绍将客户的 Web 活动数据从参与见解引入到现有访问群体见解环境中的步骤。

此示例中，我们假定有一个包含统一客户配置文件的环境。 配置文件与来自调查、零售和票证系统的源统一。 它还显示客户的相关活动。 

现在，我们想要了解客户是否访问了我们的 Web 属性并了解他们的活动。 例如，活动包括从电子邮件中收到的链接访问的网站或查看的产品页面。

## <a name="prerequisites"></a>先决条件

若要集成参与见解中的数据，需要满足几个先决条件： 

- 将参与见解 SDK 与您的网站集成。 有关详细信息，请参阅[开发人员资源概述](../engagement-insights/developer-resources.md)。
- 从参与见解导出 Web 事件需要对 Azure Data Lake Storage 帐户的访问权限，该帐户用于将 Web 事件引入到访问群体见解。 有关详细信息，请参阅[导出事件](../engagement-insights/export-events.md)。

## <a name="configure-refined-events-in-engagement-insights"></a>在参与见解中配置优化的事件

在管理员使用参与见解 SDK 检测网站后，当用户查看网页或单击某个位置时，将收集 *基本事件*。 基本事件往往包含大量详细信息。 根据您的用例，只需要基本事件的数据子集。 通过使用参与见解，可以创建仅包含所选基本事件属性的 *优化事件*。     

有关详细信息，请参阅[创建和修改优化的事件](../engagement-insights/refined-events.md)。

创建优化的事件时应考虑的注意事项： 

- 为优化的事件提供有意义的名称。 它将用作访问群体见解中的活动名称。
- 至少选择以下属性以在访问群体见解中创建活动： 
    - Signal.Action.Name – 指示活动详细信息。
    - Signal.User.Id – 用于通过客户 ID 进行映射。
    - Signal.View.Uri – 用作 web 地址，作为客户细分或度量的基础。
    - Signal.Export.Id – 用作事件的主键。
    - Signal.Timestamp – 确定活动的日期和时间。

选择筛选器以重点关注对用例重要的事件和页面。 在此示例中，我们将使用“电子邮件促销”操作名称。

## <a name="export-the-refined-web-events"></a>导出优化的 Web 事件 

定义优化的事件后，您必须配置将事件数据导出到 Azure Data Lake Storage，它可用作数据源以供在访问群体见解中引入。 当事件从 Web 属性流出时会持续进行导出。

有关详细信息，请参阅[导出事件](../engagement-insights/export-events.md)。

## <a name="ingest-event-data-to-audience-insights"></a>将事件数据引入到访问群体见解中

现在，您已经定义了优化的事件并配置了它的导出，那么我们继续将数据引入到访问群体见解中。 您需要基于 Common Data Model 文件夹创建一个新的数据源。 输入将事件导出到的存储帐户的详细信息。 在 *default.cdm.json* 文件中，选择要引入的优化事件并在访问群体见解中创建实体。

有关详细信息，请参阅[使用 Azure Data Lake 帐户连接到 Common Data Model 文件夹](connect-common-data-model.md)。


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>将优化的事件数据作为客户配置文件的活动进行关联

完成实体引入后，您可以为客户配置文件配置活动。

有关详细信息，请参阅[自定义活动](activities.md)。

:::image type="content" source="media/web-event-activity.png" alt-text="具有展开的编辑活动窗格并且填充了字段的活动页面。":::

使用以下映射配置新活动： 

- **主键**：Signal.Export.Id，这是一个唯一的 ID，可用于参与见解中的每个事件记录。 此属性是自动生成的。

- **时间戳**：事件属性中的 Signal.Timestamp。

- **事件**：Signal.Name，要跟踪的事件名称。

- **Web 地址**：Signal.View.Uri，是指创建了事件的页面的 URI。

- **详细信息**：Signal.Action.Name，用于表示要与事件关联的信息。 本案例中的选定属性指示该事件用于电子邮件促销。

- **活动类型**：在本示例中，我们选择现有的活动类型 WebLog。 此选择是一个有用的筛选选项，用于根据此活动类型运行预测模型或创建客户细分。

- **设置关系**：该重要的设置将活动与现有客户配置文件相关联。 **Signal.User.Id** 是在 SDK 中配置的要收集的标识符，它与访问群体见解中配置的其他数据源中的用户 ID 相关。 在本示例中，我们配置 Signal.User.Id 和 RetailCustomers:CustomerRetailId 之间的关系，这是在数据统一流程的映射步骤中标识的主键。

处理完活动后，您可以查看客户记录并打开客户卡，以在时间轴上查看参与见解中的活动。 

> [!TIP]
> 若要查找具有参与见解活动的客户 ID，请转到 **实体** 并预览 UnifiedActivity 实体的数据。 ActivityTypeDisplay = WebLog 包含在上述示例中配置的参与见解活动。 将其中一条记录的客户 ID 和该 ID 的相应客户 ID 复制到 **客户** 页面上。

## <a name="next-steps"></a>后续步骤

现在，您可以创建[客户细分](segments.md)、[度量](measures.md)和[预测](predictions.md)，以与客户建立有意义的联系。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
