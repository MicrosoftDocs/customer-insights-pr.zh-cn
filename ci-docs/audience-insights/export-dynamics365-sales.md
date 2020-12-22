---
title: 将 Customer Insights 数据导出到 Dynamics 365 Sales
description: 了解如何配置与 Dynamics 365 Sales 之间的连接。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643807"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales 的连接器（预览版）

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

使用您的客户数据通过 Dynamics 365 Sales 创建市场营销列表、跟进工作流以及发出促销。

## <a name="prerequisite"></a>先决条件

[来自使用 Common Data Service 引入的 Dynamics 365 Sales](connect-power-query.md)的联系人记录。

## <a name="configure-the-connector-for-sales"></a>配置 Sales 的连接器

1. 在访问群体见解中，转到 **管理员** > **导出目标**。

1. 在 **Dynamics 365 Sales** 下，选择 **设置**。

1. 在 **显示名称** 字段中为导出目标指定易于识别的名称。

1. 在 **服务器地址** 字段中输入组织的 Sales URL。

1. 在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Sales 帐户。

1. 将客户 ID 字段映射到 Dynamics 365 联系人 ID。

1. 选择 **下一步**。

1. 选择一个或多个客户细分。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。
