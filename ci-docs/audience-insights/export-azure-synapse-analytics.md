---
title: 将 Customer Insights 数据导出到 Azure Synapse Analytics
description: 了解如何配置到 Azure Synapse Analytics 的连接。
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327353"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>将数据导出到 Azure Synapse Analytics（预览版）

Azure Synapse 是一项分析服务，可加缩短跨数据存储和大型数据系统进行深入了解的时间。 您可以在 [Azure Synapse](/azure/synapse-analytics/overview-what-is) 中引入和使用您的 Customer Insights 数据。

## <a name="prerequisites"></a>先决条件

必须满足以下先决条件，才能配置从 Customer Insights 到 Azure Synapse 的连接。 

> [!NOTE]
> 确保如上所述设置所有 **角色分配**。  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights 中的先决条件

* 您在访问群体见解中具有 **管理员** 角色。 详细了解如何[在访问群体见解中设置用户权限](permissions.md#assign-roles-and-permissions)

在 Azure 中： 

- 一个有效的 Azure 订阅。

- 如果使用的是新 Azure Data Lake Storage Gen2 帐户，则此 *访问群体见解服务主体* 需要 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 访问群体见解服务主体连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 **必须** 为 Data Lake Storage Gen2 启用[分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse 工作区所在的资源组上，需要为 *服务主体* 和 *访问群体见解用户* 至少分配 **读者** 权限。 有关详细信息，请参阅[使用 Azure 门户分配 Azure 角色](/azure/role-based-access-control/role-assignments-portal)。

- 如果数据位于并链接到 Azure Synapse 工作区，则 *用户* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 如果数据位于并链接到 Azure Synapse 工作区，则 *[Azure Synapse 工作区托管标识](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 需要具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse 工作区上，需要为 *访问群体见解服务主体* 分配 **Synapse 管理员** 角色。 有关详细信息，请参阅[如何为 Synapse 工作区设置访问控制](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>设置连接并导出到 Azure Synapse

### <a name="configure-a-connection"></a>配置连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Synapse Analytics**，或在 **Azure Synapse Analytics** 磁贴中选择 **设置**，以配置连接。

1. 在显示名称字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择或搜索要在其中使用 Customer Insights 的订阅。 一旦选择了订阅，还可以马上选择 **工作区**、**存储帐户** 和 **容器**。

1. 选择 **保存** 以保存连接。

### <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 **Azure Synapse Analytics** 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的[连接](connections.md)。

1. 为导出提供一个可识别的 **显示名称** 和一个 **数据库名称**。

1. 选择要导出到 Azure Synapse Analytics 的实体。
   > [!NOTE]
   > 不支持基于 [Common Data Model 文件夹](connect-common-data-model.md)的数据源。

2. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。

### <a name="update-an-export"></a>更新导出

1. 转到 **数据** > **导出**。

1. 在想要更新的导出上选择 **编辑**。

   - 在选择的内容中 **添加** 或 **删除** 实体。 如果从选择的内容中删除了实体，则不会从 Synapse Analytics 数据库中删除它们。 但是，以后的数据刷新不会更新该数据库中删除的实体。

   - **更改数据库名称** 会创建一个新的 Synapse Analytics 数据库。 具有以前配置的名称的数据库在以后的刷新中将不会收到任何更新。
