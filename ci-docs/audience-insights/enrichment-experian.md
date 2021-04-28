---
title: 通过第三方扩充 Experian 扩充
description: 有关 Experian 第三方扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896362"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>使用来自 Experian 的人口统计数据扩充客户配置文件（预览）

Experian 是消费者和企业信用报告以及营销服务的全球领导者。 借助 Experian 的数据扩充服务，您可以通过人口统计数据（如家庭人数、收入等）扩充客户配置文件，从而加深对客户的了解。

## <a name="prerequisites"></a>先决条件

要配置 Experian，必须满足以下先决条件：

- 您有有效的 Experian 订阅。 若要获取订阅，请直接[联系 Experian](https://www.experian.com/marketing-services/contact)。 [了解有关 Experian 数据扩充的详细信息](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- 管理员已配置 Experian 连接，*或者* 您拥有[管理员](permissions.md#administrator)权限。 对于 Experian 为您创建的支持 SSH 的安全传输 (ST) 帐户，您还需要用户 ID、参与方 ID 和型号。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 Experian 磁贴上选择 **扩充我的数据**。

   > [!div class="mx-imgBorder"]
   > ![Experian 磁贴](media/experian-tile.png "Experian 磁贴")
   > 

1. 从下拉列表选择[连接](connections.md)。 如果没有连接可用，请联系管理员。 如果您是管理员，则可以通过选择 **添加连接** 并从下拉列表中选择 Experian 来创建连接。 

1. 选择 **连接到 Experian** 以确认连接选择。

1.  选择 **下一步**，然后选择您希望利用 Experian 提供的人口统计数据扩充的 **客户数据集**。 您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. 选择 **下一步**，并定义应使用统一配置文件中的哪种字段来查找来自 Experian 的匹配人口统计数据。 至少需要 **名称和地址**、**电话** 或 **电子邮件** 中的一个字段。 为了提高匹配精度，最多可添加其他两个字段。 此选项会影响您可以在下一步中访问的映射字段。

    > [!TIP]
    > 发送给 Experian 的密钥标识符属性越多，匹配率会越高。

1. 选择 **下一步** 以开始字段映射。

1. 定义应使用统一配置文件中的哪些字段来查找来自 Experian 的匹配人口统计数据。 必填字段都有标记。

1. 提供扩充的名称和输出实体的名称。

1. 在查看您的选择后选择 **保存扩充**。

## <a name="configure-the-connection-for-experian"></a>针对 Experian 配置连接 

您必须是管理员才能配置连接。 配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在 Experian 磁贴上选择 **设置**。

1. 选择 **开始**。

1. 在 **显示名称** 框中输入连接的名称。

1. 输入 Experian 扩展安全传输帐户的有效用户 ID、参与方 ID 和型号。

1. 进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**

1. 选择 **验证** 以验证配置。

1. 完成验证后，选择 **保存**。
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 连接配置窗格。":::

## <a name="enrichment-results"></a>扩充结果

要开始扩充过程，请从命令栏中选择 **运行**。 您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间取决于客户数据的大小和 Experian 为您的帐户设置的扩充流程。

扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

基于扩充的客户数据构建。 创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 Experian 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 Experian 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
