---
title: 使用 API
description: 使用 API 并了解限制。
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304731"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="7b46a-103">使用 Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="7b46a-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="7b46a-104">Dynamics 365 Customer Insights 提供 API 以基于 Customer Insights 中的数据生成您自己的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b46a-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b46a-105">这些 API 的详细信息将在 [Customer Insights API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)中列出。</span><span class="sxs-lookup"><span data-stu-id="7b46a-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="7b46a-106">其中包括有关操作、参数和响应的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7b46a-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="7b46a-107">本文介绍了如何访问 Customer Insights API，如何创建 Azure 应用注册以及如何开始使用可用的客户端库。</span><span class="sxs-lookup"><span data-stu-id="7b46a-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="7b46a-108">开始试用 Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="7b46a-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="7b46a-109">[登录](https://home.ci.ai.dynamics.com)到 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="7b46a-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="7b46a-110">如果您尚没有订阅，请[注册试用版的 Customer Insights](https://aka.ms/tryci)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="7b46a-111">若要在您的 Customer Insights 环境上启用 API，请转到 **管理员** > **权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="7b46a-112">您需要具有管理员权限才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b46a-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="7b46a-113">转到 **API** 选项卡，然后选择 **启用** 按钮。</span><span class="sxs-lookup"><span data-stu-id="7b46a-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="7b46a-114">启用 API 可为在 API 请求中使用的实例创建主要和辅助订阅密钥。</span><span class="sxs-lookup"><span data-stu-id="7b46a-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="7b46a-115">您可以通过在 **管理员** > **权限** > **API** 上选择 **再生成主要密钥** 或 **再生成辅助密钥** 来再生成密钥。</span><span class="sxs-lookup"><span data-stu-id="7b46a-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="启用 Customer Insights API":::

1. <span data-ttu-id="7b46a-117">选择 **浏览我们的 API** 以[试用 API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="7b46a-118">选择 API 操作并选择 **试用**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="7b46a-119">在侧边窗格中，将 **授权** 下拉菜单中的值设置为 **隐式**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="7b46a-120">`Authorization` 标头中将添加持有者令牌。</span><span class="sxs-lookup"><span data-stu-id="7b46a-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="7b46a-121">将自动填充您的订阅密钥。</span><span class="sxs-lookup"><span data-stu-id="7b46a-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="7b46a-122">可以选择添加所有必要的查询参数。</span><span class="sxs-lookup"><span data-stu-id="7b46a-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="7b46a-123">滚动到侧窗格底部并选择 **发送**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="7b46a-124">HTTP 响应将立即显示在下方。</span><span class="sxs-lookup"><span data-stu-id="7b46a-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="如何测试 API。":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="7b46a-126">在 Azure 门户中创建新的应用注册</span><span class="sxs-lookup"><span data-stu-id="7b46a-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="7b46a-127">这些步骤帮助您使用委托的权限开始在 Azure 应用程序中使用 Customer Insights API。</span><span class="sxs-lookup"><span data-stu-id="7b46a-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="7b46a-128">首先，确保完成[入门部分](#get-started-trying-the-customer-insights-apis)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="7b46a-129">使用可访问 Customer Insights 数据的帐户登录到 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="7b46a-130">在左侧，选择 **应用注册**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="7b46a-131">选择 **新注册**，提供应用程序名称并选择帐户类型。</span><span class="sxs-lookup"><span data-stu-id="7b46a-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="7b46a-132">可以选择添加重定向 URL。</span><span class="sxs-lookup"><span data-stu-id="7b46a-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="7b46a-133">http://localhost 足以在您的本地计算机上开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b46a-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="7b46a-134">在您的新应用注册上，转到 **API 权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="如何在应用注册中设置 API 权限。":::

1. <span data-ttu-id="7b46a-136">选择 **添加权限**，然后在侧窗格中选择 **Customer Insights**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="7b46a-137">对于 **权限类型**，选择 **委托的权限**，然后选择 **user_impersonation** 权限。</span><span class="sxs-lookup"><span data-stu-id="7b46a-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="7b46a-138">选择 **添加权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-138">Select **Add permissions**.</span></span> <span data-ttu-id="7b46a-139">如果您需要在无需用户登录的情况下访问 API，请查看[服务器到服务器应用程序权限](#server-to-server-application-permissions)部分。</span><span class="sxs-lookup"><span data-stu-id="7b46a-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="7b46a-140">选择 **对其授予管理员同意** 以完成应用注册。</span><span class="sxs-lookup"><span data-stu-id="7b46a-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="7b46a-141">您可以结合使用此应用注册的应用程序/客户端 ID 与 Microsoft 身份验证库 (MSAL)，获取持有者令牌以发送您的 API 请求。</span><span class="sxs-lookup"><span data-stu-id="7b46a-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="如何授权管理员同意。":::

<span data-ttu-id="7b46a-143">有关 MSAL 的详细信息，请参阅 [Microsoft 身份验证库 (MSAL) 概述](/azure/active-directory/develop/msal-overview)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="7b46a-144">有关 Azure 中的应用注册的详细信息，请参阅[注册应用程序](/azure/active-directory/develop/quickstart-register-app.md#register-an-application)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="7b46a-145">有关在客户端库中使用 API 的信息，请参阅 [Customer Insights 客户端库](#customer-insights-client-libraries)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="7b46a-146">服务器到服务器应用程序权限</span><span class="sxs-lookup"><span data-stu-id="7b46a-146">Server-to-server application permissions</span></span>

<span data-ttu-id="7b46a-147">[应用注册部分](#create-a-new-app-registration-in-the-azure-portal)概述了如何注册要求用户登录以进行身份验证的应用。</span><span class="sxs-lookup"><span data-stu-id="7b46a-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="7b46a-148">了解如何创建不需要用户交互即可在服务器上运行的应用注册。</span><span class="sxs-lookup"><span data-stu-id="7b46a-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="7b46a-149">在 Azure 门户中的应用注册上，转到 **API 权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="7b46a-150">选择 **添加权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="7b46a-151">选择 **我的组织使用的 API** 选项卡，然后从列表中选择 **适用于 Customer Insights 的 Dynamics 365 KPI**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="7b46a-152">对于 **权限类型**，选择 **应用程序权限**，然后选择 **CustomerInsights.Api.All** 权限。</span><span class="sxs-lookup"><span data-stu-id="7b46a-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="7b46a-153">选择 **添加权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="7b46a-154">对于您的应用注册，返回到 **API 权限**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="7b46a-155">选择 **对其授予管理员同意** 以完成应用注册。</span><span class="sxs-lookup"><span data-stu-id="7b46a-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="如何授权管理员同意。":::

1. <span data-ttu-id="7b46a-157">总之，我们必须在 Customer Insights 中添加应用注册的名称作为用户。</span><span class="sxs-lookup"><span data-stu-id="7b46a-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="7b46a-158">打开 Customer Insights，转到 **管理员** > **权限**，然后选择 **添加用户**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="7b46a-159">搜索您的应用注册的名称，从搜索结果中选择它，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="7b46a-160">Customer Insights 客户端库</span><span class="sxs-lookup"><span data-stu-id="7b46a-160">Customer Insights client libraries</span></span>

<span data-ttu-id="7b46a-161">本部分帮助您开始使用可用于 Customer Insights API 的客户端库。</span><span class="sxs-lookup"><span data-stu-id="7b46a-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="7b46a-162">所有库源代码和示例应用程序都可以在 [Customer Insights GitHub 页](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)上找到。</span><span class="sxs-lookup"><span data-stu-id="7b46a-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="7b46a-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="7b46a-163">C# NuGet</span></span>

<span data-ttu-id="7b46a-164">了解如何开始使用 NuGet.org 中的 C# 客户端库。有关 NuGet 包的详细信息，请参阅 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)。</span><span class="sxs-lookup"><span data-stu-id="7b46a-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="7b46a-165">当前，此包针对的是 netstandard2.0 和 netcoreapp2.0 框架。</span><span class="sxs-lookup"><span data-stu-id="7b46a-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="7b46a-166">将 C# 客户端库添加到 C# 项目</span><span class="sxs-lookup"><span data-stu-id="7b46a-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="7b46a-167">在 Visual Studio 中，为您的项目打开 **NuGet 包管理器**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="7b46a-168">搜索 **Microsoft.Dynamics.CustomerInsights.Api**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="7b46a-169">选择 **安装** 以将包添加到项目。</span><span class="sxs-lookup"><span data-stu-id="7b46a-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="7b46a-170">或者，在 **NuGet 包管理器控制台** 中运行此命令：`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="7b46a-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="将 NuGet 包添加到 Visual Studio 项目":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="7b46a-172">使用 C# 客户端库</span><span class="sxs-lookup"><span data-stu-id="7b46a-172">Use the C# client library</span></span>

1. <span data-ttu-id="7b46a-173">使用 [Microsoft 身份验证库 (MSAL)](/azure/active-directory/develop/msal-overview) 以使用现有的 [Azure 应用注册](#create-a-new-app-registration-in-the-azure-portal)获取 `AccessToken`。</span><span class="sxs-lookup"><span data-stu-id="7b46a-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="7b46a-174">在成功进行身份验证并获取令牌后，从您的 [Customer Insights 环境](#get-started-trying-the-customer-insights-apis)中构建新的客户端或使用现有的 `HttpClient`，其中其他 **DefaultRequestHeaders "Authorization"** 设置为 **Bearer <access token>** 和 **Ocp-Apim-Subscription-Key** 设置为 **subscription key**。</span><span class="sxs-lookup"><span data-stu-id="7b46a-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="7b46a-175">根据需要重置 **授权** 标头。</span><span class="sxs-lookup"><span data-stu-id="7b46a-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="7b46a-176">例如，当令牌到期时。</span><span class="sxs-lookup"><span data-stu-id="7b46a-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="7b46a-177">将此 `HttpClient` 传递到 `CustomerInsights` 客户端的构造中。</span><span class="sxs-lookup"><span data-stu-id="7b46a-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient 的示例":::

1. <span data-ttu-id="7b46a-179">使用客户端调用“扩展方法”，例如 `GetAllInstancesAsync`。</span><span class="sxs-lookup"><span data-stu-id="7b46a-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="7b46a-180">如果首选访问基础 `Microsoft.Rest.HttpOperationResponse`，请使用“http 消息方法”，例如 `GetAllInstancesWithHttpMessagesAsync`。</span><span class="sxs-lookup"><span data-stu-id="7b46a-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="7b46a-181">响应可能为类型 `object`，因为该方法可以返回多个类型（例如 `IList<InstanceInfo>` 和 `ApiErrorResult`）。</span><span class="sxs-lookup"><span data-stu-id="7b46a-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="7b46a-182">若要检查返回类型，您可以针对该操作安全地将对象强制转换为在 [API 详细信息页面](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)上指定的响应类型。</span><span class="sxs-lookup"><span data-stu-id="7b46a-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="7b46a-183">如果需要有关请求的详细信息，请使用 **http 消息方法** 访问原始响应对象。</span><span class="sxs-lookup"><span data-stu-id="7b46a-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="7b46a-184">NodeJS 程序包</span><span class="sxs-lookup"><span data-stu-id="7b46a-184">NodeJS package</span></span>

<span data-ttu-id="7b46a-185">使用通过 NPM 提供的 NodeJS 客户端库：https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="7b46a-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="7b46a-186">Python 程序包</span><span class="sxs-lookup"><span data-stu-id="7b46a-186">Python package</span></span>

<span data-ttu-id="7b46a-187">使用通过 PyPi 提供的 Python 客户端库：https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="7b46a-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
