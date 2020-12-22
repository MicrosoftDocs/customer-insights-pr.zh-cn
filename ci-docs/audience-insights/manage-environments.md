---
title: 创建和管理环境
description: 了解如何注册服务以及如何管理环境。
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644122"
---
# <a name="manage-environments"></a><span data-ttu-id="8f919-103">管理环境</span><span class="sxs-lookup"><span data-stu-id="8f919-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8f919-104">本文介绍如何创建新的组织以及如何预配环境。</span><span class="sxs-lookup"><span data-stu-id="8f919-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="8f919-105">注册和创建组织</span><span class="sxs-lookup"><span data-stu-id="8f919-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="8f919-106">转到 [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 网站。</span><span class="sxs-lookup"><span data-stu-id="8f919-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="8f919-107">选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="8f919-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="8f919-108">选择首选注册方案，然后选择相应链接。</span><span class="sxs-lookup"><span data-stu-id="8f919-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="8f919-109">接受条款和条件，然后选择 **继续** 开始创建组织。</span><span class="sxs-lookup"><span data-stu-id="8f919-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="8f919-110">环境创建后，您将被重定向到 [Customer Insights](https://home.ci.ai.dynamics.com)。</span><span class="sxs-lookup"><span data-stu-id="8f919-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="8f919-111">使用演示环境探索该应用，或者按照下一节中的步骤创建一个新的环境。</span><span class="sxs-lookup"><span data-stu-id="8f919-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="8f919-112">指定环境设置之后，选择 **创建**。</span><span class="sxs-lookup"><span data-stu-id="8f919-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="8f919-113">您将在成功创建环境后登录。</span><span class="sxs-lookup"><span data-stu-id="8f919-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="8f919-114">在现有组织中创建环境</span><span class="sxs-lookup"><span data-stu-id="8f919-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="8f919-115">创建新环境的方式包含以下两种：</span><span class="sxs-lookup"><span data-stu-id="8f919-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="8f919-116">您可以指定一个全新的配置，也可以复制现有环境的一些配置设置。</span><span class="sxs-lookup"><span data-stu-id="8f919-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="8f919-117">创建环境：</span><span class="sxs-lookup"><span data-stu-id="8f919-117">To create an environment:</span></span>

