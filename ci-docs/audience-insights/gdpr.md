---
title: GDPR 下的数据使用者权限 (DSR) 请求 | Microsoft Docs
description: 响应 Dynamics 365 Customer Insights 访问群体见解功能的数据主体请求。
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405211"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="11932-103">GDPR 下的数据使用者权限 (DSR) 请求</span><span class="sxs-lookup"><span data-stu-id="11932-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="11932-104">响应 Dynamics 365 Customer Insights 访问群体见解功能的 GDPR 数据主体删除请求</span><span class="sxs-lookup"><span data-stu-id="11932-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="11932-105">从组织的客户数据中删除个人数据的“删除权”是一般数据保护条例 (GDPR) 中的一项关键保护措施。</span><span class="sxs-lookup"><span data-stu-id="11932-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="11932-106">删除个人数据包括删除所有个人数据和系统生成的日志，但审核日志信息除外。</span><span class="sxs-lookup"><span data-stu-id="11932-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="11932-107">管理数据使用者删除请求</span><span class="sxs-lookup"><span data-stu-id="11932-107">Manage data subject delete requests</span></span>

<span data-ttu-id="11932-108">访问群体见解提供以下产品内体验，以删除特定客户或用户的个人数据：</span><span class="sxs-lookup"><span data-stu-id="11932-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="11932-109">**管理客户数据删除请求**：Customer Insights 中的客户数据是从 Customer Insights 外部的原始数据源引入的。</span><span class="sxs-lookup"><span data-stu-id="11932-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="11932-110">所有 GDPR 删除请求都必须在原始数据源中执行。</span><span class="sxs-lookup"><span data-stu-id="11932-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="11932-111">**管理 Customer Insights 用户数据的删除请求**：用户的数据由 Customer Insights 创建。</span><span class="sxs-lookup"><span data-stu-id="11932-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="11932-112">所有 GDPR 删除请求都必须在 Customer Insights 中执行。</span><span class="sxs-lookup"><span data-stu-id="11932-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="11932-113">管理客户数据的删除请求</span><span class="sxs-lookup"><span data-stu-id="11932-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="11932-114">Customer Insights 管理员可以按照以下步骤删除数据源中删除的客户数据：</span><span class="sxs-lookup"><span data-stu-id="11932-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="11932-115">登录到 Dynamics 365 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="11932-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="11932-116">在访问群体见解中，转到 **数据** > **数据源**</span><span class="sxs-lookup"><span data-stu-id="11932-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="11932-117">对于包含已删除客户数据的列表中的每个数据源：</span><span class="sxs-lookup"><span data-stu-id="11932-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="11932-118">选择 (...)，然后选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="11932-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="11932-119">在 **状态** 下检查数据源的状态。</span><span class="sxs-lookup"><span data-stu-id="11932-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="11932-120">选中标记表示刷新成功。</span><span class="sxs-lookup"><span data-stu-id="11932-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="11932-121">警告三角形表示已出错。</span><span class="sxs-lookup"><span data-stu-id="11932-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="11932-122">如果显示警告三角形，请与 D365CI@microsoft.com 联系。</span><span class="sxs-lookup"><span data-stu-id="11932-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11932-123">![处理客户数据的 GDPR 删除请求](media/gdpr-data-sources.png "处理客户数据的 GDPR 删除请求")</span><span class="sxs-lookup"><span data-stu-id="11932-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="11932-124">管理用户数据的删除请求</span><span class="sxs-lookup"><span data-stu-id="11932-124">Manage delete requests for user data</span></span>

<span data-ttu-id="11932-125">Customer Insights 管理员可以执行以下步骤删除 Customer Insights 用户数据：</span><span class="sxs-lookup"><span data-stu-id="11932-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="11932-126">登录到 Dynamics 365 Customer Insights。</span><span class="sxs-lookup"><span data-stu-id="11932-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="11932-127">在访问群体见解中，转到 **管理员** > **权限**。</span><span class="sxs-lookup"><span data-stu-id="11932-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="11932-128">选中要删除的用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="11932-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="11932-129">选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="11932-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11932-130">![处理用户数据的 GDPR 删除请求](media/gdpr-permissions.png "处理用户数据的 GDPR 删除请求")</span><span class="sxs-lookup"><span data-stu-id="11932-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="11932-131">响应 GDPR 数据主体导出请求</span><span class="sxs-lookup"><span data-stu-id="11932-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="11932-132">我们致力于在您通向 一般数据保护条例 (GDPR) 的旅程中与您合作，开发了文档来帮助您做好准备。</span><span class="sxs-lookup"><span data-stu-id="11932-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="11932-133">本文档介绍了针对以下操作可立即采取的步骤：在使用访问群体见解时支持 GDPR 合规性。</span><span class="sxs-lookup"><span data-stu-id="11932-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="11932-134">管理导出和查看请求</span><span class="sxs-lookup"><span data-stu-id="11932-134">Manage export and view requests</span></span>

<span data-ttu-id="11932-135">数据可移植性权限让数据使用者可请求其个人数据的电子格式（“结构化，常用，机器可识别的可互操作格式”）副本，该副本可传输到其他数据控制方。</span><span class="sxs-lookup"><span data-stu-id="11932-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="11932-136">导出客户数据（租户管理员）</span><span class="sxs-lookup"><span data-stu-id="11932-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="11932-137">租户管理员可执行以下步骤导出数据：</span><span class="sxs-lookup"><span data-stu-id="11932-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="11932-138">向 D365CI@microsoft.com 发送电子邮件，并在请求中指定客户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="11932-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="11932-139">Customer Insights 团队将向注册的租户管理员电子邮件地址发送电子邮件，请求确认导出数据。</span><span class="sxs-lookup"><span data-stu-id="11932-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="11932-140">认可确认以导出所请求客户的数据。</span><span class="sxs-lookup"><span data-stu-id="11932-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="11932-141">通过租户管理员电子邮件地址接收导出的数据。</span><span class="sxs-lookup"><span data-stu-id="11932-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="11932-142">导出用户数据（租户管理员）</span><span class="sxs-lookup"><span data-stu-id="11932-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="11932-143">向 D365CI@microsoft.com 发送电子邮件，并在请求中指定用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="11932-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="11932-144">Customer Insights 团队将向注册的租户管理员电子邮件地址发送电子邮件，请求确认导出数据。</span><span class="sxs-lookup"><span data-stu-id="11932-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="11932-145">认可确认以导出所请求用户的数据。</span><span class="sxs-lookup"><span data-stu-id="11932-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="11932-146">通过租户管理员电子邮件地址接收导出的数据。</span><span class="sxs-lookup"><span data-stu-id="11932-146">Receive the exported data through the tenant admin email address.</span></span>
