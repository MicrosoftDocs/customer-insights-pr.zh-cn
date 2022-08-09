---
title: 将数据导出到 Azure Data Lake Storage Gen2（预览版）
description: 了解如何配置与 Azure Data Lake Storage Gen2 的连接。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196429"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>将数据导出到 Azure Data Lake Storage Gen2（预览版）

将您的 Customer Insights 数据存储在 Data Lake Storage Gen2 帐户中，或使用它将您的数据传输到其他应用程序。

## <a name="prerequisites"></a>先决条件

- [用于 Azure Data Lake Gen2 的存储帐户](/azure/storage/blobs/create-data-lake-storage-account)。 要查找存储帐户名称和密钥，请参阅[在 Azure 门户中创建存储帐户设置](/azure/storage/common/storage-account-manage)。
- [Azure Blob 存储容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="known-limitations"></a>已知限制

- 对于 Azure Data Lake Storage Gen2，在[标准性能和高级性能层](/azure/storage/blobs/create-data-lake-storage-account)之间选择。 如果您选择高级性能层，请选择[高级块 blob 作为客户类型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>设置与 Azure Data Lake Storage Gen2 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Data Lake Gen 2**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入 Azure Data Lake Storage Gen2 的 **帐户名称**、**帐户密钥** 和 **容器**。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Azure Data Lake 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 输入 Azure Data Lake Storage Gen2 存储的文件夹名称。

1. 选中要导出到此目标的每个实体旁边的框。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

导出的数据存储在您配置的 Azure Data Lake Gen 2 存储容器中。

> [!TIP]
> 导出包含大量数据的实体可能会导致每次导出在同一文件夹中生成多个 CSV 文件。 出于性能原因拆分导出以最大程度地减少导出完成所需的时间。

[!INCLUDE [footer-include](includes/footer-banner.md)]
