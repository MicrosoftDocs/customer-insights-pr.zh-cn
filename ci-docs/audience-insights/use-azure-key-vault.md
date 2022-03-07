---
title: 引入您自己的 Azure 密钥保管库来管理密钥
description: 了解如何将 Customer Insights 配置为使用您自己的 Azure 密钥保管库。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606042"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>引入您自己的 Azure 密钥保管库（预览）

将专用的 [Azure 密钥保管库](/azure/key-vault/general/basic-concepts)链接到访问群体见解环境可帮助组织满足合规要求。
专用密钥保管库可用于在组织的合规边界内暂存和使用密钥。 访问群体见解可以使用 Azure 密钥保管库中的密钥[设置与第三方系统的连接](connections.md)。

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>将密钥保管库链接到访问群体见解环境

### <a name="prerequisites"></a>先决条件

要在访问群体见解中配置密钥保管库，必须满足以下先决条件：

- 您有有效的 Azure 订阅。

- 您在访问群体见解中具有[管理员](permissions.md#administrator)角色。 详细了解[访问群体见解中的用户权限](permissions.md#assign-roles-and-permissions)。

- 您对密钥保管库或密钥保管库所属的资源组具有[参与者](/azure/role-based-access-control/built-in-roles#contributor)和[用户访问管理员](/azure/role-based-access-control/built-in-roles#user-access-administrator)角色。 有关详细信息，请转到[使用 Azure 门户添加或删除 Azure 角色分配](/azure/role-based-access-control/role-assignments-portal)。 如果您没有密钥保管库的用户访问管理员角色，则必须单独为 Dynamics 365 Customer Insights 的 Azure 服务主体设置基于角色的访问控制权限。 请按照步骤为应链接的密钥保管库[使用 Azure 服务主体](connect-service-principal.md)。

- 密钥保管库必须 **禁用** 密钥保管库防火墙。

- 密钥保管库与访问群体见解环境位于同一 [Azure 位置](https://azure.microsoft.com/global-infrastructure/geographies/#overview)。 访问群体见解中环境的区域在 **管理员** > **系统** > **关于** > **区域** 下列出。

### <a name="link-a-key-vault-to-the-environment"></a>将密钥保管库链接到环境

1. 转到 **管理员** > **系统**，然后选择 **安全** 选项卡。
1. 在 **密钥保管库** 磁贴上，选择 **设置**。
1. 选择 **订阅**。
1. 从 **密钥保管库** 下拉列表中选择一个密钥保管库。 如果显示的密钥保管库过多，选择一个资源组来限制搜索结果。
1. 接受 **数据隐私声明与合规** 声明。
1. 选择 **保存**。

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="在访问群体见解中设置链接的密钥保管库的步骤。":::

**密钥保管库** 磁贴现在显示链接的密钥保管库名称、资源组和订阅。 它已经可以在连接设置中使用。
有关将密钥保管库的哪些权限授予访问群体见解的详细信息，请转到本文后面的[授予访问群体见解的密钥保管库的权限](#permissions-granted-on-the-key-vault-to-audience-insights)。

## <a name="use-the-key-vault-in-the-connection-setup"></a>在连接设置中使用密钥保管库

在[设置与第三方系统的连接](connections.md)时，可以使用来自链接的密钥保管库的密钥配置连接。

1. 转到 **管理员** > **连接**。
1. 选择 **添加连接**。
1. 对于支持的连接类型，如果您链接了密钥保管库，**使用密钥保管库** 切换将可用。
1. 您可以选择指向密钥保管库中的密钥值的密钥名称，而不是手动输入密钥。

:::image type="content" source="media/use-key-vault-secret.png" alt-text="带有使用密钥保管库密钥的 SFTP 连接的连接窗格。":::

## <a name="supported-connection-types"></a>支持的连接类型

支持以下[导出](export-destinations.md)连接：

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>授予访问群体见解的密钥保管库的权限

如果启用了[密钥保管库访问策略](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)或 [Azure 基于角色的访问控制](/azure/key-vault/general/rbac-guide?tabs=azure-cli)，将会向访问群体见解授予链接的密钥保管库的以下权限。

### <a name="key-vault-access-policy"></a>密钥保管库访问策略

| Type        | 权限          |
| ----------- | -------------------- |
| 项         | [获取密钥](/rest/api/keyvault/get-keys)、[获取密钥](/rest/api/keyvault/get-key)                                 |
| 机密      | [获取密钥](/rest/api/keyvault/get-secrets)、[获取密钥](/rest/api/keyvault/get-secret)                     |
| 证书 | [获取证书](/rest/api/keyvault/get-certificates)、[获取证书](/rest/api/keyvault/get-certificate) |

前面的值是在执行期间列出和读取的最小值。

### <a name="azure-role-based-access-control"></a>Azure 基于角色的访问控制

将添加密钥保管库读者和密钥保管库密钥用户角色以获取访问群体见解。 有关这些角色的详细信息，请转到[执行密钥保管库数据平面操作的 Azure 内置角色](/azure/key-vault/general/rbac-guide?tabs=azure-cli)。

## <a name="recommendations"></a>建议

- 使用单独或专用的密钥保管库，其中仅包含访问群体见解所需的密钥。 详细了解为何[建议使用单独的密钥保管库](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)。

- 按照[使用密钥保管库的最佳实践](/azure/key-vault/general/best-practices#turn-on-logging)控制访问、备份、审核和恢复选项。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>访问群体见解是否可以将密钥写入密钥保管库或覆盖其中的密钥？

号码 只有本文前面[授予权限](#permissions-granted-on-the-key-vault-to-audience-insights)一节所概述的读取和列出权限会被授予访问群体见解。 系统无法在密钥保管库中添加、删除或覆盖密钥。 这也是在连接使用密钥保管库时无法输入凭据的原因。

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>我能否将连接从使用密钥保管库密钥更改为使用默认身份验证？

否。 在使用链接的密钥保管库中的密钥配置默认连接后，您无法改回默认连接。 可以创建一个单独的连接，如果不再需要旧连接，应将其删除。

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>如何撤销访问群体见解对密钥保管库的访问权限？

根据是否启用了[密钥保管库访问策略](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)或 [Azure 基于角色的访问控制](/azure/key-vault/general/rbac-guide?tabs=azure-cli)，您需要删除名为 `Dynamics 365 AI for Customer Insights` 的服务主体 `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 的权限。 使用密钥保管库的所有连接将停止工作。

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>连接中使用的密钥将被从密钥保管库中删除。 我该怎么做?

当无法再访问密钥保管库中配置的密钥时，会在访问群体见解中显示通知。 在密钥保管库上启用[软删除](/azure/key-vault/general/soft-delete-overview)以在意外删除密钥时进行恢复。

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>连接不起作用，但我的秘密在密钥保管库中。 这可能是什么原因？

当无法访问密钥保管库时，会在访问群体见解中显示通知。 原因可能是：

- 访问群体见解服务主体的权限被删除。 它们需要手动恢复。

- 密钥保管库中的防火墙启用。 必须禁用防火墙才能恢复访问群体见解对密钥保管库的访问。
