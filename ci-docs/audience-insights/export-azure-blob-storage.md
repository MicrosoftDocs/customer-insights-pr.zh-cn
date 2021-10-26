---
title: 将 Customer Insights 数据导出到 Azure Blob 存储
description: 了解如何配置连接和导出到 Blob 存储。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d02c09a1869d0099db4861b65ac8ff006914873e
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605827"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>将客户细分列表和其他数据导出到 Azure Blob 存储（预览版）

将您的 Customer Insights 数据存储在 Blob 存储中，或使用它将您的数据传输到其他应用程序。

## <a name="known-limitations"></a>已知限制

1. 对于 Azure Blob 存储，您可以在[标准性能和高级性能层](/azure/storage/blobs/storage-blob-performance-tiers)之间选择。 如果您选择高级性能层，请选择[高级块 blob 作为客户类型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-the-connection-to-blob-storage"></a>设置与 Blob 存储的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Blob 存储** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入 Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。
    - 若要了解有关如何查找 Blob 存储帐户名称和帐户密钥的详细信息，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。
    - 若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 选择 **保存** 以完成连接。 

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

> [!IMPORTANT]
> 如果为 Azure Blob 存储帐户开启了软删除设置，则导出将失败。 关闭软删除以将数据导出到 Blob。 有关详细信息，请参阅[启用 Blob 软删除](/azure/storage/blobs/soft-delete-blob-enable.md)

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Azure Blob 存储部分选择连接。 如果看不到此部分名称，则没有此类型的连接可用。

1. 选中要导出到此目标的每个实体旁边的框。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。     

您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

导出的数据存储在您配置的 Blob 存储容器中。 将在容器中自动创建以下文件夹路径：

- 对于源实体和由系统生成的实体：  
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - 示例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- 导出的实体的 model.json 将处于 %ExportDestinationName% 级别。  
  - 示例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
