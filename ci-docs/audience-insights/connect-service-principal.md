---
title: 使用服务主体连接到 Azure Data Lake Storage Gen2 帐户
description: 在要附加到访问群体见解时，使用访问群体见解的 Azure 服务主体连接到您自己的 Data Lake。
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267711"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="4d7c2-103">使用访问群体见解的 Azure 服务主体连接到 Azure Data Lake Storage Gen2 帐户</span><span class="sxs-lookup"><span data-stu-id="4d7c2-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="4d7c2-104">使用 Azure 服务的自动化工具应始终具有受限权限。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="4d7c2-105">Azure 提供服务主体，而不是让应用程序以完全特权的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="4d7c2-106">继续阅读以了解如何使用 Azure 服务主体（而不是存储帐户密钥）通过 Azure Data Lake Storage Gen2 帐户连接访问群体见解。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="4d7c2-107">您可以使用服务主体安全地[添加或编辑 Common Data Model 文件夹作为数据源](connect-common-data-model.md)或[创建新环境或更新现有环境](manage-environments.md#create-an-environment-in-an-existing-organization)。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="4d7c2-108">必须为想要使用服务主体的 Azure Data Lake Gen2 存储帐户[启用分层命名空间 (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace)。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="4d7c2-109">您需要 Azure 订阅的管理员权限才能创建服务主体。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="4d7c2-110">为访问群体见解创建 Azure 服务主体</span><span class="sxs-lookup"><span data-stu-id="4d7c2-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="4d7c2-111">在为访问群体见解创建新的服务主体之前，请检查组织中是否已存在服务主体。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="4d7c2-112">查找现有服务主体</span><span class="sxs-lookup"><span data-stu-id="4d7c2-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="4d7c2-113">转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="4d7c2-114">从 Azure 服务中选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="4d7c2-115">在 **管理** 下，选择 **企业应用程序**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="4d7c2-116">搜索访问群体见解第一方应用程序 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 或名称 `Dynamics 365 AI for Customer Insights`。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="4d7c2-117">如果您找到匹配的记录，这意味着存在访问群体见解的服务主体。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="4d7c2-118">您无需再次创建。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="显示现有服务主体的屏幕截图。":::
   
6. <span data-ttu-id="4d7c2-120">如果没有返回结果，请创建新的服务主体。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="4d7c2-121">创建新的服务主体</span><span class="sxs-lookup"><span data-stu-id="4d7c2-121">Create a new service principal</span></span>

1. <span data-ttu-id="4d7c2-122">安装最新版本的 **Azure Active Directory PowerShell for Graph**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="4d7c2-123">有关详细信息，请参阅[安装 Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="4d7c2-124">在您的电脑上，选择键盘上的 Windows 键并搜索 **Windows PowerShell**，然后单击 **以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="4d7c2-125">在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="4d7c2-126">使用 Azure AD PowerShell 模块为访问群体见解创建服务主体。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="4d7c2-127">在 PowerShell 窗口中，输入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="4d7c2-128">将“您的租户 ID”替换为您要在其中创建服务主体的租户的实际 ID。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="4d7c2-129">环境名称参数 `AzureEnvironmentName` 是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="4d7c2-130">输入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="4d7c2-131">此命令将在所选租户上为访问群体见解创建服务主体。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="4d7c2-132">向服务主体授予访问存储帐户的权限</span><span class="sxs-lookup"><span data-stu-id="4d7c2-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="4d7c2-133">转到 Azure 门户，向服务主体授予要在访问群体见解中使用的存储帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="4d7c2-134">转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="4d7c2-135">打开您希望访问群体见解的服务主体对其具有访问权限的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="4d7c2-136">从导航窗格中选择 **访问控制（标识和访问管理）**，然后选择 **添加** > **添加角色分配**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="显示添加角色分配时的 Azure 门户的屏幕截图。":::
   
1. <span data-ttu-id="4d7c2-138">在 **添加角色分配** 窗格中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="4d7c2-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="4d7c2-139">角色：*存储 Blob 数据参与者*</span><span class="sxs-lookup"><span data-stu-id="4d7c2-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="4d7c2-140">向以下项分配访问权限：*用户、组或服务主体*</span><span class="sxs-lookup"><span data-stu-id="4d7c2-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="4d7c2-141">选择：*Dynamics 365 AI for Customer Insights*（[您创建的服务主体](#create-a-new-service-principal)）</span><span class="sxs-lookup"><span data-stu-id="4d7c2-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="4d7c2-142">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-142">Select **Save**.</span></span>

<span data-ttu-id="4d7c2-143">传播更改最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="4d7c2-144">在附加到访问群体见解的存储帐户中输入 Azure 资源 ID 或 Azure 订阅详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="4d7c2-145">在访问群体见解中附加 Azure Data Lake 存储帐户以[存储输出数据](manage-environments.md)或[将其用作数据源](connect-common-data-service-lake.md)。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="4d7c2-146">通过选择 Azure Data Lake 选项，您可以在基于资源或基于订阅的方法之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="4d7c2-147">按照以下步骤提供所选方法的必要信息。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="4d7c2-148">基于资源的存储帐户连接</span><span class="sxs-lookup"><span data-stu-id="4d7c2-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="4d7c2-149">转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="4d7c2-150">在导航窗格上转到 **设置** > **属性**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="4d7c2-151">复制存储帐户资源 ID 值。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="复制存储帐户资源 ID。":::

1. <span data-ttu-id="4d7c2-153">在访问群体见解中，在存储帐户连接屏幕中显示的资源字段中插入资源 ID。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="输入存储帐户资源 ID 信息。":::   
   
1. <span data-ttu-id="4d7c2-155">继续执行访问群体见解中的剩余步骤以附加存储帐户。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="4d7c2-156">基于订阅的存储帐户连接</span><span class="sxs-lookup"><span data-stu-id="4d7c2-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="4d7c2-157">转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="4d7c2-158">在导航窗格上转到 **设置** > **属性**。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="4d7c2-159">查看 **订阅**、**资源组** 和存储帐户的 **名称**，以确保在访问群体见解中选择正确的值。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="4d7c2-160">在访问群体见解中，在附加存储帐户时，请选择相应字段的值。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="4d7c2-161">继续执行访问群体见解中的剩余步骤以附加存储帐户。</span><span class="sxs-lookup"><span data-stu-id="4d7c2-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]