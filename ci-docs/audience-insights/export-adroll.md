---
title: 将 Customer Insights 数据导出到 AdRoll
description: 了解如何配置与 AdRoll 的连接。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697063"
---
# <a name="connector-for-adroll-preview"></a>用于 AdRoll 的连接器（预览版）

将统一客户配置文件的客户细分导出到 AdRoll 中，并使用它们投放广告。 

## <a name="prerequisites"></a>先决条件

-   您具有 [AdRoll 帐户](https://www.adroll.com/)和相应的管理员凭据。
-   您在访问群体见解中具有[配置的客户细分](segments.md)。
-   导出的客户细分中的统一客户配置文件包含表示电子邮件地址的字段。

## <a name="connect-to-adroll"></a>连接到 AdRoll

1. 转到 **管理员** > **导出目标**。

1. 在 **AdRoll** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 连接的配置窗格。":::

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **连接** 以初始化与 AdRoll 的连接。

1. 选择 **使用 AdRoll 进行身份验证** 并提供您的 AdRoll 管理员凭据。 

1. 选择 **将自己添加为导出用户** 并提供您的 Customer Insights 凭据。

1. 输入您的 **AdRoll 广告厂商 ID** [AdRoll 播发功能](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)。

1. 选择 **下一步** 配置导出。

## <a name="configure-the-connector"></a>配置连接器

1. 在 **数据匹配** 部分的 **电子邮件** 字段中，选择统一客户配置文件中表示客户电子邮件地址的字段。 需要将客户细分导出到 AdRoll。

1. 选择想要导出的细分。 选择至少包含 100 个成员的客户细分。 不能导出较小的客户细分。 此外，对于每个导出，要导出的客户细分的最大大小为 250'000 个成员。 

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。

## <a name="known-limitations"></a>已知限制

- 对于每个导出，您最多可以将 250'000 个配置文件导出到 AdRoll 中。
- 您不能将配置文件少于 100 个的客户细分导出到 AdRoll。 
- 导出到 AdRoll 仅限于客户细分。
- 最多将 250'000 个配置文件导出到 AdRoll 可能需要 10 分钟才能完成。 
- 可以导出到 AdRoll 的配置文件数与 AdRoll 的合同相关并受其限制。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 AdRoll 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 AdRoll 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。

您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
