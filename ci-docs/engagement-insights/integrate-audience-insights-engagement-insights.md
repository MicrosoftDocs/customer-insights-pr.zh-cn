---
title: 创建参与见解与访问群体见解之间的链接
description: 创建访问群体见解与参与见解之间的活动链接，以便实现数据双向共享。
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229861"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>创建参与见解与访问群体见解之间的链接

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解与访问群体见解之间的集成从两项功能链接环境，并在两者之间双向共享数据。

将访问群体见解的统一配置文件和客户细分用于参与见解中的更多分析选项。 从参与见解导出具有极大业务价值的事件。 将这些事件用于向访问群体见解中的统一配置文件添加数据。

## <a name="prerequisites"></a>先决条件

- 访问群体见解配置文件必须存储在您负责的 Azure Data Lake Storage 帐户中，或存储在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;托管数据湖中。 
- 您的访问群体见解环境应该具有关联的 Dataverse 环境。 如果该环境也在为数据存储使用 Dataverse，请确保在访问群体见解中选中 **启用数据共享** 选项。 有关详细信息，请参阅[在访问群体见解中创建和配置环境](../audience-insights/create-environment.md)。
- 需要参与见解和访问群体见解环境两者的管理员权限。
- 链接的环境必须位于同一地理区域内。

> [!NOTE]
> - 如果您的访问群体见解订阅为试用版，即其使用访问群体见解内部管理的数据湖，请联系 [pirequest@microsoft.com](mailto:pirequest@microsoft.com) 获取帮助。 
> - 如果您的访问群体见解使用您自己的 Azure Data Lake Storage 存储数据，您需要向您的存储帐户添加参与见解 Azure 服务主体。 有关详细信息，请转到[使用适用于访问群体见解的 Azure 服务主体连接到 Azure Data Lake Storage 帐户](../audience-insights/connect-service-principal.md)。 


## <a name="create-an-environment-link"></a>创建环境链接

可以通过在参与见解中更新 **管理** > **环境** 设置创建环境链接。

**建立参与见解与访问群体见解之间的活动链接**

1. 在 **环境管理员** 页面中，选择 **链接环境** 选项卡。

    :::image type="content" source="media/integrate1.png" alt-text="设置环境。":::

1. 在屏幕左上角或底部选择 **设置环境**。

     :::image type="content" source="media/integrate2.png" alt-text="选择一个访问群体见解环境。":::

1. 选择一个访问群体见解环境，然后选择 **下一步** 完成操作。 现在，您可以为链接的环境选择可选功能。
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>启用访问群体见解统一配置文件属性和客户细分

链接环境之后，您可以为链接的环境选择可选功能。 可通过这些功能将访问群体见解的统一配置文件属性和客户细分用于对客户数据进行交互分析。

> [!IMPORTANT]
> 若要在参与见解中显示访问群体见解客户细分，首先必须[运行合并和下游流程](../audience-insights/merge-entities.md)。 下游流程非常重要，因为它们生成一个唯一的表，用于准备要与参与见解共享的访问群体见解客户细分。 （如果安排了系统刷新，其将自动包括下游流程。）

**在参与见解中分析 Web 数据**

1. 在 **环境管理员** 页面中，开启 **与参与见解共享访问群体见解中的数据** 开关，然后选择 **下一步**。

    :::image type="content" source="media/integrate4.png" alt-text="选择功能。":::

1. 选择将成为参与见解中的维度的统一配置文件的属性。 （并非所有属性都是有用的维度。 例如，您不太可能需要 **名字** 或 **姓氏** 来充当用于分析您的网站事件的属性。）

    :::image type="content" source="media/integrate5.png" alt-text="管理维度。":::

   >[!NOTE]
   > 所有表示标识符（如 **ID** 和 **备用 ID**）的访问群体见解配置文件属性都将从可用属性中过滤掉，并成为参与见解中的维度。

1. 选择完属性后，请选择 **下一步**。
1. 添加可查看参与见解中的访问群体见解配置文件维度和客户细分的用户。

    :::image type="content" source="media/integrate6.png" alt-text="管理对客户数据的访问权限。":::

   > [!IMPORTANT]
   > 如果此步骤中不明确添加用户，参与见解中将对用户隐藏数据。
   > 若要在参与见解中显示访问群体见解客户细分，首先必须[运行合并和下游流程](../audience-insights/merge-entities.md)。 下游流程非常重要，因为它们生成一个唯一的表，用于准备要与参与见解共享的访问群体见解客户细分。 （如果安排了系统刷新，其将自动包括下游流程。）

1. 请检查您的选择，然后选择 **完成**。

    :::image type="content" source="media/integrate7.png" alt-text="检查客户数据设置。":::

## <a name="export-refined-events-to-audience-insights"></a>将已优化的事件导出到访问群体见解

创建环境之间的链接之后，可将已优化的事件从参与见解导出到访问群体见解，然后将其作为新数据源引入。 

有关详细信息，请转到[将来自参与见解的 Web 数据与访问群体见解集成](../audience-insights/integrate-engagement-insights.md)。

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
