---
title: 将 Customer Insights 数据导出到 Braze
description: 了解如何配置连接并导出到 Braze。
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645604"
---
# <a name="export-segment-lists-to-braze-preview"></a>将客户细分列表导出到 Braze（预览）

将 Unified customer profile 的客户细分导出到 Braze，然后将其用于市场营销活动。

## <a name="prerequisites"></a>先决条件

-   您有 [Braze 帐户](https://www.braze.com/)和相应的管理员凭据。
-   您在 Customer Insights 中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的 Unified customer profile 包含一个表示电子邮件地址和 Braze 客户 ID 的字段。 

## <a name="known-limitations"></a>已知限制

- 导出到 Braze 仅限于客户细分。
- 向 Braze 导出最多 100 万个客户配置文件最长可能需要 40 分钟完成。 
- 您可以导出到 Braze 的客户配置文件数量取决和受限于您与 Braze 的合同。

## <a name="set-up-connection-to-braze"></a>设置与 Braze 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接**，然后选择 **Braze** 配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 [Braze API 密钥](https://www.braze.com/docs/api/basics/)继续登录。 

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 初始化与 Braze 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Braze 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。  

3. 在 **数据匹配** 部分，在 **电子邮件** 字段中，选择代表客户电子邮件地址的字段，在“客户 ID”字段中，选择代表客户的 Braze ID 的字段。 需要将客户细分导出到 Braze。 Braze 中的客户细分将使用与 Dynamics 365 Customer Insights 中的客户细分相同的名称创建。 您可以选择其他的可选字段来匹配数据。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Braze 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 Braze 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
