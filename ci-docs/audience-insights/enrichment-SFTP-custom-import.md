---
title: 通过 SFTP 自定义导入扩充
description: 有关 SFTP 自定义导入扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 042558af801a1d1fc365939d9aa42c09b98b2679
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376543"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>使用自定义数据扩充客户配置文件（预览）

通过安全文件传输协议 (SFTP) 自定义导入，您可以导入不需要完成数据统一流程的数据。 这是一种灵活、安全和方便的数据引入方式。 SFTP 自定义导入可与 [SFTP 导出](export-sftp.md)结合使用，后者允许您导出扩充所需的客户配置文件数据。 然后，可以处理和扩充数据，SFTP 自定义导入可用于将扩充的数据引入回 Dynamics 365 Customer Insights 的访问群体见解功能。

## <a name="prerequisites"></a>先决条件

若要配置 SFTP 自定义导入，必须满足以下先决条件：

- 您将具有要在 SFTP 主机上导入的文件的文件名和位置（路径）。
- 有一个 *model.json* 文件，用于为要导入的数据指定 [Common Data Model 架构](/common-data-model/)。 此文件必须与要导入的文件位于同一目录中。
- 管理员已配置 SFTP 连接，*或者* 您拥有[管理员](permissions.md#admin)权限。 对于要从中导入数据的 SFTP 位置，您将需要用户凭据、URL 和端口号。


## <a name="configure-the-import"></a>配置导入

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 **SFTP 自定义导入磁贴** 上，选择 **扩充我的数据**，然后选择 **开始**。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 自定义导入磁贴。":::

1. 从下拉列表中选择[连接](connections.md)。 如果没有连接可用，请联系管理员。 如果您是管理员，可以通过选择 **添加连接** 并从下拉列表中选择 **SFTP 自定义导入** 来创建连接。

1. 选择 **连接到自定义导入** 以确认选择的连接。

1.  选择 **下一步**，然后输入您要导入的数据文件的 **路径** 和 **文件名**。

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="输入数据位置时的屏幕截图。":::

1. 选择 **下一步**，然后选择客户数据集。 可以是所有客户配置文件或一个客户细分。

1. 选择 **下一步** 并提供扩充的名称和输出实体的名称。 

1. 在查看您的选择后选择 **保存扩充**。

## <a name="configure-the-connection-for-sftp-custom-import"></a>配置 SFTP 自定义导入的连接 

您必须是管理员才能配置连接。 配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在自定义导入磁贴上选择 **设置**。

1. 在 **显示名称** 框中输入连接的名称。

1. 输入要导入的数据所在的 SFTP 服务器的有效用户名、密码和主机 URL。

1. 进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。

1. 选择 **验证** 以验证配置。

1. 验证完成后，可以通过选择 **保存** 来保存连接。

   > [!div class="mx-imgBorder"]
   > ![Experian 连接配置页面。](media/enrichment-SFTP-connection.png "Experian 连接配置页面")


## <a name="defining-field-mappings"></a>正在定义字段映射 

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>扩充结果

要开始扩充过程，请从命令栏中选择 **运行**。 您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间将取决于要导入的数据的大小和与 SFTP 服务器的连接。

完成扩充流程后，您可以在 **我的扩充** 下查看新导入的自定义扩充数据。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
