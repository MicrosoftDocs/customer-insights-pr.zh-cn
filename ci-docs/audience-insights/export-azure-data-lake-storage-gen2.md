---
title: 将 Customer Insights 数据导出到 Azure Data Lake Storage Gen2
description: 了解如何配置与 Azure Data Lake Storage Gen2 的连接。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cc0b3aac11a33facc366e9c57071d1fb8be4ecc4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231663"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>将客户细分列表和其他数据导出到 Azure Data Lake Storage Gen2（预览）

将您的 Customer Insights 数据存储在 Data Lake Storage Gen2 帐户中，或使用它将您的数据传输到其他应用程序。

## <a name="known-limitations"></a>已知限制

1. 对于 Azure Data Lake Storage Gen2，您可以在为数据湖创建存储帐户时在[标准性能层和高级性能层](/azure/storage/blobs/create-data-lake-storage-account)之间选择。 如果您选择高级性能层，请选择高级块 blob 作为客户类型。 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>设置与 Azure Data Lake Storage Gen2 的连接 


1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Data Lake Gen 2** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入 Azure Data Lake Storage Gen2 的 **帐户名称**、**帐户密钥** 和 **容器**。
    - 若要了解如何创建与 Azure Data Lake Storage Gen2 配合使用的存储帐户，请参阅[创建存储帐户](/azure/storage/blobs/create-data-lake-storage-account)。 
    - 若要了解 Azure Data Lake Gen2 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。

1. 选择 **保存** 以完成连接。 

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 **Azure Data Lake** 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选中要导出到此目标的每个实体旁边的框。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

导出的数据存储在您配置的 Azure Data Lake Gen 2 存储容器中。 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
