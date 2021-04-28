---
title: 将 Customer Insights 数据导出到 Azure Blob 存储
description: 了解如何配置连接和导出到 Blob 存储。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760178"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="b2399-103">将客户细分列表和其他数据导出到 Azure Blob 存储（预览版）</span><span class="sxs-lookup"><span data-stu-id="b2399-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="b2399-104">将您的 Customer Insights 数据存储在 Blob 存储中，或使用它将您的数据传输到其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2399-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="b2399-105">设置与 Blob 存储的连接</span><span class="sxs-lookup"><span data-stu-id="b2399-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="b2399-106">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="b2399-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b2399-107">选择 **添加连接** 并选择 **Azure Blob 存储** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="b2399-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="b2399-108">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="b2399-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b2399-109">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="b2399-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b2399-110">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="b2399-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b2399-111">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="b2399-111">Choose who can use this connection.</span></span> <span data-ttu-id="b2399-112">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="b2399-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b2399-113">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="b2399-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b2399-114">输入 Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="b2399-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="b2399-115">若要了解如何查找 Blob 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="b2399-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="b2399-116">若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="b2399-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="b2399-117">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="b2399-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b2399-118">配置导出</span><span class="sxs-lookup"><span data-stu-id="b2399-118">Configure an export</span></span>

<span data-ttu-id="b2399-119">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="b2399-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b2399-120">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="b2399-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b2399-121">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="b2399-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b2399-122">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="b2399-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b2399-123">在 **导出连接** 字段中，从 Azure Blob 存储部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="b2399-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="b2399-124">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="b2399-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b2399-125">选中要导出到此目标的每个实体旁边的框。</span><span class="sxs-lookup"><span data-stu-id="b2399-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="b2399-126">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="b2399-126">Select **Save**.</span></span>

<span data-ttu-id="b2399-127">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="b2399-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b2399-128">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="b2399-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="b2399-129">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="b2399-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="b2399-130">导出的数据存储在您配置的 Blob 存储容器中。</span><span class="sxs-lookup"><span data-stu-id="b2399-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="b2399-131">将在容器中自动创建以下文件夹路径：</span><span class="sxs-lookup"><span data-stu-id="b2399-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="b2399-132">对于源实体和由系统生成的实体：`%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="b2399-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="b2399-133">示例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="b2399-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="b2399-134">导出的实体的 model.json 将处于 %ExportDestinationName% 级别</span><span class="sxs-lookup"><span data-stu-id="b2399-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="b2399-135">示例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="b2399-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
