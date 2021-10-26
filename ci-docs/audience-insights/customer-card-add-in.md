---
title: Dynamics 365 应用客户卡加载项
description: 使用此加载项在 Dynamics 365 应用中显示来自访问群体见解的数据。
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9c7cfbf9f47cca53e5543e2cda2584e25ad855d
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643350"
---
# <a name="customer-card-add-in-preview"></a>客户卡加载项（预览版）

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

直接在 Dynamics 365 应用中全面了解您的客户。 在支持的 Dynamics 365 应用中安装客户卡加载项后，您可以选择显示客户配置文件字段、见解和活动时间线。 该加载项可以从 Customer Insights 检索数据，而不会影响已连接的 Dynamics 365 应用中的数据。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>先决条件

- 该加载项仅适用于 Dynamics 365 模型驱动应用，例如 Sales 或 Customer Service 版本 9.0 及更高版本。
- 若要将 Dynamics 365 数据映射到访问群体见解客户配置文件，则需要[使用 Microsoft Dataverse 连接器从 Dynamics 365 应用引入](connect-power-query.md)它们。
- 必须将此客户卡加载项的所有 Dynamics 365 用户[作为用户添加](permissions.md)到访问群体见解中以便查看数据。
- 为了能够查询数据，需要使用访问群体见解中[配置的搜索和筛选功能](search-filter-index.md)。
- 每个加载项控件都依赖于访问群体见解中的特定数据。 某些数据和控件仅在特定类型的环境中可用。 加载项配置将通知您控件是否由于所选环境类型而不可用。 详细了解[环境用例](work-with-business-accounts.md)。
  - **度量值控件**：需要配置的客户属性类型的[度量值](measures.md)。
  - **智能控件**：需要使用[预测](predictions.md)或[自定义模型](custom-models.md)生成的数据。
  - **客户详细信息控件**：配置文件的所有字段在统一客户配置文件中提供。
  - **扩充控件**：需要应用于客户配置文件的可用[扩充](enrichment-hub.md)。
  - **联系人控件**：需要定义联系人类型的语义实体。
  - **时间线控件**：需要[配置的活动](activities.md)。

## <a name="install-the-customer-card-add-in"></a>安装客户卡加载项

客户卡加载项是 Dynamics 365 中的 Customer Engagement 应用的解决方案。 若要安装此解决方案，请转到 AppSource 并搜索 **Dynamics 客户卡**。 选择 [AppSource 中的客户卡加载项](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然后选择 **立即获取**。

您可能需要使用管理员凭据登录来让 Dynamics 365 应用安装解决方案。 将此解决方案安装到环境中可能需要一些时间。

## <a name="configure-the-customer-card-add-in"></a>配置客户卡加载项

1. 以管理员身份转到 Dynamics 365 中的 **设置** 部分，然后选择 **解决方案**。

1. 选择 **Dynamics 365 Customer Insights 客户卡加载项（预览版）** 解决方案的 **显示名称** 链接。

   > [!div class="mx-imgBorder"]
   > ![选择显示名称。](media/select-display-name.png "选择显示名称。")

1. 选择 **登录**，然后输入用于配置 Customer Insights 的管理员帐户的凭据。

   > [!NOTE]
   > 检查在您选择 **登录** 按钮时，浏览器的弹出窗口阻止程序不会阻止身份验证窗口。

1. 选择要从中获取数据的 Customer Insights 环境。

1. 定义 Dynamics 365 应用程序中记录的字段映射。 根据 Customer Insights 中的数据，您可以选择映射以下选项：
   - 若要与联系人进行映射，请在客户实体中选择与联系人实体的 ID 匹配的字段。
   - 若要与帐户进行映射，请在客户实体中选择与帐户实体的 ID 匹配的字段。

   > [!div class="mx-imgBorder"]
   > ![联系人 ID 字段。](media/contact-id-field.png "联系人 ID 字段。")

1. 选择 **保存配置** 保存设置。

1. 接下来，需要在 Dynamics 365 中分派安全角色，以便用户自定义和查看客户卡。 在 Dynamics 365 中，转至 **设置** > **安全** > **用户**。 选择用户以编辑用户角色，然后选择 **管理角色**。

1. 将 **Customer Insights 卡定制员** 角色分配给将为整个组织自定义卡片上显示内容的用户。

## <a name="add-customer-card-controls-to-forms"></a>将客户卡控件添加到窗体

根据您的场景，您可以选择将控件添加到 **联系人** 窗体或 **客户** 窗体。 如果您的受众见解环境面向企业客户，我们建议将这些控件添加到“客户”窗体。 在这种情况下，将以下步骤中的“联系人”替换为“客户”。

1. 若要向联系人窗体添加客户卡控件，请在 Dynamics 365 中转到 **设置** > **自定义**。

1. 选择 **自定义系统**。

1. 浏览到 **联系人** 实体，展开，然后选择 **窗体**。

1. 选择要向其添加客户卡控件的联系人窗体。

    > [!div class="mx-imgBorder"]
    > ![选择“联系人”窗体。](media/contact-active-forms.png "选择“联系人”窗体。")

1. 若要添加控件，请在窗体编辑器中，将任何字段从 **字段资源管理器** 拖到要显示该控件的位置。

1. 在窗体中选择刚才添加的字段，然后选择 **更改属性**。

1. 转到 **控件** 选项卡，选择 **添加控件**。 选择一个可用的自定义控件，然后选择 **添加**。

1. 在 **字段属性** 对话框中，清除 **在窗体上显示标签** 复选框。

1. 为控件选择 **Web** 选项。 对于“扩充”控件，通过配置 **enrichmentType** 字段选择要显示的扩充类型。 为每种扩充类型添加一个单独的扩充控件。

1. 选择 **保存** 和 **发布** 发布更新后的联系人窗体。

1. 转到发布的联系人窗体。 将看到新添加的控件。 首次使用时，可能需要登录。

1. 若要自定义自定义控件中显示的内容，请选择右上角的编辑按钮。

## <a name="upgrade-customer-card-add-in"></a>升级客户卡加载项

客户卡加载项不会自动升级。 要升级到最新版本，请在安装了此加载项的 Dynamics 365 应用中执行以下步骤。

1. 在 Dynamics 365 应用中，转到 **设置** > **自定义**，并选择 **解决方案**。

1. 在加载项表中，查找 **CustomerInsightsCustomerCard** 并选择此行。

1. 在操作栏中选择 **应用解决方案升级**。

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="在 Dynamics 365 应用的自定义区域中升级解决方案。":::

1. 开始升级过程后，您将看到一个加载指示器，直到升级完成为止。 如果没有较新版本，升级将显示一条错误消息。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
