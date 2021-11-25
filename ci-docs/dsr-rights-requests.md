---
title: GDPR 下的数据使用者权限 (DSR) 请求 | Microsoft Docs
description: 响应 Dynamics 365 Customer Insights 访问群体见解功能的数据主体请求。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732669"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR 下的数据使用者权限 (DSR) 请求

欧盟的一般数据保护条例 (GDPR) 自 2018 年 5 月 25 日已经生效。 它向个人提供有关其数据的重要权限。 GDPR 是关于保护和支持个人的隐私权的条例。 您可以在 [Microsoft 信任中心](https://www.microsoft.com/trust-center)了解 Microsoft 对安全性和合规性的承诺。

我们致力于帮助客户满足其 GDPR 要求。 它还包括删除和导出包含个人信息（如用户 ID、电话号码和电子邮件地址）的数据的权利。 管理员可以实施用户删除或导出个人数据的请求。

## <a name="audience-insights"></a>访问群体见解

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>响应 Dynamics 365 Customer Insights 访问群体见解功能的 GDPR 数据主体删除请求

从组织的客户数据中删除个人数据的“删除权”是一般数据保护条例 (GDPR) 中的一项关键保护措施。 删除个人数据包括删除所有个人数据和系统生成的日志，但审核日志信息除外。

#### <a name="manage-data-subject-delete-requests"></a>管理数据使用者删除请求

访问群体见解提供以下产品内体验，以删除特定客户或用户的个人数据：

- **管理客户数据删除请求**：Customer Insights 中的客户数据是从 Customer Insights 外部的原始数据源引入的。 所有 GDPR 删除请求都必须在原始数据源中执行。
- **管理 Customer Insights 用户数据的删除请求**：用户的数据由 Customer Insights 创建。 所有 GDPR 删除请求都必须在 Customer Insights 中执行。

##### <a name="manage-requests-to-delete-customer-data"></a>管理有关删除客户数据的请求

Customer Insights 管理员可以按照以下步骤删除数据源中删除的客户数据：

1. 登录到 Dynamics 365 Customer Insights。
2. 在访问群体见解中，转到 **数据** > **数据源**
3. 对于包含已删除客户数据的列表中的每个数据源：
   1. 选择 (...)，然后选择 **刷新**。
   2. 在 **状态** 下检查数据源的状态。 选中标记表示刷新成功。 警告三角形表示已出错。 如果显示警告三角形，请与 D365CI@microsoft.com 联系。

> [!div class="mx-imgBorder"]
> ![处理客户数据的 GDPR 删除请求。](audience-insights/media/gdpr-data-sources.png "处理客户数据的 GDPR 删除请求")

##### <a name="manage-delete-requests-for-user-data"></a>管理用户数据的删除请求

Customer Insights 管理员可以执行以下步骤删除 Customer Insights 用户数据：

1. 登录到 Dynamics 365 Customer Insights。
2. 在访问群体见解中，转到 **管理员** > **权限**。
3. 选中要删除的用户的复选框。
4. 选择 **删除**。

### <a name="responding-to-gdpr-data-subject-export-requests"></a>响应 GDPR 数据主体导出请求

我们致力于在您通向 一般数据保护条例 (GDPR) 的旅程中与您合作，开发了文档来帮助您做好准备。 本文档介绍了针对以下操作可立即采取的步骤：在使用访问群体见解时支持 GDPR 合规性。

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

## <a name="consent-management-preview"></a>同意管理（预览版）

同意管理功能不直接收集用户数据。 它仅导入和处理用户在其他应用程序中所提供的同意数据。

若要删除有关特定用户的同意数据，请在引入到同意管理功能的数据源中将其删除。 刷新数据源后，删除的数据也将在同意中心删除。 在[刷新](audience-insights/system.md#refresh-processes)之后，使用同意实体的应用程序也将删除源中已删除的数据。 建议在响应数据主题请求后快速刷新数据源，以从所有其他进程和应用程序中删除用户数据。


## <a name="engagement-insights-preview"></a>参与见解(预览版)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>删除和导出包含最终用户可识别信息的事件数据

以下各节说明了如何删除和导出可能包含个人数据的事件数据。

要删除或导出数据，请执行以下操作：

1. 标记包含带有个人信息的数据的事件属性。
2. 删除或导出与特定值关联的数据（例如：指定的用户 ID）。

#### <a name="tag-and-update-event-properties"></a>标记和更新事件属性

在事件属性级别对个人数据进行标记。 首先，标记考虑删除或导出的属性。

要将事件属性标记为包含个人信息，请执行以下步骤：

1. 打开包含事件的工作区。

1. 转到 **数据** > **事件** 以查看所选工作区中的事件列表。
  
1. 选择您要标记的事件。

1. 选择 **编辑属性** 以打开列出所选事件的所有属性的窗格。
     
1. 选择 **...**，然后选择 **编辑** 以到达 **更新属性** 对话框。

   ![编辑事件。](engagement-insights/media/edit-event.png "编辑事件")

1. 在 **更新属性** 窗口中，选择右上角的 **...**，然后选择 **包含 EUII** 框。 选择 **更新** 以保存您所做的更改。

   ![保存您的更改。](engagement-insights/media/update-property.png "保存您的更改")

   > [!NOTE]
   > 每次事件模式更改或创建新事件时，建议您评估关联的事件属性，并在必要时将它们标记为包含个人数据或取消此类标记。

#### <a name="delete-or-export-tagged-event-data"></a>删除或导出标记的事件数据

如果已按照上一步中的说明对所有事件属性进行了适当的标记，则环境管理员可以针对标记的事件数据发出删除请求。

管理 EUII 删除或导出请求

1. 转到 **管理** > **环境** > **设置**。

1. 在 **管理最终用户识别信息 (EUII)** 部分，选择 **管理 EUII**。

##### <a name="deletion"></a>删除

要进行删除，您可以在 **删除最终用户可识别信息 (EUII)** 部分中输入逗号分隔的用户 ID 列表。 然后，通过精确的字符串匹配，将这些 ID 与当前环境中所有项目的所有标记事件属性进行比较。 

如果属性值与提供的一个 ID 匹配，将永久删除关联事件。 由于此操作不可撤消，因此必须在选择 **删除** 后确认删除。

##### <a name="export"></a>Export

就在 **导出最终用户可识别信息 (EUII)** 部分中定义事件属性值而言，导出过程与删除过程相同。 此外，您需要提供 **Azure blob 存储 URL** 以指定导出目标。 Azure Blob URL 必须包括[共享访问签名 (SAS)](/azure/storage/common/storage-sas-overview)。

选择 **导出** 后，包含匹配标记属性的当前团队的所有事件都将以 CSV 格式导出到导出目标。

### <a name="good-practices"></a>良好实践

* 请尝试避免发送包含个人数据的任何事件。
* 如果需要发送包含 EUII 数据的事件，请限制包含 EUII 数据的事件数和事件属性。 理想情况下，将自己限制为一个此类事件。
* 确保让尽可能少的人具有发送个人数据的访问权限。
* 对于包含个人数据的事件，请确保设置一个属性以发出可以轻松链接到特定用户的唯一标识符（例如，用户 ID）。 这样更便于分离数据以及导出或删除正确的数据。
* 对于每个事件，仅标记一个包含个人数据的属性。 理想情况下，仅标记只包含唯一标识符的属性。
* 不要标记包含详细值的属性（例如整个请求正文）。 在决定要删除或导出的事件时，参与度见解功能使用精确字符串匹配。

[!INCLUDE[footer-include](includes/footer-banner.md)]