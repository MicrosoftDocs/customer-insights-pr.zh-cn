---
title: 安装和配置客户卡加载项
description: 安装和配置适用于 Dynamics 365 Customer Insights 的客户卡加载项。
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597316"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="bbdc0-103">客户卡加载项（预览版）</span><span class="sxs-lookup"><span data-stu-id="bbdc0-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bbdc0-104">直接在 Dynamics 365 应用中全面了解您的客户。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="bbdc0-105">使用客户加载项查看人口统计数据、见解和活动时间线。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bbdc0-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="bbdc0-106">Prerequisites</span></span>

- <span data-ttu-id="bbdc0-107">已启用统一接口的 Dynamics 365 应用（如销售中心或客户服务中心）版本 9.0 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="bbdc0-108">[使用 Common Data Service 从 Dynamics 365 应用引入](connect-power-query.md)的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="bbdc0-109">在访问群体见解中，客户卡加载项的用户需要[添加为用户](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="bbdc0-110">[已配置搜索和筛选器功能](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="bbdc0-111">人口统计控件：统一客户配置文件中提供了人口统计字段（例如年龄或性别）。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="bbdc0-112">扩充控件：需要将可用[扩充](enrichment-hub.md)应用于客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="bbdc0-113">智能控件：需要使用 Azure 机器学习生成的数据([预测](predictions.md)或[自定义模型](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="bbdc0-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="bbdc0-114">度量控件：需要[配置的度量](measures.md)。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="bbdc0-115">时间线控件：需要[配置的活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="bbdc0-116">安装客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="bbdc0-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="bbdc0-117">客户卡加载项是 Dynamics 365 中的 Customer Engagement 应用的解决方案。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="bbdc0-118">若要安装此解决方案，请转到 AppSource 并搜索 **Dynamics 客户卡**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="bbdc0-119">选择 [AppSource 中的客户卡加载项](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)，然后选择 **立即获取**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="bbdc0-120">您可能需要使用管理员凭据登录来让 Dynamics 365 应用安装解决方案。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="bbdc0-121">将此解决方案安装到环境中可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="bbdc0-122">配置客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="bbdc0-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="bbdc0-123">以管理员身份转到 Dynamics 365 中的 **设置** 部分，然后选择 **解决方案**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="bbdc0-124">选择 **Dynamics 365 Customer Insights 客户卡加载项（预览版）** 解决方案的 **显示名称** 链接。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbdc0-125">![选择显示名称](media/select-display-name.png "选择显示名称")</span><span class="sxs-lookup"><span data-stu-id="bbdc0-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="bbdc0-126">选择 **登录**，然后输入用于配置 Customer Insights 的管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bbdc0-127">检查在您选择 **登录** 按钮时，浏览器的弹出窗口阻止程序不会阻止身份验证窗口。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="bbdc0-128">选择要从中获取数据的环境。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="bbdc0-129">定义在 Dynamics 365 应用中映射到记录的字段。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="bbdc0-130">若要与联系人进行映射，请在客户实体中选择与联系人实体的 ID 匹配的字段。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="bbdc0-131">若要与帐户进行映射，请在客户实体中选择与帐户实体的 ID 匹配的字段。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbdc0-132">![联系人 ID 字段](media/contact-id-field.png "联系人 ID 字段")</span><span class="sxs-lookup"><span data-stu-id="bbdc0-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="bbdc0-133">选择 **保存配置** 保存设置。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="bbdc0-134">接下来，需要在 Dynamics 365 中分派安全角色，以便用户自定义和查看客户卡。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="bbdc0-135">在 Dynamics 365 中，转至 **设置** > **安全** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="bbdc0-136">选择用户以编辑用户角色，然后选择 **管理角色**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="bbdc0-137">将 **Customer Insights 卡定制员** 角色分配给将为整个组织自定义卡片上显示内容的用户。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="bbdc0-138">将客户卡控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="bbdc0-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="bbdc0-139">若要向联系人窗体添加客户卡控件，请在 Dynamics 365 中转到 **设置** > **自定义**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="bbdc0-140">选择 **自定义系统**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="bbdc0-141">浏览到 **联系人** 实体，展开，然后选择 **窗体**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="bbdc0-142">选择要向其添加客户卡控件的联系人窗体。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bbdc0-143">![选择“联系人”窗体](media/contact-active-forms.png "选择“联系人”窗体")</span><span class="sxs-lookup"><span data-stu-id="bbdc0-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="bbdc0-144">若要添加控件，请在窗体编辑器中，将任何字段从 **字段资源管理器** 拖到要显示该控件的位置。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="bbdc0-145">在窗体中选择刚才添加的字段，然后选择 **更改属性**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="bbdc0-146">转到 **控件** 选项卡，选择 **添加控件**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="bbdc0-147">选择一个可用的自定义控件，然后选择 **添加**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="bbdc0-148">在 **字段属性** 对话框中，清除 **在窗体上显示标签** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="bbdc0-149">为控件选择 **Web** 选项。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="bbdc0-150">对于“扩充”控件，通过配置 **enrichmentType** 字段选择要显示的扩充类型。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="bbdc0-151">为每种扩充类型添加一个单独的扩充控件。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="bbdc0-152">选择 **保存** 和 **发布** 发布更新后的联系人窗体。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="bbdc0-153">转到发布的联系人窗体。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-153">Go to the published contact form.</span></span> <span data-ttu-id="bbdc0-154">将看到新添加的控件。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-154">You'll see the newly added control.</span></span> <span data-ttu-id="bbdc0-155">首次使用时，可能需要登录。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="bbdc0-156">若要自定义自定义控件中显示的内容，请选择右上角的编辑按钮。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="bbdc0-157">升级客户卡加载项</span><span class="sxs-lookup"><span data-stu-id="bbdc0-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="bbdc0-158">客户卡加载项不会自动升级。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="bbdc0-159">若要升级到最新版本，请在安装了该加载项的 Dynamics 365 应用中按照此过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="bbdc0-160">在 Dynamics 365 应用中，转到 **设置** > **自定义**，并选择 **解决方案**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="bbdc0-161">在加载项表中，查找 **CustomerInsightsCustomerCard** 并选择此行。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="bbdc0-162">在操作栏中选择 **应用解决方案升级**。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="在 Dynamics 365 应用的自定义区域中升级解决方案":::

1. <span data-ttu-id="bbdc0-164">开始升级过程后，您将看到一个加载指示器，直到升级完成为止。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="bbdc0-165">如果没有较新版本，升级将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="bbdc0-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]