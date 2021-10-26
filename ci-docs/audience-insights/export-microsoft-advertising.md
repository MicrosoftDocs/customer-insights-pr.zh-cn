---
title: 将 Customer Insights 数据导出到 Microsoft Advertising
description: 了解如何配置连接和导出到 Microsoft Advertising。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 12fd221acb7c0eed443c9b860aca42dcb2b3788c
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618050"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>将客户细分导出到 Microsoft Advertising（预览版）

将 Customer Insights 客户细分导出到 Microsoft Advertising，以创建客户匹配访问群体。 将这些访问群体用于您的广告市场活动。

## <a name="prerequisites"></a>先决条件

-   [Microsoft Advertising 帐户](https://ads.microsoft.com/)和相应的管理员凭据。
-   您已接受客户匹配使用条款。 
-   访问群体见解中的[配置的客户细分](segments.md)。
-   已导出客户细分中的统一客户配置文件包含带有电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次最多可以将 500'000 个客户配置文件导出到 Microsoft Advertising。
- 导出到 Microsoft Advertising 仅限于客户细分。
- 向 Microsoft Advertising 导出最多 500'000 个客户配置文件最长可能需要 10 分钟完成。 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>设置与 Microsoft Advertising 的连接（预览版）

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Microsoft Advertising** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认为管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 Microsoft Advertising 的连接。

1. 选择 **使用 Microsoft Advertising 进行身份验证**，并为 Microsoft Advertising 提供您的管理凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Microsoft Advertising 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选择要导出的客户细分。 会使用为导出选择的客户细分的名称自动创建 Microsoft Advertising 中的客户匹配访问群体。 每个客户细分将产生一个单独的客户匹配访问群体。 

1. 输入您的 **Microsoft Advertising 客户 ID 和帐户 ID**。 当您登录 Microsoft Advertising 时，您可以在 URL 的参数中查找客户 ID (`cid`) 和帐户 ID (`aid`)。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择包含客户电子邮件地址的字段。 必须将客户细分导出到 Microsoft Advertising。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以将数据传输到 Microsoft Advertising 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。 Microsoft 将在您的指示下传输此类数据，但您有责任确保 Microsoft Advertising 履行您可能具有的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来停止使用此功能。
