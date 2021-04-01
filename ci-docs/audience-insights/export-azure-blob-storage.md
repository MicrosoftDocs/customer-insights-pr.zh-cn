---
title: 将 Customer Insights 数据导出到 Azure Blob 存储
description: 了解如何配置与 Azure Blob 存储之间的连接。
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596166"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob 存储的连接器（预览版）

将您的 Customer Insights 数据存储在 Azure Blob 存储中，或使用它将您的数据传输到其他应用程序。

## <a name="configure-the-connector-for-azure-blob-storage"></a>配置 Azure Blob 存储的连接器

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **Azure Blob 存储** 下，选择 **设置**。

1. 输入 Azure Blob 存储帐户的 **账户名称**、**帐户密钥** 和 **容器**。
    - 若要了解有关如何查找 Azure Blob 存储账户名称和帐户密钥的详细信息，请参阅[管理 Azure 门户中的存储帐户设置](/azure/storage/common/storage-account-manage)。
    - 若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

1. 在 **显示名称** 字段中为目标指定易于识别的名称。

1. 选择 **下一步**。

1. 选中要导出到此目标的每个实体旁边的框。

1. 选择 **保存**。

导出的数据存储在您配置的 Azure Blob 存储容器中。 将在容器中自动创建以下文件夹路径：

- 对于源实体和由系统生成的实体：`%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - 示例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- 导出实体的 model.json 将位于 %ExportDestinationName% 级别
  - 示例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md#export-data-on-demand)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。


[!INCLUDE[footer-include](../includes/footer-banner.md)]