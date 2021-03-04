---
title: 将 Customer Insights 数据导出到 Azure Data Lake Storage Gen2
description: 了解如何配置与 Azure Data Lake Storage Gen2 的连接。
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477168"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="ec5e8-103">用于 Azure Data Lake Storage Gen2 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="ec5e8-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="ec5e8-104">将您的 Customer Insights 数据存储在 Azure Data Lake Storage Gen2 中，或使用它将您的数据传输到其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="ec5e8-105">配置 Azure Data Lake Storage Gen2 的连接器</span><span class="sxs-lookup"><span data-stu-id="ec5e8-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="ec5e8-106">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ec5e8-107">在 **Azure Data Lake Storage Gen2** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="ec5e8-108">在 **显示名称** 字段中为目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ec5e8-109">输入 Azure Data Lake Storage Gen2 的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="ec5e8-110">若要了解如何创建与 Azure Data Lake Storage Gen2 配合使用的存储帐户，请参阅[创建存储帐户](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="ec5e8-111">若要了解如何查找 Azure Data Lake Gen2 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](https://docs.microsoft.com/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="ec5e8-112">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-112">Select **Next**.</span></span>

1. <span data-ttu-id="ec5e8-113">选中要导出到此目标的每个实体旁边的框。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="ec5e8-114">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ec5e8-115">导出数据</span><span class="sxs-lookup"><span data-stu-id="ec5e8-115">Export the data</span></span>

<span data-ttu-id="ec5e8-116">可以[根据需要导出数据](export-destinations.md#export-data-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="ec5e8-117">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="ec5e8-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
