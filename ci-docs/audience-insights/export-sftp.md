---
title: 将 Customer Insights 数据导出到 SFTP 主机
description: 了解如何配置与 SFTP 主机的连接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643492"
---
# <a name="connector-for-sftp-preview"></a>SFTP 连接器（预览）

通过将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 主机，从而使用这些数据。

## <a name="prerequisites"></a>先决条件

- SFTP 主机和相应凭据的可用性。

## <a name="connect-to-sftp"></a>连接到 SFTP

1. 转到 **管理员** > **导出目标**。

1. 在 **SFTP** 下，选择 **设置**。

1. 在 **显示名称** 字段中为目标指定易于识别的名称。

1. 提供 SFTP 帐户的 **用户名**、**密码** 和 **主机名**。 示例：如果您的 SFTP 服务器的根文件夹为 /root/folder，并且您想要将数据导出到 /root/folder/ci_export_destination_folder，则该主机应该是 sftp://<server_address>/ci_export_destination_folder。

1. 选择 **验证** 测试连接。

1. 成功验证后，选择要导出 **压缩** 还是 **解压缩** 数据，然后为导出的文件选择 **字段分隔符**。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **下一步** 开始配置导出。

## <a name="configure-the-connection"></a>配置连接

1. 选择要导出的 **客户属性**。 您可以导出一个或多个属性。

1. 选择 **下一步**。

1. 选择想要导出的细分。

1. 选择 **保存**。

## <a name="export-the-data"></a>导出数据

可以[根据需要导出数据](export-destinations.md)。 导出也会在每次[计划刷新](system.md#schedule-tab)时运行。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。
