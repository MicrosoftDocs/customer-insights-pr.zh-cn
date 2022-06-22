---
title: 使用来自 Microsoft Office 365 的数据扩充客户配置文件
description: 使用来自 Microsoft Office 的专有数据用参与数据扩充您的客户配置文件。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954122"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>使用参与数据扩充客户配置文件（预览版）

使用来自 Microsoft Office 365 的数据，通过 Office 365 应用使用参与见解来扩充您的客户帐户配置文件。 参与数据由电子邮件和在客户级别聚合的会议活动组成。 例如，企业客户的电子邮件数或与该客户进行的会议数。 没有提供可用的单个用户相关数据。

## <a name="supported-countries-or-regions"></a>支持的国家或地区

我们目前支持以下区域：英国、欧洲、北美。

## <a name="prerequisites"></a>先决条件

- 有效的 Office 365 云许可证。
- 基于[企业帐户](work-with-business-accounts.md)的 [Unified customer profile](customer-profiles.md)。
- 在您的 Customer Insights 环境中[附加的 Microsoft Dataverse 组织](create-environment.md#step-3-connect-to-microsoft-dataverse)。
- [管理员](permissions.md#admin)权限。
- Office 365 租户管理员的同意，以使用 Office 365 数据在 Dynamics 365 应用程序中提供 **组织见解**。

## <a name="configure-the-enrichment"></a>配置扩充

1. 转到 **数据** > **扩充**，选择 **发现** 选项卡。

1. 在 **帐户参与** 磁贴上选择 **扩充我的数据**。

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="客户参与磁贴":::

1. 查看概览，然后选择 **下一步**。

1. 输入将聚合其 Office 数据的组织的电子邮件地址。 只会处理列出的电子邮件地址的数据来进行相关通信。 最佳做法是使用可在 Office 365 中管理的电子邮件组，例如 *美国销售团队*。 将解析和显示各组的电子邮件地址数。 电子邮件地址的总数必须至少为 2 个，不能超过 2,500 个。

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="客户参与电子邮件地址。":::

1. 选择 **我同意** 查看并提供您对 [Office 365 租户管理员同意](#office-365-tenant-administrator-consent)的同意。

1. 选择 **下一步**。

1. 选择 **联系人数据集**，然后选择您要扩充的资料。 选择 **下一步**。

1. 映射联系人电子邮件地址字段并选择 **下一步**。

1. 为扩充和 **输出实体** 提供 **名称**。

1. 在查看您的选择后选择 **保存扩充**。

1. 选择 **关闭** 返回 **扩充** 页面。

### <a name="office-365-tenant-administrator-consent"></a>Office 365 租户管理员同意

需要获得 Office 365 租户管理员的同意才能激活该扩充。 保存扩充后，会向 Office 365 租户管理员发送一封电子邮件，请求他们查看并同意让 Dynamics 365 应用程序使用您企业的 Office 365 数据以提供 **组织见解**。 Office 365 租户管理员还可以选择 **组织见解**，以直接在 Office 365 管理员控制台表示同意。

## <a name="running-the-enrichment-for-the-first-time"></a>首次运行扩充

首次启动扩充时，在 Office 365 租户管理员表示同意后，将开始从 Office 365 下载数据。 此过程需要一段时间才能完成。 第一次扩充运行将被安排为延迟六个小时进行。 扩充完成后，您可以在客户参与概览页面上看到数据涵盖的天数。 如果数据量大，请过几天后再次运行扩充。 这可以确保数据在整个时间窗口（即一年）内是完整的。

根据您的 Office 数据的大小，运行完扩充可能需要几个小时的时间。

当您运行扩充时，Microsoft 将处理 Office 365 合规性边界内的数据以创建聚合见解，然后将聚合见解添加到您的 Customer Insights 环境中。 Customer Insights 的用户无法使用个人级别的数据（例如，任何电子邮件或日历邀请的正文）。

选择 **运行** 开始扩充过程。

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>扩充结果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] 这是 *Office* 实体。 *Office_UserEntity* 包含在扩充配置期间选择的电子邮件地址的 Active Directory ID。

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="运行扩充流程后预览结果。":::

所有数据都将汇总到客户级别。 系统会计算每个客户的 0 到 100 之间的参与分数。 参与分数提供了与其他客户相关的电子邮件和会议的客户参与综合度量。 以下列表包含客户参与扩充提供的聚合数据：

| 数据​                                                                              | 列名称                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| 参与度分数                                                                  |  EngagementScore                         |
| 发送给客户的电子邮件数                                                       |  NoOfEmails_ToAccount                    |
| 客户发送的电子邮件数                                                     |  NoOfEmails_FromAccount                  |
| 由客户发起的会议的数量                                           |  NoOfMeetings_FromAccount                |
| 由组织发起的会议的数量                                 |  NoOfMeetings_ToAccount                  |
| 贵组织中与客户开会的人数                  |  NoOfContactsInvolved_Meetings           |
| 贵组织中与客户进行电子邮件对话的人数       |  NoOfContactsInvolved_Emails             |
| 客户中与贵组织开会的人数                  |  NoOfAccountContactsInvolved_Meetings    |
| 客户中与贵组织进行电子邮件对话的人数       |  NoOfAccountContactsInvolved_Emails      |
| 参与开始日期（数据中的第一封电子邮件或第一次会议）                        |  EngagementStartDate                     |
| 上次发送电子邮件以来的天数                                                             |  DaysSinceLastEmail                      |
| 上次会议以来的天数                                                           |  DaysSinceLastMeeting                    |
| 平均会议持续时间                                                      |  AverageDuration_Of_Meetings             |
| 客户答复电子邮件的平均持续时间                                    |  AverageDuration_Of_AccountEmailReplies  |
| 聚合开始日期                                                            |  AggregationStartDate                    |
| 聚合级别（年、月或周）                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>查看客户卡中的扩充数据

还可以在个人客户卡上查看客户参与。 转到 **客户**，然后选择客户配置文件。 在客户卡中，您将查找客户的参与分数、电子邮件总数和最近一年聚合的会议总数。 您还可以查找显示电子邮件和会议历史记录的图表。

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="包含扩充后数据的客户卡。":::

## <a name="next-steps"></a>后续步骤

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
例如，一个包含 *上次发送电子邮件以来的天数* 和 *上次会议以来的天数* 值大于 60 的所有客户的客户细分。 该客户细分包含您可以尝试重新激活的旧客户。

[!INCLUDE [footer-include](includes/footer-banner.md)]
