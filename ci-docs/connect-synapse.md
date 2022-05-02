---
title: 从 Azure Synapse Analytics 引入数据
description: 将 Azure Synapse 中的数据库用作 Dynamics 365 Customer Insights 中的数据源。
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645794"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>连接 Azure Synapse 数据源（预览版）

Azure Synapse Analytics 是一项企业分析服务，可加快跨数据仓库和大数据系统获取见解的速度。 Azure Synapse Analytics 汇集了用于企业数据仓库的最佳 SQL 技术、用于大数据的 Spark 技术、用于日志和时序分析的数据资源管理器、用于数据集成和 ETL/ELT 的管道，以及与其他 Azure 服务（例如 Power BI、Cosmos DB 和 AzureML）的深度集成。

有关详细信息，请参阅 [Azure Synapse 概述](/azure/synapse-analytics/overview-what-is)。

## <a name="prerequisites"></a>先决条件

必须满足以下先决条件才能配置从 Dynamics 365 Customer Insights 到 Azure Synapse 的连接。

> [!IMPORTANT]
> 确保如上所述设置所有 **角色分配**。  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights 中的先决条件

* 您在 Customer Insights 中具有 **管理员** 角色。 详细了解 [Customer Insights 中的用户权限](permissions.md#assign-roles-and-permissions)。

在 Azure 中： 

- 一个有效的 Azure 订阅。

- 如果使用新的 Azure Data Lake Storage Gen2 帐户，则 *Customer Insights 的服务主体* 需要 **存储 Blob 数据参与者** 权限。 了解有关[使用 Customer Insights 服务主体连接到 Azure Data Lake Storage](connect-service-principal.md)的详细信息。 **必须** 为 Data Lake Storage Gen2 启用[分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse workspace 所在的资源组上，需要为 *服务主体* 和 *user for Customer Insights 用户* 至少分配 **读者** 权限。 有关详细信息，请参阅[使用 Azure 门户分配 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

- 如果数据位于并链接到 Azure Synapse 工作区，则 *用户* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 如果数据位于并链接到 Azure Synapse 工作区，则 *[Azure Synapse 工作区托管标识](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse workspace 中，需要为 *Customer Insights 的服务主体* 分配 **Synapse 管理员** 角色。 有关详细信息，请参阅[如何为 Synapse 工作区设置访问控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>连接到 Azure Synapse Analytics 中的 Data Lake 数据库

1. 转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **Azure Synapse Analytics（预览版）** 方法。

1. 为数据源提供 **名称**，然后选择 **下一步** 创建数据源。 

1. 选择到 Azure Synapse Analytics 的[可用连接](connections.md)或创建一个新连接。

1. 从所选 Azure Synapse Analytics 连接中连接的工作区中选择一个 **湖数据库**，然后选择 **下一步**。

1. 选择要从连接的数据库中引入的实体。 

1. （可选）选择数据实体以允许对其进行数据分析。 

1. 选择 **保存** 以应用您的选择，并开始从链接到 Azure Synapse Analytics 中的湖数据库表的新建数据源中引入数据。
