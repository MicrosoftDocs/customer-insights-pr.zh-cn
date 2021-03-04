---
title: Common Data Model 中的 Customer Insights 实体架构
description: 使用 Common Data Model 中的实体。
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269273"
---
# <a name="entity-schemas-in-common-data-model"></a><span data-ttu-id="580b8-103">Common Data Model 中的实体架构</span><span class="sxs-lookup"><span data-stu-id="580b8-103">Entity schemas in Common Data Model</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="580b8-104">[Common Data Model](https://docs.microsoft.com/common-data-model/) 声明性规范，也是代表跨多种企业和生产力应用程序的常用概念和活动的标准实体的定义。</span><span class="sxs-lookup"><span data-stu-id="580b8-104">[Common Data Model](https://docs.microsoft.com/common-data-model/) is a declarative specification, and a definition of standard entities that represent commonly used concepts and activities across business and productivity applications.</span></span> <span data-ttu-id="580b8-105">此模型也将延伸到观察数据和分析数据。</span><span class="sxs-lookup"><span data-stu-id="580b8-105">This model is being extended to observational and analytical data as well.</span></span> <span data-ttu-id="580b8-106">Common Data Model 提供明确定义、模块化和可扩展的业务实体（例如帐户、业务部门、用例、联系人、潜在客户、机会和产品），还提供与供应商、员工和客户之间的交互（例如活动和服务级别协议）。</span><span class="sxs-lookup"><span data-stu-id="580b8-106">Common Data Model provides well-defined, modular, and extensible business entities—such as Account, Business Unit, Case, Contact, Lead, Opportunity, and Product—as well as interactions with vendors, workers, and customers—such as activities and service level agreements.</span></span> <span data-ttu-id="580b8-107">任何人都可以生成和扩展 Common Data Model 定义以捕获更多特定于业务的观点。</span><span class="sxs-lookup"><span data-stu-id="580b8-107">Anyone can build on and extend Common Data Model definitions to capture additional business-specific ideas.</span></span>

<span data-ttu-id="580b8-108">此共享数据模型可供应用程序和数据集成者通过提供统一的数据定义来进行协作。</span><span class="sxs-lookup"><span data-stu-id="580b8-108">This shared data model allows applications and data integrators to collaborate more easily by providing a unified definition of data.</span></span> <span data-ttu-id="580b8-109">Common Data Model 中包含丰富的元数据系统和标准实体、关系、层次结构、特征等。</span><span class="sxs-lookup"><span data-stu-id="580b8-109">Common Data Model includes a rich metadata system with standard entities, relationships, hierarchies, traits, and more.</span></span> <span data-ttu-id="580b8-110">其源自 Dynamics 365 应用，具有 260 多个标准实体，并在 GitHub 上开源。</span><span class="sxs-lookup"><span data-stu-id="580b8-110">It originated from Dynamics 365 apps and is open-sourced on GitHub with over 260 standard entities.</span></span> <span data-ttu-id="580b8-111">内部和外部合作伙伴构成的大型系统为 Common Data Model 贡献了业界专有的概念。</span><span class="sxs-lookup"><span data-stu-id="580b8-111">A large system of internal and external partners contributes industry-specific concepts to Common Data Model.</span></span>

