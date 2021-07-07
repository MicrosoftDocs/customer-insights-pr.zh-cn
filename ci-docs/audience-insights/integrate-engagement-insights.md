---
title: 将参与见解中的 Web 数据与访问群体见解集成
description: 将参与见解中有关客户的 Web 信息引入到访问群体见解中。
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305007"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="abb6b-103">将参与见解中的 Web 数据与访问群体见解集成</span><span class="sxs-lookup"><span data-stu-id="abb6b-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="abb6b-104">客户通常使用网站在线进行日常交易。</span><span class="sxs-lookup"><span data-stu-id="abb6b-104">Customers often do their day-to-day transactions online using web sites.</span></span> <span data-ttu-id="abb6b-105">Dynamics 365 Customer Insights 中的参与见解（预览）功能是用于将 Web 数据作为源集成的有用解决方案。</span><span class="sxs-lookup"><span data-stu-id="abb6b-105">The engagement insights (preview) capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="abb6b-106">除了查看交易、人口统计或行为数据，我们还可以在统一客户配置文件中查看 Web 上的活动。</span><span class="sxs-lookup"><span data-stu-id="abb6b-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="abb6b-107">我们可以使用这些配置文件获得访问群体激活的其他见解，例如客户细分、度量或预测。</span><span class="sxs-lookup"><span data-stu-id="abb6b-107">We can use these profiles to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="abb6b-108">本文介绍将客户的 Web 活动数据从参与见解引入到现有访问群体见解环境中的步骤。</span><span class="sxs-lookup"><span data-stu-id="abb6b-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="abb6b-109">此示例中，我们假定有一个包含统一客户配置文件的环境。</span><span class="sxs-lookup"><span data-stu-id="abb6b-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="abb6b-110">配置文件与来自调查、零售和票证系统的源统一。</span><span class="sxs-lookup"><span data-stu-id="abb6b-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="abb6b-111">它还显示客户的相关活动。</span><span class="sxs-lookup"><span data-stu-id="abb6b-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="abb6b-112">现在，我们想要了解客户是否访问了我们的 Web 属性并了解他们的活动。</span><span class="sxs-lookup"><span data-stu-id="abb6b-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="abb6b-113">例如，活动包括从电子邮件中收到的链接访问的网站或查看的产品页面。</span><span class="sxs-lookup"><span data-stu-id="abb6b-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abb6b-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="abb6b-114">Prerequisites</span></span>

