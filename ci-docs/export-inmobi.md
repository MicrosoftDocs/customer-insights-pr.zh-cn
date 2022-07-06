---
title: 将 Customer Insights 数据导出到 InMobi
description: 了解如何配置连接并导出到 InMobi。
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056534"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>将客户细分列表和其他数据导出到 InMobi（预览版）

将客户细分列表或其他数据从 Customer Insights 实例导出到 [InMobi](https://www.inmobi.com/)。

## <a name="prerequisites"></a>先决条件

1. 您具有 [InMobi 帐户](https://www.inmobi.com/)和管理员凭据。
1. 您具有 Azure Blob 存储帐户名称和相应的帐户密钥。 有关详细信息，请参阅[在 Azure 门户中创建存储帐户设置](/azure/storage/common/storage-account-manage)。 存储帐户中有一个可以将 inMobi 数据导出到的容器。 有关详细信息，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。
1. InMobi 将创建与 Blob 存储的直接连接，并配置如何将数据自动导入到 InMobi 中。 请与您的 InMobi 代表联系以开始此过程。

## <a name="known-limitations"></a>已知限制

1. 对于 Azure Blob 存储，您可以在[标准性能和高级性能层](/azure/storage/blobs/storage-blob-performance-tiers)之间选择。 如果您选择高级性能层，请选择[高级块 blob 作为客户类型](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>设置与 Azure Blob 存储的连接并配置导出

1. 按照说明[设置与 Azure Blob 存储的连接](export-azure-blob-storage.md)。
2. 按照说明[配置导出](export-azure-blob-storage.md#configure-an-export)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
