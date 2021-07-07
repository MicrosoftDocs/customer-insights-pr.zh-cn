---
title: 将 Customer Insights 数据导出到 Sendinblue
description: 了解如何配置连接和导出到 Sendinblue。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314583"
---
# <a name="export-segments-to-sendinblue-preview"></a>将客户细分导出到 Sendinblue（预览）

导出统一客户配置文件的客户细分来生成市场活动，提供电子邮件市场营销，并通过 Sendinblue 使用特定客户组。

## <a name="prerequisites-for-connection"></a>连接的先决条件

-   您具有 [Sendinblue 帐户](https://www.sendinblue.com/)和相应的管理员凭据。
-   Sendinblue 中存在现有列表和相应的 ID。
-   您已[配置客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每个导出最多将 100 万个配置文件导出到 Sendinblue。
- 导出到 Sendinblue 仅限于客户细分。
- 导出总数为 100 万个配置文件的客户细分可能需要最多 90 分钟。 
- 可以导出到 Sendinblue 的配置文件数依赖于您与 AdRoll 的合同并受其限制。

## <a name="set-up-connection-to-sendinblue"></a>设置与 Sendinblue 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Sendinblue** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，它只是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入 **[SendinBlue API 密钥](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**。

1. 选择 **我同意** 确认 **数据隐私与合规性**，然后选择 **连接** 以初始化与 Sendinblue 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **用于导出的连接** 字段中，从 Sendinblue 部分中选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 输入您的 **Sendinblue 列表 ID** 

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 

1. 您也可以选择导出 **名**、**姓** 和 **电话号码** 来创建更个性化的电子邮件。 选择 **添加属性** 以映射这些字段。

1. 选择想要导出的细分。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当启用 Dynamics 365 Customer Insights 将数据传输到 Sendinblue 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。 Microsoft 将根据您的指示传输此类数据，但您负责确保 Sendinblue 满足您可能承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
