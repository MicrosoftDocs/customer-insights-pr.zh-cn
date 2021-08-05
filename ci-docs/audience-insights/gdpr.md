---
title: GDPR 下的数据使用者权限 (DSR) 请求 | Microsoft Docs
description: 响应 Dynamics 365 Customer Insights 访问群体见解功能的数据主体请求。
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e832fbbdfb59cb06d98715223edca438d2c3a7f2
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554295"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR 下的数据使用者权限 (DSR) 请求

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>响应 Dynamics 365 Customer Insights 访问群体见解功能的 GDPR 数据主体删除请求

从组织的客户数据中删除个人数据的“删除权”是一般数据保护条例 (GDPR) 中的一项关键保护措施。 删除个人数据包括删除所有个人数据和系统生成的日志，但审核日志信息除外。

### <a name="manage-data-subject-delete-requests"></a>管理数据使用者删除请求

访问群体见解提供以下产品内体验，以删除特定客户或用户的个人数据：

- **管理客户数据删除请求**：Customer Insights 中的客户数据是从 Customer Insights 外部的原始数据源引入的。 所有 GDPR 删除请求都必须在原始数据源中执行。
- **管理 Customer Insights 用户数据的删除请求**：用户的数据由 Customer Insights 创建。 所有 GDPR 删除请求都必须在 Customer Insights 中执行。

#### <a name="manage-delete-requests-for-customer-data"></a>管理客户数据的删除请求

Customer Insights 管理员可以按照以下步骤删除数据源中删除的客户数据：

1. 登录到 Dynamics 365 Customer Insights。
2. 在访问群体见解中，转到 **数据** > **数据源**
3. 对于包含已删除客户数据的列表中的每个数据源：
   1. 选择 (...)，然后选择 **刷新**。
   2. 在 **状态** 下检查数据源的状态。 选中标记表示刷新成功。 警告三角形表示已出错。 如果显示警告三角形，请与 D365CI@microsoft.com 联系。

> [!div class="mx-imgBorder"]
> ![处理客户数据的 GDPR 删除请求。](media/gdpr-data-sources.png "处理客户数据的 GDPR 删除请求")

#### <a name="manage-delete-requests-for-user-data"></a>管理用户数据的删除请求

Customer Insights 管理员可以执行以下步骤删除 Customer Insights 用户数据：

1. 登录到 Dynamics 365 Customer Insights。
2. 在访问群体见解中，转到 **管理员** > **权限**。
3. 选中要删除的用户的复选框。
4. 选择 **删除**。

> [!div class="mx-imgBorder"]
> ![处理用户数据的 GDPR 删除请求。](media/gdpr-permissions.png "处理用户数据的 GDPR 删除请求")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>响应 GDPR 数据主体导出请求

我们致力于在您通向 一般数据保护条例 (GDPR) 的旅程中与您合作，开发了文档来帮助您做好准备。 本文档介绍了针对以下操作可立即采取的步骤：在使用访问群体见解时支持 GDPR 合规性。

### <a name="manage-export-and-view-requests"></a>管理导出和查看请求

数据可移植性权限让数据使用者可请求其个人数据的电子格式（“结构化，常用，机器可识别的可互操作格式”）副本，该副本可传输到其他数据控制方。

#### <a name="export-customer-data-tenant-admin"></a>导出客户数据（租户管理员）

租户管理员可执行以下步骤导出数据：

1. 向 D365CI@microsoft.com 发送电子邮件，并在请求中指定客户的电子邮件地址。 Customer Insights 团队将向注册的租户管理员电子邮件地址发送电子邮件，请求确认导出数据。
2. 认可确认以导出所请求客户的数据。
3. 通过租户管理员电子邮件地址接收导出的数据。

#### <a name="export-user-data-tenant-admin"></a>导出用户数据（租户管理员）

1. 向 D365CI@microsoft.com 发送电子邮件，并在请求中指定用户的电子邮件地址。 Customer Insights 团队将向注册的租户管理员电子邮件地址发送电子邮件，请求确认导出数据。
2. 认可确认以导出所请求用户的数据。
3. 通过租户管理员电子邮件地址接收导出的数据。


[!INCLUDE[footer-include](../includes/footer-banner.md)]