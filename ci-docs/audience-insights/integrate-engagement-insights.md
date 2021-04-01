---
title: 将参与见解中的 Web 数据与访问群体见解集成
description: 将参与见解中有关客户的 Web 信息引入到访问群体见解中。
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597454"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="af879-103">将参与见解中的 Web 数据与访问群体见解集成</span><span class="sxs-lookup"><span data-stu-id="af879-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="af879-104">客户通常使用网站在线进行日常交易。</span><span class="sxs-lookup"><span data-stu-id="af879-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="af879-105">Dynamics 365 Customer Insights 中的参与见解功能是一款方便的解决方案，用于将 Web 数据作为源进行集成。</span><span class="sxs-lookup"><span data-stu-id="af879-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="af879-106">除了查看交易、人口统计或行为数据，我们还可以在统一客户配置文件中查看 Web 上的活动。</span><span class="sxs-lookup"><span data-stu-id="af879-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="af879-107">我们可以使用该配置文件获得其他见解，如客户细分、度量或预测，以激活访问群体。</span><span class="sxs-lookup"><span data-stu-id="af879-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="af879-108">本文介绍将客户的 Web 活动数据从参与见解引入到现有访问群体见解环境中的步骤。</span><span class="sxs-lookup"><span data-stu-id="af879-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="af879-109">此示例中，我们假定有一个包含统一客户配置文件的环境。</span><span class="sxs-lookup"><span data-stu-id="af879-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="af879-110">配置文件与来自调查、零售和票证系统的源统一。</span><span class="sxs-lookup"><span data-stu-id="af879-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="af879-111">它还显示客户的相关活动。</span><span class="sxs-lookup"><span data-stu-id="af879-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="af879-112">现在，我们想要了解客户是否访问了我们的 Web 属性并了解他们的活动。</span><span class="sxs-lookup"><span data-stu-id="af879-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="af879-113">例如，活动包括从电子邮件中收到的链接访问的网站或查看的产品页面。</span><span class="sxs-lookup"><span data-stu-id="af879-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af879-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="af879-114">Prerequisites</span></span>