<span data-ttu-id="abb6b-115">若要集成参与见解中的数据，需要满足几个先决条件：</span><span class="sxs-lookup"><span data-stu-id="abb6b-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="abb6b-116">将参与见解 SDK 与您的网站集成。</span><span class="sxs-lookup"><span data-stu-id="abb6b-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="abb6b-117">有关详细信息，请参阅[开发人员资源概述](../engagement-insights/developer-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="abb6b-117">For more information, see [Developer resources overview](../engagement-insights/developer-resources.md).</span></span>
- <span data-ttu-id="abb6b-118">从参与见解导出 Web 事件需要对 Azure Data Lake Storage 帐户的访问权限，该帐户用于将 Web 事件引入到访问群体见解。</span><span class="sxs-lookup"><span data-stu-id="abb6b-118">Exporting web events from engagement insights requires access to an Azure Data Lake Storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="abb6b-119">有关详细信息，请参阅[导出事件](../engagement-insights/export-events.md)。</span><span class="sxs-lookup"><span data-stu-id="abb6b-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="abb6b-120">在参与见解中配置优化的事件</span><span class="sxs-lookup"><span data-stu-id="abb6b-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="abb6b-121">在管理员使用参与见解 SDK 检测网站后，当用户查看网页或单击某个位置时，将收集 *基本事件*。</span><span class="sxs-lookup"><span data-stu-id="abb6b-121">After an administrator instruments a website with the engagement insights SDK, *base events* are gathered when a user views a webpage or clicks somewhere.</span></span> <span data-ttu-id="abb6b-122">基本事件往往包含大量详细信息。</span><span class="sxs-lookup"><span data-stu-id="abb6b-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="abb6b-123">根据您的用例，只需要基本事件的数据子集。</span><span class="sxs-lookup"><span data-stu-id="abb6b-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="abb6b-124">通过使用参与见解，可以创建仅包含所选基本事件属性的 *优化事件*。</span><span class="sxs-lookup"><span data-stu-id="abb6b-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="abb6b-125">有关详细信息，请参阅[创建和修改优化的事件](../engagement-insights/refined-events.md)。</span><span class="sxs-lookup"><span data-stu-id="abb6b-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="abb6b-126">创建优化的事件时应考虑的注意事项：</span><span class="sxs-lookup"><span data-stu-id="abb6b-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="abb6b-127">为优化的事件提供有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="abb6b-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="abb6b-128">它将用作访问群体见解中的活动名称。</span><span class="sxs-lookup"><span data-stu-id="abb6b-128">It will be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="abb6b-129">至少选择以下属性以在访问群体见解中创建活动：</span><span class="sxs-lookup"><span data-stu-id="abb6b-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="abb6b-130">Signal.Action.Name – 指示活动详细信息。</span><span class="sxs-lookup"><span data-stu-id="abb6b-130">Signal.Action.Name – indicates the activity details.</span></span>
    - <span data-ttu-id="abb6b-131">Signal.User.Id – 用于通过客户 ID 进行映射。</span><span class="sxs-lookup"><span data-stu-id="abb6b-131">Signal.User.Id – used to map with the customer ID.</span></span>
    - <span data-ttu-id="abb6b-132">Signal.View.Uri – 用作 web 地址，作为客户细分或度量的基础。</span><span class="sxs-lookup"><span data-stu-id="abb6b-132">Signal.View.Uri – used as a web address as a basis for segments or measures.</span></span>
    - <span data-ttu-id="abb6b-133">Signal.Export.Id – 用作事件的主键。</span><span class="sxs-lookup"><span data-stu-id="abb6b-133">Signal.Export.Id – used as a primary key for events.</span></span>
    - <span data-ttu-id="abb6b-134">Signal.Timestamp – 确定活动的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="abb6b-134">Signal.Timestamp – determines the date and time for the activity.</span></span>

<span data-ttu-id="abb6b-135">选择筛选器以重点关注对用例重要的事件和页面。</span><span class="sxs-lookup"><span data-stu-id="abb6b-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="abb6b-136">在此示例中，我们将使用“电子邮件促销”操作名称。</span><span class="sxs-lookup"><span data-stu-id="abb6b-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="abb6b-137">导出优化的 Web 事件</span><span class="sxs-lookup"><span data-stu-id="abb6b-137">Export the refined web events</span></span> 

<span data-ttu-id="abb6b-138">定义优化的事件后，您必须配置将事件数据导出到 Azure Data Lake Storage，它可用作数据源以供在访问群体见解中引入。</span><span class="sxs-lookup"><span data-stu-id="abb6b-138">After defining the refined event, you have to configure the export of the event data to Azure Data Lake Storage, which can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="abb6b-139">当事件从 Web 属性流出时会持续进行导出。</span><span class="sxs-lookup"><span data-stu-id="abb6b-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="abb6b-140">有关详细信息，请参阅[导出事件](../engagement-insights/export-events.md)。</span><span class="sxs-lookup"><span data-stu-id="abb6b-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="abb6b-141">将事件数据引入到访问群体见解中</span><span class="sxs-lookup"><span data-stu-id="abb6b-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="abb6b-142">现在，您已经定义了优化的事件并配置了它的导出，那么我们继续将数据引入到访问群体见解中。</span><span class="sxs-lookup"><span data-stu-id="abb6b-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="abb6b-143">您需要基于 Common Data Model 文件夹创建一个新的数据源。</span><span class="sxs-lookup"><span data-stu-id="abb6b-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="abb6b-144">输入将事件导出到的存储帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="abb6b-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="abb6b-145">在 *default.cdm.json* 文件中，选择要引入的优化事件并在访问群体见解中创建实体。</span><span class="sxs-lookup"><span data-stu-id="abb6b-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="abb6b-146">有关详细信息，请参阅[使用 Azure Data Lake 帐户连接到 Common Data Model 文件夹](connect-common-data-model.md)。</span><span class="sxs-lookup"><span data-stu-id="abb6b-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md).</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="abb6b-147">将优化的事件数据作为客户配置文件的活动进行关联</span><span class="sxs-lookup"><span data-stu-id="abb6b-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="abb6b-148">完成实体引入后，您可以为客户配置文件配置活动。</span><span class="sxs-lookup"><span data-stu-id="abb6b-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="abb6b-149">有关详细信息，请参阅[自定义活动](activities.md)。</span><span class="sxs-lookup"><span data-stu-id="abb6b-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="具有展开的编辑活动窗格并且填充了字段的活动页面。":::

