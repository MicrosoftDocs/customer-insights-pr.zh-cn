---
title: 安装和配置客户卡加载项
description: 安装和配置适用于 Dynamics 365 Customer Insights 的客户卡加载项。
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268033"
---
# <a name="customer-card-add-in-preview"></a>客户卡加载项（预览版）

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

直接在 Dynamics 365 应用中全面了解您的客户。 使用客户加载项查看人口统计数据、见解和活动时间线。

## <a name="prerequisites"></a>先决条件

- 已启用统一接口的 Dynamics 365 应用（如销售中心或客户服务中心）版本 9.0 和更高版本。
- [使用 Common Data Service 从 Dynamics 365 应用引入](connect-power-query.md)的客户配置文件。
- 在访问群体见解中，客户卡加载项的用户需要[添加为用户](permissions.md)。
- [已配置搜索和筛选器功能](search-filter-index.md)。
- 人口统计控件：统一客户配置文件中提供了人口统计字段（例如年龄或性别）。
- 扩充控件：需要将可用[扩充](enrichment-hub.md)应用于客户配置文件。
- 智能控件：需要使用 Azure 机器学习生成的数据([预测](predictions.md)或[自定义模型](custom-models.md))
- 度量控件：需要[配置的度量](measures.md)。
- 时间线控件：需要[配置的活动](activities.md)。

## <a name="install-the-customer-card-add-in"></a>安装客户卡加载项

客户卡加载项是 Dynamics 365 中的 Customer Engagement 应用的解决方案。 若要安装此解决方案，请转到 AppSource 并搜索 **Dynamics 客户卡**。 选择 [AppSource 中的客户卡加载项](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然后选择 **立即获取**。

您可能需要使用管理员凭据登录来让 Dynamics 365 应用安装解决方案。

将此解决方案安装到环境中可能需要一些时间。

## <a name="configure-the-customer-card-add-in"></a>配置客户卡加载项

1. 以管理员身份转到 Dynamics 365 中的 **设置** 部分，然后选择 **解决方案**。

1. 选择 **Dynamics 365 Customer Insights 客户卡加载项（预览版）** 解决方案的 **显示名称** 链接。

   > [!div class="mx-imgBorder"]
   > ![选择显示名称](media/select-display-name.png "选择显示名称")

1. 选择 **登录**，然后输入用于配置 Customer Insights 的管理员帐户的凭据。

   > [!NOTE]
   > 检查在您选择 **登录** 按钮时，浏览器的弹出窗口阻止程序不会阻止身份验证窗口。

1. 选择要从中获取数据的环境。

1. 定义在 Dynamics 365 应用中映射到记录的字段。
   - 若要与联系人进行映射，请在客户实体中选择与联系人实体的 ID 匹配的字段。
   - 若要与帐户进行映射，请在客户实体中选择与帐户实体的 ID 匹配的字段。

   > [!div class="mx-imgBorder"]
   > ![联系人 ID 字段](media/contact-id-field.png "联系人 ID 字段")

1. 选择 **保存配置** 保存设置。

1. 接下来，需要在 Dynamics 365 中分派安全角色，以便用户自定义和查看客户卡。 在 Dynamics 365 中，转至 **设置** > **安全** > **用户**。 选择用户以编辑用户角色，然后选择 **管理角色**。

1. 将 **Customer Insights 卡定制员** 角色分配给将为整个组织自定义卡片上显示内容的用户。

## <a name="add-customer-card-controls-to-forms"></a>将客户卡控件添加到窗体
  
1. 若要向联系人窗体添加客户卡控件，请在 Dynamics 365 中转到 **设置** > **自定义**。

1. 选择 **自定义系统**。

1. 浏览到 **联系人** 实体，展开，然后选择 **窗体**。

1. 选择要向其添加客户卡控件的联系人窗体。

    > [!div class="mx-imgBorder"]
    > ![选择“联系人”窗体](media/contact-active-forms.png "选择“联系人”窗体")

1. 若要添加控件，请在窗体编辑器中，将任何字段从 **字段资源管理器** 拖到要显示该控件的位置。

1. 在窗体中选择刚才添加的字段，然后选择 **更改属性**。

1. 转到 **控件** 选项卡，选择 **添加控件**。 选择一个可用的自定义控件，然后选择 **添加**。

1. 在 **字段属性** 对话框中，清除 **在窗体上显示标签** 复选框。

1. 为控件选择 **Web** 选项。 对于“扩充”控件，通过配置 **enrichmentType** 字段选择要显示的扩充类型。 为每种扩充类型添加一个单独的扩充控件。

1. 选择 **保存** 和 **发布** 发布更新后的联系人窗体。

1. 转到发布的联系人窗体。 将看到新添加的控件。 首次使用时，可能需要登录。

1. 若要自定义自定义控件中显示的内容，请选择右上角的编辑按钮。

## <a name="upgrade-customer-card-add-in"></a>升级客户卡加载项
客户卡加载项不会自动升级。 若要升级到最新版本，请在安装了该加载项的 Dynamics 365 应用中按照此过程进行操作。

1. 在 Dynamics 365 应用中，转到 **设置** > **自定义**，并选择 **解决方案**。

1. 在加载项表中，查找 **CustomerInsightsCustomerCard** 并选择此行。

1. 在操作栏中选择 **应用解决方案升级**。

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="在 Dynamics 365 应用的自定义区域中升级解决方案":::

1. 开始升级过程后，您将看到一个加载指示器，直到升级完成为止。 如果没有较新版本，升级将显示一条错误消息。


[!INCLUDE[footer-include](../includes/footer-banner.md)]