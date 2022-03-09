---
title: 将 Customer Insights 数据导出到 Dynamics 365 Sales
description: 了解如何配置连接和导出到 Dynamics 365 Sales。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: cf680c21c55c71d99728be79fe68111dc89a79ec
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355005"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>在 Dynamics 365 Sales 中使用客户细分（预览版）



使用您的客户数据通过 Dynamics 365 Sales 创建市场营销列表、跟进工作流以及发出促销。

## <a name="known-limitations"></a>已知限制

- 只能为每个客户细分中的 100'000 成员导出到 Dynamics 365 Sales。
- 将客户细分导出至 Dynamics 365 Sales 最多可能需要 3 个小时才能完成。 

## <a name="prerequisite-for-connection"></a>连接的先决条件

1. Dynamics 365 Sales 中必须先存在联系人记录，然后才能从 Customer Insights 中将客户细分导出到 Sales。 详细了解如何[在 Dynamics 365 Sales 中使用 Microsoft Dataverse](connect-power-query.md)引入联系人。

   > [!NOTE]
   > 如果将客户细分从受众见解导出到 Sales，则将不会在 Sales 实例中创建新的联系人记录。 Sales 中的联系人记录必须引入到受众见解中，并用作数据源。 在导出客户细分之前，还需要将它们包含在统一客户实体中，以将客户 ID 映射到联系人 ID。

## <a name="set-up-the-connection-to-sales"></a>设置与 Sales 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Dynamics 365 Sales** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 在 **服务器地址** 字段中输入组织的 Sales URL。

1. 在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Sales 帐户。

1. 将客户 ID 字段映射到 Dynamics 365 联系人 ID。

1. 选择 **保存** 以完成连接。 

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Dynamics 365 Sales 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选择一个或多个客户细分。

1. 选择 **保存**

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
