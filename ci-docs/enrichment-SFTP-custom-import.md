---
title: 使用 SFTP 自定义导入扩充客户配置文件（预览版）
description: 有关 SFTP 自定义导入扩充的常规信息。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237755"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>使用 SFTP 自定义导入扩充客户配置文件（预览版）

通过安全文件传输协议 (SFTP) 自定义导入，您可以导入不需要完成数据统一流程的数据。 这是一种灵活、安全和方便的数据引入方式。 SFTP 自定义导入可与 [SFTP 导出](export-sftp.md)结合使用，后者允许您导出扩充所需的客户配置文件数据。 然后可以处理和扩充数据，并且可以使用 SFTP 自定义导入将扩充的数据引入到 Dynamics 365 Customer Insights 中。

## <a name="prerequisites"></a>先决条件

- 要导入的文件在 SFTP 主机上的文件名和位置（路径）是已知的。

- 有为要导入的数据指定 Common Data Model 架构的 *model.json* 文件。 此文件必须与要导入的文件位于同一目录中。

- 已[配置](#configure-the-connection-for-sftp-custom-import) SFTP [连接](connections.md)。

## <a name="file-schema-example"></a>文件架构示例

包含要在 SFTP 服务器上导入的文件的目录也必须包含 *model.json* 文件。 此文件定义用于导入数据的架构。 架构必须使用 [Common Data Model](/common-data-model/) 指定字段映射。 Model.json 文件的一个简单示例如下所示：

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>配置 SFTP 自定义导入的连接

您必须是 Customer Insights 中的[管理员](permissions.md#admin)，并且具有要从中导入数据的 SFTP 位置的用户凭据、URL 和端口号。

1. 配置扩充时选择 **添加连接**，或转到 **管理员** > **连接**，然后在自定义导入磁贴上选择 **设置**。

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="自定义导入连接配置页面。":::

1. 为连接输入名称。

1. 输入要导入的数据所在的 SFTP 服务器的有效用户名、密码和主机 URL。

1. 查看 [数据隐私和合规性](connections.md#data-privacy-and-compliance)，并选择 **我同意**。

1. 选择 **验证** 验证配置，然后选择 **保存**。

## <a name="configure-the-import"></a>配置导入

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 **SFTP 自定义导入** 磁贴上选择 **扩充我的数据**。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 自定义导入磁贴。":::

1. 查看概览，然后选择 **下一步**。

1. 选择连接。 如果没有连接可用，请联系管理员。

1. 选择 **客户数据集**，然后选择您想要扩充的资料或客户细分。 *客户* 实体扩充您的所有客户资料，而客户细分仅扩充该客户细分中包含的客户资料。

1. 选择 **下一步**。

1. 输入您要导入的数据文件的 **路径** 和 **文件名**。

1. 选择 **下一步**。

1. 为扩充提供 **名称**，并提供 **输出实体名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **运行** 启动扩充过程或关闭返回到 **扩充** 页面。

## <a name="view-enrichment-results"></a>查看扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]