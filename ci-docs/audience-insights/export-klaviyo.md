---
title: 将 Customer Insights 数据导出到 Klaviyo
description: 了解如何配置连接和导出到 Klaviyo。
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385777"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>将客户细分列表导出到 Klaviyo（预览版）

将统一客户配置文件的客户细分导出到 Klaviyo，并将其用于市场营销活动。

## <a name="prerequisites"></a>先决条件

-   您具有 [Klaviyo 帐户](https://www.klaviyo.com/)和相应的管理员凭据。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出到 Klaviyo 可导出最多 100'000 个配置文件。
- 导出到 Klaviyo 仅限于客户细分。
- 最多将 1 百万个配置文件导出到 Klaviyo 可能最多需要 20 分钟才能完成。 
- 可以导出到 Klaviyo 的配置文件数依赖于您与 Klaviyo 的合同并受其限制。

## <a name="set-up-connection-to-klaviyo"></a>设置与 Klaviyo 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Klaviyo** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供您的 [Klaviyo API 密钥](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys)以继续登录。 

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 Klaviyo 的连接。

1. 选择 **通过 Klaviyo 进行身份验证**，并提供您的 Klaviyo 管理员凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **用于导出的连接** 字段中，从 Klaviyo 部分中选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 输入您的 [**Klaviyo 列表 ID**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID)。     

3. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 在将客户细分导出到 Klaviyo 时需要它。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当启用 Dynamics 365 Customer Insights 将数据传输到 Klaviyo 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。 Microsoft 将根据您的指示传输此类数据，但您负责确保 Klaviyo 满足您可能承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
