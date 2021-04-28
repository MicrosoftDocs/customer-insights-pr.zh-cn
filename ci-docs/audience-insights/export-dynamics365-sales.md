---
title: 将 Customer Insights 数据导出到 Dynamics 365 Sales
description: 了解如何配置连接和导出到 Dynamics 365 Sales。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759580"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="92022-103">在 Dynamics 365 Sales 中使用客户细分（预览版）</span><span class="sxs-lookup"><span data-stu-id="92022-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="92022-104">使用您的客户数据通过 Dynamics 365 Sales 创建市场营销列表、跟进工作流以及发出促销。</span><span class="sxs-lookup"><span data-stu-id="92022-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="92022-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="92022-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="92022-106">Dynamics 365 Sales 中必须先存在联系人记录，然后才能从 Customer Insights 中将客户细分导出到 Sales。</span><span class="sxs-lookup"><span data-stu-id="92022-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="92022-107">详细了解如何[在 Dynamics 365 Sales 中使用 Common Data Services](connect-power-query.md)引入联系人。</span><span class="sxs-lookup"><span data-stu-id="92022-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="92022-108">如果将客户细分从受众见解导出到 Sales，则将不会在 Sales 实例中创建新的联系人记录。</span><span class="sxs-lookup"><span data-stu-id="92022-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="92022-109">Sales 中的联系人记录必须引入到受众见解中，并用作数据源。</span><span class="sxs-lookup"><span data-stu-id="92022-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="92022-110">在导出客户细分之前，还需要将它们包含在统一客户实体中，以将客户 ID 映射到联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="92022-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="92022-111">设置与 Sales 的连接</span><span class="sxs-lookup"><span data-stu-id="92022-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="92022-112">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="92022-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="92022-113">选择 **添加连接** 并选择 **Dynamics 365 Sales** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="92022-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="92022-114">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="92022-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="92022-115">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="92022-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="92022-116">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="92022-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="92022-117">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="92022-117">Choose who can use this connection.</span></span> <span data-ttu-id="92022-118">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="92022-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="92022-119">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="92022-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="92022-120">在 **服务器地址** 字段中输入组织的 Sales URL。</span><span class="sxs-lookup"><span data-stu-id="92022-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="92022-121">在 **服务器管理员帐户** 部分中，选择 **登录**，然后选择 Dynamics 365 Sales 帐户。</span><span class="sxs-lookup"><span data-stu-id="92022-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="92022-122">将客户 ID 字段映射到 Dynamics 365 联系人 ID。</span><span class="sxs-lookup"><span data-stu-id="92022-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="92022-123">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="92022-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="92022-124">配置导出</span><span class="sxs-lookup"><span data-stu-id="92022-124">Configure an export</span></span>

<span data-ttu-id="92022-125">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="92022-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="92022-126">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="92022-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="92022-127">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="92022-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="92022-128">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="92022-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="92022-129">在 **导出连接** 字段中，从 Dynamics 365 Sales 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="92022-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="92022-130">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="92022-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="92022-131">选择一个或多个客户细分。</span><span class="sxs-lookup"><span data-stu-id="92022-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="92022-132">选择 **保存**</span><span class="sxs-lookup"><span data-stu-id="92022-132">Select **Save**</span></span>

<span data-ttu-id="92022-133">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="92022-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="92022-134">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="92022-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="92022-135">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="92022-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
