---
title: 使用 Microsoft Dataverse 中的 Customer Insights 数据
description: 了解如何连接 Customer Insights 和 Microsoft Dataverse，并了解导出到 Dataverse 的输出实体。
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833665"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>使用 Microsoft Dataverse 中的 Customer Insights 数据

Customer Insights 提供了使输出实体可用作 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) 的选项。 这种集成通过低代码/无代码方法实现了轻松的数据共享和自定义开发。 [输出实体](#output-entities)可用作 Dataverse 环境中的表。 您可以基于 Dataverse 表将数据用于任何其他应用程序。 这些表支持通过 Power Automate 执行自动工作流或使用 Power Apps 生成应用等方案。

通过连接到 Dataverse 环境，您还可以[使用 Power Platform 数据流和网关从本地数据源中引入数据](data-sources.md#add-data-from-on-premises-data-sources)。

## <a name="prerequisites"></a>先决条件

- Customer Insights 和 Dataverse 环境必须托管在同一区域。
- 您必须在 Dataverse 环境中具有全局管理员角色。 验证此 [Dataverse 环境是否关联](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到某些安全组，并确保您已被添加到这些安全组。
- 其他 Customer Insights 环境还没有与您要连接的 Dataverse 环境关联。 了解如何[删除与 Dataverse 环境的现有连接](#remove-an-existing-connection-to-a-dataverse-environment)。
- 一个 Microsoft Dataverse 环境只能连接到一个存储帐户。 只有将环境配置为[使用 Azure Data Lake Storage](own-data-lake-storage.md) 时，它才适用。

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>将 Dataverse 环境连接到 Customer Insights

通过 **Microsoft Dataverse** 步骤，您可以在[创建 Customer Insights 环境](create-environment.md)时将 Customer Insights 连接到您的 Dataverse 环境。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="为净新环境自动启用了与 Microsoft Dataverse 的数据共享。":::

管理员可以将 Customer Insights 配置为连接现有 Dataverse 环境。 通过提供 Dataverse 环境的 URL，它会附加到他们的新 Customer Insights 环境。

如果不希望使用现有 Dataverse 环境，则系统会为租户中的 Customer Insights 数据创建新环境。 [Power Platform 管理员可以控制谁可以创建环境](/power-platform/admin/control-environment-creation)。 当您设置新的 Customer Insights 环境，并且管理员已禁止为除管理员之外的所有人创建 Dataverse 环境时，您可能无法创建新环境。

通过选中数据共享复选框 **允许与 Dataverse 共享数据**。

如果您使用的是自己的 Data Lake Storage 帐户，则还需要 **权限标识符**。 有关如何获取权限标识符的更多信息，请查看以下部分。

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>启用从您自己的 Azure Data Lake Storage 与 Dataverse 共享数据（预览）

当您的环境[使用您自己的 Azure Data Lake Storage 帐户](own-data-lake-storage.md)时，如果要允许与 Microsoft Dataverse 共享数据，则需要进行一些额外的配置。 设置 Customer Insights 环境的用户必须对 Azure Data Lake Storage 帐户中的 *CustomerInsights* 容器至少拥有 **存储 Blob 数据读取器** 权限。

1. 在您的 Azure 订阅上创建两个安全组 - 一个 **读者** 安全组和一个 **参与者** 安全组，并将 Microsoft Dataverse 服务设置为两个安全组的所有者。
2. 通过这些安全组管理存储帐户中 CustomerInsights 容器上的访问控制列表 (ACL)。 将 Microsoft Dataverse 服务和任何基于 Dataverse 的业务应用程序（如 Dynamics 365 Marketing）添加到具有 **只读** 权限的 **读者** 安全组。 *仅* 将 Customers Insights 应用程序添加到 **参与者** 安全组，以授予 **读取和写入** 权限来写入配置文件和见解。

### <a name="limitations"></a>限制

将 Dataverse 与您自己的 Azure Data Lake Storage 帐户一起使用时有两个限制：

- Dataverse 组织和 Azure Data Lake Storage 帐户之间存在一对一的映射。 Dataverse 组织连接到存储帐户后，就无法连接到另一个存储帐户。 此限制可防止 Dataverse 不填充多个存储帐户。
- 如果需要设置 Azure 专用链接来访问您的 Azure Data Lake 存储帐户，则数据共享将不起作用，因为它位于防火墙后面。 Dataverse 当前不支持通过专用链接连接到专用终结点。

### <a name="set-up-powershell"></a>设置 PowerShell

要执行 PowerShell 脚本，您首先需要相应地设置 PowerShell。

1. 安装 [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 的最新版本。
   1. 在 PC 中，选择键盘上的 Windows 键，搜索 **Windows PowerShell**，然后选择 **以管理员身份运行**。
   1. 在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。
2. 导入三个模块。
    1. 在 PowerShell 窗口中，输入 `Install-Module -Name Az.Accounts` 并按照步骤操作。
    1. 对 `Install-Module -Name Az.Resources` 和 `Install-Module -Name Az.Storage` 重复这些步骤。

### <a name="configuration-steps"></a>配置步骤

1. 从我们工程师的 [GitHub 存储库](https://github.com/trin-msft/byol)下载您需要运行的两个 PowerShell 脚本。
    1. `CreateSecurityGroups.ps1`
       - 您需要 *租户管理员* 权限来运行此 PowerShell 脚本。
       - 此 PowerShell 脚本将在您的 Azure 订阅上创建两个安全组。 一个用于读者组，另一个用于参与者组，并将 Microsoft Dataverse 服务作为这两个安全组的所有者。
       - 通过提供包含您的 Azure Data Lake Storage 的 Azure 订阅 ID，在 Windows PowerShell 中执行此 PowerShell 脚本。 在编辑器中打开 PowerShell 脚本查看其他信息和实现的逻辑。
       - 保存此脚本生成的两个安全组 ID 值，因为我们将在 `ByolSetup.ps1` 脚本中使用它们。

        > [!NOTE]
        > 可在您的租户中禁用创建安全组。 在这种情况下，需要手动设置，并且您的 Azure AD 管理员必须[启用安全组创建](/azure/active-directory/enterprise-users/groups-self-service-management)。

    2. `ByolSetup.ps1`
        - 您需要在存储帐户/容器级别具有 *存储 Blob 数据负责人* 权限才能运行此脚本，否则此脚本将为您创建权限。 成功运行脚本后，您的角色分配可以手动删除。
        - 此 PowerShell 脚本为 Microsoft Dataverse 服务和任何基于 Dataverse 的业务应用程序添加所需的基于角色的访问控制 (RBAC)。 它还为使用 `CreateSecurityGroups.ps1` 脚本创建的安全组更新 CustomerInsights 容器上的访问控制列表 (ACL)。 参与者组将具有 *rwx* 权限，读者组将仅具有 *r-x* 权限。
        - 通过提供包含您的 Azure Data Lake Storage、存储帐户名称、资源组名称以及读者和参与者安全组 ID 值的 Azure 订阅 ID，在 Windows PowerShell 中执行此 PowerShell 脚本。 在编辑器中打开 PowerShell 脚本查看其他信息和实现的逻辑。
        - 成功运行脚本后复制输出字符串。 输出字符串如：`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. 将从上面复制的输出字符串输入到 Microsoft Dataverse 的环境配置步骤的 **权限标识符** 字段。

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="启用从您自己的 Azure Data Lake Storage 与 Microsoft Dataverse 共享数据的配置选项。":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>删除与 Dataverse 环境的现有连接

连接到 Dataverse 环境时，错误消息 **此 CDS 组织已附加到另一个 Customer Insights 实例** 表示 Dataverse 环境已在 Customer Insights 环境中使用。 您可以在 Dataverse 环境中以全局管理员身份删除现有连接。 可能需要几个小时的时间填充更改。

1. 转至 [Power Apps](https://make.powerapps.com)。
1. 从环境选取器中选择环境。
1. 转到 **解决方案**
1. 卸载或删除名为 **Dynamics 365 Customer Insights 客户卡加载项（预览）** 的解决方案。

OR

1. 打开您的 Dataverse 环境。
1. 转到 **高级设置** > **解决方案**。
1. 卸载 **CustomerInsightsCustomerCard** 解决方案。

如果由于依赖项的缘故而导致删除连接失败，那么您也需要删除依赖项。 有关详细信息，请参阅[删除依赖项](/power-platform/alm/removing-dependencies)。

## <a name="output-entities"></a>输出实体

Customer Insights 中的某些输出实体作为表在 Dataverse 中可用。 下面的部分描述了这些表格的预期架构。

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [扩充](#enrichment)
- [预测](#prediction)
- [客户细分成员身份](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

此表包含来自 Customer Insights 的统一客户配置文件。 统一的客户配置文件的架构取决于数据统一过程中使用的实体和属性。 客户配置文件架构通常包含来自 [CustomerProfile Common Data Model 定义](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)的属性子集。

### <a name="alternatekey"></a>AlternateKey

AlternateKey 表包含参与统一流程的实体的键。

|Column  |Type  |描述  |
|---------|---------|---------|
|DataSourceName    |String         | 数据源的名称。 例如: `datasource5`        |
|EntityName        | String        | Customer Insights 中的实体名称。 例如: `contact1`        |
|AlternateValue    |String         |映射到客户 ID 的备用 ID。 示例: `cntid_1078`         |
|KeyRing           | 多行文本        | JSON 值  </br> 示例：[{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | 统一客户配置文件的 ID。         |
|AlternateKeyId     | GUID         |  基于 msdynci_identifier 的 AlternateKey 确定性 GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> 示例：`testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

此表包含 Customer Insights 中可用的用户活动。

| Column            | Type        | 描述                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | 客户配置文件 ID                                                                      |
| ActivityId        | String      | 客户活动的内部 ID（主键）                                       |
| SourceEntityName  | String      | 源实体的名称                                                                |
| SourceActivityId  | String      | 源实体的主键                                                       |
| ActivityType      | String      | 语义活动类型或自定义活动的名称                                        |
| ActivityTimeStamp | 日期/时间    | 活动时间戳                                                                      |
| 职务             | String      | 活动的标题或名称                                                               |
| 描述       | String      | 活动说明                                                                     |
| URL               | String      | 特定于活动的外部 URL 的链接                                         |
| SemanticData      | JSON 字符串 | 包括特定于活动类型的语义映射字段的键值对列表 |
| RangeIndex        | String      | 用于排序活动时间线和有效范围查询的 Unix 时间戳 |
| mydynci_unifiedactivityid   | GUID | 客户活动的内部 ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

此表包含基于客户属性的度量输出数据。

| Column             | Type             | 描述                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | 客户配置文件 ID        |
| 度量           | JSON 字符串      | 包括给定客户的度量名称和值的键值对列表 | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | 客户配置文件 ID |


### <a name="enrichment"></a>扩充

此表包含扩充流程的输出。

| Column               | Type             |  描述                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | 客户配置文件 ID                                 |
| EnrichmentProvider   | String           | 扩充的提供程序的名称                                  |
| EnrichmentType       | String           | 扩充的类型                                      |
| 值               | JSON 字符串      | 扩充流程产生的属性列表 |
| msdynci_enrichmentid | GUID             | 通过 msdynci_identifier 产生的确定性 GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>预测

此表包含模型预测的输出。

| Column               | Type        | 描述                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | 客户配置文件 ID                                  |
| ModelProvider        | String      | 模型的提供程序的名称                                      |
| 模型                | String      | 模型名称                                                |
| 值               | JSON 字符串 | 模型产生的属性列表 |
| msdynci_predictionid | GUID        | 通过 msdynci_identifier 产生的确定性 GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>客户细分成员身份

此表包含客户配置文件的客户细分成员身份信息。

| Column        | 类型​​ | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | 客户配置文件 ID        |
| SegmentProvider      | String       | 发布客户细分的应用。      |
| SegmentMembershipType | String       | 此客户细分成员身份记录的客户类型。 支持多种类型，例如顾客、联系人或客户。 默认：客户  |
| 客户细分       | JSON 字符串  | 客户配置文件所属的独特客户细分的列表      |
| msdynci_identifier  | String   | 客户细分成员身份记录的唯一标识符。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | 从 `msdynci_identifier` 中生成的确定 GUID          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