<span data-ttu-id="af879-115">若要集成参与见解中的数据，需要满足几个先决条件：</span><span class="sxs-lookup"><span data-stu-id="af879-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="af879-116">将参与见解 SDK 与您的网站集成。</span><span class="sxs-lookup"><span data-stu-id="af879-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="af879-117">有关详细信息，请参阅 [Web SDK 入门](../engagement-insights/instrument-website.md)。</span><span class="sxs-lookup"><span data-stu-id="af879-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="af879-118">从参与见解中导出 Web 事件需要访问 ADLS Gen 2 存储帐户，该帐户将用于将 Web 事件数据引入到访问群体见解中。</span><span class="sxs-lookup"><span data-stu-id="af879-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="af879-119">有关详细信息，请参阅[导出事件](../engagement-insights/export-events.md)。</span><span class="sxs-lookup"><span data-stu-id="af879-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="af879-120">在参与见解中配置优化的事件</span><span class="sxs-lookup"><span data-stu-id="af879-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="af879-121">在管理员使用参与见解 SDK 检测网站后，用户查看网页或单击某个位置时，系统会收集 *基本事件*。</span><span class="sxs-lookup"><span data-stu-id="af879-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="af879-122">基本事件往往包含大量详细信息。</span><span class="sxs-lookup"><span data-stu-id="af879-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="af879-123">根据您的用例，只需要基本事件的数据子集。</span><span class="sxs-lookup"><span data-stu-id="af879-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="af879-124">通过使用参与见解，可以创建仅包含所选基本事件属性的 *优化事件*。</span><span class="sxs-lookup"><span data-stu-id="af879-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="af879-125">有关详细信息，请参阅[创建和修改优化的事件](../engagement-insights/refined-events.md)。</span><span class="sxs-lookup"><span data-stu-id="af879-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="af879-126">创建优化的事件时应考虑的注意事项：</span><span class="sxs-lookup"><span data-stu-id="af879-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="af879-127">为优化的事件提供有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="af879-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="af879-128">它在访问群体见解中用作活动名称。</span><span class="sxs-lookup"><span data-stu-id="af879-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="af879-129">至少选择以下属性以在访问群体见解中创建活动：</span><span class="sxs-lookup"><span data-stu-id="af879-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="af879-130">Signal.Action.Name - 指示活动详细信息</span><span class="sxs-lookup"><span data-stu-id="af879-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="af879-131">Signal.User.Id - 用于通过客户 ID 进行映射</span><span class="sxs-lookup"><span data-stu-id="af879-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="af879-132">Signal.View.Uri - 用作网址，当做客户细分或度量的基础</span><span class="sxs-lookup"><span data-stu-id="af879-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="af879-133">Signal.Export.Id - 用作事件的主键</span><span class="sxs-lookup"><span data-stu-id="af879-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="af879-134">Signal.Timestamp - 用于确定活动的日期和时间</span><span class="sxs-lookup"><span data-stu-id="af879-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="af879-135">选择筛选器以重点关注对用例重要的事件和页面。</span><span class="sxs-lookup"><span data-stu-id="af879-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="af879-136">在此示例中，我们将使用“电子邮件促销”操作名称。</span><span class="sxs-lookup"><span data-stu-id="af879-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="af879-137">导出优化的 Web 事件</span><span class="sxs-lookup"><span data-stu-id="af879-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="af879-138">定义优化的事件后，您必须配置如何将事件数据导出到 Azure Data Lake Storage（可设置为要引入到访问群体见解中的数据源）。</span><span class="sxs-lookup"><span data-stu-id="af879-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="af879-139">当事件从 Web 属性流出时会持续进行导出。</span><span class="sxs-lookup"><span data-stu-id="af879-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="af879-140">有关详细信息，请参阅[导出事件](../engagement-insights/export-events.md)。</span><span class="sxs-lookup"><span data-stu-id="af879-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="af879-141">将事件数据引入到访问群体见解中</span><span class="sxs-lookup"><span data-stu-id="af879-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="af879-142">现在，您已经定义了优化的事件并配置了它的导出，那么我们继续将数据引入到访问群体见解中。</span><span class="sxs-lookup"><span data-stu-id="af879-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="af879-143">您需要基于 Common Data Model 文件夹创建一个新的数据源。</span><span class="sxs-lookup"><span data-stu-id="af879-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="af879-144">输入将事件导出到的存储帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af879-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="af879-145">在 *default.cdm.json* 文件中，选择要引入的优化事件并在访问群体见解中创建实体。</span><span class="sxs-lookup"><span data-stu-id="af879-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="af879-146">有关详细信息，请参阅[使用 Azure Data Lake 帐户连接到 Common Data Model 文件夹](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="af879-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="af879-147">将优化的事件数据作为客户配置文件的活动进行关联</span><span class="sxs-lookup"><span data-stu-id="af879-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="af879-148">完成实体引入后，您可以为客户配置文件配置活动。</span><span class="sxs-lookup"><span data-stu-id="af879-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="af879-149">有关详细信息，请参阅[自定义活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="af879-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="具有展开的编辑活动窗格并且填充了字段的活动页面。":::

<span data-ttu-id="af879-151">使用以下映射配置新活动：</span><span class="sxs-lookup"><span data-stu-id="af879-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="af879-152">**主键**：Signal.Export.Id，这是一个唯一的 ID，可用于参与见解中的每个事件记录。</span><span class="sxs-lookup"><span data-stu-id="af879-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="af879-153">此属性是自动生成的。</span><span class="sxs-lookup"><span data-stu-id="af879-153">This property is automatically generated.</span></span>

- <span data-ttu-id="af879-154">**时间戳：** 事件属性中的 Signal.Timestamp。</span><span class="sxs-lookup"><span data-stu-id="af879-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="af879-155">**事件：** Signal.Name，这是要跟踪的事件名称。</span><span class="sxs-lookup"><span data-stu-id="af879-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="af879-156">**Web 地址：** Signal.View.Uri，这是指创建事件所在的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="af879-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="af879-157">**详细信息：** Signal.Action.Name，用于表示要与事件关联的信息。</span><span class="sxs-lookup"><span data-stu-id="af879-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="af879-158">本案例中的选定属性指示该事件用于电子邮件促销。</span><span class="sxs-lookup"><span data-stu-id="af879-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="af879-159">**活动类型：** 在本示例中，我们选择现有活动类型 WebLog。</span><span class="sxs-lookup"><span data-stu-id="af879-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="af879-160">此选择是一个有用的筛选选项，用于根据此活动类型运行预测模型或创建客户细分。</span><span class="sxs-lookup"><span data-stu-id="af879-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="af879-161">**设置关系：** 该重要的设置将活动与现有客户配置文件相关联。</span><span class="sxs-lookup"><span data-stu-id="af879-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="af879-162">**Signal.User.Id** 是在 SDK 中配置的要收集的标识符，它与访问群体见解中配置的其他数据源中的用户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="af879-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="af879-163">在此示例中，我们将配置 Signal.User.Id 与 RetailCustomers:CustomerRetailId 之间的关系，这是在数据统一过程的映射步骤中定义的主键。</span><span class="sxs-lookup"><span data-stu-id="af879-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="af879-164">处理完活动后，您可以查看客户记录并打开客户卡，以在时间轴上查看参与见解中的活动。</span><span class="sxs-lookup"><span data-stu-id="af879-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="af879-165">要查找具有参与见解活动的客户 ID，请转到 **实体** 并预览 UnifiedActivity 实体的数据。</span><span class="sxs-lookup"><span data-stu-id="af879-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="af879-166">ActivityTypeDisplay = WebLog 包含上述示例中配置的参与见解活动。</span><span class="sxs-lookup"><span data-stu-id="af879-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="af879-167">将其中一条记录的客户 ID 和该 ID 的相应客户 ID 复制到 **客户** 页面上。</span><span class="sxs-lookup"><span data-stu-id="af879-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af879-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="af879-168">Next Steps</span></span>

<span data-ttu-id="af879-169">现在，您可以创建[客户细分](segments.md)、[度量](measures.md)和[预测](predictions.md)，以与客户建立有意义的联系。</span><span class="sxs-lookup"><span data-stu-id="af879-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]