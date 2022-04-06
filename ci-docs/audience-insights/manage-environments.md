---
title: 创建和管理环境
description: 了解如何注册服务以及如何管理环境。
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
  - ci-system-about
  - customerInsights
---

# <a name="manage-environments"></a>管理环境

## <a name="switch-environments"></a>切换环境

选择页面右上角中的 **环境** 控件以更改环境。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="用于切换环境的控件的屏幕截图。":::

管理员可以[创建](create-environment.md)和管理环境。

## <a name="edit-an-existing-environment"></a>编辑现有环境

您可以编辑现有环境的某些详细信息。

1.  选择应用标题中的 **环境** 选择器。

2.  选择 **编辑** 图标。

3. 在 **编辑环境** 框中，可以更新环境设置。

有关环境设置的详细信息，请参阅[创建新环境](create-environment.md)。

## <a name="connect-to-microsoft-dataverse"></a>连接到 Microsoft Dataverse
   
**Microsoft Dataverse** 步骤让您可以将 Customer Insights 与您的 Dataverse 环境相连接。 

提供您自己的 Microsoft Dataverse 环境，以便与基于 Dataverse 的业务应用程序（例如 Dynamics 365 Marketing 或 Power Apps 中的模型驱动应用程序）共享数据（配置文件和见解）。

