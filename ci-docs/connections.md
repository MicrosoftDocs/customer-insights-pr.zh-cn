---
title: 连接（预览版）概述
description: 连接到 Customer Insights 中的其他服务。
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245500"
---
# <a name="connections-preview-overview"></a>连接（预览版）概述

连接是实现与 Customer Insights 之间共享数据的关键。 每个连接均可实现与特定服务共享数据。 使用连接[配置第三方扩充](enrichment-hub.md)和[配置导出](export-destinations.md)。 同一连接可以多次使用。 例如，Dynamics 365 Marketing 的一个连接适用于多项导出，Leadspace 连接可用于多项扩充。

## <a name="export-connections"></a>导出连接

只有管理员才能配置新的连接，但他们可以[授予参与者](#allow-contributors-to-use-a-connection-for-exports)使用现有连接的访问权限。 管理员控制数据的去向，参与者定义满足其需求的有效载荷和频率。

## <a name="enrichment-connections"></a>扩充连接

只有管理员才能配置新的连接，但创建的连接始终可供管理员和参与者使用。 管理员将管理凭据并同意数据传输。 然后，管理员和参与者都可以使用这些连接进行扩充。

## <a name="add-a-new-connection"></a>添加新连接

### <a name="prerequisites"></a>先决条件

- [管理员权限](permissions.md)
- 其他 Microsoft 服务（如果有）在同一组织中

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接**，然后选择您要创建的连接类型。 或者，转到 **发现** 选项卡，在连接磁贴上选择 **设置**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 输入所需的详细信息。 确切字段取决于您要连接到的服务。 有关特定连接类型的详细信息，请参阅有关目标服务的文章。

1. 如果您 [使用自己的密钥保管库](use-azure-key-vault.md)存储密钥，请激活 **使用密钥保管库**，然后从列表中选择密钥。

1. 查看数据隐私和合规性，并选择 **我同意**。

1. 选择 **保存** 创建连接。

### <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以将数据传输到第三方或其他 Microsoft 产品时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。 Microsoft 将在您的指导下传输此类数据，但您有责任确保第三方满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理员可以随时删除连接来中止使用此功能。

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>允许参与者使用连接进行导出

在设置或编辑导出连接时，选择允许哪些用户使用此特定连接来定义[导出](export-destinations.md)。 默认情况下，具有管理员角色的用户可以使用连接。 更改 **选择可使用此连接的人员** 设置，允许具有参与者角色的用户使用此连接。

- 参与者将无法查看或编辑连接。 只有在创建导出时，他们才会看到显示名称及其类型。
- 通过共享连接，您允许参与者使用连接。 参与者在设置导出时将看到共享连接。 他们可以管理使用此特定连接的每个导出。
- 您可以更改此设置，同时保留参与者已定义的导出。

## <a name="manage-existing-connections"></a>管理现有连接

1. 转到 **管理员** > **连接**。

1. 选择 **扩充** 或 **导出** 选项卡查看扩充或导出连接、连接类型、创建时间以及具有访问权限的用户的列表。 您可以按任何列对连接列表进行排序。

1. 选择连接查看可用操作。

   - **编辑** 连接。
   - [**删除**](#remove-a-connection)连接。

### <a name="remove-a-connection"></a>删除连接

如果您要删除的连接被扩充或导出使用，首先拆离或删除它们。 “删除”对话框将引导您完成相关的扩充或导出。

> [!TIP]
> 停用的扩充和拆离的导出会变为不可用状态。 通过在[扩充](enrichment-hub.md)或[导出](export-destinations.md)页面上添加另一个连接，您可以重新激活它们。

1. 转到 **管理员** > **连接**。

1. 选择 **扩充** 或 **导出** 选项卡。

1. 选择您要删除的连接。

1. 此下拉菜单中选择 **删除**。 此时会出现确认对话框。

   1. 如果有使用此连接的扩充或导出，请选择此按钮以查看使用连接的内容。
      - **导出：** 选择 **删除** 导出或 **拆离连接**。 拆离连接将保留导出配置，但它不会运行，直到将另一个连接添加到其中。
      - **扩充：** 选择 **删除** 或 **停用** 扩充。
   1. 连接不再有依赖项后，请返回到 **管理** > **连接** 并尝试再次删除连接。

1. 若要确认删除，请选择 **删除**。

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>使用您自己的密钥保管库管理的密钥设置连接

有些连接需要 API 密钥或密码等密钥。 有些连接支持存储在自己的密钥保管库中的密钥。 详细了解支持的连接以及如何对[您自己的 Customer Insights 密钥保管库](use-azure-key-vault.md)进行设置。

[!INCLUDE [footer-include](includes/footer-banner.md)]
