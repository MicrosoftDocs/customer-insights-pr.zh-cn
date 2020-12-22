---
title: 使用服务主体连接到 Azure Data Lake Storage Gen2 帐户
description: 在要附加到访问群体见解时，使用访问群体见解的 Azure 服务主体连接到您自己的 Data Lake。
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644077"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>使用访问群体见解的 Azure 服务主体连接到 Azure Data Lake Storage Gen2 帐户

使用 Azure 服务的自动化工具应始终具有受限权限。 Azure 提供服务主体，而不是让应用程序以完全特权的用户身份登录。 继续阅读以了解如何使用 Azure 服务主体（而不是存储帐户密钥）通过 Azure Data Lake Storage Gen2 帐户连接访问群体见解。 

您可以使用服务主体安全地[添加或编辑 Common Data Model 文件夹作为数据源](connect-common-data-model.md)或[创建新环境或更新现有环境](manage-environments.md#create-an-environment-in-an-existing-organization)。

您需要 Azure 订阅的管理员权限才能创建服务主体。

## <a name="create-azure-service-principal-for-audience-insights"></a>为访问群体见解创建 Azure 服务主体

在为访问群体见解创建新的服务主体之前，请检查组织中是否已存在服务主体。

### <a name="look-for-an-existing-service-principal"></a>查找现有服务主体

1. 转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。

2. 从 Azure 服务中选择 **Azure Active Directory**。

3. 在 **管理** 下，选择 **企业应用程序**。

4. 搜索访问群体见解第一方应用程序 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 或名称 `Dynamics 365 AI for Customer Insights`。

5. 如果您找到匹配的记录，这意味着存在访问群体见解的服务主体。 您无需再次创建。
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="显示现有服务主体的屏幕截图。":::
   
6. 如果没有返回结果，请创建新的服务主体。

### <a name="create-a-new-service-principal"></a>创建新的服务主体

1. 安装最新版本的 **Azure Active Directory PowerShell for Graph**。 有关详细信息，请参阅[安装 Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。
   - 在您的电脑上，选择键盘上的 Windows 键并搜索 **Windows PowerShell**，然后单击 **以管理员身份运行**。
   
   - 在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。

2. 使用 Azure AD PowerShell 模块为访问群体见解创建服务主体。
   - 在 PowerShell 窗口中，输入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。 将“您的租户 ID”替换为您要在其中创建服务主体的租户的实际 ID。 环境名称参数 `AzureEnvironmentName` 是可选的。
  
   - 输入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。 此命令将在所选租户上为访问群体见解创建服务主体。  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>向服务主体授予访问存储帐户的权限

转到 Azure 门户，向服务主体授予要在访问群体见解中使用的存储帐户的权限。

1. 转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。

1. 打开您希望访问群体见解的服务主体对其具有访问权限的存储帐户。

1. 从导航窗格中选择 **访问控制（标识和访问管理）**，然后选择 **添加** > **添加角色分配**。
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="显示添加角色分配时的 Azure 门户的屏幕截图。":::
   
1. 在 **添加角色分配** 窗格中，设置以下属性：
   - 角色：*存储 Blob 数据参与者*
   - 向以下项分配访问权限：*用户、组或服务主体*
   - 选择：*Dynamics 365 AI for Customer Insights*（[您创建的服务主体](#create-a-new-service-principal)）

1.  选择 **保存**。

传播更改最多可能需要 15 分钟。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>在附加到访问群体见解的存储帐户中输入 Azure 资源 ID 或 Azure 订阅详细信息。

在访问群体见解中附加 Azure Data Lake 存储帐户以[存储输出数据](manage-environments.md)或[将其用作数据源](connect-common-data-service-lake.md)。 通过选择 Azure Data Lake 选项，您可以在基于资源或基于订阅的方法之间进行选择。

按照以下步骤提供所选方法的必要信息。

### <a name="resounce-based-storage-account-connection"></a>基于资源的存储帐户连接

1. 转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。

1. 在导航窗格上转到 **设置** > **属性**。

1. 复制存储帐户资源 ID 值。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="复制存储帐户资源 ID。":::

1. 在访问群体见解中，在存储帐户连接屏幕中显示的资源字段中插入资源 ID。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="输入存储帐户资源 ID 信息。":::   
   
1. 继续执行访问群体见解中的剩余步骤以附加存储帐户。

### <a name="subscription-based-storage-account-connection"></a>基于订阅的存储帐户连接

1. 转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。

1. 在导航窗格上转到 **设置** > **属性**。

1. 查看 **订阅**、**资源组** 和存储帐户的 **名称**，以确保在访问群体见解中选择正确的值。

1. 在访问群体见解中，在附加存储帐户时，请选择相应字段的值。

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="输入存储帐户资源 ID 信息。":::
   
1. 继续执行访问群体见解中的剩余步骤以附加存储帐户。
