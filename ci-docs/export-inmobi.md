---
title: 将 Customer Insights 数据导出到 InMobi
description: 了解如何配置连接并导出到 InMobi。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195877"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>将 Customer Insights 数据导出到 InMobi（预览）

将客户细分列表或其他数据从 Customer Insights 实例导出到 [InMobi](https://www.inmobi.com/)。

## <a name="prerequisites"></a>先决条件

- [InMobi 帐户](https://www.inmobi.com/)和管理员凭据。
- [Azure Blob 存储帐户](/azure/storage/blobs/create-data-lake-storage-account)名称和帐户密钥。 要查找名称和密钥，请参阅[在 Azure 门户中创建存储帐户设置](/azure/storage/common/storage-account-manage)。
- 要将 InMobi 数据导出到的 [Azure Blob 存储容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。
- InMobi 将创建与 Blob 存储的直接连接，并配置如何将数据自动导入到 InMobi 中。 请与您的 InMobi 代表联系以开始此过程。

## <a name="known-limitations"></a>已知限制

- 对于 Azure Blob 存储，在[标准性能和高级性能层](/azure/storage/blobs/storage-blob-performance-tiers)之间选择。 如果您选择高级性能层，请选择[高级块 blob 作为客户类型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-azure-blob-storage"></a>设置与 Azure Blob 存储的连接

[设置与 Azure Blob 存储的连接](export-azure-blob-storage.md)。

## <a name="configure-an-export"></a>配置导出

[配置导出](export-azure-blob-storage.md#configure-an-export)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