1. <span data-ttu-id="8f919-118">在应用标题中选择 **设置** 符号。</span><span class="sxs-lookup"><span data-stu-id="8f919-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="8f919-119">选择 **新建环境**。</span><span class="sxs-lookup"><span data-stu-id="8f919-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8f919-120">![环境设置](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="8f919-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="8f919-121">在 **创建新环境** 对话框中，选择 **新建环境**。</span><span class="sxs-lookup"><span data-stu-id="8f919-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="8f919-122">如果要 [从当前环境复制数据](#additional-considerations-for-copy-configuration-preview)，请选择 **从现有环境复制**。</span><span class="sxs-lookup"><span data-stu-id="8f919-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="8f919-123">您将看到组织中可以从中复制数据的所有可用环境的列表。</span><span class="sxs-lookup"><span data-stu-id="8f919-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="8f919-124">提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8f919-124">Provide the following details:</span></span>
   - <span data-ttu-id="8f919-125">**名称**：此环境的名称。</span><span class="sxs-lookup"><span data-stu-id="8f919-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="8f919-126">如果已从现有环境中复制，则此字段已填写，但可以更改。</span><span class="sxs-lookup"><span data-stu-id="8f919-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="8f919-127">**区域**：要在其中部署和托管该服务的区域。</span><span class="sxs-lookup"><span data-stu-id="8f919-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="8f919-128">**类型**：选择是要创建生产环境还是沙盒环境。</span><span class="sxs-lookup"><span data-stu-id="8f919-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="8f919-129">或者，您可以选择 **高级设置**：</span><span class="sxs-lookup"><span data-stu-id="8f919-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="8f919-130">**保存所有数据到**：指定要存储从 Customer Insights 生成的输出数据的位置。</span><span class="sxs-lookup"><span data-stu-id="8f919-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="8f919-131">有两个选项：**Customer Insights 存储**（Customer Insights 团队托管的 Azure Data Lake）和 **Azure Data Lake Storage Gen2**（您自己的 Azure Data Lake Storage）。</span><span class="sxs-lookup"><span data-stu-id="8f919-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="8f919-132">默认情况下已选择 Customer Insights 存储选项。</span><span class="sxs-lookup"><span data-stu-id="8f919-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8f919-133">将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输到适合该 Azure 存储帐户的地理位置并存储在其中，此位置可能与 Dynamics 365 Customer Insights 中存储数据的位置不同。</span><span class="sxs-lookup"><span data-stu-id="8f919-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="8f919-134">有关详细信息，请访问 Microsoft 信任中心。</span><span class="sxs-lookup"><span data-stu-id="8f919-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="8f919-135">现在，引入的实体始终存储在 Customer Insights 托管数据湖中。</span><span class="sxs-lookup"><span data-stu-id="8f919-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="8f919-136">我们仅支持在创建环境时选择的同一 Azure 区域中的 Azure Data Lake Gen2 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="8f919-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="8f919-137">我们仅支持 Azure Data Lake Gen2 分层命名空间 (HNS) 支持的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="8f919-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="8f919-138">对于 Azure Data Lake Storage Gen2 选项，在进行身份验证时，您可以在基于资源的选项和基于订阅的选项之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="8f919-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="8f919-139">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="8f919-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8f919-140">**容器** 名称不可更改，该名称将为“customerinsights”。</span><span class="sxs-lookup"><span data-stu-id="8f919-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="8f919-141">如果要使用 [预测](predictions.md)，请在 **使用预测** 下的 **服务器地址** 字段中输入 Common Data Service 实例 URL。</span><span class="sxs-lookup"><span data-stu-id="8f919-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="8f919-142">当您运行流程（例如数据引入或客户细分创建）时，将在上述指定的存储帐户中创建相应的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8f919-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="8f919-143">数据文件和 model.json 文件将根据您运行的流程创建并添加到相应的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8f919-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="8f919-144">如果您创建了多个 Customer Insights 环境并选择将这些环境中的输出实体保存在存储帐户中，将为容器中具有 ci_<environmentid> 的每个环境创建单独的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8f919-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="8f919-145">复制配置的其他注意事项（预览）</span><span class="sxs-lookup"><span data-stu-id="8f919-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="8f919-146">复制以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="8f919-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="8f919-147">功能配置</span><span class="sxs-lookup"><span data-stu-id="8f919-147">Feature configurations</span></span>
- <span data-ttu-id="8f919-148">引入/导入的数据源</span><span class="sxs-lookup"><span data-stu-id="8f919-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="8f919-149">数据统一（映射、匹配、合并）配置</span><span class="sxs-lookup"><span data-stu-id="8f919-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="8f919-150">客户细分</span><span class="sxs-lookup"><span data-stu-id="8f919-150">Segments</span></span>
- <span data-ttu-id="8f919-151">度量</span><span class="sxs-lookup"><span data-stu-id="8f919-151">Measures</span></span>
- <span data-ttu-id="8f919-152">关系</span><span class="sxs-lookup"><span data-stu-id="8f919-152">Relationships</span></span>
- <span data-ttu-id="8f919-153">活动</span><span class="sxs-lookup"><span data-stu-id="8f919-153">Activities</span></span>
- <span data-ttu-id="8f919-154">搜索和筛选索引</span><span class="sxs-lookup"><span data-stu-id="8f919-154">Search & filter Index</span></span>
- <span data-ttu-id="8f919-155">导出目标</span><span class="sxs-lookup"><span data-stu-id="8f919-155">Export destinations</span></span>
- <span data-ttu-id="8f919-156">计划刷新</span><span class="sxs-lookup"><span data-stu-id="8f919-156">Scheduled refresh</span></span>
- <span data-ttu-id="8f919-157">扩充</span><span class="sxs-lookup"><span data-stu-id="8f919-157">Enrichments</span></span>
- <span data-ttu-id="8f919-158">模型管理</span><span class="sxs-lookup"><span data-stu-id="8f919-158">Model management</span></span>
- <span data-ttu-id="8f919-159">角色分配</span><span class="sxs-lookup"><span data-stu-id="8f919-159">Role assignments</span></span>

