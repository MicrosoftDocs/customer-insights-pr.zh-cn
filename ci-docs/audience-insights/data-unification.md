---
title: 数据统一
description: 了解如何统一引入的数据。
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405188"
---
# <a name="data-unification"></a><span data-ttu-id="d3b59-103">数据统一</span><span class="sxs-lookup"><span data-stu-id="d3b59-103">Data unification</span></span>

<span data-ttu-id="d3b59-104">在[设置数据源](data-sources.md)后，您可以统一数据。</span><span class="sxs-lookup"><span data-stu-id="d3b59-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="d3b59-105">数据的使用包括三个步骤：**映射**、**匹配** 和 **合并**。</span><span class="sxs-lookup"><span data-stu-id="d3b59-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="d3b59-106">数据统一过程将迥异的数据源统一为一个主数据集来提供统一的客户视图。</span><span class="sxs-lookup"><span data-stu-id="d3b59-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="d3b59-107">统一阶段必须执行，并按照以下顺序执行：</span><span class="sxs-lookup"><span data-stu-id="d3b59-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="d3b59-108">映射</span><span class="sxs-lookup"><span data-stu-id="d3b59-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="d3b59-109">匹配</span><span class="sxs-lookup"><span data-stu-id="d3b59-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="d3b59-110">合并</span><span class="sxs-lookup"><span data-stu-id="d3b59-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="d3b59-111">完成数据统一后，您可以选择</span><span class="sxs-lookup"><span data-stu-id="d3b59-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="d3b59-112">[设置实体之间的关系](relationships.md)以创建精细的细分</span><span class="sxs-lookup"><span data-stu-id="d3b59-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="d3b59-113">[扩充数据](enrichment-hub.md)以深入了解客户</span><span class="sxs-lookup"><span data-stu-id="d3b59-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="d3b59-114">从某些引入的属性[定义活动](activities.md)</span><span class="sxs-lookup"><span data-stu-id="d3b59-114">[define activities](activities.md) from some of the ingested attributes</span></span>
