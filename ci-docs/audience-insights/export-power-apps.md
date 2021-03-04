---
title: Power Apps 连接器
description: 与 Power Apps 和 Power Automate 连接。
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268905"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps 连接器（预览版）

使用 Power Apps 将统一客户配置文件导入到个性化的应用中。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>连接 Power Apps 和 Dynamics 365 Customer Insights

Customer Insights 是 [Power Apps 中众多数据源](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources)之一。

请参阅 Power Apps 文档了解如何[向应用添加数据连接](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)。 我们建议您另外回顾一下 [Power Apps 如何使用代理来处理画布应用中的大型数据集](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview)。

## <a name="available-entities"></a>可用实体

将 Customer Insights 作为数据连接添加之后，可以在 Power Apps 中选择以下实体：

- 客户：如果要使用[统一客户配置文件](customer-profiles.md)中的数据。
- UnifiedActivity：在应用中显示[活动时间线](activities.md)。

## <a name="limitations"></a>限制

### <a name="retrievable-entities"></a>可检索实体

您只能通过 Power Apps 连接器检索 **客户**、**统一活动** 和 **客户细分** 实体。 之所以显示其他实体，是因为基础连接器通过 Power Automate 中的触发器支持它们。  

### <a name="delegation"></a>代理

委派适用于“客户”实体和“统一活动”实体。 

- **客户** 实体的委派：若要针对此实体使用委派，需要在[搜索和筛选索引](search-filter-index.md)中对字段编制索引。  

- **统一活动** 实体的委派：此实体的委派仅适用于字段 **ActivityId** 和 **CustomerId**。  

- 有关委派的详细信息，请参阅 [Power Apps 可委派函数和操作](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)。 

## <a name="example-gallery-control"></a>示例库控件

例如，您可以将客户配置文件添加到[库控件](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery)。

1. 请向正在构建的应用添加一个 **库** 控件。

> [!div class="mx-imgBorder"]
> ![添加库元素](media/connector-powerapps9.png "添加库元素")

1. 选择 **客户** 充当项的数据源。

    > [!div class="mx-imgBorder"]
    > ![选择数据源](media/choose-datasource-powerapps.png "选择数据源")

1. 可以更改右侧的数据面板以选择在库中显示客户实体的哪个字段。

1. 如果要在库中显示所选客户的任何字段，请填写标签的“文本”属性：**{Name_of_the_gallery}.Selected.{property_name}**

    示例：Gallery1.Selected.address1_city

1. 若要显示客户的统一时间线，请添加一个库元素，然后添加项属性：**Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    示例：Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]