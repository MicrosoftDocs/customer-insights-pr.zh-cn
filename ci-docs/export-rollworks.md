---
title: 将客户细分导出到 RollWorks（预览版）
description: 了解如何配置连接和导出到 RollWorks。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 83c3f2437b9822d29d1d2f99ead96815b1b0881a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055157"
---
# <a name="export-segments-to-rollworks-preview"></a>将客户细分导出到 RollWorks（预览版）

将统一客户配置文件的客户细分导出到 RollWorks，并将其用于广告。 

## <a name="prerequisites-for-a-connection"></a>连接的先决条件

-   您有一个 [RollWorks 帐户](https://www.rollworks.com/)和相应的管理员凭据。
-   您在 Customer Insights 中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="known-limitations"></a>已知限制

- 每次最多可以将 250'000 个客户配置文件导出到 RollWorks。
- 不能将少于 100 个客户配置文件的客户细分导出到 RollWorks。 
- 导出到 RollWorks 仅限于客户细分。
- 向 RollWorks 导出最多 250'000 个客户配置文件最长可能需要 10 分钟完成。 
- 您可以导出到 RollWorks 的客户配置文件数量取决和受限于您与 RollWorks 的合同。

## <a name="set-up-connection-to-rollworks"></a>设置与 RollWorks 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **RollWorks** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 RollWorks 的连接。

1. 选择 **使用 RollWorks 进行身份验证**，并为 RollWorks 提供您的管理凭据。

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 RollWorks 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 输入您的 **RollWorks 广告商 ID** [RollWorks 播发信息](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择表示客户电子邮件地址的字段。 必须将客户细分导出到 RollWorks。

1. 选择想要导出的细分。 选择至少包含 100 个成员的客户细分。 不能导出较小的客户细分。 此外，对于每个导出，要导出的客户细分的最大大小为 250'000 个成员。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 


## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以将数据传输到 RollWorks 时，您允许将数据传输到 Dynamics 365 Customer Insights 合规性边界之外，包括潜在的敏感数据（如个人数据）。 Microsoft 将在您的指示下传输此类数据，但您有责任确保 RollWorks 履行您可能具有的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
