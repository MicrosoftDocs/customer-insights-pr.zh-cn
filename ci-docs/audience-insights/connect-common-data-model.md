---
title: 将 Common Data Model 数据连接到 Azure Data Lake 帐户
description: 使用 Azure Data Lake Storage 处理 Common Data Model 数据。
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643447"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="15bd3-103">使用 Azure Data Lake 帐户连接到 Common Data Model 文件夹</span><span class="sxs-lookup"><span data-stu-id="15bd3-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="15bd3-104">本文提供有关如何使用 Azure Data Lake Storage Gen2 帐户从 Common Data Model 文件夹中引入数据的信息。</span><span class="sxs-lookup"><span data-stu-id="15bd3-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="15bd3-105">重要考虑因素</span><span class="sxs-lookup"><span data-stu-id="15bd3-105">Important considerations</span></span>

- <span data-ttu-id="15bd3-106">Azure Data Lake 中的数据需要遵守 Common Data Model 标准。</span><span class="sxs-lookup"><span data-stu-id="15bd3-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="15bd3-107">目前不支持其他格式。</span><span class="sxs-lookup"><span data-stu-id="15bd3-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="15bd3-108">数据引入将以独占方式支持 Azure Data Lake *Gen2* 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="15bd3-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="15bd3-109">您不能使用 Azure Data Lake Gen1 存储帐户来引入数据。</span><span class="sxs-lookup"><span data-stu-id="15bd3-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="15bd3-110">若要使用 Azure 服务主体进行身份验证，请确保已在您的租户中配置它。</span><span class="sxs-lookup"><span data-stu-id="15bd3-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="15bd3-111">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="15bd3-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="15bd3-112">您想要从中连接和引入数据的 Azure Data Lake 必须位于 Dynamics 365 Customer Insights 环境所在的同一 Azure 区域中。</span><span class="sxs-lookup"><span data-stu-id="15bd3-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="15bd3-113">不支持从不同的 Azure 区域中的 Data Lake 连接到 Common Data Model 文件夹。</span><span class="sxs-lookup"><span data-stu-id="15bd3-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="15bd3-114">若要了解环境的 Azure 区域，请在访问群体见解中转到 **管理员** > **系统** > **关于**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="15bd3-115">联机服务中存储的数据可以存储在与在 Dynamics 365 Customer Insights 中处理或存储数据不同的位置。</span><span class="sxs-lookup"><span data-stu-id="15bd3-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="15bd3-116">导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="15bd3-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="15bd3-117">连接到 Common Data Model 文件夹</span><span class="sxs-lookup"><span data-stu-id="15bd3-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="15bd3-118">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="15bd3-119">选择 **添加数据源**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="15bd3-120">选择 **连接到 Common Data Model 文件夹**，输入数据源的 **名称**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="15bd3-121">您可以在使用基于资源的选项进行身份验证和基于订阅的选项进行身份验证之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="15bd3-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="15bd3-122">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="15bd3-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="15bd3-123">输入 **容器** 信息并选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15bd3-124">![用于输入 Azure Data Lake 的连接详细信息的对话框](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="15bd3-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="15bd3-125">在 **选择 Common Data Model 文件夹** 对话框中，选择要从中导入数据的 model.json 文件，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="15bd3-126">与环境中其他数据源相关联的任何 model.json 文件都不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="15bd3-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="15bd3-127">您将获得所选 model.json 文件中可用实体的列表。</span><span class="sxs-lookup"><span data-stu-id="15bd3-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="15bd3-128">您可以查看并从可用实体列表中进行选择，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="15bd3-129">将从新的数据源中引入所有选定实体。</span><span class="sxs-lookup"><span data-stu-id="15bd3-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15bd3-130">![其中显示了 model.json 文件中的实体的列表的对话框](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="15bd3-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="15bd3-131">指示想要哪些数据实体启用数据分析，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="15bd3-132">数据分析可启用分析和其他功能。</span><span class="sxs-lookup"><span data-stu-id="15bd3-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="15bd3-133">您可以选择整个实体（选择实体中的所有属性），也可以选择所选的某些属性。</span><span class="sxs-lookup"><span data-stu-id="15bd3-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="15bd3-134">默认情况下，不会为数据分析启用任何实体。</span><span class="sxs-lookup"><span data-stu-id="15bd3-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15bd3-135">![显示数据分析的对话框](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="15bd3-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="15bd3-136">保存所作选择后，**数据源** 页面将打开。</span><span class="sxs-lookup"><span data-stu-id="15bd3-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="15bd3-137">现在，您应该会看到作为数据源的 Common Data Model 文件夹连接。</span><span class="sxs-lookup"><span data-stu-id="15bd3-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="15bd3-138">Model.json 文件只能与同一环境中的一个数据源相关联。</span><span class="sxs-lookup"><span data-stu-id="15bd3-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="15bd3-139">但是，相同的 model.json 文件可用于多个环境中的数据源。</span><span class="sxs-lookup"><span data-stu-id="15bd3-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="15bd3-140">编辑 Common Data Model 文件夹数据源</span><span class="sxs-lookup"><span data-stu-id="15bd3-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="15bd3-141">您可以更新包含 Common Data Model 文件夹的存储帐户的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="15bd3-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="15bd3-142">您还可以更改 model.json 文件。</span><span class="sxs-lookup"><span data-stu-id="15bd3-142">You may also change the model.json file.</span></span> <span data-ttu-id="15bd3-143">若要连接到除存储帐户之外的容器，或更改帐户名称，应[创建新的数据源连接](#connect-to-a-common-data-model-folder)。</span><span class="sxs-lookup"><span data-stu-id="15bd3-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="15bd3-144">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="15bd3-145">选择要更新的数据源旁边的省略号。</span><span class="sxs-lookup"><span data-stu-id="15bd3-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="15bd3-146">从列表中选择 **编辑** 选项。</span><span class="sxs-lookup"><span data-stu-id="15bd3-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="15bd3-147">（可选）更新 **访问密钥**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="15bd3-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![用于编辑和更新现有数据源的访问密钥的对话框](media/edit-access-key.png)

5. <span data-ttu-id="15bd3-149">或者，您可以从帐户密钥连接更新到基于资源或基于订阅的连接。</span><span class="sxs-lookup"><span data-stu-id="15bd3-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="15bd3-150">有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="15bd3-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="15bd3-151">在更新连接时，无法更改 **容器** 信息。</span><span class="sxs-lookup"><span data-stu-id="15bd3-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15bd3-152">![用于输入 Azure Data Lake 的连接详细信息的对话框](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="15bd3-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="15bd3-153">（可选）选择其中包含容器中的另一组实体的另一个 model.json 文件。</span><span class="sxs-lookup"><span data-stu-id="15bd3-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="15bd3-154">或者，您可以选择要引入的其他实体。</span><span class="sxs-lookup"><span data-stu-id="15bd3-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="15bd3-155">如果没有任何依赖项，还可以删除任何已选定的实体。</span><span class="sxs-lookup"><span data-stu-id="15bd3-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="15bd3-156">如果需要依赖现有 model.json 文件和实体集，将显示错误消息，并且不能选择其他 model.json 文件。</span><span class="sxs-lookup"><span data-stu-id="15bd3-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="15bd3-157">更改 model.json 文件或使用要使用的 model.json 文件创建新数据源之前，删除这些依赖项，以免删除依赖项。</span><span class="sxs-lookup"><span data-stu-id="15bd3-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="15bd3-158">或者，您可以选择其他属性或实体以启用数据分析或禁用所选项。</span><span class="sxs-lookup"><span data-stu-id="15bd3-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
