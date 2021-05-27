---
title: 将 Customer Insights 数据导出到 Azure Synapse Analytics
description: 了解如何配置到 Azure Synapse Analytics 的连接。
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977366"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="8924a-103">将数据导出到 Azure Synapse Analytics（预览版）</span><span class="sxs-lookup"><span data-stu-id="8924a-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="8924a-104">Azure Synapse 是一项分析服务，可加缩短跨数据存储和大型数据系统进行深入了解的时间。</span><span class="sxs-lookup"><span data-stu-id="8924a-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="8924a-105">您可以在 [Azure Synapse](/azure/synapse-analytics/overview-what-is) 中引入和使用您的 Customer Insights 数据。</span><span class="sxs-lookup"><span data-stu-id="8924a-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8924a-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="8924a-106">Prerequisites</span></span>

<span data-ttu-id="8924a-107">必须满足以下先决条件，才能配置从 Customer Insights 到 Azure Synapse 的连接。 </span><span class="sxs-lookup"><span data-stu-id="8924a-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="8924a-108">确保如上所述设置所有 **角色分配**。</span><span class="sxs-lookup"><span data-stu-id="8924a-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="8924a-109">Customer Insights 中的先决条件</span><span class="sxs-lookup"><span data-stu-id="8924a-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="8924a-110">您在访问群体见解中具有 **管理员** 角色。</span><span class="sxs-lookup"><span data-stu-id="8924a-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="8924a-111">详细了解如何[在访问群体见解中设置用户权限](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="8924a-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="8924a-112">在 Azure 中：</span><span class="sxs-lookup"><span data-stu-id="8924a-112">In Azure:</span></span> 

- <span data-ttu-id="8924a-113">一个有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8924a-113">An active Azure subscription.</span></span>

- <span data-ttu-id="8924a-114">如果使用的是新 Azure Data Lake Storage Gen2 帐户，则此 *访问群体见解服务主体* 需要 **存储 Blob 数据参与者** 权限。</span><span class="sxs-lookup"><span data-stu-id="8924a-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="8924a-115">详细了解如何[使用 Azure 访问群体见解服务主体连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。</span><span class="sxs-lookup"><span data-stu-id="8924a-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="8924a-116">**必须** 为 Data Lake Storage Gen2 启用[分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。</span><span class="sxs-lookup"><span data-stu-id="8924a-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="8924a-117">在 Azure Synapse 工作区所在的资源组上，需要为 *服务主体* 和 *访问群体见解用户* 至少分配 **读者** 权限。</span><span class="sxs-lookup"><span data-stu-id="8924a-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="8924a-118">有关详细信息，请参阅[使用 Azure 门户分配 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。</span><span class="sxs-lookup"><span data-stu-id="8924a-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="8924a-119">如果数据位于并链接到 Azure Synapse 工作区，则 *用户* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。</span><span class="sxs-lookup"><span data-stu-id="8924a-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="8924a-120">详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。</span><span class="sxs-lookup"><span data-stu-id="8924a-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="8924a-121">如果数据位于并链接到 Azure Synapse 工作区，则 *[Azure Synapse 工作区托管标识](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。</span><span class="sxs-lookup"><span data-stu-id="8924a-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="8924a-122">详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。</span><span class="sxs-lookup"><span data-stu-id="8924a-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="8924a-123">在 Azure Synapse 工作区上，需要为 *访问群体见解服务主体* 分配 **Synapse 管理员** 角色。</span><span class="sxs-lookup"><span data-stu-id="8924a-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="8924a-124">有关详细信息，请参阅[如何为 Synapse 工作区设置访问控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。</span><span class="sxs-lookup"><span data-stu-id="8924a-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="8924a-125">设置连接并导出到 Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="8924a-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="8924a-126">配置连接</span><span class="sxs-lookup"><span data-stu-id="8924a-126">Configure a connection</span></span>

1. <span data-ttu-id="8924a-127">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="8924a-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8924a-128">选择 **添加连接** 并选择 **Azure Synapse Analytics**，或在 **Azure Synapse Analytics** 磁贴中选择 **设置**，以配置连接。</span><span class="sxs-lookup"><span data-stu-id="8924a-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="8924a-129">在显示名称字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="8924a-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="8924a-130">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="8924a-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="8924a-131">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="8924a-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8924a-132">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="8924a-132">Choose who can use this connection.</span></span> <span data-ttu-id="8924a-133">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="8924a-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8924a-134">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="8924a-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8924a-135">选择或搜索要在其中使用 Customer Insights 的订阅。</span><span class="sxs-lookup"><span data-stu-id="8924a-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="8924a-136">一旦选择了订阅，还可以马上选择 **工作区**、**存储帐户** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="8924a-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="8924a-137">选择 **保存** 以保存连接。</span><span class="sxs-lookup"><span data-stu-id="8924a-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="8924a-138">配置导出</span><span class="sxs-lookup"><span data-stu-id="8924a-138">Configure an export</span></span>

<span data-ttu-id="8924a-139">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="8924a-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8924a-140">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="8924a-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8924a-141">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="8924a-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8924a-142">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="8924a-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="8924a-143">在 **导出连接** 字段中，从 **Azure Synapse Analytics** 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="8924a-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="8924a-144">如果您没有看到此部分名称，则您无法使用此类型的[连接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="8924a-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="8924a-145">为导出提供一个可识别的 **显示名称** 和一个 **数据库名称**。</span><span class="sxs-lookup"><span data-stu-id="8924a-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="8924a-146">选择要导出到 Azure Synapse Analytics 的实体。</span><span class="sxs-lookup"><span data-stu-id="8924a-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="8924a-147">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="8924a-147">Select **Save**.</span></span>

<span data-ttu-id="8924a-148">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="8924a-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8924a-149">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="8924a-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8924a-150">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="8924a-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="8924a-151">更新导出</span><span class="sxs-lookup"><span data-stu-id="8924a-151">Update an export</span></span>

1. <span data-ttu-id="8924a-152">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="8924a-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8924a-153">在想要更新的导出上选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="8924a-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="8924a-154">在选择的内容中 **添加** 或 **删除** 实体。</span><span class="sxs-lookup"><span data-stu-id="8924a-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="8924a-155">如果从选择的内容中删除了实体，则不会从 Synapse Analytics 数据库中删除它们。</span><span class="sxs-lookup"><span data-stu-id="8924a-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="8924a-156">但是，以后的数据刷新不会更新该数据库中删除的实体。</span><span class="sxs-lookup"><span data-stu-id="8924a-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="8924a-157">**更改数据库名称** 会创建一个新的 Synapse Analytics 数据库。</span><span class="sxs-lookup"><span data-stu-id="8924a-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="8924a-158">具有以前配置的名称的数据库在以后的刷新中将不会收到任何更新。</span><span class="sxs-lookup"><span data-stu-id="8924a-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
