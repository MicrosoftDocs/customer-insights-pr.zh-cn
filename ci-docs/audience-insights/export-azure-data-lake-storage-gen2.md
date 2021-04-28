---
title: 将 Customer Insights 数据导出到 Azure Data Lake Storage Gen2
description: 了解如何配置与 Azure Data Lake Storage Gen2 的连接。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760040"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="13efb-103">设置与 Azure Data Lake Storage Gen2 的连接（预览版）</span><span class="sxs-lookup"><span data-stu-id="13efb-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="13efb-104">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="13efb-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13efb-105">选择 **添加连接** 并选择 **Azure Data Lake Gen 2** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="13efb-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="13efb-106">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="13efb-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13efb-107">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="13efb-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13efb-108">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="13efb-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13efb-109">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="13efb-109">Choose who can use this connection.</span></span> <span data-ttu-id="13efb-110">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="13efb-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="13efb-111">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="13efb-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13efb-112">输入 Azure Data Lake Storage Gen2 的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="13efb-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="13efb-113">若要了解如何创建与 Azure Data Lake Storage Gen2 配合使用的存储帐户，请参阅[创建存储帐户](/azure/storage/blobs/create-data-lake-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="13efb-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="13efb-114">若要了解 Azure Data Lake Gen2 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="13efb-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="13efb-115">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="13efb-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="13efb-116">配置导出</span><span class="sxs-lookup"><span data-stu-id="13efb-116">Configure an export</span></span>

<span data-ttu-id="13efb-117">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="13efb-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="13efb-118">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="13efb-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13efb-119">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="13efb-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13efb-120">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="13efb-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="13efb-121">在 **导出连接** 字段中，从 **Azure Data Lake** 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="13efb-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="13efb-122">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="13efb-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13efb-123">选中要导出到此目标的每个实体旁边的框。</span><span class="sxs-lookup"><span data-stu-id="13efb-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="13efb-124">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="13efb-124">Select **Save**.</span></span>

<span data-ttu-id="13efb-125">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="13efb-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13efb-126">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="13efb-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13efb-127">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="13efb-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="13efb-128">导出的数据存储在您配置的 Azure Data Lake Gen 2 存储容器中。</span><span class="sxs-lookup"><span data-stu-id="13efb-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
