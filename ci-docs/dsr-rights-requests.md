---
title: GDPR 下的数据使用者权限 (DSR) 请求 | Microsoft Docs
description: 响应 Dynamics 365 Customer Insights 的数据使用者请求。
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146684"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR 下的数据使用者权限 (DSR) 请求

欧盟的一般数据保护条例 (GDPR) 自 2018 年 5 月 25 日已经生效。 它向个人提供有关其数据的重要权限。 GDPR 是关于保护和支持个人的隐私权的条例。 您可以在 [Microsoft 信任中心](https://www.microsoft.com/trust-center)了解 Microsoft 对安全性和合规性的承诺。

我们致力于帮助客户满足其 GDPR 要求。 它还包括删除和导出包含个人信息（如用户 ID、电话号码和电子邮件地址）的数据的权利。 管理员可以实施用户删除或导出个人数据的请求。

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>响应 Dynamics 365 Customer Insights 的 GDPR 数据使用者删除请求

从组织的客户数据中删除个人数据的“删除权”是一般数据保护条例 (GDPR) 中的一项关键保护措施。 删除个人数据包括删除所有个人数据和系统生成的日志，但审核日志信息除外。

#### <a name="manage-data-subject-delete-requests"></a>管理数据使用者删除请求

Customer Insights 提供以下产品内体验，以便删除特定客户或用户的个人数据：

- **管理客户数据删除请求**：Customer Insights 中的客户数据是从 Customer Insights 外部的原始数据源引入的。 首先在原始数据源中执行 GDPR 删除请求。
- **管理 Customer Insights 用户数据的删除请求**：用户的数据由 Customer Insights 创建。 所有 GDPR 删除请求都必须在 Customer Insights 中执行。

##### <a name="manage-requests-to-delete-customer-data"></a>管理有关删除客户数据的请求

Customer Insights 管理员可以按照以下步骤删除数据源中删除的客户数据。 在继续执行下面列出的步骤之前，请确保在您的数据源中执行了删除请求。 

1. 登录到 Dynamics 365 Customer Insights。
1. 转到 **数据** > **数据源**
1. 对于包含已删除客户数据的列表中的每个数据源：
   1. 选择竖省略号 (&vellip;)，然后选择 **刷新**。
   1. 在 **状态** 下检查数据源的状态。 选中标记表示刷新成功。 警告三角形表示已出错。 如果显示警告三角形，请与 D365CI@microsoft.com 联系。
1. 成功刷新数据源后，也应运行下游刷新。 特别是在您没有计划定期完全刷新 Customer Insights 时。 

> [!IMPORTANT]
> 删除请求后，静态客户细分不包含在完全刷新或正在运行的下游刷新中。 要确保客户数据也从静态客户细分中删除，使用刷新的源数据重新创建静态客户细分。

> [!div class="mx-imgBorder"]
> ![处理客户数据的 GDPR 删除请求。](media/gdpr-data-sources.png "处理客户数据的 GDPR 删除请求")

##### <a name="manage-delete-requests-for-user-data"></a>管理用户数据的删除请求

Customer Insights 管理员可以执行以下步骤删除 Customer Insights 用户数据：

1. 登录到 Dynamics 365 Customer Insights。
2. 转到 **管理** > **安全** > **权限**。
3. 选中要删除的用户的复选框。
4. 选择 **删除**。

### <a name="responding-to-gdpr-data-subject-export-requests"></a>响应 GDPR 数据主体导出请求

我们致力于在您通向 一般数据保护条例 (GDPR) 的旅程中与您合作，开发了文档来帮助您响应数据使用者的请求。

#### <a name="manage-export-and-view-requests"></a>管理导出和查看请求

数据可移植性权限让数据使用者可请求其个人数据的电子格式（“结构化，常用，机器可识别的可互操作格式”）副本，该副本可传输到其他数据控制方。

##### <a name="export-customer-data-tenant-admin"></a>导出客户数据（租户管理员）

租户管理员可执行以下步骤导出数据：

1. 向 D365CI@microsoft.com 发送电子邮件，并在请求中指定客户的电子邮件地址。 Customer Insights 团队将向注册的租户管理员电子邮件地址发送电子邮件，请求确认导出数据。
2. 认可确认以导出所请求客户的数据。
3. 通过租户管理员电子邮件地址接收导出的数据。

##### <a name="export-user-data-tenant-admin"></a>导出用户数据（租户管理员）

1. 向 D365CI@microsoft.com 发送电子邮件，并在请求中指定用户的电子邮件地址。 Customer Insights 团队将向注册的租户管理员电子邮件地址发送电子邮件，请求确认导出数据。
2. 认可确认以导出所请求用户的数据。
3. 通过租户管理员电子邮件地址接收导出的数据。

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 中的数据删除处理

1. 如果数据分区和数据快照处于非活动状态超过 30 天，数据将被删除（数据分区和数据快照），这意味着它们已通过数据源的刷新被新的数据分区和快照替换。
2. 并非所有数据和快照都会被删除。 最新的数据分区和数据快照根据定义激活，因为它们在 Customer Insights 中使用。 对于最新数据，数据源是否在过去 30 天内未刷新不重要。

[!INCLUDE [footer-include](includes/footer-banner.md)]
