---
title: 使用自己的 Azure Data Lake Storage Gen2 帐户
author: mukeshpo
description: 了解使用自己的 Azure Data Lake Storage 帐户存储 Customer Insights 数据的要求。
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304370"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>使用自己的 Azure Data Lake Storage Gen2 帐户

Dynamics 365 Customer Insights 提供了用于在 [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction) 中存储您的所有数据的选项。 将数据保存到 Data Lake Storage，即表示您同意将数据传输并存储到该 Azure 存储帐户的适当地理位置。 有关详细信息，请参阅 [Microsoft 信任中心](https://www.microsoft.com/trust-center)。

Customer Insights 中的管理员可以在此过程中[创建环境](create-environment.md)并[指定数据存储选项](create-environment.md#step-2-configure-data-storage)。

## <a name="prerequisites"></a>先决条件

- Azure Data Lake Storage 帐户必须位于创建 Customer Insights 环境时选择的同一 Azure 区域中。 若要了解该环境的区域，请在 Customer Insights 中转到 **管理** > **系统** > **关于**
- Data Lake Storage 帐户必须是 Gen2。 Azure Data Lake Gen1 存储帐户不受支持。
- 必须为 Data Lake Storage 帐户[启用了分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。
- 存储帐户上必须存在名为 `customerinsights` 的容器。 应先创建它，然后在 Customer Insights 中使用您自己的 Data Lake Storage。
- 设置 Customer Insights 环境的管理员需要对存储帐户或 `customerinsights` 容器具有存储 Blob 数据参与者或存储 Blob 数据所有者角色。 有关在存储帐户中分配权限的详细信息，请参阅[创建存储帐户](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal)。

## <a name="connect-customer-insights-with-your-storage-account"></a>连接 Customer Insights 与存储帐户

创建新环境时，请确保 Data Lake Storage 帐户存在并且满足所有必备条件。

1. 在环境创建期间的 **数据存储** 步骤中，将 **保存输出数据** 设置为 **Azure Data Lake Storage Gen2**。
1. 选择如何 **连接您的存储**。 您可以在基于资源的选项和基于订阅的选项之间进行选择以进行身份验证。 有关详细信息，请参阅[使用 Azure 服务主体连接到 Azure Data Lake Storage 帐户](connect-service-principal.md)。
   - 对于 **Azure 订阅**，请选择包含 `customerinsights` 容器的 **订阅**、**资源组** 和 **存储帐户**。
   - 对于 **帐户密钥**，请提供 Data Lake Storage 帐户的 **帐户名称** 和 **帐户密钥**。 使用此身份验证方法意味着在您的组织轮换密钥时您会收到通知。 在轮换密钥时，您必须用新密钥[更新环境配置](manage-environments.md#edit-an-existing-environment)。
1. 在您想要使用 Azure 专用链接连接到存储帐户并[创建与专用链接的连接](security-overview.md#set-up-an-azure-private-link)时选择。

当数据引入等系统流程完成时，系统会在存储帐户内创建相应的文件夹。 将根据流程名称创建数据文件和 model.json 文件并将其添加到文件夹中。

如果您创建多个 Customer Insights 环境并选择将这些环境中的输出实体保存到您的存储帐户，Customer Insights 将为容器中具有 `ci_environmentID` 的每个环境创建单独的文件夹。