<span data-ttu-id="abb6b-151">使用以下映射配置新活动：</span><span class="sxs-lookup"><span data-stu-id="abb6b-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="abb6b-152">**主键**：Signal.Export.Id，这是一个唯一的 ID，可用于参与见解中的每个事件记录。</span><span class="sxs-lookup"><span data-stu-id="abb6b-152">**Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="abb6b-153">此属性是自动生成的。</span><span class="sxs-lookup"><span data-stu-id="abb6b-153">This property is automatically generated.</span></span>

- <span data-ttu-id="abb6b-154">**时间戳**：事件属性中的 Signal.Timestamp。</span><span class="sxs-lookup"><span data-stu-id="abb6b-154">**Timestamp**: Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="abb6b-155">**事件**：Signal.Name，要跟踪的事件名称。</span><span class="sxs-lookup"><span data-stu-id="abb6b-155">**Event**: Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="abb6b-156">**Web 地址**：Signal.View.Uri，是指创建了事件的页面的 URI。</span><span class="sxs-lookup"><span data-stu-id="abb6b-156">**Web address**: Signal.View.Uri referring to the URI of the page that created the event.</span></span>

- <span data-ttu-id="abb6b-157">**详细信息**：Signal.Action.Name，用于表示要与事件关联的信息。</span><span class="sxs-lookup"><span data-stu-id="abb6b-157">**Details**: Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="abb6b-158">本案例中的选定属性指示该事件用于电子邮件促销。</span><span class="sxs-lookup"><span data-stu-id="abb6b-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="abb6b-159">**活动类型**：在本示例中，我们选择现有的活动类型 WebLog。</span><span class="sxs-lookup"><span data-stu-id="abb6b-159">**Activity type**: In this example, we choose the existing activity type WebLog.</span></span> <span data-ttu-id="abb6b-160">此选择是一个有用的筛选选项，用于根据此活动类型运行预测模型或创建客户细分。</span><span class="sxs-lookup"><span data-stu-id="abb6b-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="abb6b-161">**设置关系**：该重要的设置将活动与现有客户配置文件相关联。</span><span class="sxs-lookup"><span data-stu-id="abb6b-161">**Set up relationship**: This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="abb6b-162">**Signal.User.Id** 是在 SDK 中配置的要收集的标识符，它与访问群体见解中配置的其他数据源中的用户 ID 相关。</span><span class="sxs-lookup"><span data-stu-id="abb6b-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="abb6b-163">在本示例中，我们配置 Signal.User.Id 和 RetailCustomers:CustomerRetailId 之间的关系，这是在数据统一流程的映射步骤中标识的主键。</span><span class="sxs-lookup"><span data-stu-id="abb6b-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.</span></span>

<span data-ttu-id="abb6b-164">处理完活动后，您可以查看客户记录并打开客户卡，以在时间轴上查看参与见解中的活动。</span><span class="sxs-lookup"><span data-stu-id="abb6b-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="abb6b-165">若要查找具有参与见解活动的客户 ID，请转到 **实体** 并预览 UnifiedActivity 实体的数据。</span><span class="sxs-lookup"><span data-stu-id="abb6b-165">To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="abb6b-166">ActivityTypeDisplay = WebLog 包含在上述示例中配置的参与见解活动。</span><span class="sxs-lookup"><span data-stu-id="abb6b-166">ActivityTypeDisplay = WebLog contains the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="abb6b-167">将其中一条记录的客户 ID 和该 ID 的相应客户 ID 复制到 **客户** 页面上。</span><span class="sxs-lookup"><span data-stu-id="abb6b-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="abb6b-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="abb6b-168">Next steps</span></span>

<span data-ttu-id="abb6b-169">现在，您可以创建[客户细分](segments.md)、[度量](measures.md)和[预测](predictions.md)，以与客户建立有意义的联系。</span><span class="sxs-lookup"><span data-stu-id="abb6b-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
