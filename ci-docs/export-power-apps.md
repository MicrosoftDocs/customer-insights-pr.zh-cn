---
title: Power Apps 连接器
description: 与 Power Apps 和 Power Automate 连接。
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645958"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps 连接器（预览版）

使用 Power Apps 将统一客户配置文件导入到个性化的应用中。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>连接 Power Apps 和 Dynamics 365 Customer Insights

Customer Insights 是 [Power Apps 中众多数据源](/powerapps/maker/canvas-apps/working-with-data-sources)之一。

请参阅 Power Apps 文档了解如何[向应用添加数据连接](/powerapps/maker/canvas-apps/add-data-connection)。 我们建议您另外回顾一下 [Power Apps 如何使用代理来处理画布应用中的大型数据集](/powerapps/maker/canvas-apps/delegation-overview)。

## <a name="available-entities"></a>可用实体

将 Customer Insights 作为数据连接添加之后，可以在 Power Apps 中选择以下实体：

- **Customer**：如果要使用[统一客户配置文件](customer-profiles.md)中的数据。
- **UnifiedActivity**：如果要在应用中显示[活动时间线](activities.md)。
- **ContactProfile**：如果要显示客户的联系人。 此实体仅在企业客户的 Customer Insights 环境中可用。

## <a name="limitations"></a>限制

### <a name="retrievable-entities"></a>可检索实体

您只能通过 Power Apps 连接器检索 **Customer**、**UnifiedActivity**、**Segments** 和 **ContactProfile** 实体。 ContactProfile 仅在企业客户的 Customer Insights 实例中可用。 之所以显示其他实体，是因为基础连接器通过 Power Automate 中的触发器支持它们。

每 60 秒最多可以进行 100 次调用。 您可以使用 $skip 参数多次调用 API 终结点。 [了解有关 $skip 参数的详细信息](/connectors/customerinsights/#get-items-from-an-entity)。

### <a name="delegation"></a>代理

委派适用于 **Customer** 实体和 **UnifiedActivity** 实体。 

- **客户** 实体的委派：若要针对此实体使用委派，需要在[搜索和筛选索引](search-filter-index.md)中对字段编制索引。  
- **统一活动** 实体的委派：此实体的委派仅适用于字段 **ActivityId** 和 **CustomerId**。  
- **ContactProfile** 的委派：此实体的委派仅适用于 **ContactId** 和 **CustomerId** 字段。 ContactProfile 仅在企业客户的 Customer Insights 环境中可用。

有关委派的详细信息，请转到 [Power Apps 可委派函数和操作](/powerapps/maker/canvas-apps/delegation-overview)。 

## <a name="example-gallery-control"></a>示例库控件

您可以将客户配置文件添加到[库控件](/powerapps/maker/canvas-apps/add-gallery)。

1. 请向正在构建的应用添加一个 **库** 控件。

    > [!div class="mx-imgBorder"]
    > ![添加库元素。](media/connector-powerapps9.png "添加库元素。")

2. 选择 **客户** 充当项的数据源。

    > [!div class="mx-imgBorder"]
    > ![选择数据源。](media/choose-datasource-powerapps.png "选择数据源。")

3. 可以更改右侧的数据面板以选择在库中显示客户实体的哪个字段。

4. 如果要在库中显示所选客户的任何字段，使用 **{Name_of_the_gallery}.Selected.{property_name}** 填充标签的 **Text** 属性  
    - 例如：_Gallery1.Selected.address1_city_

5. 要显示客户的统一时间线，添加一个库元素，然后使用 **Filter('UnifiedActivity', CustomerId = {Customer_Id})** 添加 **Items** 属性  
    - 例如：_Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
