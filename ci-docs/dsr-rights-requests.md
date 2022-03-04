---
title: GDPR 下的数据使用者权限 (DSR) 请求 | Microsoft Docs
description: 响应 Dynamics 365 Customer Insights 访问群体见解功能的数据主体请求。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350258"
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


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]