---
title: 将 Customer Insights 数据导出到 ActiveCampaign
description: 了解如何配置连接和导出到 ActiveCampaign。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645818"
---
# <a name="export-segments-to-activecampaign-preview"></a>将客户细分导出到 ActiveCampaign（预览）

将统一客户配置文件的客户细分导出到 ActiveCampaign，并将其用于市场营销活动。

## <a name="prerequisites"></a>先决条件

-   您具有 [ActiveCampaign 帐户](https://www.activecampaign.com/)和相应的管理员凭据。
-   您在 Customer Insights 中具有[配置的客户细分](segments.md)。
-   已导出客户细分中的统一客户配置文件包含带有电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 一次导出最多可将 100 万个客户配置文件导出到 ActiveCampaign，最多可能需要 90 分钟完成。
- 导出到 ActiveCampaign 仅限于客户细分。
- 您可以导出到 ActiveCampaign 的客户配置文件数量取决于您与 ActiveCampaign 的合同。

## <a name="set-up-connection-to-activecampaign"></a>设置与 ActiveCampaign 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **ActiveCampaign** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 输入您的 [ActiveCampaign API 密钥和 REST 终结点主机名](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key)。 REST 终结点主机名是纯主机名，不带 https://。 

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 ActiveCampaign 的连接。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **用于导出的连接** 字段中，从 ActiveCampaign 部分中选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 输入您的 [**ActiveCampaign 列表 ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)。    

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 在将客户细分导出到 ActiveCampaign 时需要它。 您也可以选择导出名、姓和电话号码来创建更个性化的电子邮件。 选择添加属性以映射这些字段。

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当启用 Dynamics 365 Customer Insights 将数据传输到 ActiveCampaign 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。 Microsoft 将根据您的指示传输此类数据，但您负责确保 ActiveCampaign 满足您可能承担的任何隐私或安全责任。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
