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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="96c0d-103">使用访问群体见解的 Azure 服务主体连接到 Azure Data Lake Storage Gen2 帐户</span><span class="sxs-lookup"><span data-stu-id="96c0d-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="96c0d-104">使用 Azure 服务的自动化工具应始终具有受限权限。</span><span class="sxs-lookup"><span data-stu-id="96c0d-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="96c0d-105">Azure 提供服务主体，而不是让应用程序以完全特权的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="96c0d-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="96c0d-106">继续阅读以了解如何使用 Azure 服务主体（而不是存储帐户密钥）通过 Azure Data Lake Storage Gen2 帐户连接访问群体见解。</span><span class="sxs-lookup"><span data-stu-id="96c0d-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="96c0d-107">您可以使用服务主体安全地[添加或编辑 Common Data Model 文件夹作为数据源](connect-common-data-model.md)或[创建新环境或更新现有环境](manage-environments.md#create-an-environment-in-an-existing-organization)。</span><span class="sxs-lookup"><span data-stu-id="96c0d-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="96c0d-108">您需要 Azure 订阅的管理员权限才能创建服务主体。</span><span class="sxs-lookup"><span data-stu-id="96c0d-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="96c0d-109">为访问群体见解创建 Azure 服务主体</span><span class="sxs-lookup"><span data-stu-id="96c0d-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="96c0d-110">在为访问群体见解创建新的服务主体之前，请检查组织中是否已存在服务主体。</span><span class="sxs-lookup"><span data-stu-id="96c0d-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="96c0d-111">查找现有服务主体</span><span class="sxs-lookup"><span data-stu-id="96c0d-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="96c0d-112">转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。</span><span class="sxs-lookup"><span data-stu-id="96c0d-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="96c0d-113">从 Azure 服务中选择 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="96c0d-114">在 **管理** 下，选择 **企业应用程序**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="96c0d-115">搜索访问群体见解第一方应用程序 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 或名称 `Dynamics 365 AI for Customer Insights`。</span><span class="sxs-lookup"><span data-stu-id="96c0d-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="96c0d-116">如果您找到匹配的记录，这意味着存在访问群体见解的服务主体。</span><span class="sxs-lookup"><span data-stu-id="96c0d-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="96c0d-117">您无需再次创建。</span><span class="sxs-lookup"><span data-stu-id="96c0d-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="显示现有服务主体的屏幕截图。":::
   
6. <span data-ttu-id="96c0d-119">如果没有返回结果，请创建新的服务主体。</span><span class="sxs-lookup"><span data-stu-id="96c0d-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="96c0d-120">创建新的服务主体</span><span class="sxs-lookup"><span data-stu-id="96c0d-120">Create a new service principal</span></span>

1. <span data-ttu-id="96c0d-121">安装最新版本的 **Azure Active Directory PowerShell for Graph**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="96c0d-122">有关详细信息，请参阅[安装 Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)。</span><span class="sxs-lookup"><span data-stu-id="96c0d-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="96c0d-123">在您的电脑上，选择键盘上的 Windows 键并搜索 **Windows PowerShell**，然后单击 **以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="96c0d-124">在打开的 PowerShell 窗口中，输入 `Install-Module AzureAD`。</span><span class="sxs-lookup"><span data-stu-id="96c0d-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="96c0d-125">使用 Azure AD PowerShell 模块为访问群体见解创建服务主体。</span><span class="sxs-lookup"><span data-stu-id="96c0d-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="96c0d-126">在 PowerShell 窗口中，输入 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`。</span><span class="sxs-lookup"><span data-stu-id="96c0d-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="96c0d-127">将“您的租户 ID”替换为您要在其中创建服务主体的租户的实际 ID。</span><span class="sxs-lookup"><span data-stu-id="96c0d-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="96c0d-128">环境名称参数 `AzureEnvironmentName` 是可选的。</span><span class="sxs-lookup"><span data-stu-id="96c0d-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="96c0d-129">输入 `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`。</span><span class="sxs-lookup"><span data-stu-id="96c0d-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="96c0d-130">此命令将在所选租户上为访问群体见解创建服务主体。</span><span class="sxs-lookup"><span data-stu-id="96c0d-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="96c0d-131">向服务主体授予访问存储帐户的权限</span><span class="sxs-lookup"><span data-stu-id="96c0d-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="96c0d-132">转到 Azure 门户，向服务主体授予要在访问群体见解中使用的存储帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="96c0d-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="96c0d-133">转到 [Azure 管理门户](https://portal.azure.com)，然后登录到您的组织。</span><span class="sxs-lookup"><span data-stu-id="96c0d-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="96c0d-134">打开您希望访问群体见解的服务主体对其具有访问权限的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="96c0d-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="96c0d-135">从导航窗格中选择 **访问控制（标识和访问管理）**，然后选择 **添加** > **添加角色分配**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="显示添加角色分配时的 Azure 门户的屏幕截图。":::
   
1. <span data-ttu-id="96c0d-137">在 **添加角色分配** 窗格中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="96c0d-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="96c0d-138">角色：*存储 Blob 数据参与者*</span><span class="sxs-lookup"><span data-stu-id="96c0d-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="96c0d-139">向以下项分配访问权限：*用户、组或服务主体*</span><span class="sxs-lookup"><span data-stu-id="96c0d-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="96c0d-140">选择：*Dynamics 365 AI for Customer Insights*（[您创建的服务主体](#create-a-new-service-principal)）</span><span class="sxs-lookup"><span data-stu-id="96c0d-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="96c0d-141">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-141">Select **Save**.</span></span>

<span data-ttu-id="96c0d-142">传播更改最多可能需要 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="96c0d-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="96c0d-143">在附加到访问群体见解的存储帐户中输入 Azure 资源 ID 或 Azure 订阅详细信息。</span><span class="sxs-lookup"><span data-stu-id="96c0d-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="96c0d-144">在访问群体见解中附加 Azure Data Lake 存储帐户以[存储输出数据](manage-environments.md)或[将其用作数据源](connect-common-data-service-lake.md)。</span><span class="sxs-lookup"><span data-stu-id="96c0d-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="96c0d-145">通过选择 Azure Data Lake 选项，您可以在基于资源或基于订阅的方法之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="96c0d-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="96c0d-146">按照以下步骤提供所选方法的必要信息。</span><span class="sxs-lookup"><span data-stu-id="96c0d-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="96c0d-147">基于资源的存储帐户连接</span><span class="sxs-lookup"><span data-stu-id="96c0d-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="96c0d-148">转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。</span><span class="sxs-lookup"><span data-stu-id="96c0d-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="96c0d-149">在导航窗格上转到 **设置** > **属性**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="96c0d-150">复制存储帐户资源 ID 值。</span><span class="sxs-lookup"><span data-stu-id="96c0d-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="复制存储帐户资源 ID。":::

1. <span data-ttu-id="96c0d-152">在访问群体见解中，在存储帐户连接屏幕中显示的资源字段中插入资源 ID。</span><span class="sxs-lookup"><span data-stu-id="96c0d-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="输入存储帐户资源 ID 信息。":::   
   
1. <span data-ttu-id="96c0d-154">继续执行访问群体见解中的剩余步骤以附加存储帐户。</span><span class="sxs-lookup"><span data-stu-id="96c0d-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="96c0d-155">基于订阅的存储帐户连接</span><span class="sxs-lookup"><span data-stu-id="96c0d-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="96c0d-156">转到 [Azure 管理门户](https://portal.azure.com)，登录到您的订阅并打开存储帐户。</span><span class="sxs-lookup"><span data-stu-id="96c0d-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="96c0d-157">在导航窗格上转到 **设置** > **属性**。</span><span class="sxs-lookup"><span data-stu-id="96c0d-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="96c0d-158">查看 **订阅**、**资源组** 和存储帐户的 **名称**，以确保在访问群体见解中选择正确的值。</span><span class="sxs-lookup"><span data-stu-id="96c0d-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="96c0d-159">在访问群体见解中，在附加存储帐户时，请选择相应字段的值。</span><span class="sxs-lookup"><span data-stu-id="96c0d-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="输入存储帐户资源 ID 信息。":::
   
1. <span data-ttu-id="96c0d-161">继续执行访问群体见解中的剩余步骤以附加存储帐户。</span><span class="sxs-lookup"><span data-stu-id="96c0d-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
