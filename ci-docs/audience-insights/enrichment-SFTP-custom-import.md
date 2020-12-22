---
title: 通过 SFTP 自定义导入扩充
description: 有关 SFTP 自定义导入扩充的常规信息。
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568411"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>使用自定义数据扩充客户配置文件（预览）

通过安全文件传输协议 (SFTP) 自定义导入，您可以导入不需要完成数据统一流程的数据。 这是一种灵活、安全和方便的数据引入方式。 SFTP 自定义导入可与 [SFTP 导出](export-sftp.md)结合使用，后者允许您导出扩充所需的客户配置文件数据。 然后可以处理和扩充该数据，SFTP 自定义导入可用于将扩充的数据重新导入到 Dynamics 365 Customer Insights 的访问群体见解功能。

## <a name="prerequisites"></a>先决条件

若要配置 SFTP 自定义导入，必须满足以下先决条件：

- 您具有要从中导入数据的 SFTP 位置的用户凭据（用户名和密码）。
- 您具有 STFP 主机的 URL 和端口号（通常为 22）。
- 您具有要在 SFTP 主机上导入的文件的文件名和位置。
- 存在一个 *model.json* 文件，用于指定要导入的数据的架构。 此文件必须与要导入的文件位于同一目录中。
- 您具有[管理员](permissions.md#administrator)权限。

## <a name="configuration"></a>配置

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 **SFTP 自定义导入磁贴** 上，选择 **扩充我的数据**。

   > [!div class="mx-imgBorder"]
   > ![SFTP 自定义导入磁贴](media/SFTP_Custom_Import_tile.png "SFTP 自定义导入磁贴")

1. 选择 **入门**，并提供 SFTP 服务器的凭据和地址。 例如，sftp://mysftpserver.com:22。

1. 如果文件未在根文件夹中，输入包含数据的文件的名称以及该文件在 SFTP 服务器上的路径。

1. 通过选择 **连接到自定义导入** 确认所有输入。

   > [!div class="mx-imgBorder"]
   > ![SFTP 自定义导入配置弹出项目](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP 自定义导入配置弹出项目")

## <a name="defining-field-mappings"></a>正在定义字段映射 

包含要在 SFTP 服务器上导入的文件的目录也必须包含 *model.json* 文件。 此文件定义用于导入数据的架构。 架构必须使用 [Common Data Model](https://docs.microsoft.com/common-data-model/) 才能指定字段映射。 Model.json 文件的一个简单示例如下所示：

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

基于扩充的客户数据构建。 创建[细分](segments.md)、[度量](measures.md)和[导出数据](export-destinations.md)以为客户提供个性化的体验。


