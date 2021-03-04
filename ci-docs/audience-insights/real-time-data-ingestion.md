---
title: 实时数据引入和限制
description: 有关访问群体见解中的实时功能的常规信息。
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270269"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="87159-103">实时数据引入（预览版）</span><span class="sxs-lookup"><span data-stu-id="87159-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="87159-104">近实时功能让您可以在数秒内查看客户与您的产品或服务进行的最近交互。</span><span class="sxs-lookup"><span data-stu-id="87159-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="87159-105">[计划刷新](system.md#schedule-tab)包括大量记录和几个复杂操作。</span><span class="sxs-lookup"><span data-stu-id="87159-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="87159-106">首先，从数据源中提取数据。</span><span class="sxs-lookup"><span data-stu-id="87159-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="87159-107">接下来统一数据，然后使用更多信息进行扩充。</span><span class="sxs-lookup"><span data-stu-id="87159-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="87159-108">每次运行此过程都可能需要数分钟到数小时时间。</span><span class="sxs-lookup"><span data-stu-id="87159-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="87159-109">实时功能将立即提供数据以供使用，直到后续计划刷新从数据源中提取此数据。</span><span class="sxs-lookup"><span data-stu-id="87159-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="87159-110">实时更新有到期时间，此时间之后，更新不再会覆盖数据源中的值。</span><span class="sxs-lookup"><span data-stu-id="87159-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="87159-111">配置文件更新将保留 4 小时</span><span class="sxs-lookup"><span data-stu-id="87159-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="87159-112">活动将保留 30 天</span><span class="sxs-lookup"><span data-stu-id="87159-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="87159-113">这些值是您可以更改的 API 调用参数。</span><span class="sxs-lookup"><span data-stu-id="87159-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="87159-114">它们旨在确保源数据一直充当您的真相来源。</span><span class="sxs-lookup"><span data-stu-id="87159-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="87159-115">如果您希望实时更新保留更长时间，需要将其添加到数据源，以便在下次计划刷新期间获取它们。</span><span class="sxs-lookup"><span data-stu-id="87159-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="87159-116">统一客户配置文件字段的实时更新</span><span class="sxs-lookup"><span data-stu-id="87159-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="87159-117">更新的配置文件将在几秒钟内显示在客户卡视图或任何其他可视化中。</span><span class="sxs-lookup"><span data-stu-id="87159-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="87159-118">因为实时操作在数据统一后进行，所以仅适用于统一客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="87159-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="87159-119">因此，实施配置文件更改不会更新度量、细分成员资格或扩充。</span><span class="sxs-lookup"><span data-stu-id="87159-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="87159-120">限制</span><span class="sxs-lookup"><span data-stu-id="87159-120">Limitations</span></span>

- <span data-ttu-id="87159-121">可以更新，但是不能创建或删除客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="87159-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="87159-122">目前不能将实时更新导出到外部系统，如 Power BI。</span><span class="sxs-lookup"><span data-stu-id="87159-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="87159-123">实时创建活动</span><span class="sxs-lookup"><span data-stu-id="87159-123">Real-time creation of activities</span></span>

