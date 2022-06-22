---
title: Customer Insights 中的安全设置
description: 了解 Dynamics 365 Customer Insights 中的安全设置。
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947404"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights 中的安全设置

**安全** 页列出了用于配置用户权限和功能的选项，以帮助使 Dynamics 365 Customer Insights 更安全。 只有管理员才能访问此页面。

转到 **管理** > **安全** 以配置这些设置。

**安全** 页面包括以下选项卡：

- [用户](#users-tab)
- [API](#apis-tab)
- [专用链接](#private-links-tab)
- [密钥保管库](#key-vault-tab)
- [使用客户密码箱安全地访问客户数据（预览）](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>“用户”选项卡

对 Customer Insights 的访问仅限于您组织中由管理员添加到应用程序的用户。**用户** 选项卡可让您管理用户访问权限及其权限。 有关详细信息，请参阅[用户权限](permissions.md)。

## <a name="apis-tab"></a>“API”选项卡

查看和管理密钥以将 [Customer Insights API](apis.md) 与您的环境数据配合使用。

您可以通过选择 **重新生成主密钥** 或 **重新生成辅助密钥** 来创建新的主密钥和辅助密钥。 

若要阻止 API 访问环境，请选择 **禁用**。 如果禁用了 API，您可以选择 **启用** 以再次授予访问权限。

## <a name="private-links-tab"></a>专用链接选项卡

[Azure 专用链接](/azure/private-link/private-link-overview)让 Customer Insights 通过虚拟网络中的专用终结点连接到您的 Azure Data Lake Storage 帐户。 对于不向公共 Internet 公开的存储帐户中的数据，专用链接启用与该受限网络的连接。

> [!IMPORTANT]
> 设置专用链接连接的最低角色要求：
>
> - Customer Insights：管理员
> - Azure 内置角色：[存储帐户参与者](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - 自定义 Azure 角色的权限：[Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

在 Customer Insights 中设置专用链接是一个两步过程。 首先，您从 Customer Insights 中的 **管理员** > **安全性** > **专用链接** 开始创建专用链接。 **添加专用链接** 窗格将列出您有权查看的租户中的存储帐户。 选择存储帐户并提供同意以创建专用链接。

接下来，您需要在 Data Lake Storage 帐户端批准专用链接。 打开屏幕上显示的链接批准新的专用链接。

## <a name="key-vault-tab"></a>“密钥保管库”选项卡

使用 **密钥保管库** 选项卡，可以链接和管理您自己的环境 [Azure Key Vault](/azure/key-vault/general/basic-concepts)。
专用密钥保管库可用于在组织的合规边界内暂存和使用密钥。 Customer Insights 可以使用 Azure Key Vault 中的密钥[设置与第三方系统的连接](connections.md)。

有关详细信息，请参阅[引入您自己的 Azure Key Vault](use-azure-key-vault.md)。

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>使用客户密码箱安全地访问客户数据（预览）

Customer Insights 现在使用 Power Platform 客户密码箱功能。 客户密码箱提供了一个界面来审查和批准（或拒绝）数据访问请求。 当需要对客户数据进行数据访问以解决支持案例时，会出现这些请求。 要使用此功能，Customer Insights 必须与租户中的 Microsoft Dataverse 环境之间有现有连接。

有关客户密码箱的详细信息，请参阅 Power Platform 客户密码箱[摘要](/power-platform/admin/about-lockbox#summary)。 本文还介绍了启用客户密码箱的[工作流](/power-platform/admin/about-lockbox#workflow)和所需的[设置](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)。

> [!IMPORTANT]
> Power Platform 或 Power Platform 管理员的全局管理员可以批准为 Customer Insights 发出的客户密码箱请求。

[!INCLUDE [footer-include](includes/footer-banner.md)]
