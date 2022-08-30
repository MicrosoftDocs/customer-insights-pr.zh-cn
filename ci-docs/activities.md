---
title: 客户或业务联系人活动
description: 定义客户或业务联系人活动，然后在客户配置文件中的时间线内查看这些客户活动。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304094"
---
# <a name="customer-or-business-contact-activities"></a>客户或业务联系人活动

客户活动是客户或业务联系人执行的操作或事件。 例如，交易、支持通话持续时间、网站评价、购买或退货。 这些活动包含在一个或多个数据源中。 使用 Customers Insights，可以整合来自这些[数据源](data-sources.md)的客户活动，并将它们与客户资料相关联。 这些活动按时间顺序显示在客户资料的时间线上。 将时间线与[客户卡加载项](customer-card-add-in.md)解决方案一起包括在 Dynamics 365 应用中。

## <a name="define-a-customer-activity"></a>定义客户活动

实体必须至少有一个类型为 **日期** 的属性才能包含在客户时间线中。 如果未找到此类实体，将禁用 **添加活动** 控件。

1. 转到 **数据** > **活动**。

1. 选择 **添加活动** 启动引导式体验。

1. 在 **活动数据** 步骤中，输入以下信息：

   - **活动名称**：为您的活动选择一个名称。
   - **活动实体**：选择包含交易数据或活动数据的实体。
   - **主键**：选择唯一标识记录的字段。 其中不应包含任何重复值、空值或缺少值。

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="使用名称、实体和主键设置活动数据。":::

1. 选择 **下一步**。

1. 在 **关系** 步骤中，选择 **添加关系** 将您的活动数据连接到其相应的客户记录。 此步骤显示实体之间的连接。  

   - **外键**：活动实体中的外键字段，将用于与另一个实体建立关系。
   - **目标实体名称**：将与您的活动实体有关系的相应源客户实体。 您只能与数据统一过程中使用的源客户实体关联。
   - **关系名称**：如果此活动实体与所选源客户实体之间的关系已存在，则关系名称处于只读模式。 如果不存在此关系，将使用您在此框中提供的名称创建新关系。

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="定义实体关系。":::

   > [!TIP]
   > 在企业对企业环境中，可在客户实体和其他实体之间选择。 如果选择客户实体，将自动设置关系路径。 对于其他实体，您必须定义到达客户实体前一个或多个中间实体之间的关系路径。

1. 选择 **应用** 创建关系。

1. 选择 **下一步**。

1. 在 **活动统一** 步骤中，选择活动事件和活动开始时间。
   - **必填字段**
      - **事件活动**：作为该活动的事件的字段。
      - **时间戳**：表示活动开始时间的字段。

   - **可选字段**
      - **其他详细信息**：具有此活动的相关信息的字段。
      - **图标**：最能代表此活动类型的图标。
      - **网址**：包含此活动相关信息的 URL 的字段。 例如，提供该活动的交易系统。 此 URL 可以是数据源中的任何字段，也可以使用 Power Query 转换将其构造为新字段。 URL 数据将存储在 *统一活动* 实体中，可以通过 [API](apis.md) 在下游使用该实体。

   - **显示在时间线中**
      - 选择是否要在客户配置文件的时间线视图中查看此活动。 若要在时间线中显示此活动，请选择 **是**，若要隐藏此活动，请选择 **否**。

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="在统一活动实体中指定客户活动数据。":::

1. 选择 **下一步** 选择活动类型，或选择 **完成并查看** 保存活动并将活动类型设置为 **其他**。

1. 在 **活动类型** 步骤中，选择活动类型，并根据需要选择是否要在语意上映射某些活动类型，以便在 Customer Insights 的其他区域中使用。 当前，在同意映射字段后，*反馈*、*忠诚度*、*SalesOrder*、*SalesOrderLine* 和 *订阅* 活动类型支持语义。 如果活动类型与新活动无关，您可以为自定义活动类型选择 *其他* 或 *新建*。

1. 选择 **下一步**。

