---
title: 将细分市场导出到 LiveRamp（预览版）
description: 了解如何配置连接和导出到 LiveRamp。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196705"
---
# <a name="export-segments-to-liverampreg-preview"></a>将细分市场导出到 LiveRamp&reg;（预览版）

在 LiveRamp 中激活您的数据，以在数字、社交和 TV 中与 500 多个平台进行连接。 在 LiveRamp 中处理数据以便为广告市场活动设置目标，隐藏广告市场活动和个性化广告市场活动。

## <a name="prerequisites"></a>先决条件

- 使用此连接器的 LiveRamp 订阅。 若要获取订阅，请直接[联系 LiveRamp](https://liveramp.com/contact/)。 [详细了解 LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="known-limitations"></a>已知限制

- LiveRamp 导出使用 SFTP 导出。 防火墙后的 SFTP 目标当前不受支持。
- 如果您使用 SSH 密钥进行身份验证，请确保以 PEM 或 SSH.COM 格式[创建您的私钥](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)。 如果您使用的是 Putty，请通过导出为 Open SSH 来转换您的私钥。 支持以下私钥格式：
  - OpenSSL PEM 和 ssh.com 格式的 RSA
  - OpenSSL PEM 和 ssh.com 格式的 DSA
  - OpenSSL PEM 格式的 ECDSA 256/384/521
  - OpenSSH 密钥格式的 ED25519 和 RSA
- 导出的运行时间取决于系统性能。 建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。
- 在使用建议的两个 CPU 内核和 1 GB 内存这种最低配置时，导出具有多达 1 亿个客户配置文件的实体可能需要 90 分钟。
- 您可以导出到 LiveRamp 的配置文件（或数据）的实际数量取决于您的 LiveRamp 订阅。

## <a name="set-up-connection-to-liveramp"></a>设置与 LiveRamp 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **LiveRamp**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 选择是否要通过 SSH 或连接的用户名/密码进行身份验证，并提供必要的详细信息。

1. 选择 **验证** 以测试与 LiveRamp 之间的连接。

1. 验证成功后，查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. 转到 **数据** > **导出**。

1. 选择 **添加导出**。

1. 在 **导出连接** 字段中，从 LiveRamp 部分选择连接。 如果没有连接可用，请联系管理员。

1. 为导出输入名称。

1. 在 **连接数据** 字段中，选择要发送到 LiveRamp 以进行身份识别的 **电子邮件**、**姓名和地址** 或 **电话**。

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="具有属性映射的 LiveRamp 连接器。":::

1. 映射选定密钥标识符在您的 *客户* 实体中的对应属性。

1. 选择 **添加属性** 以映射要发送到 LiveRamp 的更多属性。

   > [!TIP]
   > 向 LiveRamp 发送更多密钥标识符属性可提高匹配率。

1. 选择想要导出的细分。

1. 选择 **保存**。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
