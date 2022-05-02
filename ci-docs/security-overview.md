---
title: Dynamics 365 Customer Insights 中的安全设置
description: 了解 Dynamics 365 Customer Insights 中的安全设置。
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653702"
---
# <a name="security-overview-page"></a>安全概览页面

**安全** 页列出了用于配置用户权限和功能的选项，以帮助使 Dynamics 365 Customer Insights 更安全。 只有管理员才能访问此页面。 

转到 **管理** > **安全** 以配置这些设置。

**安全** 页面包括以下选项卡：
- [用户](#users-tab)
- [API](#apis-tab)
- [密钥保管库](#key-vault-tab)

## <a name="users-tab"></a>“用户”选项卡

对 Customer Insights 的访问仅限于您组织中由管理员添加到应用程序的用户。**用户** 选项卡可让您管理用户访问权限及其权限。 有关详细信息，请参阅[用户权限](permissions.md)。

## <a name="apis-tab"></a>“API”选项卡

查看和管理密钥以将 [Customer Insights API](apis.md) 与您的环境数据配合使用。

您可以通过选择 **重新生成主密钥** 或 **重新生成辅助密钥** 来创建新的主密钥和辅助密钥。 

若要阻止 API 访问环境，请选择 **禁用**。 如果禁用了 API，您可以选择 **启用** 以再次授予访问权限。

## <a name="key-vault-tab"></a>“密钥保管库”选项卡

使用 **密钥保管库** 选项卡，可以链接和管理您自己的环境 [Azure Key Vault](/azure/key-vault/general/basic-concepts)。
专用密钥保管库可用于在组织的合规边界内暂存和使用密钥。 Customer Insights 可以使用 Azure Key Vault 中的密钥[设置与第三方系统的连接](connections.md)。

有关详细信息，请参阅[引入您自己的 Azure Key Vault](use-azure-key-vault.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]
