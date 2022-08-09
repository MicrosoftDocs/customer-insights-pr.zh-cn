---
title: 将数据导出到 Salesforce 市场营销云（预览版）
description: 了解如何配置连接和导出到 Salesforce Marketing Cloud。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197027"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>将数据导出到 Salesforce 市场营销云（预览版）

通过安全文件传输协议 (SFTP) 位置导出客户数据以在 Salesforce Marketing Cloud 中使用它们。

## <a name="prerequisites"></a>先决条件

- [Salesforce Marketing Cloud 的 SFTP 主机](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5)和相应的管理员凭据。

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>设置与 Salesforce Marketing Cloud 的连接

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Salesforce Marketing Cloud**。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 默认情况下，仅限管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。

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

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>将 Customer Insights 数据从 SFTP 位置导入到 Salesforce Marketing Cloud

1. [在 Salesforce Marketing Cloud 中创建数据扩展](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)以从 SFTP 位置导入 Customer Insights 数据文件。

2. [将数据从 SFTP 位置导入](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)到 Salesforce Marketing Cloud 数据扩展。

3. 设置自动化以将数据导入到数据扩展。 了解有关[文件拖放自动化和计划自动化](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)的详细信息。

   定义[文件拖放自动化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)或[计划自动化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)。

下面是[使用 SFTP 的自动化](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)的示例。

[!INCLUDE [footer-include](includes/footer-banner.md)]
