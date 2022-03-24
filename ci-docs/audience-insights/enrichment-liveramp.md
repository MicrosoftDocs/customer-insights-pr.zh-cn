---
title: LiveRamp 标识数据扩充
description: 使用 LiveRamp 数据扩充客户资料。
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373004"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>使用 LiveRamp 的标识数据扩充客户资料（预览） 

LiveRamp 提供确定性的离线标识解析和客户数据整合。 您可以将客户数据中的个人标识符映射到 AbiliTec 标识图形，然后接收 AbiliTec ID。 然后，您可以使用这些 ID 更好地统一您的客户数据。 

## <a name="prerequisites"></a>先决条件 

要配置扩充，必须满足以下先决条件： 

- 您有有效的 LiveRamp 订阅。 要获取订阅，请联系您的 LiveRamp 客户团队或 [dynamics@liveramp.com](mailto:dynamics@liveramp.com) 了解更多信息。   

- 具有客户端 ID 和机密的有效 AbiliTec 订阅，用于访问 API。 有关详细信息，请参阅 [AbiliTec API 开发人员中心](https://developers.liveramp.com/abilitec-api/)。 

## <a name="supported-countriesregions"></a>支持的国家/地区 

我们目前仅支持在美国使用 LiveRamp 数据扩充客户资料。 

## <a name="configure-the-enrichment"></a>配置扩充 

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。 

1. 在 **标识** 磁贴上选择 **扩充我的数据**。 

   :::image type="content" source="media/liveramp-tile.png" alt-text="扩充概览页面的标识磁贴。":::

1. 从下拉列表中选择[连接](connections.md)。 如果没有连接可用，请联系管理员。 如果您是管理员，您可以通过选择 **添加连接** 来创建连接。 从下拉列表中选择 **LiveRamp**。 

1. 选择 **下一步**，然后选择您要使用 LiveRamp 中的标识数据扩充的 **客户数据集**。 您可以选择 *客户* 实体以扩充所有客户配置文件，也可以选择 *客户细分* 实体以仅扩充该客户细分中包含的客户配置文件。 

1. 选择 **下一步**，定义应使用统一配置文件中的哪种字段查找 LiveRamp 中的匹配的标识数据。 **姓名和地址**、**电话** 或 **电子邮件** 字段中至少有一个是必填项。 

   > [!TIP]
   > 您映射的键标识符和字段越多，匹配率较高的可能性就越大 

1. 映射来自统一 *客户* 实体的字段，这些字段将用于与 LiveRamp 的 AbiliTec ID 图形进行匹配。 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp 扩充的数据映射选项。":::

1. 选择 **下一步** 以完成字段映射。 

1. 为扩充和 **输出实体** 提供 **名称**。 

1. 在查看您的选择后选择 **保存扩充**。 

## <a name="configure-the-connection-for-liveramp"></a>配置 LiveRamp 的连接 

您必须是管理员才能[配置连接](connections.md)。 配置扩充时选择 **添加连接**，或转到 **管理** > **连接**，在 **LiveRamp** 磁贴上选择 **设置**。 

:::image type="content" source="media/liveramp-connection.png" alt-text="用于设置与 LiveRamp AbiliTec 服务的连接的配置窗格。":::

1. 对于 **显示名称**，输入连接的名称。 

1. 提供有效的 LiveRamp 客户端 ID 和机密。 

1. 进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。 

1. 选择 **验证** 以验证配置。 

1. 要完成连接，选择 **保存**。 

## <a name="enrichment-results"></a>扩充结果 

要开始扩充过程，请从命令栏中选择“运行”。 您还可以让系统在 [计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间取决于客户数据的大小。 

扩充过程完成后，您可以在 **我的扩充** 下查看新扩充的客户资料数据。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。 

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。 

## <a name="next-steps"></a>后续步骤

基于扩充的客户数据构建。 使用 AbiliTec ID 将客户资料整合到基于个人的视图中。 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性 

当您启用 Dynamics 365 Customer Insights 将数据传输到 LiveRamp 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将按照您的指示传输此类数据，但您有责任确保 LiveRamp 满足您可能需要承担的任何隐私或安全责任。 有关详细信息，请查看 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。 您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
