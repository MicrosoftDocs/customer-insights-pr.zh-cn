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
# <a name="work-with-customer-insights-apis"></a>使用 Customer Insights API

Dynamics 365 Customer Insights 提供 API，用于基于 Customer Insights 中的数据生成您自己的应用程序。

> [!IMPORTANT]
> 这些 API 的详细信息将在 [Customer Insights API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)中列出。 其中包括有关操作、参数和响应的其他信息。

本文引导您访问 Customer Insights API，创建 Azure 应用注册，并帮助您开始使用可用的客户端库。

## <a name="get-started-trying-the-customer-insights-apis"></a>开始试用 Customer Insights API

1. [登录](https://home.ci.ai.dynamics.com)到 Customer Insights。 如果您尚没有订阅，请[注册试用版的 Customer Insights](https://aka.ms/tryci)。

1. 若要在您的 Customer Insights 环境上启用 API，请转到 **管理员** > **权限**。 您需要具有管理员权限才能执行此操作。

1. 转到 **API** 选项卡，然后选择 **启用** 按钮。    
   启用 API 可为在 API 请求中使用的实例创建主要和辅助订阅密钥。 您可以通过在 **管理员** > **权限** > **API** 上选择 **再生成主要密钥** 或 **再生成辅助密钥** 来再生成密钥。

   :::image type="content" source="media/enable-apis.gif" alt-text="启用 Customer Insights API":::

1. 选择 **浏览我们的 API** 以试用 API。

1. 选择 API 操作并选择 **试用**。

1. 在侧窗格中，将 **授权** 下拉菜单中的值设置为 **隐式**。 `Authorization` 标头将通过添加持有者令牌获得。 将自动填充您的订阅密钥。
  
1. 可以选择添加所有必要的查询参数。

1. 滚动到侧窗格底部并选择 **发送**。

HTTP 响应将立即显示在下方。

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>在 Azure 门户中创建新的应用注册

以下步骤帮助您开始使用委托的权限将 Customer Insights API 用于 Azure 应用程序中。 首先，请确保已完成[入门部分](#get-started-trying-the-customer-insights-apis)。

1. 使用可访问 Customer Insights 数据的帐户登录到 [Azure 门户](https://portal.azure.com)。

1. 在左侧，选择 **应用注册**。

1. 选择 **新注册**，提供应用程序名称并选择帐户类型。
   可以选择添加重定向 URL。 http://localhost 足以在您的本地计算机上开发应用程序。

1. 在您的新应用注册上，转到 **API 权限**。

1. 选择 **添加权限**，然后在侧窗格中选择 **Customer Insights**。

1. 对于 **权限类型**，选择 **委托的权限**，然后选择 **user_impersonation** 权限。

1. 选择 **添加权限**。 如果您需要在无需用户登录的情况下访问 API，请查看[服务器到服务器应用程序权限](#server-to-server-application-permissions)部分。

1. 选择 **对其授予管理员同意** 以完成应用注册。

您可以结合使用此应用注册的应用程序/客户端 ID 与 Microsoft 身份验证库 (MSAL)，获取持有者令牌以发送您的 API 请求。

有关 MSAL 的详细信息，请参阅 [Microsoft 身份验证库 (MSAL) 概述](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)。

有关 Azure 中应用注册的详细信息，请参阅[新的 Azure 门户应用注册体验](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide)。

有关使用 API 和我们的客户端库的信息，请参阅 [Customer Insights 客户端库](#customer-insights-client-libraries)。

### <a name="server-to-server-application-permissions"></a>服务器到服务器应用程序权限

[应用注册部分](#create-a-new-app-registration-in-the-azure-portal)概述了如何注册要求用户登录以进行身份验证的应用。 了解如何创建不需要用户交互即可在服务器上运行的应用注册。

1. 在 Azure 门户中的应用注册上，转到 **API 权限**。

1. 选择 **添加权限**，然后在侧窗格中选择 **Customer Insights**。

1. 对于 **权限类型**，选择 **应用程序权限**，然后选择 **CustomerInsights.Api.All** 权限。

1. 选择 **添加权限**。

1. 若要对此应用程序权限授予管理员同意，您需要添加服务主体。

   1. 安装 Azure Active Directory (AD) PowerShell 模块：`Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. 连接到您的 AD 帐户：`Connect-AzureAD -TenantId <your tenant id>`。 可以在 **概述** > **Azure Active Directory** 上找到您的租户 ID。
   1. 运行以下命令以添加 Azure AD 服务主体：`New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"`。AppId 参数与 Customer Insights API 应用相关。

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="服务主体示例":::

1. 对于您的应用注册，返回到 **API 权限**。

1. 选择 **对其授予管理员同意** 以完成应用注册。

1. 总之，我们必须在 Customer Insights 中添加应用注册的名称作为用户。    
   打开 Customer Insights，转到 **管理员** > **权限**，然后选择 **添加用户**。

1. 搜索您的应用注册的名称，从搜索结果中选择它，然后选择 **保存**。

## <a name="customer-insights-client-libraries"></a>Customer Insights 客户端库

本部分帮助您开始使用可用于 Customer Insights API 的客户端库。

### <a name="c-nuget"></a>C# NuGet

了解如何开始使用 NuGet.org 中的 C# 客户端库。有关 NuGet 包的详细信息，请参阅 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)。 当前，此包针对的是 netstandard2.0 和 netcoreapp2.0 框架。

#### <a name="add-the-c-client-library-to-a-c-project"></a>将 C# 客户端库添加到 C# 项目

1. 在 Visual Studio 中，为您的项目打开 **NuGet 包管理器**。

1. 搜索 **Microsoft.Dynamics.CustomerInsights.Api**。

1. 选择 **安装** 以将包添加到项目。
   或者，在 **NuGet 包管理器控制台** 中运行此命令：`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="将 NuGet 包添加到 Visual Studio 项目":::

#### <a name="use-the-c-client-library"></a>使用 C# 客户端库

1. 使用 [Microsoft 身份验证库 (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) 以使用现有的 [Azure 应用注册](#create-a-new-app-registration-in-the-azure-portal)获取 `AccessToken`。

1. 在成功进行身份验证并获取令牌后，从您的 [Customer Insights 环境](#get-started-trying-the-customer-insights-apis)中构建新的客户端或使用现有的 `HttpClient`，其中其他 **DefaultRequestHeaders "Authorization"** 设置为 **Bearer <access token>** 和 **Ocp-Apim-Subscription-Key** 设置为 **subscription key**。    
   根据需要重置 **授权** 标头。 例如，当令牌到期时。

1. 将此 `HttpClient` 传递到 `CustomerInsights` 客户端的构造中。

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient 的示例":::

1. 使用客户端调用“扩展方法”，例如 `GetAllInstancesAsync`。 如果首选访问基础 `Microsoft.Rest.HttpOperationResponse`，请使用“http 消息方法”，例如 `GetAllInstancesWithHttpMessagesAsync`。

1. 响应可能为类型 `object`，因为该方法可以返回多个类型（例如 `IList<InstanceInfo>` 和 `ApiErrorResult`）。 若要检查返回类型，您可以针对该操作安全地将对象强制转换为在 [API 详细信息页面](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)上指定的响应类型。    
   如果需要有关请求的详细信息，请使用 **http 消息方法** 访问原始响应对象。


[!INCLUDE[footer-include](../includes/footer-banner.md)]