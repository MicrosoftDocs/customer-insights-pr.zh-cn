---
title: 使用 Customer Insights API
description: 使用 API 并了解限制。
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387329"
---
# <a name="work-with-customer-insights-apis"></a>使用 Customer Insights API

Dynamics 365 Customer Insights 提供 API 以基于 Customer Insights 中的数据生成您自己的应用程序。

> [!IMPORTANT]
> 这些 API 的详细信息将在 [Customer Insights API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)中列出。 其中包括有关操作、参数和响应的其他信息。

试用 Customer Insights API、创建 Azure 应用注册以及开始使用客户端库。

## <a name="get-started-trying-the-customer-insights-apis"></a>开始试用 Customer Insights API

启用 Customer Insights API 并试用。Customer Insights 管理员必须启用对 Customer Insights 的 API 访问。 启用访问后，任何用户都可以通过订阅密钥使用 API。

1. [登录](https://home.ci.ai.dynamics.com)到 Customer Insights。 如果您尚没有订阅，请[注册试用版的 Customer Insights](https://aka.ms/tryci)。

1. 转到 **管理员** > **安全**，然后选择 **API** 选项卡。

1. 如果尚未设置对环境的 API 访问，请选择 **启用**。

   启用 API 可为在 API 请求中使用的实例创建主要和辅助订阅密钥。 要重新生成密钥，在 **API** 选项卡上选择 **重新生成主密钥** 或 **重新生成辅助密钥**。

1. 选择 [**浏览我们的 API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) 试用 API。

1. 搜索并选择一个 API 操作，然后选择 **试用**。

   :::image type="content" source="media/try-api.png" alt-text="如何测试 API。":::

1. 在侧边窗格中，将 **授权** 下拉菜单中的值设置为 **隐式**。 `Authorization` 标头中将添加持有者令牌。 将自动填充您的订阅密钥。
  
1. 可以选择添加所有必要的查询参数。

1. 滚动到侧窗格底部并选择 **发送**。

   HTTP 响应显示在窗格底部。

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>在 Azure 门户中创建新的应用注册

创建一个新的[应用注册](/graph/auth-register-app-v2)来使用委托的权限在 Azure 应用程序中使用 Customer Insights API。

1. 完成[“入门”一节](#get-started-trying-the-customer-insights-apis)。

1. 使用可访问 Customer Insights 数据的帐户登录到 [Azure 门户](https://portal.azure.com)。

1. 进行搜索，然后选择 **应用注册**。

1. 选择 **新注册**，提供应用程序名称并选择帐户类型。

   可以选择添加重定向 URL。 http://localhost 足以在您的本地计算机上开发应用程序。

1. 选择 **注册**。

1. 在您的新应用注册上，转到 **API 权限**。

1. 选择 **添加权限**，然后在侧窗格中选择 **Dynamics 365 AI for Customer Insights**。

1. 对于 **权限类型**，选择 **委托的权限**，然后选择 **user_impersonation** 权限。

1. 选择 **添加权限**。

1. 选择 **对其授予管理员同意** 以完成应用注册。

1. 要在无需用户登录的情况下访问 API，请转到[服务器到服务器应用程序权限](#server-to-server-application-permissions)。

您可以结合使用此应用注册的应用程序/客户端 ID 与 [Microsoft 身份验证库 (MSAL)](/azure/active-directory/develop/msal-overview)，获取持有者令牌以发送您的 API 请求。

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

有关在客户端库中使用 API 的信息，请参阅 [Customer Insights 客户端库](#customer-insights-client-libraries)。

### <a name="server-to-server-application-permissions"></a>服务器到服务器应用程序权限

创建不需要用户交互并且可在服务器上运行的应用注册。

1. 在 Azure 门户中的应用注册上，转到 **API 权限**。

1. 选择 **添加权限**。

1. 选择 **我的组织使用的 API** 选项卡，然后从列表中选择 **适用于 Customer Insights 的 Dynamics 365 KPI**。

1. 对于 **权限类型**，选择 **应用程序权限**，然后选择 **CustomerInsights.Api.All** 权限。

1. 选择 **添加权限**。

1. 对于您的应用注册，返回到 **API 权限**。

1. 选择 **对其授予管理员同意** 以完成应用注册。

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. 在 Customer Insights 中作为用户添加应用注册的名称。

   1. 打开 Customer Insights，转到 **管理** > **安全性** 并选择 **添加用户**。

   1. 搜索您的应用注册的名称，从搜索结果中选择它，然后选择 **保存**。

## <a name="sample-queries"></a>示例查询

有关使用 API 的 OData 示例查询的简短列表，请参阅[OData 查询示例](odata-examples.md)。

## <a name="customer-insights-client-libraries"></a>Customer Insights 客户端库

开始使用可用于 Customer Insights API 的客户端库。 所有库源代码和示例应用程序都可以在 [Customer Insights GitHub 页](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)上找到。

### <a name="c-nuget"></a>C# NuGet

使用 NuGet.org 中的 C# 客户端库。当前，此包针对的是 netstandard2.0 和 netcoreapp2.0 框架。 有关 NuGet 包的更多信息，请参阅 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)。

#### <a name="add-the-c-client-library-to-a-c-project"></a>将 C# 客户端库添加到 C# 项目

1. 在 Visual Studio 中，为您的项目打开 **NuGet 包管理器**。

1. 搜索 **Microsoft.Dynamics.CustomerInsights.Api**。

1. 选择 **安装** 以将包添加到项目。

   或者，在 **NuGet 包管理器控制台** 中运行此命令：`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>使用 C# 客户端库

1. 使用 [Microsoft 身份验证库 (MSAL)](/azure/active-directory/develop/msal-overview) 以使用现有的 [Azure 应用注册](#create-a-new-app-registration-in-the-azure-portal)获取 `AccessToken`。

1. 成功验证并获取令牌后，构建一个新的或使用现有的 `HttpClient`，并将 **DefaultRequestHeaders 授权** 设置为 **持有者访问令牌**，将 **Ocp-Apim-Subscription-Key** 设置为 [Customer Insights 环境中的 **订阅密钥**](#get-started-trying-the-customer-insights-apis)。   

   根据需要重置 **授权** 标头。 例如，当令牌到期时。

1. 将此 `HttpClient` 传递到 `CustomerInsights` 客户端的构造中。

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. 使用客户端调用“扩展方法”，例如 `GetAllInstancesAsync`。 如果首选访问基础 `Microsoft.Rest.HttpOperationResponse`，请使用“http 消息方法”，例如 `GetAllInstancesWithHttpMessagesAsync`。

1. 响应可能是 `object` 类型，因为该方法可以返回多个类型（例如 `IList<InstanceInfo>` 和 `ApiErrorResult`）。 要检查返回类型，可以针对该操作使用 [API 详细信息页](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)上指定的响应类型中的对象。

   如果需要有关请求的详细信息，请使用 **http 消息方法** 访问原始响应对象。

### <a name="nodejs-package"></a>NodeJS 程序包

使用通过 NPM 提供的 NodeJS 客户端库：https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python 程序包

使用通过 PyPi 提供的 Python 客户端库：https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
