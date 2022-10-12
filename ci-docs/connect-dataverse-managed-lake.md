---
title: 连接到 Microsoft Dataverse 托管数据湖中的数据
description: 从 Microsoft Dataverse 托管数据湖导入数据。
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609781"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>连接到 Microsoft Dataverse 托管数据湖中的数据

Microsoft Dataverse 用户可以快速连接到 Microsoft Dataverse 托管湖中的分析实体。 仅环境中的一个数据源可以同时使用相同的 Dataverse 托管湖。

> [!NOTE]
> 您必须是 Dataverse 组织的管理员才能继续查看托管湖中可用的实体列表。

## <a name="prerequisites"></a>先决条件

- 可以将联机服务（如 Azure Data Lake Storage）中存储的数据存储到 Dynamics 365 Customer Insights 中处理或存储数据之外的位置。导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心](https://www.microsoft.com/trust-center)。

- 只有启用了[更改跟踪](/power-platform/admin/enable-change-tracking-control-data-synchronization)的 Dataverse 实体可见。 这些实体可以导出到 Dataverse 托管的数据湖并在 Customer Insights 中使用。 现成可用的 Dataverse 表默认已启用更改跟踪。 您需要为自定义表打开更改跟踪。 要检查 Dataverse 表是否启用了更改跟踪，请转到 [Power Apps](https://make.powerapps.com) > **数据** > **表**。 查找您感兴趣的表并选择它。 转到 **设置** > **高级选项**，查看 **跟踪更改** 设置。

## <a name="connect-to-a-dataverse-managed-lake"></a>连接到 Dataverse 托管湖

1. 转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **Microsoft Dataverse**。

1. 为数据源输入 **名称** 和 **说明**（可选）。

1. 为 Dataverse 组织提供 **服务器地址**，然后选择 **登录**。

1. 从可用列表中选择要作为实体引入到 Customer Insights 中的表。

   > [!NOTE]
   > 如果已选择某些表，则其他 Dynamics 365 应用程序（例如 Dynamics 365 Sales Insights 或 Customer Service Insights）可能会使用它们。 您不能更改此选择。 创建数据源后，这些表将可用作实体。

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="显示 Dataverse 环境中的实体列表的对话框。":::

1. 保存您的选择，以开始同步 Dataverse 中的选定表。 您将在 **数据源** 页上找到新添加的连接。 它将排队等待刷新并将实体计数显示为 0，直到同步了所有选定表为止。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

加载数据可能需要一些时间。 成功刷新后，可以从 [**实体**](entities.md)页查看引入的数据。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>编辑 Dataverse 托管湖数据源

您仅在创建数据源之后才编辑对实体的选择。 例如，如果其他实体被添加到 Dataverse 中，并且您也希望导入它们。
要连接到不同的 Dataverse Data Lake，请[创建新数据源](#connect-to-a-dataverse-managed-lake)。

1. 转到 **数据** > **数据源**。

1. 在要更新的数据源旁边，选择 **编辑**。

1. 从可用实体列表中选择其他实体。

1. 单击 **保存** 应用您的更改并返回到 **数据源** 页面。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>引入错误或数据损坏的常见原因

对引入的数据运行了以下检查以显示损坏的记录：

- 字段的值与其列的数据类型不匹配。
- 字段包含导致列与预期架构不匹配的字符。 例如：格式不正确的引号、未转义的引号或换行符。
- 如果存在日期时间/日期/datetimeoffset 列，则必须在模型中指定其格式（如果它没有遵循标准的 ISO 格式）。

### <a name="schema-or-data-type-mismatch"></a>架构或数据类型不匹配

如果数据不符合架构，记录将被分类为损坏。 更正源数据或架构，然后重新引入数据。

### <a name="datetime-fields-in-the-wrong-format"></a>格式错误的日期/时间字段

实体中的日期/时间字段不是 ISO 或 en-US 格式。 Customer Insights 中的默认日期/时间格式为 en-US 格式。 实体中的所有日期/时间字段应采用相同格式。 Customer Insights 还支持其他格式，前提是在模型或 manifest.json 中的源或实体级别进行注释或设置特征。 例如: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  在 manifest.json 中，可以在实体级别或属性级别指定日期/时间格式。 在实体级别，在 *.manifest.cdm.json 中的实体中使用“exhibitsTraits”定义日期/时间格式。 在属性级别，在 entityname.cdm.json 中的属性中使用“appliedTraits”。

**实体级别的 Manifest.json**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**属性级别的 Entity.json**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
