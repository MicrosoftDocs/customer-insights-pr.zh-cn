---
title: 使用 Azure 服务主体连接到 Azure Data Lake Storage 帐户
description: 使用 Azure 服务主体连接到您自己的数据湖。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304186"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>使用 Azure 服务主体连接到 Azure Data Lake Storage 帐户

Dynamics 365 Customer Insights 提供了一个选项，可使用 Azure 服务主体而不是存储帐户密钥连接到 Azure Data Lake Storage 帐户。

使用 Azure 服务的自动化工具必须具有受限权限。 Azure 提供服务主体，而不是让应用程序以完全特权的用户身份登录。 使用服务主体安全地[以数据源形式添加或编辑 Common Data Model 文件夹](connect-common-data-model.md)或者[创建或更新环境](create-environment.md)。

## <a name="prerequisites"></a>先决条件

- 将使用此服务主体的 Data Lake Storage 帐户必须是 Gen2。 Azure Data Lake Gen1 存储帐户不受支持。
- 为 Data Lake Storage 帐户[启用了分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。
- Azure 租户的管理员权限（如果必须创建新的服务主体）。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>为 Customer Insights 创建一个 Azure 服务主体

在为 Customer Insights 创建新服务主体之前，请检查组织中是否已存在服务主体。 大多数情况下，它已经存在。

### <a name="look-for-an-existing-service-principal"></a>查找现有服务主体

1. 转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。

2. 在 **Azure 服务** 中，选择 **Azure Active Directory**。

3. 在 **管理** 下面，选择 **Microsoft 应用程序**。

4. 为 **应用程序 ID 的开头为** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 添加筛选器，或搜索名称 `Dynamics 365 AI for Customer Insights`。

5. 如果找到匹配记录，则表示已存在该服务主体。 为服务主体[授予访问存储帐户的权限](#grant-permissions-to-the-service-principal-to-access-the-storage-account)。

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="屏幕截图显示一个现有服务主体。":::

6. 如果没有返回结果，请[创建新的服务主体](#create-a-new-service-principal)。

### <a name="create-a-new-service-principal"></a>创建新的服务主体

1. 安装 Azure Active Directory PowerShell for Graph 的最新版本。 有关详细信息，请转到[安装 Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)。

   1. 在 PC 上，按键盘上的 Windows 键，搜索 **Windows PowerShell** 并选择 **以管理员身份运行**。

   1. 在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。

2. 使用 Azure AD PowerShell 模块为 Customer Insights 创建服务主体。

   1. 在 PowerShell 窗口中，输入 `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`。 将 *您的 [目录 ID]* 替换为要在其中创建服务主体的 Azure 订阅的实际目录 ID。 环境名称参数 `AzureEnvironmentName` 是可选参数。
  
   1. 输入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 此命令针对所选 Azure 订阅上创建Customer Insights 服务主体。

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>向服务主体授予访问存储帐户的权限

要向您要在 Customer Insights 中使用的存储帐户的服务主体授予权限，必须将以下角色之一分配给存储帐户或容器：

|凭据|要求|
|----------|------------|
|当前登录用户|**角色**：存储 Blob 数据读者、存储 Blob 参与者或存储 Blob 负责人。<br>**级别**：授予存储帐户或容器的权限。</br>|
|Customer Insights 服务主体 -<br>使用 Azure Data Lake Storage 作为数据源</br>|选项 1<ul><li>**角色**：存储 Blob 数据读者、存储 Blob 数据参与者或存储 Blob 数据负责人。</li><li>**级别**：授予存储帐户的权限。</li></ul>选项 2 *（不共享对存储帐户的服务主体访问权限）*<ul><li>**角色 1**：存储 Blob 数据读者、存储 Blob 数据参与者或存储 Blob 数据负责人。</li><li>**级别**：授予容器的权限。</li><li>**角色 2**：存储 Blob 数据代理。</li><li>**级别**：授予存储帐户的权限。</li></ul>|
|Customer Insights 服务主体 - <br>使用 Azure Data Lake Storage 作为输出或目标</br>|选项 1<ul><li>**角色**：存储 Blob 数据参与者或存储 Blob 负责人。</li><li>**级别**：授予存储帐户的权限。</li></ul>选项 2 *（不共享对存储帐户的服务主体访问权限）*<ul><li>**角色**：存储 Blob 数据参与者或存储 Blob 负责人。</li><li>**级别**：授予容器的权限。</li><li>**角色 2**：存储 Blob 代理。</li><li>**级别**：授予存储帐户的权限。</li></ul>|

1. 转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。

1. 打开您希望 Customer Insights 服务主体有权访问的存储帐户。

1. 在左窗格中，选择 **访问控制 (IAM)**，然后选择 **添加** > **添加角色分配**。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="屏幕截图显示添加角色分配时的 Azure 门户。":::

1. 在 **添加角色分配** 窗格中，设置以下属性：
   - **角色**：存储 Blob 数据读者、存储 Blob 数据参与者或存储 Blob 数据负责人（基于上面列出的凭据）。
   - **向以下项分配访问权限**：**用户、组或服务主体**
   - **选择** 成员：**Dynamics 365 AI for Customer Insights**（您在此过程中前面查找的[服务主体](#create-a-new-service-principal)）

1. 选择 **查看 + 分配**。

传播更改最多可能需要 15 分钟。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>在 Customer Insights 的存储帐户附件中输入 Azure 资源 ID 或 Azure 订阅详细信息

在 Customer Insights 中附加 Data Lake Storage 帐户，以便[存储输出数据](manage-environments.md)或[将其用作数据源](connect-dataverse-managed-lake.md)。 在[基于资源](#resource-based-storage-account-connection)或[基于订阅](#subscription-based-storage-account-connection)的方法之间进行选择，然后按照这些步骤操作。

### <a name="resource-based-storage-account-connection"></a>基于资源的存储帐户连接

1. 转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。

1. 在左侧窗格中，转到 **设置** > **终结点**。

1. 复制存储帐户资源 ID 值。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="复制存储帐户资源 ID。":::

1. 在 Customer Insights 中，在存储帐户连接屏幕上显示的资源字段中插入资源 ID。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="输入存储帐户资源 ID 信息。":::

1. 继续执行 Customer Insights 中的剩余步骤以附加存储帐户。

### <a name="subscription-based-storage-account-connection"></a>基于订阅的存储帐户连接

1. 转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。

1. 在左窗格中，转到 **设置** > **属性**。

1. 查看 **订阅**、**资源组** 和 **存储帐户** 的名称，以确保在 Customer Insights 中选择正确的值。

1. 在 Customer Insights 中，在附加存储帐户时选择相应字段的值。

1. 继续执行 Customer Insights 中的剩余步骤以附加存储帐户。

[!INCLUDE [footer-include](includes/footer-banner.md)]
