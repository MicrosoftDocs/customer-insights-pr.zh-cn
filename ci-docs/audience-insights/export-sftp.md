---
title: 将 Customer Insights 数据导出到 SFTP 主机
description: 了解如何配置连接和导出到 SFTP 位置。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b19ca6b8085846785682046f83d0ed4758269e5b98303692c703d995407ca7dd
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035450"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>将客户细分和其他数据导出到 SFTP（预览版）

将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 位置，以使用这些数据。

## <a name="prerequisites-for-connection"></a>连接的先决条件

- SFTP 主机的可用性和相应的凭据。

## <a name="known-limitations"></a>已知限制

- 导出的运行时间取决于系统性能。 建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。 
- 在使用建议的两个 CPU 内核和 1 GB 内存这种最低配置时，导出具有多达 1 亿个客户配置文件的实体可能需要 90 分钟。 

## <a name="set-up-connection-to-sftp"></a>设置与 SFTP 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **SFTP** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。

1. 选择 **验证** 测试连接。

1. 选择要为导出的文件导出 **已进行 gzip 压缩** 的数据还是 **已解压缩** 的数据，以及是否导出 **字段分隔符**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 SFTP 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选择要导出的实体，如客户细分。

   > [!NOTE]
   > 导出后，每个选定实体最多将拆分成五个输出文件。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
