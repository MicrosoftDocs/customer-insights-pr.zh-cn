---
title: 连接 Azure Synapse 数据源（预览版）
description: 将 Azure Synapse 中的数据库用作 Dynamics 365 Customer Insights 中的数据源。
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259787"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>连接 Azure Synapse Analytics 数据源（预览版）

Azure Synapse Analytics 是一项企业分析服务，可加快跨数据仓库和大数据系统获取见解的速度。 Azure Synapse Analytics 汇集了用于企业数据仓库的最佳 SQL 技术、用于大数据的 Spark 技术、用于日志和时序分析的数据资源管理器、用于数据集成和 ETL/ELT 的管道，以及与其他 Azure 服务（例如 Power BI、Cosmos DB 和 AzureML）的深度集成。

有关详细信息，请参阅 [Azure Synapse 概述](/azure/synapse-analytics/overview-what-is)。

## <a name="prerequisites"></a>先决条件

> [!NOTE]
> 目前不支持[启用防火墙](/azure/synapse-analytics/security/synapse-workspace-ip-firewall)的 Synapse 工作区。
> [!IMPORTANT]
> 确保如上所述设置所有 **角色分配**。  

**在 Customer Insights 中**：

* 您在 Customer Insights 中具有 **管理员** 角色。 详细了解 [Customer Insights 中的用户权限](permissions.md#add-users)。

**在 Azure 中**：

- 一个有效的 Azure 订阅。

- 如果使用新的 Azure Data Lake Storage Gen2 帐户，*Customer Insights 的服务主体*（即“Dynamics 365 AI for Customer Insights”）需要 **存储 Blob 数据参与者** 权限。 了解有关[使用 Customer Insights 服务主体连接到 Azure Data Lake Storage](connect-service-principal.md)的详细信息。 **必须** 为 Data Lake Storage Gen2 启用[分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse workspace 所在的资源组上，需要为 *服务主体*（即“Dynamics 365 AI for Customer Insights”）和 *Customer Insights 用户* 至少分配 **读者** 权限。 有关详细信息，请参阅[使用 Azure 门户分配 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

- 如果数据位于并链接到 Azure Synapse 工作区，则 *用户* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 如果数据位于并链接到 Azure Synapse 工作区，则 *[Azure Synapse 工作区托管标识](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse workspace 中，需要为 *Customer Insights 的服务主体*（即“Dynamics 365 AI for Customer Insights”）分配 **Synapse 管理员** 角色。 有关详细信息，请参阅[如何为 Synapse 工作区设置访问控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。

- 如果您的 Customer Insights 环境将数据存储在您 [自己的 Azure Data Lake Storage](own-data-lake-storage.md) 中，设置与 Azure Synapse Analytics 的连接的用户至少需要 Data Lake Storage 帐户的内置 **读者** 角色。 有关详细信息，请参阅[使用 Azure 门户分配 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>连接到 Azure Synapse Analytics 中的 Data Lake 数据库

1. 转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **Azure Synapse Analytics（预览版）** 方法。

   :::image type="content" source="media/data_sources_synapse.png" alt-text="用于连接到 Synapse Analytics 数据的对话框":::
  
1. 为数据源输入 **名称** 和 **说明**（可选）。

1. 选择到 Azure Synapse Analytics 的[可用连接](connections.md)或[创建一个新连接](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse)。

1. 从所选 Azure Synapse Analytics 连接中连接的工作区中选择一个 **数据库**，然后选择 **下一步**。 当前，我们仅支持数据库类型 *湖数据库*。

1. 选择要从连接的数据库中引入的实体，然后选择 **下一步**。

1. （可选）选择数据实体以允许对其进行数据分析。

1. 选择 **保存** 以应用您的选择，并开始从链接到 Azure Synapse Analytics 中的湖数据库表的新建数据源中引入数据。 **数据源** 页面将打开，显示处于 **正在刷新** 状态的新数据源。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

加载数据可能需要一些时间。 成功刷新后，可以从 [**实体**](entities.md)页查看引入的数据。

[!INCLUDE [footer-include](includes/footer-banner.md)]