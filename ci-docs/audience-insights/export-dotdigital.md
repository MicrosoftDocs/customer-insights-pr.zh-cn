---
title: 将 Customer Insights 数据导出到 DotDigital
description: 了解如何配置连接和导出到 DotDigital。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124400"
---
# <a name="export-segments-to-dotdigital-preview"></a>将客户细分导出到 DotDigital（预览版）

将统一客户配置文件的客户细分导出到 DotDigital 通讯簿，并将其用于市场活动、电子邮件市场营销和使用 DotDigital 生成客户细分。 

## <a name="prerequisites-for-a-connection"></a>连接的先决条件

-   您具有 [DotDigital 帐户](https://dotdigital.com/)和相应的管理员凭据。
-   DotDigital 中有现有通讯簿和相应的 ID。 当您选择并打开通讯簿时，可以在 URL 中找到 ID。 有关详细信息，请参阅 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次最多可以向 DotDigital 导出 100 万个配置文件。
- 导出到 DotDigital 仅限于客户细分。
- 由于对提供者有限制，因此，导出总共包含 100 万个配置文件的客户细分可能最多需要 3 小时。 
- 可以导出到 DotDigital 的配置文件数与 DotDigital 的合同相关并受其限制。

## <a name="set-up-connection-to-dotdigital"></a>设置与 DotDigital 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **DotDigital** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 **DotDigital 用户名和密码**。

1. 输入您的 **[DotDigital 通讯簿 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 DotDigital 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。 

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 DotDigital 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。


1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 对于其他可选字段（例如 **名**、**姓**、**全名**、**性别** 和 **邮政编码**），请重复相同的步骤。

1. 选择想要导出的细分。 您总共可以将最多 100 万个客户配置文件导出到 DotDigital 中。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 
 
在 DotDigital 中，您现在可以在 [DotDigital 通讯簿](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)中找到您的客户细分。


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 DotDigital 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 DotDigital 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