<span data-ttu-id="8f919-160">*不* 复制以下设置：</span><span class="sxs-lookup"><span data-stu-id="8f919-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="8f919-161">客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f919-161">Customer profiles.</span></span>
- <span data-ttu-id="8f919-162">数据源凭据。</span><span class="sxs-lookup"><span data-stu-id="8f919-162">Data source credentials.</span></span> <span data-ttu-id="8f919-163">您必须为每个数据源提供凭据，并手动刷新数据源。</span><span class="sxs-lookup"><span data-stu-id="8f919-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="8f919-164">Common Data Model 文件夹和 Common Data Service 托管湖中的数据源。</span><span class="sxs-lookup"><span data-stu-id="8f919-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="8f919-165">您必须使用与源环境中相同的名称手动创建这些数据源。</span><span class="sxs-lookup"><span data-stu-id="8f919-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="8f919-166">复制环境时，您会看到一条确认消息，显示新环境已创建。</span><span class="sxs-lookup"><span data-stu-id="8f919-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="8f919-167">选择 **转到数据源** 查看数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="8f919-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="8f919-168">所有数据源都将显示 **需要凭据** 状态。</span><span class="sxs-lookup"><span data-stu-id="8f919-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="8f919-169">编辑数据源并输入凭据来刷新。</span><span class="sxs-lookup"><span data-stu-id="8f919-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8f919-170">![数据源已复制](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="8f919-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="8f919-171">刷新数据源后，请转到 **数据** > **统一**。</span><span class="sxs-lookup"><span data-stu-id="8f919-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="8f919-172">在这里，您将找到源环境中的设置。</span><span class="sxs-lookup"><span data-stu-id="8f919-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="8f919-173">根据需要进行编辑，或选择 **运行** 启动数据统一流程，创建统一的客户实体。</span><span class="sxs-lookup"><span data-stu-id="8f919-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="8f919-174">当数据统一完成时，再转到 **度量** 和 **细分** 进行刷新。</span><span class="sxs-lookup"><span data-stu-id="8f919-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="8f919-175">编辑现有环境</span><span class="sxs-lookup"><span data-stu-id="8f919-175">Edit an existing environment</span></span>

<span data-ttu-id="8f919-176">您可以编辑现有环境的某些详细信息。</span><span class="sxs-lookup"><span data-stu-id="8f919-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="8f919-177">转到 **管理** > **系统** > **关于**。</span><span class="sxs-lookup"><span data-stu-id="8f919-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="8f919-178">选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="8f919-178">Select **Edit**.</span></span>

3. <span data-ttu-id="8f919-179">您可以更新环境的 **显示名称**，但不能更改 **区域** 或 **类型**。</span><span class="sxs-lookup"><span data-stu-id="8f919-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="8f919-180">如果环境配置为在Azure Data Lake Storage Gen2 中存储数据，则可以更新 **帐户密钥**。</span><span class="sxs-lookup"><span data-stu-id="8f919-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="8f919-181">但是，您不能更改 **帐户名称** 或 **容器** 名称。</span><span class="sxs-lookup"><span data-stu-id="8f919-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="8f919-182">或者，您可以从基于帐户密钥的连接更新到基于资源或基于订阅的连接。</span><span class="sxs-lookup"><span data-stu-id="8f919-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="8f919-183">升级后，您将无法在更新后还原到帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="8f919-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="8f919-184">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="8f919-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8f919-185">在更新连接时，无法更改 **容器** 信息。</span><span class="sxs-lookup"><span data-stu-id="8f919-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="8f919-186">重置现有环境</span><span class="sxs-lookup"><span data-stu-id="8f919-186">Reset an existing environment</span></span>

<span data-ttu-id="8f919-187">如果您想要删除所有配置并删除引入的数据，可以将环境重置为空状态。</span><span class="sxs-lookup"><span data-stu-id="8f919-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="8f919-188">转到 **管理** > **系统** > **关于**。</span><span class="sxs-lookup"><span data-stu-id="8f919-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="8f919-189">选择 **重置**。</span><span class="sxs-lookup"><span data-stu-id="8f919-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="8f919-190">若要确认删除，请输入环境名称并选择 **重置**。</span><span class="sxs-lookup"><span data-stu-id="8f919-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="8f919-191">删除现有环境</span><span class="sxs-lookup"><span data-stu-id="8f919-191">Delete an existing environment</span></span>

1. <span data-ttu-id="8f919-192">转到 **管理** > **系统** > **关于**。</span><span class="sxs-lookup"><span data-stu-id="8f919-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="8f919-193">选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="8f919-193">Select **Delete**.</span></span>

1. <span data-ttu-id="8f919-194">若要确认删除，请输入环境名称，然后选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="8f919-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
