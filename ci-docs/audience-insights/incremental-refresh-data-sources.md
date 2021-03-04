---
title: 基于 Power Query 的数据源的增量刷新
description: 刷新基于 Power Query 的大型数据源的新数据和更新数据。
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268537"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="48e03-103">基于 Power Query 的数据源的增量刷新</span><span class="sxs-lookup"><span data-stu-id="48e03-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="48e03-104">对数据源进行增量刷新具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="48e03-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="48e03-105">**刷新速度更快** - 仅刷新已更改的数据。</span><span class="sxs-lookup"><span data-stu-id="48e03-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="48e03-106">例如，可以仅刷新过去五天的历史数据集。</span><span class="sxs-lookup"><span data-stu-id="48e03-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="48e03-107">**提高可靠性** - 因为刷新量较小，所以无需长时间与不稳定源系统保持连接，从而可以降低连接问题风险。</span><span class="sxs-lookup"><span data-stu-id="48e03-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="48e03-108">**减少资源消耗** - 仅刷新所有数据中的一小部分，从而更有效地使用计算资源和降低对环境的破坏。</span><span class="sxs-lookup"><span data-stu-id="48e03-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="48e03-109">配置增量刷新</span><span class="sxs-lookup"><span data-stu-id="48e03-109">Configure incremental refresh</span></span>

<span data-ttu-id="48e03-110">访问群体见解允许对通过支持增量引入的 Power Query 导入的数据源进行增量刷新。</span><span class="sxs-lookup"><span data-stu-id="48e03-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="48e03-111">例如，具有日期和时间字段的 Azure SQL 数据库，这些字段指示数据记录的上次更新时间。</span><span class="sxs-lookup"><span data-stu-id="48e03-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="48e03-112">[创建新的基于 Power Query 的数据源](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="48e03-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="48e03-113">为该数据源提供名称。</span><span class="sxs-lookup"><span data-stu-id="48e03-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="48e03-114">选择支持增量刷新的数据源，如 Azure SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="48e03-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="48e03-115">选择要引入的实体或表。</span><span class="sxs-lookup"><span data-stu-id="48e03-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="48e03-116">完成传输步骤，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="48e03-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="48e03-117">在 **设置增量刷新** 对话框中，选择 **设置** 打开 **增量刷新设置**。</span><span class="sxs-lookup"><span data-stu-id="48e03-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="48e03-118">如果选择 **跳过**，数据源将刷新整个数据集。</span><span class="sxs-lookup"><span data-stu-id="48e03-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="48e03-119">也可以在以后通过编辑现有数据源来应用增量刷新。</span><span class="sxs-lookup"><span data-stu-id="48e03-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="48e03-120">在 **增量刷新设置** 中，为创建数据源时选择的所有实体配置增量刷新。</span><span class="sxs-lookup"><span data-stu-id="48e03-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48e03-121">![为数据源中的实体配置增量刷新](media/incremental-refresh-settings.png "为数据源中的实体配置增量刷新")</span><span class="sxs-lookup"><span data-stu-id="48e03-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="48e03-122">选择实体，然后提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="48e03-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="48e03-123">**定义主键**：选择实体或表的主键。</span><span class="sxs-lookup"><span data-stu-id="48e03-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="48e03-124">**定义“上次更新时间”字段**：此字段将仅显示类型为日期或时间的属性。</span><span class="sxs-lookup"><span data-stu-id="48e03-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="48e03-125">选择用于指示记录的上次更新时间的属性。</span><span class="sxs-lookup"><span data-stu-id="48e03-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="48e03-126">它将用于标识在增量刷新期限内的记录。</span><span class="sxs-lookup"><span data-stu-id="48e03-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="48e03-127">**更新检查频率**：指定所需的增量刷新时间范围长度。</span><span class="sxs-lookup"><span data-stu-id="48e03-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="48e03-128">选择 **保存** 完成数据源的创建。</span><span class="sxs-lookup"><span data-stu-id="48e03-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="48e03-129">数据的初始刷新为完全刷新。</span><span class="sxs-lookup"><span data-stu-id="48e03-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="48e03-130">之后，将按照上一步中的配置进行数据增量刷新。</span><span class="sxs-lookup"><span data-stu-id="48e03-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]