<span data-ttu-id="87159-124">实时 API 允许您将源系统中的新活动（单个源记录）发布到统一客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="87159-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="87159-125">新活动将在数秒内在该统一客户配置文件的时间线中以统一活动的形式提供。</span><span class="sxs-lookup"><span data-stu-id="87159-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="87159-126">您可以在客户卡视图中查看该时间线或您配置的任何其他时间线集成。</span><span class="sxs-lookup"><span data-stu-id="87159-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="87159-127">活动不可变。</span><span class="sxs-lookup"><span data-stu-id="87159-127">Activities are immutable.</span></span> <span data-ttu-id="87159-128">一经创建就不会改变。</span><span class="sxs-lookup"><span data-stu-id="87159-128">They don't change once created.</span></span>
> - <span data-ttu-id="87159-129">现在，细分和度量不会根据新活动更新。</span><span class="sxs-lookup"><span data-stu-id="87159-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="87159-130">导出时不包含仅通过实时 API 添加的活动，所以不会在 PowerBI 中显示此类活动。</span><span class="sxs-lookup"><span data-stu-id="87159-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="87159-131">可通过两种方法连接到实时 API：</span><span class="sxs-lookup"><span data-stu-id="87159-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="87159-132">[间接](#connect-via-the-dynamics-365-customer-insights-connector)，即使用 [Dynamics 365 Customer Insights 连接器](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="87159-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="87159-133">[直接 ](#connect-directly-to-the-real-time-api)，即使用代码</span><span class="sxs-lookup"><span data-stu-id="87159-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="87159-134">这两种方法都需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="87159-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="87159-135">Customer Insights 环境</span><span class="sxs-lookup"><span data-stu-id="87159-135">A Customer Insights environment</span></span>
- <span data-ttu-id="87159-136">统一客户配置文件</span><span class="sxs-lookup"><span data-stu-id="87159-136">Unified customer profiles</span></span>
- <span data-ttu-id="87159-137">配置并运行的活动</span><span class="sxs-lookup"><span data-stu-id="87159-137">Activities configured and run</span></span>
- <span data-ttu-id="87159-138">用于对您的帐户进行身份验证的参与者或管理员权限</span><span class="sxs-lookup"><span data-stu-id="87159-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="87159-139">通过 Dynamics 365 Customer Insights 连接器连接</span><span class="sxs-lookup"><span data-stu-id="87159-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="87159-140">此实时 API 可以从专用 Power Platform 连接器（[Dynamics 365 Customer Insights 连接器](https://docs.microsoft.com/connectors/customerinsights/)）引入数据，无需编写和部署任何代码。</span><span class="sxs-lookup"><span data-stu-id="87159-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="87159-141">此连接器可以执行与 API 执行的相同实时操作。</span><span class="sxs-lookup"><span data-stu-id="87159-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="87159-142">需要高级连接器的有效许可证。</span><span class="sxs-lookup"><span data-stu-id="87159-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="87159-143">有关详细信息，请参阅 [Power Apps 和 Power Automate 许可常见问题解答](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq)。</span><span class="sxs-lookup"><span data-stu-id="87159-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="87159-144">Power Platform [Power Apps 和/或 Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="87159-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="87159-145">Azure [逻辑应用](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="87159-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="87159-146">有关创建流的详细信息，请参阅 [Power Automate 文档](https://docs.microsoft.com/power-automate/)。</span><span class="sxs-lookup"><span data-stu-id="87159-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="87159-147">直接连接到实时 API</span><span class="sxs-lookup"><span data-stu-id="87159-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="87159-148">您可以通过生成自己的管道并直接连接到实时 API 来使用实时功能。</span><span class="sxs-lookup"><span data-stu-id="87159-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="87159-149">可发布源系统格式或 UnifiedActivity 格式的活动。</span><span class="sxs-lookup"><span data-stu-id="87159-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="87159-150">请通过对 /api/instances/{instanceId}/manage/entities/UnifiedActivity 进行 API 调用来获取该格式。</span><span class="sxs-lookup"><span data-stu-id="87159-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="87159-151">可在 [Customer Insights API 参考](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)的 **EntityData** 部分中找到此 API 的详细信息（包括参数和响应）。</span><span class="sxs-lookup"><span data-stu-id="87159-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="87159-152">有关详细信息，请参阅[使用 Customer Insights API](apis.md)。</span><span class="sxs-lookup"><span data-stu-id="87159-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="87159-153">了解遥测时的实时使用情况</span><span class="sxs-lookup"><span data-stu-id="87159-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="87159-154">概要介绍实时 API 的请求量以及有关系统可能遇到的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="87159-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="87159-155">您可以[访问实时遥测数据](system.md#api-usage-tab)。</span><span class="sxs-lookup"><span data-stu-id="87159-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]