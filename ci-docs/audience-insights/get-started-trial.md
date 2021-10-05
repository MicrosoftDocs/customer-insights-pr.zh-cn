---
title: 创建和配置 Customer Insights 的试用版
description: 用于获取 Dynamics 365 Customer Insights 试用版订阅并对其进行配置的步骤。
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558812"
---
# <a name="set-up-a-trial-environment"></a>设置试用环境 

利用 Dynamics 365 Customer Insights 的试用版，您可以查看关键功能并了解有关各项功能的更多信息。 试用版订阅过期后被删除。 试用环境由成为其试用环境管理员的个人用户创建。 他们可以邀请更多用户使用他们的试用版并配置各种功能。

## <a name="create-a-trial-environment"></a>创建试用环境

您可以在[试用注册页](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)注册试用。 

1. 选择 **注册免费试用** 选项，然后选择 **立即注册**。

1. 提供您的工作或学校电子邮件地址，告诉我们您自己的详细信息并选择 **开始**。

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="用于注册试用实例的对话框":::

1. 查看条款和条件，然后选择 **继续** 以确认。

1. 为您的新环境提供一个 **名称**。 

1. 将环境 **类型** 设置为 **试用**。

1. 在 **选择行业演示** 字段中，您可以有选择性地选择行业特定的数据集。 您还可以在以后[更改为行业演示](#use-industry-specific-demo-data-sets-in-audience-insights)，并开始使用默认数据集。

1. 选择环境的 **区域**。

1. （可选）如果您是 Dynamics 365 组织的管理员：请选择 **高级设置**，并提供组织的 URL 以使用客户流失预测等预测功能。 

1. 选择 **创建**。 

完成环境设置需要一些时间。 完成后，您将重定向到您在上面步骤中选择的演示环境或行业演示。 现在，您可以使用只读演示数据浏览应用。 要将自己的数据添加到环境中，请参阅[在您自己的环境中创建特定于场景的演示数据](#create-scenario-specific-demo-data-in-your-own-environment)。

:::image type="content" source="media/trial-environment.png" alt-text="新建试用环境的屏幕截图。":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>在访问群体见解中使用特定于行业的演示数据集

连接实际数据源是使用 Customer Insights 功能过程中的一个关键步骤。 要在不干扰您自己的数据的情况下试用功能，您可以有选择性地使用特定于行业的演示数据。 有一些演示数据集可用于以下行业： 

-   汽车业
-   银行业
-   消费品
-   政府
-   卫生保健业
-   酒店
-   保险
-   制造
-   专业服务
-   零售

### <a name="see-industry-specific-demo-data-in-trials"></a>请参阅试用版中的行业特定演示数据

对于针对特定行业或方案量身定制的 Customer Insights 只读版本，请在演示环境中开始。 
 
1.  在访问群体见解内的环境选择器中，选择 **演示** 环境。

2.  在 **主页** 上，从“选择行业演示”下拉菜单中选择一个选项。

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="为试用环境选择行业。":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>在您自己的环境中创建方案特定演示数据

作为管理员，请在应用标题中选择环境选择器以创建新环境。 在新环境中，您可以按照您的要求配置自己的数据源并设置应用。 

1.  在访问群体见解中，转到 **数据** > **数据源**。

2.  要导入自己的数据源，请转到[数据引入指南](data-sources.md)。     
   如果您更愿意使用允许您试用数据引入的示例数据，则您可以在您的环境中引入行业演示数据。 选择 **从数据中心导入** 选项，并执行以下步骤。

3.  选择符合您的方案的行业卡。 

4.  查看并有选择性地更新数据源的建议名称。 

5.  选择 **下一步** 以引入示例数据。 

您现在可以使用引入的数据根据您的方案定制 Customer Insights。 要查看特定于引入的演示数据的环境，请在环境选择器中选择 **<Industry> 演示** 选项。

## <a name="limitations-in-trials"></a>试用中的限制

- 默认情况下，试用版有效期为 30 天。 不过，您可以在登录试用版的第 23 天后开始延长试用期。
- 在试用期间，不能使用自己的 Azure Data Lake Storage 帐户来存储输出数据。 但是，您可以通过 Data Lake 存储帐户来引入数据。
- 您可以在 Dataverse 环境中存储最多 3 GB 的数据，在您开始试用 Customer Insights 时会自动预配该环境。

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>将数据从试用版复制到付费订阅

通常，我们建议在升级到 Customer Insights 的付费版本时使用您自己的数据重新开始。 

或者，如果您购买 Customer Insights，您可以从试用环境复制您的数据。 您必须是 Customer Insights 试用版的管理员和 Microsoft 365 租户的全局管理员，或者您组织中的 Dynamics 365 管理员，才能将设置从试用环境迁移到付费环境。 

首次登录 Customer Insights 的付费实例后，系统会要求您创建一个新环境。 在此过程中，您可以选择从现有环境复制配置并迁移大部分设置。 如果您拥有上述权限，试用环境将显示在此列表中。 有关详细信息，请参阅[复制环境配置](manage-environments.md#copy-the-environment-configuration)。

## <a name="next-steps"></a>后续步骤

查看以下文章以帮助您开始配置 Customer Insights。 

- [添加更多用户和分配权限](permissions.md)。
- [引入您的数据源](data-sources.md)并通过[数据统一过程](data-unification.md)运行它们，以获得[统一的客户配置文件](customer-profiles.md)。
- [扩充统一的客户配置文件](enrichment-hub.md)或[运行预测模型](predictions-overview.md)。
- 创建[客户细分](segments.md)以为客户分组并[衡量](measures.md)评价 KPI。
- 设置[连接](connections.md)和[导出](export-destinations.md)，以处理其他应用程序中的数据子集。
