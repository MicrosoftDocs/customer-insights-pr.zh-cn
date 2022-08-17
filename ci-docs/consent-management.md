---
title: 使用客户同意
description: 通过导入同意数据来遵从客户在 Customer Insights 中的同意首选项。
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245684"
---
# <a name="use-customer-consent"></a>使用客户同意

数据保护和隐私法规赋予个人控制组织如何使用其个人数据的权利。 此类法规如欧盟的《一般数据保护条例》或美国的《加州消费者隐私法案》。 这些法规允许人们选择不让第三方收集、处理或不与其共享他们的个人数据。  

客户可以选择撤回或保留对特定形式的联系的同意。 他们还可能要求您选择退出收集、存储、使用或出售他们的个人数据。 您的组织遵从所有客户的同意和隐私首选项，这一点很重要。  

Dynamics 365 Customer Insights 通过作为 Unified customer profile 的一部分导入并存储客户首选项，来帮助您遵从客户的要求。

如果同意数据与您的客户资料分开存储，[请作为新数据源添加您的同意数据](#import-and-unify-consent-data)。 包含同意数据的数据源将被添加到数据统一过程中。 同意数据和客户资料成功统一之后，将生成包含同意信息的统一客户资料。 对于已包含同意信息的客户资料，请直接转到[使用同意数据](#use-consent-data)一节。

## <a name="prerequisites"></a>先决条件

您的源数据中必须提供以下信息，才能将同意数据与其他客户资料统一起来：

- 用于将同意信息映射到 Customer Insights 中的用户资料的备用键。 例如，电子邮件地址或电话号码。
- 确定客户同意状态的同意值。

考虑添加以下 *可选* 信息：

- 在客户要求更改时用于更新同意状态的主键。
- 同意的类型（如果处理客户信息的方式不止一种）。
- 同意日期或与您的同意场景相关的任何其他类型的数据。

具有多个同意选项的简单同意数据库示例表：

|同意 ID（主键）   |电子邮件（备用键）  |同意选项  |同意值  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  时事通讯       |  错误       |
|2    |  holly@contoso.com       |  产品更新       |  TRUE       |
|3    |  frank@contoso.com       |  时事通讯       | TRUE        |
|4    |  frank@contoso.com       |  产品更新       |  错误       |

## <a name="import-and-unify-consent-data"></a>导入和统一同意数据

像将其他数据源引入 Customer Insights 一样导入同意数据。 有关支持的数据源以及如何导入它们的详细信息，请参阅[数据源概述](data-sources.md)。

有关统一数据源的详细信息，请参阅[数据统一概述](data-unification.md)。

## <a name="use-consent-data"></a>使用同意数据

在您的同意数据成为统一客户资料的一部分后，您即可以在 Customer Insights 中使用它。 例如，创建一个具有规则的客户细分来确保您遵从客户的隐私和数据保护首选项。 支持同意首选项的规则用于根据资料属性将用户排除在客户细分之外。 将规则添加到排除不提供联系同意的客户资料的客户细分。

参考上面的示例表，客户细分可以包含此规则：`Consent option=Newsletter & Consent value=True`。 此配置会生成一个遵从发送时事通讯的联系首选项的客户细分。

有关构建客户细分的详细信息，请参阅[创建客户细分](segment-builder.md)。

创建客户细分后，您可以使用多个[导出选项](export-destinations.md)中的一个在其他应用程序中使用该客户细分。

## <a name="ensure-updated-consent-status"></a>确保同意状态更新

保持客户的同意状态更新非常重要。 Customer Insights 中的计划刷新始终会导入数据源的最新状态。 然后通过数据统一处理此信息，并生成更新的客户资料。 然后，这些更新的资料将用于刷新客户细分，以确保您使用最新的信息。

换言之，确保导入到 Customer Insights 的源数据始终包含最新信息。

有关详细信息，请参阅[手动刷新客户细分](segments.md#refresh-segments)或[配置计划刷新](schedule-refresh.md)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
