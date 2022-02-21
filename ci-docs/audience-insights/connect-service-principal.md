---
title: 使用服务主体连接到 Azure Data Lake Storage 帐户
description: 使用 Azure 服务主体连接到您自己的数据湖。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088107"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>使用 Azure 服务主体连接到 Azure Data Lake Storage 帐户

本文讨论如何使用 Azure 服务主体（而不是存储帐户密钥）连接 Dynamics 365 Customer Insights 与 Azure Data Lake Storage 帐户。 

使用 Azure 服务的自动化工具应始终具有受限权限。 Azure 提供服务主体，而不是让应用程序以完全特权的用户身份登录。 您可以使用服务主体安全地[以数据源形式添加或编辑 Common Data Model 文件夹](connect-common-data-model.md)或者[创建或更新环境](create-environment.md)。

> [!IMPORTANT]
> - 将使用服务主体的 Data Lake Storage 帐户必须是 Gen2 并且[启用了分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。 Azure Data Lake Gen1 存储帐户不受支持。
> - 需要 Azure 订阅的管理员权限才能创建服务主体。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>为 Customer Insights 创建一个 Azure 服务主体

在为 Customer Insights 创建新服务主体之前，请检查组织中是否已存在服务主体。

### <a name="look-for-an-existing-service-principal"></a>查找现有服务主体

1. 转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。

2. 在 **Azure 服务** 中，选择 **Azure Active Directory**。

3. 在 **管理** 下，选择 **企业应用程序**。

4. 搜索 Microsoft 应用程序 ID：
   - 访问群体见解：`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`，名称为 `Dynamics 365 AI for Customer Insights`
   - 参与见解：`ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`，名称为 `Dynamics 365 AI for Customer Insights engagement insights`

5. 如果找到匹配记录，则表示已存在该服务主体。 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="屏幕截图显示一个现有服务主体。":::
   
6. 如果没有返回结果，请创建新的服务主体。

>[!NOTE]
>若要充分使用 Dynamics 365 Customer Insights，建议将这两个应用都添加到该服务主体。

### <a name="create-a-new-service-principal"></a>创建新的服务主体

1. 安装 Azure Active Directory PowerShell for Graph 的最新版本。 有关详细信息，请转到[安装 Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)。

   1. 在 PC 中，选择键盘上的 Windows 键，搜索 **Windows PowerShell**，然后选择 **以管理员身份运行**。
   
   1. 在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。

2. 使用 Azure AD PowerShell 模块为 Customer Insights 创建服务主体。

   1. 在 PowerShell 窗口中，输入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。 将 *[您的租户 ID]* 替换为您要在其中创建服务主体的租户的实际 ID。 环境名称参数 `AzureEnvironmentName` 是可选参数。
  
   1. 输入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 此命令将在所选租户上为访问群体见解创建服务主体。 

   1. 输入 `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`。 此名称为所选租户中参与见解创建服务主体。

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>向服务主体授予访问存储帐户的权限

转到 Azure 门户，向服务主体授予要在访问群体见解中使用的存储帐户的权限。

1. 转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。

1. 打开您希望访问群体见解的服务主体对其具有访问权限的存储帐户。

1. 在左窗格中，选择 **访问控制 (IAM)**，然后选择 **添加** > **添加角色分配**。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="屏幕截图显示添加角色分配时的 Azure 门户。":::

1. 在 **添加角色分配** 窗格中，设置以下属性：
   - 角色：**存储 Blob 数据参与者**
   - 向以下项分配访问权限：**用户、组或服务主体**
   - 选择 **Dynamics 365 AI for Customer Insights** 和 **Dynamics 365 AI for Customer Insights 参与见解**（您在此过程中前面创建的两个[服务主体](#create-a-new-service-principal)）

1.  选择 **保存**。

传播更改最多可能需要 15 分钟。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>在附加到访问群体见解的存储帐户中输入 Azure 资源 ID 或 Azure 订阅详细信息

可在访问群体见解中附加 Data Lake Storage 帐户，以便[存储输出数据](manage-environments.md)或[将其用作数据源](connect-common-data-service-lake.md)。 此选项让您可以在基于资源的方法与基于订阅的方法之间进行选择。 请根据您选择的方法，执行以下部分之一中的过程。

### <a name="resource-based-storage-account-connection"></a>基于资源的存储帐户连接

1. 转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。

1. 在左窗格中，转到 **设置** > **属性**。

1. 复制存储帐户资源 ID 值。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="复制存储帐户资源 ID。":::

1. 在访问群体见解中，在存储帐户连接屏幕中显示的资源字段内插入资源 ID。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="输入存储帐户资源 ID 信息。":::   

1. 继续执行访问群体见解中的剩余步骤以附加存储帐户。

### <a name="subscription-based-storage-account-connection"></a>基于订阅的存储帐户连接

1. 转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。

1. 在左窗格中，转到 **设置** > **属性**。

1. 查看 **订阅**、**资源组** 和存储帐户的 **名称**，以确保在访问群体见解中选择正确的值。

1. 在附加存储帐户时，在访问群体见解中选择相应字段的值。

1. 继续执行访问群体见解中的剩余步骤以附加存储帐户。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
