---
title: 通过第三方扩充 HERE Technologies 扩充
description: 有关 HERE Technologies 第三方扩充的常规信息。
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668667"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>通过 HERE Technologies 扩充客户配置文件（预览）

HERE Technologies 是一家位置平台公司，可提供以位置为中心的数据和服务。 通过 HERE Technologies 的数据扩充服务，您可以使用地址标准化、维度和精度提取等来更准确地了解客户的位置信息。

## <a name="prerequisites"></a>先决条件

若要配置 HERE Technologies 扩充，必须满足以下先决条件：

- 您具有有效的 HERE Technologies 订阅。 若要获取订阅，您可以在[此处注册](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)或直接[与 HERE Technologies 联系](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)。 [了解有关 HERE Technologies 位置扩充的详细信息。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- 您具有 HERE Technologies API 密钥。

- 您具有[管理员](permissions.md#administrator)权限。

## <a name="configuration"></a>配置

1. 转到 **数据** > **扩充**。

1. 在 HERE Technologies 磁贴上选择 **扩充我的数据**。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 磁贴](media/HERE-tile.png "HERE Technologies 磁贴")

1. 输入有效的 **HERE Technologies API 密钥**。 进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。 

1. 通过选择 **连接到 HERE** 确认输入。

1. 选择 **添加数据**，然后选择是否要将字段映射到主要地址和/或辅助地址。 您可以为这两个地址（例如家庭和公司地址）指定字段映射，并分别扩充这两个地址的配置文件。 选择 **下一步**。

1. 定义应使用统一配置文件中的哪些字段来查找 HERE Technologies 中的匹配位置数据。 必须为所选的主要和/或辅助地址指定 **街道 1** 和 **邮政编码** 字段。 为了使匹配精度更高，可添加更多字段。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 扩充配置页面](media/enrichment-HERE-configuration.png "HERE Technologies 扩充配置页面")

1. 选择 **应用** 以完成字段映射。

## <a name="enrichment-results"></a>扩充结果

要开始扩充过程，请从命令栏中选择 **运行**。 您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。 处理时间将取决于您的客户数据的大小和 HERE Technologies 的 API 响应时间。

扩充流程完成后，您可以在 **我的扩充** 下查看新扩充的客户配置文件数据。 此外，您还会看到上次更新的时间和扩充的配置文件的数量。

您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。

## <a name="next-steps"></a>后续步骤

基于扩充的客户数据构建。 创建[客户细分](segments.md)、[度量](measures.md)，甚至[导出数据](export-destinations.md)，以便为客户提供个性化的体验。

## <a name="data-privacy-and-compliance"></a>数据隐私与合规性

当您启用 Dynamics 365 Customer Insights 将数据传输到 HERE Technologies 时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。 Microsoft 将在您的指导下传输此类数据，但您有责任确保 HERE Technologies 满足您可能需遵守的任何隐私或安全义务。 有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。
您的 Dynamics 365 Customer Insights 管理员可以随时删除此扩充来中止使用此功能。
