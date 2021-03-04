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
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>用于 Azure Data Lake Storage Gen2 的连接器（预览版）

将您的 Customer Insights 数据存储在 Azure Data Lake Storage Gen2 中，或使用它将您的数据传输到其他应用程序。

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>配置 Azure Data Lake Storage Gen2 的连接器

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **Azure Data Lake Storage Gen2** 下，选择 **设置**。

1. 在 **显示名称** 字段中为目标指定易于识别的名称。

1. 输入 Azure Data Lake Storage Gen2 的 **帐户名称**、**帐户密钥** 和 **容器**。
    - 若要了解如何创建与 Azure Data Lake Storage Gen2 配合使用的存储帐户，请参阅[创建存储帐户](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)。 
    - 若要了解如何查找 Azure Data Lake Gen2 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](https://docs.microsoft.com/azure/storage/common/storage-account-manage)。

1. 选择 **下一步**。

1. 选中要导出到此目标的每个实体旁边的框。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md#export-data-on-demand)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。
