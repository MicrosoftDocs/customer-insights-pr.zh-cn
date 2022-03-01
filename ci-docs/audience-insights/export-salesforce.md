---
title: 将 Customer Insights 数据导出到 Salesforce Marketing Cloud
description: 了解如何配置连接和导出到 Salesforce Marketing Cloud。
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8ce243918c2388e931a98df3bbe576ddf692f707
ms.sourcegitcommit: 4823684a1399fd66ffecfce21735f2bc90a1733c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "6660256"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>将客户细分和其他数据导出到 Salesforce Marketing Cloud（预览）

通过安全文件传输协议 (SFTP) 位置导出客户数据以在 Salesforce Marketing Cloud 中使用它们。

## <a name="prerequisites-for-connection"></a>连接的先决条件

- SFTP 主机和相应的管理员凭据的可用性。 [如何为 Salesforce Marketing Cloud 设置 SFTP 位置](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>设置与 Salesforce Marketing Cloud 的连接

1. 转到 **管理员** > **连接**。

1. 选择 **添加连接** 并选择 **Salesforce Marketing Cloud** 以配置连接。

1. 在 **显示名称** 字段中为连接指定易于识别的名称。 连接的名称和类型描述了此连接。 我们建议选择一个名称来解释此连接的用途和目标。

1. 选择可使用此连接的人员。 如果不采取任何行动，默认值将是管理员。 有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. 提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。

1. 选择 **验证** 测试连接。

1. 选择 **我同意** 确认 **数据隐私与合规性**。

1. 选择 **保存** 以完成连接。

## <a name="configure-an-export"></a>配置导出

如果您有权访问此类类型的连接，则可以配置此导出。 有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。

1. 转到 **数据** > **导出**。

1. 要创建新导出，请选择 **添加导出**。

1. 在 **导出连接** 字段中，从 SFTP 部分选择连接。 如果您没有看到此部分名称，则您无法使用此类型的连接。

1. 选择要为导出的文件导出 **已进行 gzip 压缩** 的数据还是 **已解压缩** 的数据，以及是否导出 **字段分隔符**。

1. 选择要导出的实体，如客户细分。

   > [!NOTE]
   > 导出后，每个选定实体最多将拆分成五个输出文件。 

1. 选择 **保存**。

保存导出不会立即运行导出。

每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。 您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>将 Customer Insights 数据从 SFTP 位置导入到 Salesforce Marketing Cloud

1. [在 Salesforce Marketing Cloud 中创建数据扩展](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)以从 SFTP 位置导入 Customer Insights 数据文件。

2. [将数据从 SFTP 位置导入](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)到 Salesforce Marketing Cloud 数据扩展。 

3. 设置自动化以将数据导入到数据扩展。 了解有关[文件拖放自动化和计划自动化](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)的详细信息。

   定义[文件拖放自动化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)或[计划自动化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)。 

下面是[使用 SFTP 的自动化](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)的示例。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
