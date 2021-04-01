---
title: 通过第三方扩充 Experian 扩充
description: 有关 Experian 第三方扩充的常规信息。
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597776"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>使用来自 Experian 的人口统计数据扩充客户配置文件（预览）

Experian 是消费者和企业信用报告以及营销服务的全球领导者。 借助 Experian 的数据扩充服务，您可以通过人口统计数据（如家庭人数、收入等）扩充客户配置文件，从而加深对客户的了解。

## <a name="prerequisites"></a>先决条件

要配置 Experian，必须满足以下先决条件：

- 您有有效的 Experian 订阅。 若要获取订阅，请直接[联系 Experian](https://www.experian.com/marketing-services/contact)。 [了解有关 Experian 数据扩充的详细信息](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。
- 您有 Experian 为您创建的已启用 SSH 的安全传输 (ST) 帐户的用户 ID、参与方 ID 和型号。
- 您在访问群体见解中具有[管理员](permissions.md#administrator)权限。

## <a name="configuration"></a>配置

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 Experian 磁贴上选择 **扩充我的数据**。

   > [!div class="mx-imgBorder"]
   > ![Experian 磁贴](media/experian-tile.png "Experian 磁贴")

1. 选择 **开始**，输入您的 Experian 安全传输帐户的用户 ID、参与方 ID 和型号。 进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。 选择 **应用** 确认所有输入。

## <a name="map-your-fields"></a>映射字段

1.  选择 **添加数据** 并选择要使用 Experian 的统计信息数据扩充的 **客户数据集**。 您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。

1. 从 **姓名和地址**、**电子邮件** 或 **电话** 中选择您的密钥标识符，以发送给 Experian 进行身份解析。

   > [!TIP]
   > 发送给 Experian 的密钥标识符属性越多，匹配率会越高。

1. 选择 **下一步**，为所选密钥标识符字段映射统一客户实体中的对应属性。

1. 选择 **添加属性** 可映射您想要发送到 Experian 的任何其他属性。

1.  选择 **保存** 完成字段映射。

    > [!div class="mx-imgBorder"]
    > ![Experian 字段映射](media/experian-field-mapping.png "Experian 字段映射")

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