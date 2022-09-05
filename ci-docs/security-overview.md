---
title: 配置安全性设置
description: 了解 Dynamics 365 Customer Insights 中的安全设置。
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387238"
---
# <a name="configure-security-settings"></a>配置安全性设置

管理 API 密钥、访问客户数据以及设置 Azure 专用链接。

## <a name="manage-api-keys"></a>管理 API 密钥

查看和管理密钥以将 [Customer Insights API](apis.md) 与您环境中的数据配合使用。

1. 转到 **管理员** > **安全**，然后选择 **API** 选项卡。

1. 如果尚未设置对环境的 API 访问，请选择 **启用**。 或者，要阻止 API 访问环境，选择 **禁用** 并确认。

1. 管理主要和次要 API 密钥：

   1. 要显示主要或次要 API 密钥，选择 **显示** 符号。

   1. 要复制主要或次要 API 密钥，选择 **复制** 符号。

   1. 要创建新的主要或次要 API 密钥，选择 **重新生成主要密钥** 或 **重新生成次要密钥**。

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>使用客户密码箱安全地访问客户数据（预览）

Customer Insights 使用 Power Platform 客户密码箱功能。 客户密码箱提供了一个界面来审查和批准（或拒绝）数据访问请求。 当需要对客户数据进行数据访问以解决支持案例时，会出现这些请求。 要使用此功能，Customer Insights 必须与租户中的 Microsoft Dataverse 环境之间有现有连接。

有关客户密码箱的详细信息，请参阅 Power Platform 客户密码箱[摘要](/power-platform/admin/about-lockbox#summary)。 本文还介绍了启用客户密码箱的[工作流](/power-platform/admin/about-lockbox#workflow)和所需的[设置](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)。

> [!IMPORTANT]
> Power Platform 或 Power Platform 管理员的全局管理员可以批准为 Customer Insights 发出的客户密码箱请求。

## <a name="set-up-an-azure-private-link"></a>设置 Azure 专用链接

[Azure 专用链接](/azure/private-link/private-link-overview)让 Customer Insights 通过虚拟网络中的专用终结点连接到您的 Azure Data Lake Storage 帐户。 对于不向公共 Internet 公开的存储帐户中的数据，专用链接启用与该受限网络的连接。

> [!IMPORTANT]
> 设置专用链接连接的最低角色要求：
>
> - Customer Insights：管理员
> - Azure 内置角色：[存储帐户参与者](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - 自定义 Azure 角色的权限：[Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. 在 Customer Insights 中，转到 **管理** > **安全性**，然后选择 **专用链接** 选项卡。

1. 选择 **添加专用链接**。

   **添加专用链接** 窗格将列出您有权查看的租户中的存储帐户。

1. 选择订阅、资源组和存储帐户。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存**。

1. 转到您的 Data Lake Storage 帐户，打开屏幕上显示的链接。

1. 批准专用链接。


[!INCLUDE [footer-include](includes/footer-banner.md)]
