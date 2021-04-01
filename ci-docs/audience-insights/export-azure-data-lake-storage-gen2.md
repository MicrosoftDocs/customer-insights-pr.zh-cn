---
title: 将 Customer Insights 数据导出到 Azure Data Lake Storage Gen2
description: 了解如何配置与 Azure Data Lake Storage Gen2 的连接。
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596626"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="640aa-103">用于 Azure Data Lake Storage Gen2 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="640aa-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="640aa-104">将您的 Customer Insights 数据存储在 Azure Data Lake Storage Gen2 中，或使用它将您的数据传输到其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="640aa-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="640aa-105">配置 Azure Data Lake Storage Gen2 的连接器</span><span class="sxs-lookup"><span data-stu-id="640aa-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="640aa-106">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="640aa-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="640aa-107">在 **Azure Data Lake Storage Gen2** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="640aa-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="640aa-108">在 **显示名称** 字段中为目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="640aa-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="640aa-109">输入 Azure Data Lake Storage Gen2 的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="640aa-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="640aa-110">若要了解如何创建与 Azure Data Lake Storage Gen2 配合使用的存储帐户，请参阅[创建存储帐户](/azure/storage/blobs/create-data-lake-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="640aa-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="640aa-111">若要了解如何查找 Azure Data Lake Gen2 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="640aa-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="640aa-112">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="640aa-112">Select **Next**.</span></span>

1. <span data-ttu-id="640aa-113">选中要导出到此目标的每个实体旁边的框。</span><span class="sxs-lookup"><span data-stu-id="640aa-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="640aa-114">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="640aa-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="640aa-115">导出数据</span><span class="sxs-lookup"><span data-stu-id="640aa-115">Export the data</span></span>

<span data-ttu-id="640aa-116">可以[根据需要导出数据](export-destinations.md#export-data-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="640aa-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="640aa-117">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="640aa-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>