---
title: 将 Customer Insights 数据导出到 Dynamics 365 Marketing
description: 了解如何配置连接和导出到 Dynamics 365 Marketing。
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645582"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>在 Dynamics 365 Marketing 中使用客户细分（预览版）



使用[客户细分](segments.md)来生成市场活动，并通过 Dynamics 365 Marketing 联系特定客户组。 有关详细信息，请参阅[将来自 Dynamics 365 Customer Insights 的客户细分与 Dynamics 365 Marketing 结合使用](/dynamics365/marketing/customer-insights-segments)。

如果要将 Dynamics 365 Marketing 的新功能用于 Dataverse 组织中的实时客户旅程构建，则无需创建到 Dynamics 365 Marketing 的标准导出。 连接 Marketing 和 Customer Insights 后，可直接在 Dynamics 365 Marketing 中使用 Customer Insights 中的联系人和客户细分。 在删除现有导出之前，请查看有关[如何连接 Customer Insights 和 Dynamics 365 Marketing 客户旅程业务流程](/dynamics365/marketing/real-time-marketing-ci-profile)的文档。

## <a name="prerequisite-for-a-connection"></a>连接的先决条件

- Dynamics 365 Marketing 中必须先存在联系人记录，然后才能从 Customer Insights 中将客户细分导出到 Marketing。 详细了解如何[在 Dynamics 365 Marketing 中使用 Microsoft Dataverse](connect-dataverse-managed-lake.md)引入联系人。

  > [!NOTE]
  > 将客户细分从 Customer Insights 导出到 Marketing 不会在 Marketing 实例中创建新的联系人记录。 来自 Marketing 的联系人记录必须引入 Customer Insights 中并用作数据源。 在导出客户细分之前，还需要将它们包含在统一客户实体中，以将客户 ID 映射到联系人 ID。

## <a name="set-up-connection-to-marketing"></a>设置与 Marketing 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Dynamics 365 Marketing** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 在 **服务器地址** 字段中输入组织的 Marketing URL。

1. 在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Marketing 帐户。

1. 将客户实体中的联系人 ID 字段映射到 Dynamics 365 联系人 ID。

1. 选择 **保存** 以完成连接。 

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Dynamics 365 Marketing 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选择一个或多个客户细分。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

[!INCLUDE [footer-include](includes/footer-banner.md)]
