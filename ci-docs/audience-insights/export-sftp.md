---
title: 将 Customer Insights 数据导出到 SFTP 主机
description: 了解如何配置与 SFTP 主机的连接。
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267987"
---
# <a name="connector-for-sftp-preview"></a>SFTP 连接器（预览）

通过将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 主机，从而使用这些数据。

## <a name="prerequisites"></a>先决条件

- SFTP 主机的可用性和相应的凭据。

## <a name="connect-to-sftp"></a>连接到 SFTP

1. 转到 **管理员** > **导出目标**。

1. 在 **SFTP** 下，选择 **设置**。

1. 在 **显示名称** 字段中为目标指定易于识别的名称。

1. 提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。

1. 选择 **验证** 测试连接。

1. 成功验证后，选择是要导出 **已进行 gzip 压缩** 还是 **已解压缩** 的数据，然后为导出的文件选择 **字段分隔符**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **下一步** 开始配置导出。

## <a name="configure-the-export"></a>配置导出

1. 选择要导出的实体，如客户细分。

   > [!NOTE]
   > 导出后，每个选定实体最多将有五个输出文件。 

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。

## <a name="known-limitations"></a>已知限制

- 导出的运行时间取决于系统性能。 建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。 
- 在使用建议的两个 CPU 内核和 1 GB 内存这种最低配置时，导出具有多达 1 亿个客户配置文件的实体可能需要 90 分钟。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]