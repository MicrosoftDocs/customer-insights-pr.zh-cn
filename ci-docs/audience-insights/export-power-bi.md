---
title: Power BI 连接器
description: 了解如何在 Power BI 中使用 Dynamics 365 Customer Insights 连接器。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477077"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="307fc-103">适用于 Power BI 的连接器（预览版）</span><span class="sxs-lookup"><span data-stu-id="307fc-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="307fc-104">使用 Power BI Desktop 为您的数据创建可视化。</span><span class="sxs-lookup"><span data-stu-id="307fc-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="307fc-105">使用您的统一客户数据生成更多见解和构建报告。</span><span class="sxs-lookup"><span data-stu-id="307fc-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="307fc-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="307fc-106">Prerequisites</span></span>

- <span data-ttu-id="307fc-107">您具有统一的客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="307fc-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="307fc-108">您的计算机上已安装最新版本的 [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)。</span><span class="sxs-lookup"><span data-stu-id="307fc-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="307fc-109">[了解有关 Power BI Desktop 的更多信息](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)。</span><span class="sxs-lookup"><span data-stu-id="307fc-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="307fc-110">配置适用于 Power BI 的连接器</span><span class="sxs-lookup"><span data-stu-id="307fc-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="307fc-111">在 Power BI Desktop 中，选择 **文件** > **获取数据**。</span><span class="sxs-lookup"><span data-stu-id="307fc-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="307fc-112">选择 **查看更多**，然后搜索 **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="307fc-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="307fc-113">选择 **连接**。</span><span class="sxs-lookup"><span data-stu-id="307fc-113">Select **Connect**.</span></span>

1. <span data-ttu-id="307fc-114">使用用于 Customer Insights 的相同组织帐户 **登录**，然后选择 **连接**。</span><span class="sxs-lookup"><span data-stu-id="307fc-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="307fc-115">您在此步骤中指定的帐户用于从 Customer Insights 获取数据，不需要与您登录 Power BI 所使用的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="307fc-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="307fc-116">若要重置用于数据提取的帐户，请打开 Power BI，然后转到 **文件** > **选项** > **设置** > **数据源设置**。</span><span class="sxs-lookup"><span data-stu-id="307fc-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="307fc-117">在数据源列表中，选择 **Dynamics 365 Customer Insights 登录**，然后选择 **清除权限**。</span><span class="sxs-lookup"><span data-stu-id="307fc-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="307fc-118">在 **导航器** 对话框中。</span><span class="sxs-lookup"><span data-stu-id="307fc-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="307fc-119">您将看到有权访问的所有环境的列表。</span><span class="sxs-lookup"><span data-stu-id="307fc-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="307fc-120">展开环境并打开任何文件夹（实体、度量、客户细分、扩充）。</span><span class="sxs-lookup"><span data-stu-id="307fc-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="307fc-121">例如，打开 **实体** 文件夹，查看可导入的所有实体。</span><span class="sxs-lookup"><span data-stu-id="307fc-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="307fc-122">![Power BI连接器导航器](media/power-bi-navigator.png "Power BI 连接器导航器")</span><span class="sxs-lookup"><span data-stu-id="307fc-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="307fc-123">选中要包含的实体旁边的复选框，然后 **加载**。</span><span class="sxs-lookup"><span data-stu-id="307fc-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="307fc-124">可以从多个环境选择多个实体。</span><span class="sxs-lookup"><span data-stu-id="307fc-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="307fc-125">加载实体时，您将看到“正在加载”对话框。</span><span class="sxs-lookup"><span data-stu-id="307fc-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="307fc-126">在已加载所有选择的实体后，您可以使用 Power BI 的功能可视化数据。</span><span class="sxs-lookup"><span data-stu-id="307fc-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="307fc-127">大型数据集</span><span class="sxs-lookup"><span data-stu-id="307fc-127">Large data sets</span></span>

<span data-ttu-id="307fc-128">Power BI 的 Customer Insights 连接器用于最多包含 100 万个客户配置文件的数据集。</span><span class="sxs-lookup"><span data-stu-id="307fc-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="307fc-129">导入更大的数据集可能会运行，但需要花费较长时间。</span><span class="sxs-lookup"><span data-stu-id="307fc-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="307fc-130">而且，此过程还可能由于 Power BI 限制而超时。</span><span class="sxs-lookup"><span data-stu-id="307fc-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="307fc-131">有关详细信息，请参阅 [Power BI：针对大型数据集的建议](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)。</span><span class="sxs-lookup"><span data-stu-id="307fc-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="307fc-132">使用数据的子集</span><span class="sxs-lookup"><span data-stu-id="307fc-132">Work with a subset of data</span></span>

<span data-ttu-id="307fc-133">考虑使用数据的子集。</span><span class="sxs-lookup"><span data-stu-id="307fc-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="307fc-134">例如，您可以创建[客户细分](segments.md)，而不是将所有客户记录导出到 Power BI。</span><span class="sxs-lookup"><span data-stu-id="307fc-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="307fc-135">疑难解答​​</span><span class="sxs-lookup"><span data-stu-id="307fc-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="307fc-136">Customer Insights 环境不会显示在 Power BI 中</span><span class="sxs-lookup"><span data-stu-id="307fc-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="307fc-137">在访问群体见解中的两个相同实体之间定义了多种[关系](relationships.md)的环境在 Power BI 连接器中不可用。</span><span class="sxs-lookup"><span data-stu-id="307fc-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="307fc-138">您可以标识和删除重复的关系。</span><span class="sxs-lookup"><span data-stu-id="307fc-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="307fc-139">在访问群体见解中，在 Power BI 中缺少的环境上转到 **数据** > **关系**。</span><span class="sxs-lookup"><span data-stu-id="307fc-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="307fc-140">识别重复关系：</span><span class="sxs-lookup"><span data-stu-id="307fc-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="307fc-141">检查是否在这两个实体之间定义了多种关系。</span><span class="sxs-lookup"><span data-stu-id="307fc-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="307fc-142">检查在统一过程中都包含的两个实体之间是否创建了关系。</span><span class="sxs-lookup"><span data-stu-id="307fc-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="307fc-143">在统一过程中包括的所有实体之间定义了隐式关系。</span><span class="sxs-lookup"><span data-stu-id="307fc-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="307fc-144">删除标识的任何重复关系。</span><span class="sxs-lookup"><span data-stu-id="307fc-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="307fc-145">在删除重复的关系后，尝试再次配置 Power BI 连接器。</span><span class="sxs-lookup"><span data-stu-id="307fc-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="307fc-146">该环境现在应该可用了。</span><span class="sxs-lookup"><span data-stu-id="307fc-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