<span data-ttu-id="580b8-112">现在多个系统和平台实施 Common Data Model，包括 Power BI 数据流和 Azure Data Services。</span><span class="sxs-lookup"><span data-stu-id="580b8-112">Multiple systems and platforms implement Common Data Model today, including Power BI dataflows and Azure Data Services.</span></span> <span data-ttu-id="580b8-113">其在 Common Data Service、Dynamics 365、Power Apps、Power BI 和即将推出的 Azure 数据服务中已受支持，并且正在直接为[开放数据方案](https://www.microsoft.com/open-data-initiative)贡献力量。</span><span class="sxs-lookup"><span data-stu-id="580b8-113">It's already supported in the Common Data Service, Dynamics 365, Power Apps, Power BI, and upcoming Azure data services, directly accruing value towards the [Open Data Initiative](https://www.microsoft.com/open-data-initiative).</span></span>

## <a name="customer-insights-entity-schemas"></a><span data-ttu-id="580b8-114">Customer Insights 实体架构</span><span class="sxs-lookup"><span data-stu-id="580b8-114">Customer Insights entity schemas</span></span>

<span data-ttu-id="580b8-115">为了建立 360 度的客户视图和在 Common Data Model 中提供 Customer Insights 模型以进行扩展，我们发布了以下实体架构：</span><span class="sxs-lookup"><span data-stu-id="580b8-115">To establish a 360-degree view of the customer and make Customer Insights models available in Common Data Model for extensibility, we've published the following entity schemas:</span></span>

| <span data-ttu-id="580b8-116">实体</span><span class="sxs-lookup"><span data-stu-id="580b8-116">Entity</span></span> | <span data-ttu-id="580b8-117">说明</span><span class="sxs-lookup"><span data-stu-id="580b8-117">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="580b8-118">CustomerActivity</span><span class="sxs-lookup"><span data-stu-id="580b8-118">CustomerActivity</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | <span data-ttu-id="580b8-119">用户执行且具有业务的观察价值的活动。</span><span class="sxs-lookup"><span data-stu-id="580b8-119">An activity performed by a user that has observational value to the business.</span></span> |
|[<span data-ttu-id="580b8-120">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="580b8-120">CustomerProfile</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | <span data-ttu-id="580b8-121">执行了业务活动或有潜力参与业务活动的人员或组织。</span><span class="sxs-lookup"><span data-stu-id="580b8-121">A person or organization that either performed, or has the potential to engage in, business activities.</span></span> |
|[<span data-ttu-id="580b8-122">MeasureDefinition</span><span class="sxs-lookup"><span data-stu-id="580b8-122">MeasureDefinition</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | <span data-ttu-id="580b8-123">无或多个维度划分的 KPI（如月度活跃用户、客户总开支、平均获客成本）的定义</span><span class="sxs-lookup"><span data-stu-id="580b8-123">Definition of KPIs partitioned by zero or more dimensions (such as Monthly Active Users, Total Spend By Customer, Average Customer Acquisition Cost)</span></span> |
|[<span data-ttu-id="580b8-124">细分</span><span class="sxs-lookup"><span data-stu-id="580b8-124">Segment</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | <span data-ttu-id="580b8-125">定义一组具有共同特征的成员。</span><span class="sxs-lookup"><span data-stu-id="580b8-125">Defines a group of members with common traits.</span></span> |
|[<span data-ttu-id="580b8-126">SegmentMembership</span><span class="sxs-lookup"><span data-stu-id="580b8-126">SegmentMembership</span></span>](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | <span data-ttu-id="580b8-127">参与给定细分的成员。</span><span class="sxs-lookup"><span data-stu-id="580b8-127">Members participating in a given segment.</span></span> |

<span data-ttu-id="580b8-128">有关详细信息，请参阅有关 [Common Data Model 中的 Customer Insights 实体架构](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)的文档。</span><span class="sxs-lookup"><span data-stu-id="580b8-128">For more information, see the documentation about the [Customer Insights entity schemas in Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).</span></span>

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a><span data-ttu-id="580b8-129">使用 Common Data Model 实体导航器查看实体</span><span class="sxs-lookup"><span data-stu-id="580b8-129">View entities using the Common Data Model Entity Navigator</span></span>

<span data-ttu-id="580b8-130">您可以在 [Common Data Model 实体导航器中](https://microsoft.github.io/CDM/)查看实体。</span><span class="sxs-lookup"><span data-stu-id="580b8-130">You can view entities in the [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/).</span></span> <span data-ttu-id="580b8-131">选择 **从 GitHub 加载!**</span><span class="sxs-lookup"><span data-stu-id="580b8-131">Select the **Load from GitHub!**</span></span> <span data-ttu-id="580b8-132">按钮，然后导航到 **foundationCommon** > **crmCommon** > **解决方案** > **customerInsights**，可在这里找到 Customer Insights 实体及其定义的列表。</span><span class="sxs-lookup"><span data-stu-id="580b8-132">button and navigate to **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** where you'll find the list of Customer Insights entities and their definitions.</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="580b8-133">![CDM 实体导航器，其中显示了 CustomerActivity 实体](media/CDM-entity-navigator.png "CDM 实体导航器，其中显示了 CustomerActivity 实体")</span><span class="sxs-lookup"><span data-stu-id="580b8-133">![CDM Entity Navigator showing CustomerActivity entity](media/CDM-entity-navigator.png "CDM Entity Navigator showing CustomerActivity entity")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]