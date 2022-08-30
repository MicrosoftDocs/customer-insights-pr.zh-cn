---
title: 使用 Microsoft Dataverse 中的 Customer Insights 数据
description: 了解如何连接 Customer Insights 和 Microsoft Dataverse，并了解导出到 Dataverse 的输出实体。
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303818"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>使用 Microsoft Dataverse 中的 Customer Insights 数据

Customer Insights 提供了使输出实体在 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) 中可用的选项。 这种集成通过低代码/无代码方法实现了轻松的数据共享和自定义开发。 [输出实体](#output-entities)可用作 Dataverse 环境中的表。 您可以基于 Dataverse 表将数据用于任何其他应用程序。 这些表支持通过 Power Automate 执行自动工作流或使用 Power Apps 生成应用等方案。

通过连接到 Dataverse 环境，您还可以[使用 Power Platform 数据流和网关从本地数据源中引入数据](connect-power-query.md#add-data-from-on-premises-data-sources)。

## <a name="prerequisites"></a>先决条件

- Customer Insights 和 Dataverse 环境必须托管在同一区域。
- 在 Dataverse 环境中设置的全局管理员角色。 验证此 [Dataverse 环境是否关联](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到某些安全组，并确保您已被添加到这些安全组。
- 其他 Customer Insights 环境还没有与您要连接的 Dataverse 环境关联。 了解如何[删除与 Dataverse 环境的现有连接](#remove-an-existing-connection-to-a-dataverse-environment)。
- 连接到单个存储帐户的 Microsoft Dataverse 环境（如果您将环境配置为[使用您的 Azure Data Lake Storage](own-data-lake-storage.md)）。

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse 存储容量权利

订阅 Customer Insights 后，您可以为组织现有的 [Dataverse 存储容量](/power-platform/admin/capacity-storage)获得额外容量。 增加的容量取决于您的订阅使用的配置文件数量。

**示例：**

假设您为每 100,000 个客户配置文件获取了 15 GB 的数据库存储和 20 GB 的文件存储。 如果您的订阅包括 300,000 个客户配置文件，您的总存储容量为 45 GB (3 x 15 GB) 数据库存储和 60 GB 文件存储 (3 x 20 GB)。 同样，如果您有一个包含 30K 帐户的企业对企业订阅，那么您的总存储容量为 45 GB (3 x 15 GB) 数据库存储和 60 GB 文件存储 (3 x 20 GB)。

日志容量对于组织不是增量和固定的。

有关详细的容量权利的详细信息，请参阅 [Dynamics 365 许可指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>将 Dataverse 环境连接到 Customer Insights

通过 **Microsoft Dataverse** 步骤，您可以在[创建 Customer Insights 环境](create-environment.md)时将 Customer Insights 连接到您的 Dataverse 环境。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="为新环境自动启用了与 Microsoft Dataverse 的数据共享。":::

1. 提供您的 Dataverse 环境的 URL 或留空，系统将为您创建一个。

   > [!NOTE]
   > 在 Customer Insights 和 Dataverse 之间建立连接后，不要更改 Dataverse 环境的组织名称。 Dataverse URL 中使用组织的名称，更改的名称会破坏与 Customer Insights 的连接。

   [Power Platform 管理员可以控制谁可以创建新 Dataverse 环境](/power-platform/admin/control-environment-creation)。 如果您尝试设置新的 Customer Insights 环境但无法设置，可能是由于管理员已禁用为除管理员之外的所有人创建 Dataverse 环境。

1. 如果您使用的是自己的 Data Lake Storage 帐户：
   1. 选择 **启用与 Dataverse 共享数据**。
   1. 输入 **权限标识符**。 要获取权限标识符，请[启用从您自己的 Azure Data Lake Storage 与 Dataverse 共享数据](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)。

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>启用从您自己的 Azure Data Lake Storage 与 Dataverse 共享数据（预览）

在 [您自己的 Azure Data Lake Storage 帐户](own-data-lake-storage.md)中，验证设置 Customer Insights 环境的用户对存储帐户中的 `customerinsights` 容器是否至少具有 **存储 Blob 数据读者** 权限。

### <a name="limitations"></a>限制

- Dataverse 组织和 Azure Data Lake Storage 帐户之间只能进行一对一映射。 Dataverse 组织连接到存储帐户后，就无法连接到另一个存储帐户。 此限制可防止 Dataverse 填充多个存储帐户。
- 如果需要设置 Azure 专用链接来访问您的 Azure Data Lake Storage 帐户，则数据共享将不起作用，因为它位于防火墙后面。 Dataverse 当前不支持通过专用链接连接到专用终结点。

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>在您自己的 Azure Data Lake Storage 上设置安全组

1. 在您的 Azure 订阅上创建两个安全组 - 一个 **读者** 安全组和一个 **参与者** 安全组，并将 Microsoft Dataverse 服务设置为两个安全组的所有者。

1. 通过这些安全组管理存储帐户中 `customerinsights` 容器上的访问控制列表 (ACL)。
   1. 将 Microsoft Dataverse 服务和任何基于 Dataverse 的业务应用程序（如 Dynamics 365 Marketing）添加到具有 **只读** 权限的 **读者** 安全组。
   1. *仅* 将 Customers Insights 应用程序添加到 **参与者** 安全组，以授予 **读取和写入** 权限来写入配置文件和见解。

### <a name="set-up-powershell"></a>设置 PowerShell

设置 PowerShell 来执行 PowerShell 脚本。

1. 安装 [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 的最新版本。
   1. 在 PC 中，选择键盘上的 Windows 键，搜索 **Windows PowerShell**，然后选择 **以管理员身份运行**。
   1. 在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。

1. 导入三个模块。
   1. 在 PowerShell 窗口中，输入 `Install-Module -Name Az.Accounts` 并按照步骤操作。
   1. 对 `Install-Module -Name Az.Resources` 和 `Install-Module -Name Az.Storage` 重复这些步骤。

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>执行 PowerShell 脚本并获取权限标识符

1. 从我们工程师的 [GitHub 存储库](https://github.com/trin-msft/byol)下载您需要运行的两个 PowerShell 脚本。
   - `CreateSecurityGroups.ps1`：需要租户管理员权限。
   - `ByolSetup.ps1`：需要存储帐户/容器级别的存储 Blob 数据负责人权限。 此脚本将为您创建此权限。 成功运行脚本后，您的角色分配可以手动删除。

1. 通过提供包含您的 Azure Data Lake Storage 的 Azure 订阅 ID，在 Windows PowerShell 中执行 `CreateSecurityGroups.ps1`。 在编辑器中打开 PowerShell 脚本查看其他信息和实现的逻辑。

   此脚本在您的 Azure 订阅上创建两个安全组：一个是读者组，另一个是参与者组。 Microsoft Dataverse 服务是这两个安全组的所有者。

1. 保存此脚本生成的两个安全组 ID 值，以在 `ByolSetup.ps1` 脚本中使用。

   > [!NOTE]
   > 可在您的租户中禁用创建安全组。 在这种情况下，需要手动设置，并且您的 Azure AD 管理员必须[启用安全组创建](/azure/active-directory/enterprise-users/groups-self-service-management)。

1. 通过提供包含您的 Azure Data Lake Storage、存储帐户名称、资源组名称以及读者和参与者安全组 ID 值的 Azure 订阅 ID，在 Windows PowerShell 中执行 `ByolSetup.ps1`。 在编辑器中打开 PowerShell 脚本查看其他信息和实现的逻辑。

   此脚本为 Microsoft Dataverse 服务和任何基于 Dataverse 的业务应用程序添加所需的基于角色的访问控制。 它还为使用 `CreateSecurityGroups.ps1` 脚本创建的安全组更新 `customerinsights` 容器上的访问控制列表 (ACL)。 参与者组将被授予 *rwx* 权限，读者组仅被授予 *r-x* 权限。

1. 复制如下所示的输出字符串：`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. 将复制的输出字符串输入到 Microsoft Dataverse 的环境配置步骤的 **权限标识符** 字段。

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="启用从您自己的 Azure Data Lake Storage 与 Microsoft Dataverse 共享数据的配置选项。":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>删除与 Dataverse 环境的现有连接

连接到 Dataverse 环境时，错误消息 **此 CDS 组织已附加到另一个 Customer Insights 实例** 表示 Dataverse 环境已在 Customer Insights 环境中使用。 您可以在 Dataverse 环境中以全局管理员身份删除现有连接。 可能需要几个小时的时间填充更改。

1. 转至 [Power Apps](https://make.powerapps.com)。
1. 从环境选取器中选择环境。
1. 转到 **解决方案**。
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

| Column            | 类型​​        | 说明                                                                               |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | 客户配置文件 ID                                                                      |
| ActivityId        | String      | 客户活动的内部 ID（主键）                                       |
| SourceEntityName  | String      | 源实体的名称                                                                |
| SourceActivityId  | String      | 源实体的主键                                                       |
| ActivityType      | String      | 语义活动类型或自定义活动的名称                                        |
| ActivityTimeStamp | 日期/时间    | 活动时间戳                                                                      |
| 称谓             | String      | 活动的标题或名称                                                               |
| 说明        | String      | 活动说明                                                                     |
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

| Column               | 类型​​        | 说明                                           |
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
