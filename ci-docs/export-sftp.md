---
title: 将数据导出到 SFTP 主机（预览版）（包含视频）
description: 了解如何配置连接和导出到 SFTP 位置。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207218"
---
# <a name="export-data-to-sftp-hosts-preview"></a>将数据导出到 SFTP 主机（预览）

将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 位置，以使用这些数据。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>先决条件

- SFTP 主机的可用性和相应的凭据。

## <a name="known-limitations"></a>已知限制

- 防火墙后的 SFTP 目标当前不受支持。
- 导出的运行时间取决于系统性能。 建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。
- 在使用建议的两个 CPU 内核和 1 GB 内存这种最低配置时最多导出 1 亿个客户配置文件，可能需要 90 分钟。
- 如果您使用 SSH 密钥进行身份验证，请确保以 PEM 或 SSH.COM 格式[创建您的私钥](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)。 如果您使用的是 Putty，请通过导出为 Open SSH 来转换您的私钥。 支持以下私钥格式：
  - OpenSSL PEM 和 ssh.com 格式的 RSA
  - OpenSSL PEM 和 ssh.com 格式的 DSA
  - OpenSSL PEM 格式的 ECDSA 256/384/521
  - OpenSSH 密钥格式的 ED25519 和 RSA

## <a name="set-up-connection-to-sftp"></a>设置与 SFTP 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **SFTP**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择是否要通过 SSH 或连接的用户名/密码进行身份验证，并提供必要的详细信息。 如果您使用 SSH 密钥进行身份验证，请确保以 PEM 或 SSH.COM 格式[创建您的私钥](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)。 如果您使用的是 Putty，请通过导出为 Open SSH 来转换您的私钥。 支持以下私钥格式：
   - OpenSSL PEM 和 ssh.com 格式的 RSA
   - OpenSSL PEM 和 ssh.com 格式的 DSA
   - OpenSSL PEM 格式的 ECDSA 256/384/521
   - OpenSSH 密钥格式的 ED25519 和 RSA

1. 选择 **验证** 测试连接。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 SFTP 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 选择要为导出的文件导出 **已进行 gzip 压缩** 的数据还是 **已解压缩** 的数据，以及是否导出 **字段分隔符**。

1. 选择要导出的实体，如客户细分。

   > [!NOTE]
   > 导出后，每个选定实体最多将拆分成五个输出文件。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> 导出包含大量数据的实体可能会导致每次导出在同一文件夹中生成多个 CSV 文件。 出于性能原因拆分导出以最大程度地减少导出完成所需的时间。

[!INCLUDE [footer-include](includes/footer-banner.md)]
