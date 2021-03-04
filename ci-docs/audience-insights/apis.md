---
title: 使用 API
description: 使用 API 并了解限制。
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267513"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="6d429-103">使用 Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="6d429-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="6d429-104">Dynamics 365 Customer Insights 提供 API，用于基于 Customer Insights 中的数据生成您自己的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6d429-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d429-105">这些 API 的详细信息将在 [Customer Insights API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)中列出。</span><span class="sxs-lookup"><span data-stu-id="6d429-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="6d429-106">其中包括有关操作、参数和响应的其他信息。</span><span class="sxs-lookup"><span data-stu-id="6d429-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="6d429-107">本文引导您访问 Customer Insights API，创建 Azure 应用注册，并帮助您开始使用可用的客户端库。</span><span class="sxs-lookup"><span data-stu-id="6d429-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="6d429-108">开始试用 Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="6d429-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="6d429-109">[登录](https://home.ci.ai.dynamics.com)到 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="6d429-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="6d429-110">如果您尚没有订阅，请[注册试用版的 Customer Insights](https://aka.ms/tryci)。</span><span class="sxs-lookup"><span data-stu-id="6d429-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="6d429-111">若要在您的 Customer Insights 环境上启用 API，请转到 **管理员** > **权限**。</span><span class="sxs-lookup"><span data-stu-id="6d429-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="6d429-112">您需要具有管理员权限才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6d429-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="6d429-113">转到 **API** 选项卡，然后选择 **启用** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6d429-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="6d429-114">启用 API 可为在 API 请求中使用的实例创建主要和辅助订阅密钥。</span><span class="sxs-lookup"><span data-stu-id="6d429-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="6d429-115">您可以通过在 **管理员** > **权限** > **API** 上选择 **再生成主要密钥** 或 **再生成辅助密钥** 来再生成密钥。</span><span class="sxs-lookup"><span data-stu-id="6d429-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="启用 Customer Insights API":::

1. <span data-ttu-id="6d429-117">选择 **浏览我们的 API** 以试用 API。</span><span class="sxs-lookup"><span data-stu-id="6d429-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="6d429-118">选择 API 操作并选择 **试用**。</span><span class="sxs-lookup"><span data-stu-id="6d429-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="6d429-119">在侧窗格中，将 **授权** 下拉菜单中的值设置为 **隐式**。</span><span class="sxs-lookup"><span data-stu-id="6d429-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="6d429-120">`Authorization` 标头将通过添加持有者令牌获得。</span><span class="sxs-lookup"><span data-stu-id="6d429-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="6d429-121">将自动填充您的订阅密钥。</span><span class="sxs-lookup"><span data-stu-id="6d429-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="6d429-122">可以选择添加所有必要的查询参数。</span><span class="sxs-lookup"><span data-stu-id="6d429-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="6d429-123">滚动到侧窗格底部并选择 **发送**。</span><span class="sxs-lookup"><span data-stu-id="6d429-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="6d429-124">HTTP 响应将立即显示在下方。</span><span class="sxs-lookup"><span data-stu-id="6d429-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="6d429-125">在 Azure 门户中创建新的应用注册</span><span class="sxs-lookup"><span data-stu-id="6d429-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="6d429-126">以下步骤帮助您开始使用委托的权限将 Customer Insights API 用于 Azure 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="6d429-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="6d429-127">首先，请确保已完成[入门部分](#get-started-trying-the-customer-insights-apis)。</span><span class="sxs-lookup"><span data-stu-id="6d429-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="6d429-128">使用可访问 Customer Insights 数据的帐户登录到 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="6d429-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="6d429-129">在左侧，选择 **应用注册**。</span><span class="sxs-lookup"><span data-stu-id="6d429-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="6d429-130">选择 **新注册**，提供应用程序名称并选择帐户类型。</span><span class="sxs-lookup"><span data-stu-id="6d429-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="6d429-131">可以选择添加重定向 URL。</span><span class="sxs-lookup"><span data-stu-id="6d429-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="6d429-132">http://localhost 足以在您的本地计算机上开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="6d429-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="6d429-133">在您的新应用注册上，转到 **API 权限**。</span><span class="sxs-lookup"><span data-stu-id="6d429-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="6d429-134">选择 **添加权限**，然后在侧窗格中选择 **Customer Insights**。</span><span class="sxs-lookup"><span data-stu-id="6d429-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="6d429-135">对于 **权限类型**，选择 **委托的权限**，然后选择 **user_impersonation** 权限。</span><span class="sxs-lookup"><span data-stu-id="6d429-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="6d429-136">选择 **添加权限**。</span><span class="sxs-lookup"><span data-stu-id="6d429-136">Select **Add permissions**.</span></span> <span data-ttu-id="6d429-137">如果您需要在无需用户登录的情况下访问 API，请查看[服务器到服务器应用程序权限](#server-to-server-application-permissions)部分。</span><span class="sxs-lookup"><span data-stu-id="6d429-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="6d429-138">选择 **对其授予管理员同意** 以完成应用注册。</span><span class="sxs-lookup"><span data-stu-id="6d429-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="6d429-139">您可以结合使用此应用注册的应用程序/客户端 ID 与 Microsoft 身份验证库 (MSAL)，获取持有者令牌以发送您的 API 请求。</span><span class="sxs-lookup"><span data-stu-id="6d429-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="6d429-140">有关 MSAL 的详细信息，请参阅 [Microsoft 身份验证库 (MSAL) 概述](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)。</span><span class="sxs-lookup"><span data-stu-id="6d429-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="6d429-141">有关 Azure 中应用注册的详细信息，请参阅[新的 Azure 门户应用注册体验](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide)。</span><span class="sxs-lookup"><span data-stu-id="6d429-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="6d429-142">有关使用 API 和我们的客户端库的信息，请参阅 [Customer Insights 客户端库](#customer-insights-client-libraries)。</span><span class="sxs-lookup"><span data-stu-id="6d429-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="6d429-143">服务器到服务器应用程序权限</span><span class="sxs-lookup"><span data-stu-id="6d429-143">Server-to-server application permissions</span></span>

<span data-ttu-id="6d429-144">[应用注册部分](#create-a-new-app-registration-in-the-azure-portal)概述了如何注册要求用户登录以进行身份验证的应用。</span><span class="sxs-lookup"><span data-stu-id="6d429-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="6d429-145">了解如何创建不需要用户交互即可在服务器上运行的应用注册。</span><span class="sxs-lookup"><span data-stu-id="6d429-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="6d429-146">在 Azure 门户中的应用注册上，转到 **API 权限**。</span><span class="sxs-lookup"><span data-stu-id="6d429-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="6d429-147">选择 **添加权限**，然后在侧窗格中选择 **Customer Insights**。</span><span class="sxs-lookup"><span data-stu-id="6d429-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="6d429-148">对于 **权限类型**，选择 **应用程序权限**，然后选择 **CustomerInsights.Api.All** 权限。</span><span class="sxs-lookup"><span data-stu-id="6d429-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="6d429-149">选择 **添加权限**。</span><span class="sxs-lookup"><span data-stu-id="6d429-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="6d429-150">若要对此应用程序权限授予管理员同意，您需要添加服务主体。</span><span class="sxs-lookup"><span data-stu-id="6d429-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="6d429-151">安装 Azure Active Directory (AD) PowerShell 模块：`Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="6d429-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="6d429-152">连接到您的 AD 帐户：`Connect-AzureAD -TenantId <your tenant id>`。</span><span class="sxs-lookup"><span data-stu-id="6d429-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="6d429-153">可以在 **概述** > **Azure Active Directory** 上找到您的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="6d429-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="6d429-154">运行以下命令以添加 Azure AD 服务主体：`New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"`。AppId 参数与 Customer Insights API 应用相关。</span><span class="sxs-lookup"><span data-stu-id="6d429-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="服务主体示例":::

1. <span data-ttu-id="6d429-156">对于您的应用注册，返回到 **API 权限**。</span><span class="sxs-lookup"><span data-stu-id="6d429-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="6d429-157">选择 **对其授予管理员同意** 以完成应用注册。</span><span class="sxs-lookup"><span data-stu-id="6d429-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="6d429-158">总之，我们必须在 Customer Insights 中添加应用注册的名称作为用户。</span><span class="sxs-lookup"><span data-stu-id="6d429-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="6d429-159">打开 Customer Insights，转到 **管理员** > **权限**，然后选择 **添加用户**。</span><span class="sxs-lookup"><span data-stu-id="6d429-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="6d429-160">搜索您的应用注册的名称，从搜索结果中选择它，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="6d429-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="6d429-161">Customer Insights 客户端库</span><span class="sxs-lookup"><span data-stu-id="6d429-161">Customer Insights client libraries</span></span>

<span data-ttu-id="6d429-162">本部分帮助您开始使用可用于 Customer Insights API 的客户端库。</span><span class="sxs-lookup"><span data-stu-id="6d429-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="6d429-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="6d429-163">C# NuGet</span></span>

<span data-ttu-id="6d429-164">了解如何开始使用 NuGet.org 中的 C# 客户端库。有关 NuGet 包的详细信息，请参阅 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)。</span><span class="sxs-lookup"><span data-stu-id="6d429-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="6d429-165">当前，此包针对的是 netstandard2.0 和 netcoreapp2.0 框架。</span><span class="sxs-lookup"><span data-stu-id="6d429-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="6d429-166">将 C# 客户端库添加到 C# 项目</span><span class="sxs-lookup"><span data-stu-id="6d429-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="6d429-167">在 Visual Studio 中，为您的项目打开 **NuGet 包管理器**。</span><span class="sxs-lookup"><span data-stu-id="6d429-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="6d429-168">搜索 **Microsoft.Dynamics.CustomerInsights.Api**。</span><span class="sxs-lookup"><span data-stu-id="6d429-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="6d429-169">选择 **安装** 以将包添加到项目。</span><span class="sxs-lookup"><span data-stu-id="6d429-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="6d429-170">或者，在 **NuGet 包管理器控制台** 中运行此命令：`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="6d429-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="将 NuGet 包添加到 Visual Studio 项目":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="6d429-172">使用 C# 客户端库</span><span class="sxs-lookup"><span data-stu-id="6d429-172">Use the C# client library</span></span>

1. <span data-ttu-id="6d429-173">使用 [Microsoft 身份验证库 (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) 以使用现有的 [Azure 应用注册](#create-a-new-app-registration-in-the-azure-portal)获取 `AccessToken`。</span><span class="sxs-lookup"><span data-stu-id="6d429-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="6d429-174">在成功进行身份验证并获取令牌后，从您的 [Customer Insights 环境](#get-started-trying-the-customer-insights-apis)中构建新的客户端或使用现有的 `HttpClient`，其中其他 **DefaultRequestHeaders "Authorization"** 设置为 **Bearer <access token>** 和 **Ocp-Apim-Subscription-Key** 设置为 **subscription key**。</span><span class="sxs-lookup"><span data-stu-id="6d429-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="6d429-175">根据需要重置 **授权** 标头。</span><span class="sxs-lookup"><span data-stu-id="6d429-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="6d429-176">例如，当令牌到期时。</span><span class="sxs-lookup"><span data-stu-id="6d429-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="6d429-177">将此 `HttpClient` 传递到 `CustomerInsights` 客户端的构造中。</span><span class="sxs-lookup"><span data-stu-id="6d429-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient 的示例":::

1. <span data-ttu-id="6d429-179">使用客户端调用“扩展方法”，例如 `GetAllInstancesAsync`。</span><span class="sxs-lookup"><span data-stu-id="6d429-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="6d429-180">如果首选访问基础 `Microsoft.Rest.HttpOperationResponse`，请使用“http 消息方法”，例如 `GetAllInstancesWithHttpMessagesAsync`。</span><span class="sxs-lookup"><span data-stu-id="6d429-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="6d429-181">响应可能为类型 `object`，因为该方法可以返回多个类型（例如 `IList<InstanceInfo>` 和 `ApiErrorResult`）。</span><span class="sxs-lookup"><span data-stu-id="6d429-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="6d429-182">若要检查返回类型，您可以针对该操作安全地将对象强制转换为在 [API 详细信息页面](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)上指定的响应类型。</span><span class="sxs-lookup"><span data-stu-id="6d429-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="6d429-183">如果需要有关请求的详细信息，请使用 **http 消息方法** 访问原始响应对象。</span><span class="sxs-lookup"><span data-stu-id="6d429-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]