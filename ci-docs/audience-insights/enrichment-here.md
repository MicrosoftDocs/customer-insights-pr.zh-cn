---
title: 通过第三方扩充 HERE Technologies 进行的扩充
description: 有关 HERE Technologies 第三方扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376269"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>通过 HERE Technologies 扩充客户配置文件（预览）

HERE Technologies 是一家位置平台公司，可提供以位置为中心的数据和服务。 通过 HERE Technologies 的数据扩充服务，您可以使用地址标准化、维度和精度提取等来更准确地了解客户的位置信息。

## <a name="prerequisites"></a>先决条件

若要配置 HERE Technologies 扩充，必须满足以下先决条件：

- 您具有有效的 HERE Technologies 订阅。 若要获取订阅，您可以在[此处注册](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)或直接[与 HERE Technologies 联系](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。 [了解有关 HERE Technologies 位置扩充的详细信息。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [连接](connections.md)可用，*或者* 您具有[管理员](permissions.md#admin)权限和 HERE Technologies API 密钥。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**。 

1. 在 HERE Technologies 磁贴上选择 **扩充我的数据**，然后选择 **开始**。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 磁贴。](media/HERE-tile.png "HERE Technologies 磁贴")

1. 从下拉列表中选择[连接](connections.md)。 如果没有连接可用，请联系管理员。 如果您是管理员，则可以通过选择 **添加连接** 来创建连接。 从下拉列表中选择 **HERE Technologies**。 

1. 选择 **连接到 HERE Technologies** 以确认选择。

1.  选择 **下一步**，然后选择您希望利用 HERE Technologies 提供的位置数据扩充的 **客户数据集**。 您可以选择 **客户** 实体以扩充所有客户配置文件，也可以选择客户细分实体以仅扩充该客户细分中包含的客户配置文件。

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="选择客户数据集时的屏幕截图。":::

1. 选择是否要将字段映射到主要地址和/或辅助地址。 您可以为两个地址指定字段映射，并分别扩充这两个地址的配置文件。 例如，如果有一个家庭地址和一个商业地址。 选择 **下一步**。

1. 定义应使用统一配置文件中的哪些字段来查找 HERE Technologies 中的匹配位置数据。 必须为所选的主要和/或辅助地址指定 **街道 1** 和 **邮政编码** 字段。 为了使匹配精度更高，可添加更多字段。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 扩充配置页面。](media/enrichment-HERE-configuration.png "HERE Technologies 扩充配置页面")

1. 选择 **下一步** 以完成字段映射。

1. 提供扩充的名称。 

1. 在查看您的选择后选择 **保存扩充**。

## <a name="configure-the-connection-for-here-technologies"></a>为 HERE Technologies 配置连接 

您必须是管理员才能配置连接。 配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在 HERE Technologies 磁贴上选择 **设置**。

1. 在 **显示名称** 框中输入连接的名称。

1. 提供有效的 HERE Technologies API 密钥。

1. 通过选择 **我同意**，查看并同意 **数据隐私与合规性**。

1. 选择 **验证** 以验证配置。

1. 完成验证后，选择 **保存**。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 连接配置页面。](media/enrichment-HERE-connection.png "HERE Technologies 连接配置页面")

## <a name="enrichment-results"></a>扩充结果

要开始扩充过程，请从命令栏中选择 **运行**。 您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间将取决于您的客户数据的大小和 HERE Technologies 的 API 响应时间。

扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 HERE Technologies 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 HERE Technologies 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
