---
title: 实体和数据集
description: 在“实体”页面上查看数据。
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049383"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="ce58d-103">访问群体见解中的实体</span><span class="sxs-lookup"><span data-stu-id="ce58d-103">Entities in audience insights</span></span>

<span data-ttu-id="ce58d-104">[配置数据源](data-sources.md)之后，转到 **实体** 页以评估引入的数据的质量。</span><span class="sxs-lookup"><span data-stu-id="ce58d-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="ce58d-105">实体将会视为数据集。</span><span class="sxs-lookup"><span data-stu-id="ce58d-105">Entities are considered datasets.</span></span> <span data-ttu-id="ce58d-106">Dynamics 365 Customer Insights 的多个功能基于这些实体生成。</span><span class="sxs-lookup"><span data-stu-id="ce58d-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="ce58d-107">近距离查看它们有助您验证这些功能的输出。</span><span class="sxs-lookup"><span data-stu-id="ce58d-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="ce58d-108">**实体** 页列出实体，并且有多列：</span><span class="sxs-lookup"><span data-stu-id="ce58d-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="ce58d-109">**名称**：数据实体的名称。</span><span class="sxs-lookup"><span data-stu-id="ce58d-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="ce58d-110">如果看到实体名称旁边有警告符号，说明未成功加载该实体的数据。</span><span class="sxs-lookup"><span data-stu-id="ce58d-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="ce58d-111">**源**：引入的实体的数据源类型</span><span class="sxs-lookup"><span data-stu-id="ce58d-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="ce58d-112">**创建者**：创建实体的用户的名称</span><span class="sxs-lookup"><span data-stu-id="ce58d-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="ce58d-113">**创建时间**：实体的创建日期和时间</span><span class="sxs-lookup"><span data-stu-id="ce58d-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="ce58d-114">**更新者**：更新实体的用户的名称</span><span class="sxs-lookup"><span data-stu-id="ce58d-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="ce58d-115">**上次更新时间**：实体的上次更新日期和时间</span><span class="sxs-lookup"><span data-stu-id="ce58d-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="ce58d-116">**上次刷新时间**：上次刷新数据的日期和时间</span><span class="sxs-lookup"><span data-stu-id="ce58d-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="ce58d-117">浏览特定实体的数据</span><span class="sxs-lookup"><span data-stu-id="ce58d-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="ce58d-118">选择实体以浏览该实体中包含的不同字段和记录。</span><span class="sxs-lookup"><span data-stu-id="ce58d-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce58d-119">![选择实体](media/data-manager-entities-data.png "选择实体")</span><span class="sxs-lookup"><span data-stu-id="ce58d-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="ce58d-120">**数据** 选项卡显示一个表，其中列出了有关实体各个记录的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ce58d-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce58d-121">![字段表](media/data-manager-entities-fields.PNG "字段表")</span><span class="sxs-lookup"><span data-stu-id="ce58d-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="ce58d-122">默认情况下，**属性** 选项卡已被选定，并且会显示一个表，用于查看选定实体的详细信息，例如字段名称、数据类型和类型。</span><span class="sxs-lookup"><span data-stu-id="ce58d-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="ce58d-123">**类型** 列显示 Common Data Model 关联的类型，其由系统自动确定，或由用户[手动映射](map-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="ce58d-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="ce58d-124">这些是可能与属性的数据类型不同的语义类型 — 例如，下面的 *电子邮件* 字段的数据类型为 *文本*，但是，其（语义）的 Common Data Model 类型可能未 *电子邮件* 或 *电子邮件地址*。</span><span class="sxs-lookup"><span data-stu-id="ce58d-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="ce58d-125">这两个表都仅显示您的实体的数据的一个示例。</span><span class="sxs-lookup"><span data-stu-id="ce58d-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="ce58d-126">若要查看完整数据集，请转到 **数据源** 页，选择一个实体，选择 **编辑**，然后按照[数据源](data-sources.md)中的说明使用 Power Query 查看此实体的数据。</span><span class="sxs-lookup"><span data-stu-id="ce58d-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="ce58d-127">若要详细了解实体中引入的数据，可通过 **摘要** 列查看数据的某些重要特征，如空、缺少值、唯一值、计数和分发（如果适用于您的数据）。</span><span class="sxs-lookup"><span data-stu-id="ce58d-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="ce58d-128">选择图表图标查看数据的摘要。</span><span class="sxs-lookup"><span data-stu-id="ce58d-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce58d-129">![摘要符号](media/data-manager-entities-summary.png "数据摘要表")</span><span class="sxs-lookup"><span data-stu-id="ce58d-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="ce58d-130">下一步</span><span class="sxs-lookup"><span data-stu-id="ce58d-130">Next step</span></span>

<span data-ttu-id="ce58d-131">请参阅 [统一](data-unification.md)状态了解如何 *映射*、*匹配* 和 *合并* 引入的数据。</span><span class="sxs-lookup"><span data-stu-id="ce58d-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
