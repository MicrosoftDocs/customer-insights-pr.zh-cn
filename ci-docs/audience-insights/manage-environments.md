---
title: 创建和管理环境
description: 了解如何注册服务以及如何管理环境。
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887975"
---
# <a name="manage-environments"></a><span data-ttu-id="db026-103">管理环境</span><span class="sxs-lookup"><span data-stu-id="db026-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="db026-104">本文介绍如何创建新的组织以及如何预配环境。</span><span class="sxs-lookup"><span data-stu-id="db026-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="db026-105">注册和创建组织</span><span class="sxs-lookup"><span data-stu-id="db026-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="db026-106">转到 [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 网站。</span><span class="sxs-lookup"><span data-stu-id="db026-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="db026-107">选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="db026-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="db026-108">选择首选注册方案，然后选择相应链接。</span><span class="sxs-lookup"><span data-stu-id="db026-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="db026-109">接受条款和条件，然后选择 **继续** 开始创建组织。</span><span class="sxs-lookup"><span data-stu-id="db026-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="db026-110">环境创建后，您将被重定向到 [Customer Insights](https://home.ci.ai.dynamics.com)。</span><span class="sxs-lookup"><span data-stu-id="db026-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="db026-111">使用演示环境探索该应用，或者按照下一节中的步骤创建一个新的环境。</span><span class="sxs-lookup"><span data-stu-id="db026-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="db026-112">指定环境设置之后，选择 **创建**。</span><span class="sxs-lookup"><span data-stu-id="db026-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="db026-113">您将在成功创建环境后登录。</span><span class="sxs-lookup"><span data-stu-id="db026-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="db026-114">在现有组织中创建环境</span><span class="sxs-lookup"><span data-stu-id="db026-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="db026-115">创建新环境的方式包含以下两种：</span><span class="sxs-lookup"><span data-stu-id="db026-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="db026-116">您可以指定一个全新的配置，也可以复制现有环境的一些配置设置。</span><span class="sxs-lookup"><span data-stu-id="db026-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="db026-117">组织可以为每个 Customer Insights 许可证创建 *两个* 环境。</span><span class="sxs-lookup"><span data-stu-id="db026-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="db026-118">如果您的组织购买了多个许可证，请[联系我们的支持团队](https://go.microsoft.com/fwlink/?linkid=2079641)，以增加可用环境的数量。</span><span class="sxs-lookup"><span data-stu-id="db026-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="db026-119">有关容量和加载项容量的更多信息，请下载 [Dynamics 365 许可指南 ](https://go.microsoft.com/fwlink/?LinkId=866544)。</span><span class="sxs-lookup"><span data-stu-id="db026-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="db026-120">创建环境：</span><span class="sxs-lookup"><span data-stu-id="db026-120">To create an environment:</span></span>

