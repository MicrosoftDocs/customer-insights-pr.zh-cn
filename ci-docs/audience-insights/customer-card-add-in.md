---
title: Dynamics 365 应用客户卡加载项
description: 使用此加载项在 Dynamics 365 应用中显示来自访问群体见解的数据。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059577"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="cf4c7-103">客户卡加载项（预览版）</span><span class="sxs-lookup"><span data-stu-id="cf4c7-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cf4c7-104">直接在 Dynamics 365 应用中全面了解您的客户。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="cf4c7-105">在支持的 Dynamics 365 应用中安装了客户卡加载项后，您可以选择显示人口统计数据、见解和活动时间线。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="cf4c7-106">该加载项可以从 Customer Insights 检索数据，而不会影响已连接的 Dynamics 365 应用中的数据。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cf4c7-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="cf4c7-107">Prerequisites</span></span>

- <span data-ttu-id="cf4c7-108">该加载项仅适用于 Dynamics 365 模型驱动应用，例如 Sales 或 Customer Service 版本 9.0 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="cf4c7-109">若要将 Dynamics 365 数据映射到访问群体见解客户配置文件，则需要[使用 Common Data Service 连接器从 Dynamics 365 应用引入](connect-power-query.md)它们。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="cf4c7-110">必须将此客户卡加载项的所有 Dynamics 365 用户[作为用户添加](permissions.md)到访问群体见解中以便查看数据。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="cf4c7-111">为了能够查询数据，需要使用访问群体见解中[配置的搜索和筛选功能](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="cf4c7-112">每个加载项控件都依赖于访问群体见解中的特定数据：</span><span class="sxs-lookup"><span data-stu-id="cf4c7-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="cf4c7-113">度量控件：需要[配置的度量](measures.md)。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="cf4c7-114">智能控件：需要使用[预测](predictions.md)或[自定义模型](custom-models.md)生成的数据。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="cf4c7-115">人口统计控件：统一客户配置文件中提供了人口统计字段（例如年龄或性别）。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="cf4c7-116">扩充控件：需要将可用[扩充](enrichment-hub.md)应用于客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="cf4c7-117">时间线控件：需要[配置的活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="cf4c7-118">安装客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="cf4c7-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="cf4c7-119">客户卡加载项是 Dynamics 365 中的 Customer Engagement 应用的解决方案。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="cf4c7-120">若要安装此解决方案，请转到 AppSource 并搜索 **Dynamics 客户卡**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="cf4c7-121">选择 [AppSource 中的客户卡加载项](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然后选择 **立即获取**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="cf4c7-122">您可能需要使用管理员凭据登录来让 Dynamics 365 应用安装解决方案。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="cf4c7-123">将此解决方案安装到环境中可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="cf4c7-124">配置客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="cf4c7-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="cf4c7-125">以管理员身份转到 Dynamics 365 中的 **设置** 部分，然后选择 **解决方案**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="cf4c7-126">选择 **Dynamics 365 Customer Insights 客户卡加载项（预览版）** 解决方案的 **显示名称** 链接。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cf4c7-127">![选择显示名称](media/select-display-name.png "选择显示名称")</span><span class="sxs-lookup"><span data-stu-id="cf4c7-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="cf4c7-128">选择 **登录**，然后输入用于配置 Customer Insights 的管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cf4c7-129">检查在您选择 **登录** 按钮时，浏览器的弹出窗口阻止程序不会阻止身份验证窗口。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="cf4c7-130">选择要从中获取数据的 Customer Insights 环境。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="cf4c7-131">定义 Dynamics 365 应用程序中记录的字段映射。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="cf4c7-132">根据 Customer Insights 中的数据，您可以选择映射以下选项：</span><span class="sxs-lookup"><span data-stu-id="cf4c7-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="cf4c7-133">若要与联系人进行映射，请在客户实体中选择与联系人实体的 ID 匹配的字段。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="cf4c7-134">若要与帐户进行映射，请在客户实体中选择与帐户实体的 ID 匹配的字段。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cf4c7-135">![联系人 ID 字段](media/contact-id-field.png "联系人 ID 字段")</span><span class="sxs-lookup"><span data-stu-id="cf4c7-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="cf4c7-136">选择 **保存配置** 保存设置。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="cf4c7-137">接下来，需要在 Dynamics 365 中分派安全角色，以便用户自定义和查看客户卡。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="cf4c7-138">在 Dynamics 365 中，转至 **设置** > **安全** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="cf4c7-139">选择用户以编辑用户角色，然后选择 **管理角色**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="cf4c7-140">将 **Customer Insights 卡定制员** 角色分配给将为整个组织自定义卡片上显示内容的用户。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="cf4c7-141">将客户卡控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="cf4c7-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="cf4c7-142">若要向联系人窗体添加客户卡控件，请在 Dynamics 365 中转到 **设置** > **自定义**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="cf4c7-143">选择 **自定义系统**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="cf4c7-144">浏览到 **联系人** 实体，展开，然后选择 **窗体**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="cf4c7-145">选择要向其添加客户卡控件的联系人窗体。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cf4c7-146">![选择“联系人”窗体](media/contact-active-forms.png "选择“联系人”窗体")</span><span class="sxs-lookup"><span data-stu-id="cf4c7-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="cf4c7-147">若要添加控件，请在窗体编辑器中，将任何字段从 **字段资源管理器** 拖到要显示该控件的位置。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="cf4c7-148">在窗体中选择刚才添加的字段，然后选择 **更改属性**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="cf4c7-149">转到 **控件** 选项卡，选择 **添加控件**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="cf4c7-150">选择一个可用的自定义控件，然后选择 **添加**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="cf4c7-151">在 **字段属性** 对话框中，清除 **在窗体上显示标签** 复选框。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="cf4c7-152">为控件选择 **Web** 选项。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="cf4c7-153">对于“扩充”控件，通过配置 **enrichmentType** 字段选择要显示的扩充类型。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="cf4c7-154">为每种扩充类型添加一个单独的扩充控件。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="cf4c7-155">选择 **保存** 和 **发布** 发布更新后的联系人窗体。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="cf4c7-156">转到发布的联系人窗体。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-156">Go to the published contact form.</span></span> <span data-ttu-id="cf4c7-157">将看到新添加的控件。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-157">You'll see the newly added control.</span></span> <span data-ttu-id="cf4c7-158">首次使用时，可能需要登录。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="cf4c7-159">若要自定义自定义控件中显示的内容，请选择右上角的编辑按钮。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="cf4c7-160">升级客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="cf4c7-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="cf4c7-161">客户卡加载项不会自动升级。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="cf4c7-162">若要升级到最新版本，请在安装了该加载项的 Dynamics 365 应用中按照此过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="cf4c7-163">在 Dynamics 365 应用中，转到 **设置** > **自定义**，并选择 **解决方案**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="cf4c7-164">在加载项表中，查找 **CustomerInsightsCustomerCard** 并选择此行。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="cf4c7-165">在操作栏中选择 **应用解决方案升级**。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="在 Dynamics 365 应用的自定义区域中升级解决方案":::

1. <span data-ttu-id="cf4c7-167">开始升级过程后，您将看到一个加载指示器，直到升级完成为止。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="cf4c7-168">如果没有较新版本，升级将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="cf4c7-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
