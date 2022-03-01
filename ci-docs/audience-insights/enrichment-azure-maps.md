---
title: 使用 Azure Maps 中的位置数据扩充客户配置文件
description: 有关 Azure Maps 第一方扩充的常规信息。
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466751"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>使用 Azure Maps（预览版）扩充客户配置文件

Azure Maps 提供以位置为中心的数据和服务，通过内置位置智能提供基于地理空间数据的体验。 Azure Maps 数据扩充服务可以提高有关客户位置的信息的精度。 其为 Dynamics 365 Customer Insights 提供地址标准化和经纬度提取之类功能。

## <a name="prerequisites"></a>先决条件

若要配置 Azure Maps 数据扩充，必须满足以下先决条件：

- 拥有有效的 Azure Maps 订阅。 要获取订阅，您可以[注册或获取免费版](https://azure.microsoft.com/services/azure-maps/)。

- 有 Azure Maps [连接](connections.md)，*或者* 拥有[管理员](permissions.md#administrator)权限和有效的 Azure Maps API 密钥。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**。 

1. 在 **位置** 磁贴中，选择 **扩充我的数据**。

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps 磁贴。":::

1. 从下拉列表中选择[连接](connections.md)。 如果没有可用的 Azure Maps 连接，请联系管理员。 如果您是管理员，您可以[为 Azure Maps 配置连接](#configure-the-connection-for-azure-maps)。 

1. 选择 **下一步** 确认选择。

1. 选择要使用 Azure Maps 中的位置数据扩充的 **客户数据集**。 可以选择 **Customer** 实体以扩充所有统一客户配置文件，也可以选择一个客户细分实体以仅扩充该客户细分中包含的客户配置文件。

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. 选择是否将字段映射到主地址/或辅助地址。 可以为这两种地址指定字段映射，并分别扩充这两种地址的配置文件 &mdash; 流入，对于家庭地址和业务地址。 选择 **下一步**。

1. 定义应该使用统一配置文件中的哪些字段来查找 Azure Maps 中的匹配位置数据。 所选主地址或辅助地址需要 **街道 1** 和 **邮政编码** 字段。 若要提高匹配准确性，可以添加更多字段。

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps 扩充配置页。":::

1. 选择 **下一步** 以完成字段映射。

1. 评估是否要修改 **高级设置**。 这是为了尽量灵活地处理高级用例，但是大多数情况下，默认值就足够了：
   - **地质类型**：默认行为是，即使扩充不完整，也会返回最匹配的地址。 若要仅获取完整地址 &mdash; 例如，包含住宅编号的地址 &mdash; 请清除除 **点地址** 之外的所有复选框。 
   - **语言：** 默认情况下，将使用已确定地址所属区域的语言返回地址。 若要应用标准化地址语言，请从下拉菜单中选择该语言。 例如，选择 **英语** 将返回 **Copenhagen, Denmark**，而不是返回 **København, Danmark**。

1. 提供扩充的名称。

1. 检查选择，然后选择 **保存扩充**。

## <a name="configure-the-connection-for-azure-maps"></a>为 Azure Maps 配置连接

在访问群体见解中，只有管理员才能配置连接。 当配置扩充时选择 **添加连接**，或者转到 **管理** > **连接**，然后在 Azure Maps 磁贴上选择 **设置**。

1. 在 **显示名称** 框中，输入连接的名称。

1. 提供有效的 Azure Maps API 密钥。

1. 进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**

1. 选择 **验证** 以验证配置。

1. 完成验证后，选择 **保存**。

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps 连接配置页。":::

## <a name="enrichment-results"></a>扩充结果

要开始扩充过程，请从命令栏中选择 **运行**。 您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间取决于客户数据的大小和 API 响应时间。

完成扩充过程后，可以在 **我的扩充** 下查看新扩充的客户配置文件数据 。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

基于扩充的客户数据构建。 创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当启用 Dynamics 365 Customer Insights 将数据传输到 Azure Maps 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括可能敏感的数据（例如个人数据）。 Microsoft 将根据您的指示传输此类数据，但您负责确保 Azure Maps 满足您可能承担的任何隐私或安全责任。 有关详细信息，请转到 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
