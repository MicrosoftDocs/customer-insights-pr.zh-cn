---
title: 将 Customer Insights 数据导出到 Criteo
description: 了解如何配置连接并导出到 Criteo。
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808760"
---
# <a name="export-segments-to-criteo-preview"></a>将客户细分导出到 Criteo（预览版）

导出统一客户配置文件的客户细分，以生成市场活动、提供电子邮件市场营销，并将特定客户组与 Criteo 配合使用。

## <a name="prerequisites-for-connection"></a>连接的先决条件

-   您有一个 [Criteo Dynamics Retargeting 帐户](https://www.criteo.com/login/)和相应的管理员凭据。
-   您已[配置客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次导出到 Criteo 最多可导出 100 万个客户配置文件。
- 导出到 Criteo 仅限于客户细分。
- 导出总计包含 100 万个客户配置文件的客户细分最长可能需要 30 分钟。 
- 您可以导出到 Criteo 的客户配置文件数量取决和受限于您与 Criteo 的合同。

## <a name="set-up-connection-to-criteo"></a>设置与 Criteo 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接**，然后选择 **Criteo** 配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择 **我同意** 以确认 **数据隐私与合规性**，并选择 **连接** 以初始化与 Criteo 的连接。

1. 选择 **向 Criteo 进行身份验证**，并为 Criteo 提供您的管理员用户名和密码。 

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 Criteo 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。 

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 

1. 您也可以选择性地导出 **广告厂商 ID** 和 **名称**

1. 选择想要导出的细分。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Criteo 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 Criteo 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](includes/footer-banner.md)]
