---
title: Power BI 连接器
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 连接器。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405185"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="f5aea-103">适用于 Power BI 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="f5aea-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="f5aea-104">使用 Power BI Desktop 为您的数据创建可视化。</span><span class="sxs-lookup"><span data-stu-id="f5aea-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="f5aea-105">使用您的统一客户数据生成更多见解和构建报告。</span><span class="sxs-lookup"><span data-stu-id="f5aea-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5aea-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="f5aea-106">Prerequisites</span></span>

- <span data-ttu-id="f5aea-107">您具有统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="f5aea-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="f5aea-108">您的计算机上已安装最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)。</span><span class="sxs-lookup"><span data-stu-id="f5aea-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="f5aea-109">[了解有关 Power BI Desktop 的更多信息](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)。</span><span class="sxs-lookup"><span data-stu-id="f5aea-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="f5aea-110">配置适用于 Power BI 的连接器</span><span class="sxs-lookup"><span data-stu-id="f5aea-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="f5aea-111">在 Power BI Desktop 中，选择 **文件** > **获取数据**。</span><span class="sxs-lookup"><span data-stu-id="f5aea-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="f5aea-112">选择 **查看更多**，然后搜索 **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="f5aea-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="f5aea-113">选择结果，然后选择 **连接**。</span><span class="sxs-lookup"><span data-stu-id="f5aea-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="f5aea-114">使用用于 Customer Insights 的相同组织帐户 **登录**，然后选择 **连接**。</span><span class="sxs-lookup"><span data-stu-id="f5aea-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f5aea-115">您在此步骤中指定的帐户用于从 Customer Insights 获取数据，不需要与您登录 Power BI 所使用的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="f5aea-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="f5aea-116">若要重置用于数据提取的帐户，请打开 Power BI，然后转到 **文件** > **选项** > **设置** > **数据源设置**。</span><span class="sxs-lookup"><span data-stu-id="f5aea-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="f5aea-117">在数据源列表中，选择 **Dynamics 365 Customer Insights 登录**，然后选择 **清除权限**。</span><span class="sxs-lookup"><span data-stu-id="f5aea-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="f5aea-118">在 **导航器** 对话框中。</span><span class="sxs-lookup"><span data-stu-id="f5aea-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="f5aea-119">您将看到有权访问的所有环境的列表。</span><span class="sxs-lookup"><span data-stu-id="f5aea-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="f5aea-120">展开环境并打开任何文件夹（实体、度量、客户细分、扩充）。</span><span class="sxs-lookup"><span data-stu-id="f5aea-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="f5aea-121">例如，打开 **实体** 文件夹，查看可导入的所有实体。</span><span class="sxs-lookup"><span data-stu-id="f5aea-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="f5aea-122">![Power BI连接器导航器](media/power-bi-navigator.png "Power BI 连接器导航器")</span><span class="sxs-lookup"><span data-stu-id="f5aea-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="f5aea-123">选中要包含的实体旁边的复选框，然后 **加载**。</span><span class="sxs-lookup"><span data-stu-id="f5aea-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="f5aea-124">可以从多个环境选择多个实体。</span><span class="sxs-lookup"><span data-stu-id="f5aea-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="f5aea-125">加载实体时，您将看到“正在加载”对话框。</span><span class="sxs-lookup"><span data-stu-id="f5aea-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="f5aea-126">在已加载所有选择的实体后，您可以使用 Power BI 的功能可视化数据。</span><span class="sxs-lookup"><span data-stu-id="f5aea-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="f5aea-127">大型数据集</span><span class="sxs-lookup"><span data-stu-id="f5aea-127">Large data sets</span></span>

<span data-ttu-id="f5aea-128">Power BI 的 Customer Insights 连接器用于最多包含 100 万个客户配置文件的数据集。</span><span class="sxs-lookup"><span data-stu-id="f5aea-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="f5aea-129">导入更大的数据集可能会运行，但需要花费较长时间。</span><span class="sxs-lookup"><span data-stu-id="f5aea-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="f5aea-130">而且，此过程还可能由于 Power BI 限制而超时。</span><span class="sxs-lookup"><span data-stu-id="f5aea-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="f5aea-131">有关详细信息，请参阅 [Power BI：针对大型数据集的建议](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)。</span><span class="sxs-lookup"><span data-stu-id="f5aea-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="f5aea-132">使用数据的子集</span><span class="sxs-lookup"><span data-stu-id="f5aea-132">Work with a subset of data</span></span>

<span data-ttu-id="f5aea-133">考虑使用数据的子集。</span><span class="sxs-lookup"><span data-stu-id="f5aea-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="f5aea-134">例如，您可以创建[客户细分](segments.md)，而不是将所有客户记录导出到 Power BI。</span><span class="sxs-lookup"><span data-stu-id="f5aea-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
