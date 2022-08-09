---
title: 将数据导出到 Azure Synapse Analytics（预览版）
description: 了解如何配置与 Azure Synapse Analytics 的连接。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196383"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>将数据导出到 Azure Synapse Analytics（预览版）

Azure Synapse 是一项分析服务，可加缩短跨数据存储和大型数据系统进行深入了解的时间。 您可以在 [Azure Synapse](/azure/synapse-analytics/overview-what-is) 中引入和使用您的 Customer Insights 数据。

## <a name="prerequisites"></a>先决条件

> [!NOTE]
> 确保如上所述设置所有 **角色分配**。

- 在 Customer Insights 中，您的 Azure Active Directory (AD) 用户帐户必须具有[管理员角色](permissions.md#assign-roles-and-permissions)。

在 Azure 中：

- 一个有效的 Azure 订阅。

- 如果使用新的 Azure Data Lake Storage Gen2 帐户，则 [Customer Insights 的服务主体](connect-service-principal.md)具有 **存储 Blob 数据参与者** 权限。 **必须** 为 Data Lake Storage Gen2 启用[分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。

- 在 Azure Synapse workspace 所在的资源组上，必须为 *服务主体* 和 *Customer Insights 中具有管理员权限的 Azure AD 用户* 至少分配 **读者**[权限](/azure/role-based-access-control/role-assignments-portal)。

- *Customer Insights 中具有管理员权限的 Azure AD 用户* 具有对数据所在并链接到 Azure Synapse workspace 的 Azure Data Lake Storage Gen2 帐户拥有 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 如果数据位于并链接到 Azure Synapse workspace，则 *[Azure Synapse workspace 托管标识](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 具有对 Azure Data Lake Storage Gen2 帐户的 **存储 Blob 数据参与者** 权限。 详细了解如何[使用 Azure 门户分配用于访问 blob 和队列数据的 Azure 角色](/azure/storage/common/storage-auth-aad-rbac-portal)和[存储 Blob 数据参与者权限](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)。

- 在 Azure Synapse workspace 中，*Customer Insights 的服务主体* 分配有 **Synapse 管理员**[角色](/azure/synapse-analytics/security/how-to-set-up-access-control)。

## <a name="set-up-connection-to-azure-synapse"></a>设置与 Azure Synapse 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Azure Synapse Analytics**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择或搜索要在其中使用 Customer Insights 的订阅。 一旦选择了订阅，还可以马上选择 **工作区**、**存储帐户** 和 **容器**。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)] 要使用共享连接配置导出，您需要在 Customer Insights 中至少具有 **参与者** 权限。

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Azure Synapse Analytics 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出提供一个可识别的 **显示名称** 和一个 **数据库名称**。 导出将在连接中定义的工作区中创建一个新的 [Azure Synapse 湖数据库](/azure/synapse-analytics/database-designer/concepts-lake-database)。

1. 选择要导出到 Azure Synapse Analytics 的实体。
   > [!NOTE]
   > 不支持基于 [Common Data Model 文件夹](connect-common-data-model.md)的数据源。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

要查询导出到 Synapse Analytics 的数据，您需要具有对导出工作区上的目标存储的 **存储 Blob 数据读者** 访问权限。

## <a name="update-an-export"></a>更新导出

1. 转到 **数据** > **导出**。

1. 在想要更新的导出上选择 **编辑**。

   - 在选择的内容中 **添加** 或 **删除** 实体。 如果从选择的内容中删除了实体，则不会从 Synapse Analytics 数据库中删除它们。 但是，以后的数据刷新不会更新该数据库中删除的实体。

   - **更改数据库名称** 会创建一个新的 Synapse Analytics 数据库。 具有以前配置的名称的数据库在以后的刷新中将不会收到任何更新。

[!INCLUDE [footer-include](includes/footer-banner.md)]