要使用[现成的预测模型](predictions-overview.md#out-of-box-models)，请配置与 Dataverse 的数据共享。 或者，您可以启用来自本地数据源的数据引入，提供您的组织管理的 Microsoft Dataverse 环境 URL。

通过选中数据共享复选框启用与 Microsoft Dataverse 的数据共享将触发您的数据源和所有其他流程的一次性完全刷新。

> [!IMPORTANT]
> 1. Customer Insights 和 Dataverse 必须在同一区域才能启用数据共享。
> 1. 您必须在 Dataverse 环境中具有全局管理员角色。 验证此 [Dataverse 环境是否关联](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)到某些安全组，并确保您已被添加到这些安全组。
> 1. 现有 Customer Insights 环境中没有与该 Dataverse 环境关联的环境。 了解如何[删除与 Dataverse 环境的现有连接](#remove-an-existing-connection-to-a-dataverse-environment)。

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="用于启用与 Microsoft Dataverse 的数据共享的配置选项。":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>启用从您自己的 Azure Data Lake Storage 与 Dataverse 共享数据（预览）

如果您的环境配置为使用您自己的 Azure Data Lake Storage 来存储 Customer Insights 数据，启用与 Microsoft Dataverse 共享数据需要一些额外的配置。

1. 在您的 Azure 订阅上创建两个安全组 - 一个 **读者** 安全组和一个 **参与者** 安全组，并将 Microsoft Dataverse 服务设置为两个安全组的所有者。
2. 通过这些安全组管理存储帐户中 CustomerInsights 容器上的访问控制列表 (ACL)。 将 Microsoft Dataverse 服务和任何基于 Dataverse 的业务应用程序（如 Dynamics 365 Marketing）添加到具有 **只读** 权限的 **读者** 安全组。 *仅* 将 Customers Insights 应用程序添加到 **参与者** 安全组，以授予 **读取和写入** 权限来写入配置文件和见解。
   
#### <a name="prerequisites"></a>先决条件

要执行 PowerShell 脚本，您需要导入以下三个模块。 

1. 安装 [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 的最新版本。
   1. 在 PC 中，选择键盘上的 Windows 键，搜索 **Windows PowerShell**，然后选择 **以管理员身份运行**。
   1. 在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。
2. 导入三个模块。
    1. 在 PowerShell 窗口中，输入 `Install-Module -Name Az.Accounts` 并按照步骤操作。 
    1. 对 `Install-Module -Name Az.Resources` 和 `Install-Module -Name Az.Storage` 重复这些步骤。

#### <a name="configuration-steps"></a>配置步骤

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
        - 成功运行脚本后复制输出字符串。 输出字符串如：`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. 将从上面复制的输出字符串输入到 Microsoft Dataverse 的环境配置步骤的 **权限标识符** 字段。

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="启用从您自己的 Azure Data Lake Storage 与 Microsoft Dataverse 共享数据的配置选项。":::

Customer Insights 不支持以下数据共享场景：
- 如果您启用与 Dataverse 的数据共享，那么您将无法[在实体中创建预测值或缺失值](predictions.md)。
- 如果您启用与 Dataverse 共享数据，您将无法在 Customer Insights 环境中查看任何可选的 PowerBI 嵌入式报表。

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

## <a name="copy-the-environment-configuration"></a>复制环境配置

作为管理员，您可以选择在创建新环境时从现有环境中复制配置。 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="环境设置中的设置选项的屏幕截图。":::

您将看到组织中可以从中复制数据的所有可用环境的列表。

复制以下配置设置：

- 引入/导入的数据源
- 数据统一（映射、匹配、合并）配置
- 客户细分
- 度量
- 关系
- 活动
- 搜索和筛选索引
- 导出目标
- 计划刷新
- 扩充
- 模型管理
- 角色分配

## <a name="set-up-a-copied-environment"></a>设置复制的环境

复制环境配置时，*不会* 复制以下数据：

- 客户配置文件。
- 数据源凭据。 您必须为每个数据源提供凭据，并手动刷新数据源。
- Common Data Model 文件夹和 Dataverse 托管数据湖中的数据源。 您必须使用与源环境中相同的名称手动创建这些数据源。
- 用于导出和扩充的连接机密。 您必须重新验证连接，然后重新激活扩充和导出。 

复制环境时，您会看到一条确认消息，显示新环境已创建。 选择 **转到数据源** 查看数据源的列表。

所有数据源都将显示 **需要凭据** 状态。 编辑数据源并输入凭据来刷新。

:::image type="content" source="media/data-sources-copied.png" alt-text="已复制并需要验证的数据源列表。":::

刷新数据源后，请转到 **数据** > **统一**。 在这里，您将找到源环境中的设置。 根据需要进行编辑，或选择 **运行** 启动数据统一流程，创建统一的客户实体。

当数据统一完成时，再转到 **度量** 和 **细分** 进行刷新。

在重新激活导出和扩充功能之前，请转到 **管理** > **连接** 重新验证新环境中的连接。

## <a name="change-the-owner-of-an-environment"></a>更改环境负责人

虽然多个用户可以在 Customer Insights 中具有管理员权限，但只有一个用户是环境的负责人。 默认情况下，最初将由管理员创建环境。 作为环境的管理员，您可以将所有权分配给具有管理员权限的其他用户。

1. 选择应用标题中的 **环境** 选择器。

1. 选择 **编辑** 图标。

1. 在 **编辑环境** 框中，转到 **基本信息** 步骤。

1. 在 **更改环境负责人** 字段中，选择新的环境负责人。  

1. 选择 **查看并完成**，然后选择 **更新** 应用更改。 

## <a name="claim-ownership-of-an-environment"></a>认领环境的所有权

如果环境的负责人离开组织或其用户帐户被删除，环境将没有负责人。 具有管理员权限的用户可以认领所有权，成为新负责人。 他们可以继续负责环境或[将所有权更改为其他管理员](#change-the-owner-of-an-environment)。 

要认领所有权，选择在原始负责人离开组织时显示在 Customer Insights 中每个页面顶部的 **获取所有权** 按钮。

## <a name="reset-an-existing-environment"></a>重置现有环境

作为环境的负责人，如果您想要删除所有配置并删除引入的数据，可以将环境重置为空状态。

1.  选择应用标题中的 **环境** 选择器。 

2.  选择要重置的环境，并选择省略号 (**...**)。 

3. 选择 **重置** 选项。 

4.  若要确认删除，请输入环境名称并选择 **重置**。

## <a name="delete-an-existing-environment"></a>删除现有环境

作为环境的负责人，您可以删除您管理的环境。

1.  选择应用标题中的 **环境** 选择器。

2.  选择要重置的环境，并选择省略号 (**...**)。 

3. 选择 **删除** 选项。 

4.  若要确认删除，请输入环境名称，然后选择 **删除**。

> [!NOTE]
> 删除环境不会删除与 Dataverse 环境的关联。了解如何[删除与 Dataverse 环境的现有连接](#remove-an-existing-connection-to-a-dataverse-environment)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