1. 在 **查看** 步骤中，验证您的选择。 返回到上述任何步骤并在必要时更新信息。

1. 选择 **保存活动** 以应用您的更改，并选择 **完成** 以返回到 **数据** > **活动**。 将显示创建的活动。

1. 创建所有活动后，选择 **运行** 处理这些活动。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>管理现有客户活动

转到 **数据** > **活动** 查看您保存的活动、活动源实体、活动类型以及它们是否包含在客户时间线中。 您可以按任何列对活动列表进行排序，或使用搜索框查找要管理的活动。

选择活动查看可用操作。

- **编辑** 活动更改活动的配置。 配置将在审查步骤中打开。 更改配置后，选择 **保存活动**，然后选择 **运行** 来处理更改。
- **重命名** 活动。 选择 **保存** 以应用您所做的更改。
- **删除** 活动。 要一次删除多个活动，选择活动，然后选择 **删除**。 确认删除。

## <a name="view-activity-timelines-on-customer-profiles"></a>查看客户配置文件上的活动时间线

1. 如果您在活动配置中选择了 **在活动时间线中显示**，转到 **客户**，选择客户资料在 **活动时间线** 部分查看客户的活动。

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="在客户配置文件中查看配置的活动。":::

1. 要筛选活动时间线中的活动：

   - 选择一个或多个活动图标来细化结果，仅包括所选类型。

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="使用图标按类型筛选活动。":::

   - 选择 **筛选器** 打开筛选器面板配置时间线筛选器。 按 *ActivityType* 和/或 *日期* 进行筛选。 选择 **应用**。

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="使用筛选器面板配置筛选条件。":::

> [!NOTE]
> 当您离开客户配置文件时，活动筛选器将被删除。 您必须在每次打开客户资料时应用它们。

## <a name="define-a-contact-activity"></a>定义联系人活动

对于企业客户（企业对企业），使用 *ContactProfile* 实体来捕获联系人的活动。 您可以在活动时间线中查看由联系人负责每个活动的客户。 大多数步骤都采用客户活动映射配置。

   > [!NOTE]
   > 要定义联系人级别的活动，必须创建一个 *ContactProfile* 实体，作为[统一的联系人配置文件](data-unification-contacts.md)或通过[语义映射](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping)。
   >
   > 活动数据中每个记录都必须具有 **AccountID** 和 **ContactID** 属性。
  
1. 转到 **数据** > **活动**。

1. 选择 **添加活动**。

1. 命名活动，选择源活动实体，并选择活动实体的主键。

1. 在 **关系** 步骤中，使用您的联系人数据作为中间实体，在您的活动源数据与客户之间创建间接关系。 有关详细信息，请参阅[直接和间接关系路径](relationships.md#relationship-paths)。
   - 名为 *购买* 的活动的示例关系：
      - 属性 **ContactID** 上的 **采购来源活动数据** > **联系人数据**
      - 属性 **AccountID** 上的 **联系人属性** > **客户数据**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="所建立关系示例。":::

1. 建立关系后，选择 **下一步** 并完成您的活动映射配置。 有关创建活动的详细步骤，请参阅[定义客户活动](#define-a-customer-activity)。

1. 运行活动映射。

1. 现在，您的联系人级别的活动将在客户时间线上可见。

   :::image type="content" source="media/Contact_Activities2.png" alt-text="配置联系人活动后的最终结果":::

## <a name="contact-level-activity-timeline-filtering"></a>联系人级别的活动时间线筛选

配置联系人级别的活动映射并运行此映射后，将更新您的客户的活动时间线。 这包括他们所执行活动的 ID 或名称，具体取决于您的 *ContactProfile* 配置。 可以按时间线中的联系人筛选活动，以查看您感兴趣的特定联系人。 此外，您还可以通过选择 **未映射到联系人的活动** 来查看未分配给特定联系人的所有活动。

   :::image type="content" source="media/Contact_Activities3.png" alt-text="适用于联系人级别的活动的筛选选项。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
