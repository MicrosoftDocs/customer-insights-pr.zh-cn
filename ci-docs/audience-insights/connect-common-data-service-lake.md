---
title: 连接到 Common Data Service 托管湖中的实体
description: 从 Common Data Service 托管数据湖导入数据。
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596948"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="b23d7-103">连接到 Common Data Service 托管数据湖中的数据</span><span class="sxs-lookup"><span data-stu-id="b23d7-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b23d7-104">本文提供有关现有 Dynamics 365 客户如何快速连接他们到 Common Data Service 托管湖中的分析实体的信息。</span><span class="sxs-lookup"><span data-stu-id="b23d7-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="b23d7-105">您必须是 Common Data Service 组织的管理员才能继续和查看托管湖中提供的实体列表。</span><span class="sxs-lookup"><span data-stu-id="b23d7-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="b23d7-106">重要考虑因素</span><span class="sxs-lookup"><span data-stu-id="b23d7-106">Important considerations</span></span>

<span data-ttu-id="b23d7-107">可以将联机服务（如 Azure Data Lake Storage）中存储的数据存储到 Dynamics 365 Customer Insights 中处理或存储数据之外的位置。</span><span class="sxs-lookup"><span data-stu-id="b23d7-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="b23d7-108">导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="b23d7-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="b23d7-109">连接到 Common Data Service 托管湖</span><span class="sxs-lookup"><span data-stu-id="b23d7-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="b23d7-110">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b23d7-111">选择 **添加数据源**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="b23d7-112">选择 **连接到 Common Data Service**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="b23d7-113">输入数据源的 **名称**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="b23d7-114">命名准则：</span><span class="sxs-lookup"><span data-stu-id="b23d7-114">Name guidelines:</span></span> 
   - <span data-ttu-id="b23d7-115">以字母开头。</span><span class="sxs-lookup"><span data-stu-id="b23d7-115">Start with a letter.</span></span>
   - <span data-ttu-id="b23d7-116">只能使用字母和数字。</span><span class="sxs-lookup"><span data-stu-id="b23d7-116">Use letters and numbers only.</span></span> <span data-ttu-id="b23d7-117">不允许使用特殊字符和空格。</span><span class="sxs-lookup"><span data-stu-id="b23d7-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="b23d7-118">使用 3 至 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="b23d7-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="b23d7-119">提供您的 Common Data Service 组织的 **服务器地址**，然后选择 **登录**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b23d7-120">![用于输入 Common Data Service 服务器地址的对话框](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="b23d7-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="b23d7-121">选择您希望从可用列表中引入的实体。</span><span class="sxs-lookup"><span data-stu-id="b23d7-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="b23d7-122">如果已经选择了某些实体，其他 Dynamics 365 应用程序（例如 Dynamics 365 Sales Insights 或 Customer Service Insights）可能会使用它们。</span><span class="sxs-lookup"><span data-stu-id="b23d7-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="b23d7-123">您不能更改此选择。</span><span class="sxs-lookup"><span data-stu-id="b23d7-123">You can't change the selection.</span></span> <span data-ttu-id="b23d7-124">这些实体在创建数据源后即可供使用。</span><span class="sxs-lookup"><span data-stu-id="b23d7-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b23d7-125">![显示 Common Data Service 组织中的实体列表的对话框](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="b23d7-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="b23d7-126">保存您的选择以开始将所选实体同步到 Common Data Service 托管湖。</span><span class="sxs-lookup"><span data-stu-id="b23d7-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="b23d7-127">您将在 **数据源** 页上找到新添加的连接。</span><span class="sxs-lookup"><span data-stu-id="b23d7-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="b23d7-128">它将排队等待刷新，显示实体计数为 0，直到所有实体都同步为止。</span><span class="sxs-lookup"><span data-stu-id="b23d7-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="b23d7-129">仅环境中的一个数据源可以同时使用相同的 Common Data Service 托管湖。</span><span class="sxs-lookup"><span data-stu-id="b23d7-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="b23d7-130">编辑 Common Data Service 托管湖数据源</span><span class="sxs-lookup"><span data-stu-id="b23d7-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="b23d7-131">您仅在创建数据源之后才编辑对实体的选择。</span><span class="sxs-lookup"><span data-stu-id="b23d7-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="b23d7-132">例如，如果其他实体被添加到 Common Data Service 中，并且您也希望导入它们。</span><span class="sxs-lookup"><span data-stu-id="b23d7-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="b23d7-133">要连接到其他 Common Data Service，请[创建新数据源](#connect-to-a-common-data-service-managed-lake)。</span><span class="sxs-lookup"><span data-stu-id="b23d7-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="b23d7-134">在访问群体见解中，转到 **数据** > **数据源**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b23d7-135">选择要更新的数据源旁边的省略号。</span><span class="sxs-lookup"><span data-stu-id="b23d7-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="b23d7-136">从列表中选择 **编辑** 选项。</span><span class="sxs-lookup"><span data-stu-id="b23d7-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="b23d7-137">从可用实体列表中选择其他实体，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="b23d7-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]