1. <span data-ttu-id="db026-121">选择应用标题中的 **环境** 选择器。</span><span class="sxs-lookup"><span data-stu-id="db026-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="db026-122">选择 **新建**。</span><span class="sxs-lookup"><span data-stu-id="db026-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="db026-123">![环境设置](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="db026-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="db026-124">在 **创建新环境** 对话框中，选择 **新建环境**。</span><span class="sxs-lookup"><span data-stu-id="db026-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="db026-125">如果要 [从当前环境复制数据](#considerations-for-copy-configuration-preview)，请选择 **从现有环境复制**。</span><span class="sxs-lookup"><span data-stu-id="db026-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="db026-126">您将看到组织中可以从中复制数据的所有可用环境的列表。</span><span class="sxs-lookup"><span data-stu-id="db026-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="db026-127">提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="db026-127">Provide the following details:</span></span>
   - <span data-ttu-id="db026-128">**名称**：此环境的名称。</span><span class="sxs-lookup"><span data-stu-id="db026-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="db026-129">如果已从现有环境中复制，则此字段已填写，但可以更改。</span><span class="sxs-lookup"><span data-stu-id="db026-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="db026-130">**区域**：要在其中部署和托管该服务的区域。</span><span class="sxs-lookup"><span data-stu-id="db026-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="db026-131">**类型**：选择是要创建生产环境还是沙盒环境。</span><span class="sxs-lookup"><span data-stu-id="db026-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="db026-132">或者，您可以选择 **高级设置**：</span><span class="sxs-lookup"><span data-stu-id="db026-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="db026-133">**保存所有数据到**：指定要存储从 Customer Insights 生成的输出数据的位置。</span><span class="sxs-lookup"><span data-stu-id="db026-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="db026-134">有两个选项：**Customer Insights 存储**（Customer Insights 团队托管的 Azure Data Lake）和 **Azure Data Lake Storage Gen2**（您自己的 Azure Data Lake Storage）。</span><span class="sxs-lookup"><span data-stu-id="db026-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="db026-135">默认情况下已选择 Customer Insights 存储选项。</span><span class="sxs-lookup"><span data-stu-id="db026-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="db026-136">将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输到适合该 Azure 存储帐户的地理位置并存储在其中，此位置可能与 Dynamics 365 Customer Insights 中存储数据的位置不同。</span><span class="sxs-lookup"><span data-stu-id="db026-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="db026-137">有关详细信息，请访问 Microsoft 信任中心。</span><span class="sxs-lookup"><span data-stu-id="db026-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="db026-138">现在，引入的实体始终存储在 Customer Insights 托管数据湖中。</span><span class="sxs-lookup"><span data-stu-id="db026-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="db026-139">我们仅支持在创建环境时选择的同一 Azure 区域中的 Azure Data Lake Gen2 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="db026-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="db026-140">我们仅支持 Azure Data Lake Gen2 分层命名空间 (HNS) 支持的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="db026-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="db026-141">对于 Azure Data Lake Storage Gen2 选项，在进行身份验证时，您可以在基于资源的选项和基于订阅的选项之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="db026-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="db026-142">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="db026-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="db026-143">**容器** 名称不可更改，该名称将为“customerinsights”。</span><span class="sxs-lookup"><span data-stu-id="db026-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="db026-144">如果您想使用 [预测](predictions.md)，请配置根据 Microsoft Dataverse 与应用程序和解决方案的数据共享，或启用本地数据源的数据引入，在 **配置与 Microsoft Dataverse 的数据共享并启用其他功能** 下面提供 Microsoft Dataverse 环境 URL。</span><span class="sxs-lookup"><span data-stu-id="db026-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="db026-145">选择 **启用数据共享** 以与 Microsoft Dataverse 托管 Data Lake 共享 Customer Insights 输出数据。</span><span class="sxs-lookup"><span data-stu-id="db026-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="db026-146">将所有数据保存到自己的 Azure Data Lake Storage 时，当前不支持与 Microsoft Dataverse 托管 Data Lake 共享数据。</span><span class="sxs-lookup"><span data-stu-id="db026-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="db026-147">启用与 Microsoft Dataverse 托管 Data Lake 的数据共享时，当前不支持[预测实体中缺少的值 ](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="db026-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="db026-148">![用于启用与 Microsoft Dataverse 的数据共享的配置选项](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="db026-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="db026-149">当您运行流程（例如数据引入或客户细分创建）时，将在上述指定的存储帐户中创建相应的文件夹。</span><span class="sxs-lookup"><span data-stu-id="db026-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="db026-150">数据文件和 model.json 文件将根据您运行的流程创建并添加到相应的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="db026-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="db026-151">如果您创建了多个 Customer Insights 环境并选择将这些环境中的输出实体保存在存储帐户中，将为容器中具有 ci_<environmentid> 的每个环境创建单独的文件夹。</span><span class="sxs-lookup"><span data-stu-id="db026-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="db026-152">副本配置的注意事项（预览版）</span><span class="sxs-lookup"><span data-stu-id="db026-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="db026-153">复制以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="db026-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="db026-154">功能配置</span><span class="sxs-lookup"><span data-stu-id="db026-154">Feature configurations</span></span>
- <span data-ttu-id="db026-155">引入/导入的数据源</span><span class="sxs-lookup"><span data-stu-id="db026-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="db026-156">数据统一（映射、匹配、合并）配置</span><span class="sxs-lookup"><span data-stu-id="db026-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="db026-157">客户细分</span><span class="sxs-lookup"><span data-stu-id="db026-157">Segments</span></span>
- <span data-ttu-id="db026-158">度量</span><span class="sxs-lookup"><span data-stu-id="db026-158">Measures</span></span>
- <span data-ttu-id="db026-159">关系</span><span class="sxs-lookup"><span data-stu-id="db026-159">Relationships</span></span>
- <span data-ttu-id="db026-160">活动</span><span class="sxs-lookup"><span data-stu-id="db026-160">Activities</span></span>
- <span data-ttu-id="db026-161">搜索和筛选索引</span><span class="sxs-lookup"><span data-stu-id="db026-161">Search & filter Index</span></span>
- <span data-ttu-id="db026-162">导出目标</span><span class="sxs-lookup"><span data-stu-id="db026-162">Export destinations</span></span>
- <span data-ttu-id="db026-163">计划刷新</span><span class="sxs-lookup"><span data-stu-id="db026-163">Scheduled refresh</span></span>
- <span data-ttu-id="db026-164">扩充</span><span class="sxs-lookup"><span data-stu-id="db026-164">Enrichments</span></span>
- <span data-ttu-id="db026-165">模型管理</span><span class="sxs-lookup"><span data-stu-id="db026-165">Model management</span></span>
- <span data-ttu-id="db026-166">角色分配</span><span class="sxs-lookup"><span data-stu-id="db026-166">Role assignments</span></span>

<span data-ttu-id="db026-167">*不* 复制以下设置：</span><span class="sxs-lookup"><span data-stu-id="db026-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="db026-168">客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="db026-168">Customer profiles.</span></span>
- <span data-ttu-id="db026-169">数据源凭据。</span><span class="sxs-lookup"><span data-stu-id="db026-169">Data source credentials.</span></span> <span data-ttu-id="db026-170">您必须为每个数据源提供凭据，并手动刷新数据源。</span><span class="sxs-lookup"><span data-stu-id="db026-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="db026-171">Common Data Model 文件夹和 Common Data Service 托管湖中的数据源。</span><span class="sxs-lookup"><span data-stu-id="db026-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="db026-172">您必须使用与源环境中相同的名称手动创建这些数据源。</span><span class="sxs-lookup"><span data-stu-id="db026-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="db026-173">复制环境时，您会看到一条确认消息，显示新环境已创建。</span><span class="sxs-lookup"><span data-stu-id="db026-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="db026-174">选择 **转到数据源** 查看数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="db026-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="db026-175">所有数据源都将显示 **需要凭据** 状态。</span><span class="sxs-lookup"><span data-stu-id="db026-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="db026-176">编辑数据源并输入凭据来刷新。</span><span class="sxs-lookup"><span data-stu-id="db026-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="db026-177">![数据源已复制](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="db026-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="db026-178">刷新数据源后，请转到 **数据** > **统一**。</span><span class="sxs-lookup"><span data-stu-id="db026-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="db026-179">在这里，您将找到源环境中的设置。</span><span class="sxs-lookup"><span data-stu-id="db026-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="db026-180">根据需要进行编辑，或选择 **运行** 启动数据统一流程，创建统一的客户实体。</span><span class="sxs-lookup"><span data-stu-id="db026-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="db026-181">当数据统一完成时，再转到 **度量** 和 **细分** 进行刷新。</span><span class="sxs-lookup"><span data-stu-id="db026-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="db026-182">编辑现有环境</span><span class="sxs-lookup"><span data-stu-id="db026-182">Edit an existing environment</span></span>

<span data-ttu-id="db026-183">您可以编辑现有环境的某些详细信息。</span><span class="sxs-lookup"><span data-stu-id="db026-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="db026-184">选择应用标题中的 **环境** 选择器。</span><span class="sxs-lookup"><span data-stu-id="db026-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="db026-185">选择 **编辑** 图标。</span><span class="sxs-lookup"><span data-stu-id="db026-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="db026-186">在 **编辑环境** 框中，可以更新环境的 **显示名称**，但不能更改 **区域** 或 **类型**。</span><span class="sxs-lookup"><span data-stu-id="db026-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="db026-187">如果环境配置为在Azure Data Lake Storage Gen2 中存储数据，则可以更新 **帐户密钥**。</span><span class="sxs-lookup"><span data-stu-id="db026-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="db026-188">但是，您不能更改 **帐户名称** 或 **容器** 名称。</span><span class="sxs-lookup"><span data-stu-id="db026-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="db026-189">或者，您可以从基于帐户密钥的连接更新到基于资源或基于订阅的连接。</span><span class="sxs-lookup"><span data-stu-id="db026-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="db026-190">升级后，您将无法在更新后还原到帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="db026-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="db026-191">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="db026-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="db026-192">在更新连接时，无法更改 **容器** 信息。</span><span class="sxs-lookup"><span data-stu-id="db026-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="db026-193">（可选）您可以在 **配置与 Microsoft Dataverse 的数据共享并启用其他功能** 下面提供 Microsoft Dataverse 环境 URL。</span><span class="sxs-lookup"><span data-stu-id="db026-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="db026-194">这些功能包括基于应用和解决方案与 Microsoft Dataverse 共享数据、本地数据源数据引入或使用[预测](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="db026-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="db026-195">选择 **启用数据共享** 以与 Microsoft Dataverse 托管 Data Lake 共享 Customer Insights 输出数据。</span><span class="sxs-lookup"><span data-stu-id="db026-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="db026-196">将所有数据保存到自己的 Azure Data Lake Storage 时，当前不支持与 Microsoft Dataverse 托管 Data Lake 共享数据。</span><span class="sxs-lookup"><span data-stu-id="db026-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="db026-197">当您启用与 Microsoft Dataverse 托管 Data Lake 的数据共享时，当前不支持[预测实体中缺少的值](predictions.md)。</span><span class="sxs-lookup"><span data-stu-id="db026-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="db026-198">启用与 Microsoft Dataverse 共享数据后，将触发数据源和其他流程的完全刷新。</span><span class="sxs-lookup"><span data-stu-id="db026-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="db026-199">如果流程当前正在运行并且已排队，则您将看不到用于启用与 Microsoft Dataverse 共享数据的选项。</span><span class="sxs-lookup"><span data-stu-id="db026-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="db026-200">您可以等待这些流程完成或取消它们，以启用数据共享。</span><span class="sxs-lookup"><span data-stu-id="db026-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="用于启用与 Microsoft Dataverse 的数据共享的配置选项。":::
   
   <span data-ttu-id="db026-202">当您运行流程（例如数据引入或客户细分创建）时，将在上述指定的存储帐户中创建相应的文件夹。</span><span class="sxs-lookup"><span data-stu-id="db026-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="db026-203">数据文件和 model.json 文件将创建并添加到相应的子文件夹中，具体取决于您运行的流程。</span><span class="sxs-lookup"><span data-stu-id="db026-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="db026-204">重置现有环境</span><span class="sxs-lookup"><span data-stu-id="db026-204">Reset an existing environment</span></span>

<span data-ttu-id="db026-205">作为管理员，如果您想要删除所有配置并删除引入的数据，可以将环境重置为空状态。</span><span class="sxs-lookup"><span data-stu-id="db026-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="db026-206">选择应用标题中的 **环境** 选择器。</span><span class="sxs-lookup"><span data-stu-id="db026-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="db026-207">选择要重置的环境，并选择省略号 **...**。</span><span class="sxs-lookup"><span data-stu-id="db026-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="db026-208">选择 **重置** 选项。</span><span class="sxs-lookup"><span data-stu-id="db026-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="db026-209">若要确认删除，请输入环境名称并选择 **重置**。</span><span class="sxs-lookup"><span data-stu-id="db026-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="db026-210">删除现有环境（仅适用于管理员）</span><span class="sxs-lookup"><span data-stu-id="db026-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="db026-211">作为管理员，您可以删除您管理的环境。</span><span class="sxs-lookup"><span data-stu-id="db026-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="db026-212">选择应用标题中的 **环境** 选择器。</span><span class="sxs-lookup"><span data-stu-id="db026-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="db026-213">选择要重置的环境，并选择省略号 **...**。</span><span class="sxs-lookup"><span data-stu-id="db026-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="db026-214">选择 **删除** 选项。</span><span class="sxs-lookup"><span data-stu-id="db026-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="db026-215">若要确认删除，请输入环境名称，然后选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="db026-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
