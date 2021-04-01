---
title: 将 Customer Insights 数据导出到 Dynamics 365 Marketing
description: 了解如何配置与 Dynamics 365 Marketing 之间的连接。
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597592"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing 的连接器（预览版）

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

使用[客户细分](segments.md)来生成市场活动，并通过 Dynamics 365 Marketing 联系特定客户组。 有关详细信息，请参阅[将来自 Dynamics 365 Customer Insights 的客户细分与 Dynamics 365 Marketing 结合使用](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>先决条件

- Dynamics 365 Marketing 中必须先存在联系人记录，然后才能从 Customer Insights 中将客户细分导出到 Marketing。 详细了解如何[在 Dynamics 365 Marketing 中使用 Common Data Services](connect-power-query.md)引入联系人。

  > [!NOTE]
  > 如果将客户细分从受众见解导出到 Marketing，则将不会在 Marketing 实例中创建新的联系人记录。 Marketing 中的联系人记录必须引入到受众见解中，并用作数据源。 在导出客户细分之前，还需要将它们包含在统一客户实体中，以将客户 ID 映射到联系人 ID。

## <a name="configure-the-connector-for-marketing"></a>配置 Marketing 的连接器

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **Dynamics 365 Marketing** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

1. 在 **服务器地址** 字段中输入组织的 Marketing URL。

1. 在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Marketing 帐户。

1. 将客户 ID 字段映射到 Dynamics 365 联系人 ID。

1. 选择 **下一步**。

1. 选择一个或多个客户细分。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。


[!INCLUDE[footer-include](../includes/footer-banner.md)]