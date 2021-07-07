---
title: 连接到 Customer Insights 中的其他服务。
description: 与其他服务共享数据。
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304961"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="b9e05-103">连接（预览版）概述</span><span class="sxs-lookup"><span data-stu-id="b9e05-103">Connections (preview) overview</span></span>

<span data-ttu-id="b9e05-104">连接是实现与 Customer Insights 之间共享数据的关键。</span><span class="sxs-lookup"><span data-stu-id="b9e05-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="b9e05-105">每个连接均可实现与特定服务共享数据。</span><span class="sxs-lookup"><span data-stu-id="b9e05-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="b9e05-106">连接是[配置第三方扩充](enrichment-hub.md)和[配置导出](export-destinations.md)的基础。</span><span class="sxs-lookup"><span data-stu-id="b9e05-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="b9e05-107">同一连接可以多次使用。</span><span class="sxs-lookup"><span data-stu-id="b9e05-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="b9e05-108">例如，Dynamics 365 Marketing 的一个连接适用于多项导出，Leadspace 连接可用于多项扩充。</span><span class="sxs-lookup"><span data-stu-id="b9e05-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="b9e05-109">转到 **管理员** > **连接** 以创建和查看连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="b9e05-110">**连接** 选项卡显示所有可用连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="b9e05-111">列表显示每个连接的行。</span><span class="sxs-lookup"><span data-stu-id="b9e05-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="b9e05-112">获取快速概述、描述，并了解您可以如何使用 **发现** 选项卡上的每个扩展选项。</span><span class="sxs-lookup"><span data-stu-id="b9e05-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="b9e05-113">导出</span><span class="sxs-lookup"><span data-stu-id="b9e05-113">Exports</span></span>

<span data-ttu-id="b9e05-114">只有管理员才能配置新的连接，但他们可以授予参与者使用现有连接的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b9e05-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="b9e05-115">管理员控制数据的去向，参与者定义满足其需求的有效载荷和频率。</span><span class="sxs-lookup"><span data-stu-id="b9e05-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="b9e05-116">有关更多信息，请参阅[允许参与者使用连接进行导出](#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="b9e05-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="b9e05-117">扩充</span><span class="sxs-lookup"><span data-stu-id="b9e05-117">Enrichments</span></span>

<span data-ttu-id="b9e05-118">只有管理员才能配置新的连接，但创建的连接始终可供管理员和参与者使用。</span><span class="sxs-lookup"><span data-stu-id="b9e05-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="b9e05-119">管理员将管理凭据并同意数据传输。</span><span class="sxs-lookup"><span data-stu-id="b9e05-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="b9e05-120">然后，管理员和参与者都可以使用这些连接进行扩充。</span><span class="sxs-lookup"><span data-stu-id="b9e05-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="b9e05-121">添加新连接</span><span class="sxs-lookup"><span data-stu-id="b9e05-121">Add a new connection</span></span>

<span data-ttu-id="b9e05-122">要添加连接，您需要拥有[管理员权限](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e05-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="b9e05-123">如果您连接到其他 Microsoft 服务，我们假设这两项服务都在同一个组织中。</span><span class="sxs-lookup"><span data-stu-id="b9e05-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="b9e05-124">转到 **管理员** > **连接（预览版）**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="b9e05-125">转到 **连接** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9e05-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="b9e05-126">选择 **添加连接** 以创建新连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="b9e05-127">从下拉菜单中选择您要创建的连接类型。</span><span class="sxs-lookup"><span data-stu-id="b9e05-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="b9e05-128">在 **设置连接** 窗格中，提供所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9e05-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="b9e05-129">连接的 **显示名称** 和类型描述了连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="b9e05-130">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="b9e05-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="b9e05-131">确切的字段取决于您连接到的服务。</span><span class="sxs-lookup"><span data-stu-id="b9e05-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="b9e05-132">您可以了解文章中有关目标服务的特定连接类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9e05-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="b9e05-133">要创建连接，请选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="b9e05-134">也可以在 **发现** 选项卡中的磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="b9e05-135">允许参与者使用连接进行导出</span><span class="sxs-lookup"><span data-stu-id="b9e05-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="b9e05-136">在设置或编辑导出连接时，您可以选择允许哪些用户使用此特定连接来定义[导出](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e05-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="b9e05-137">默认情况下，具有管理员角色的用户可以使用连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="b9e05-138">您可以在 **选择可使用此连接的人员** 下面更改此设置，并允许具有参与者角色的用户使用此连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="b9e05-139">参与者将无法查看或编辑连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="b9e05-140">他们只会在创建导出时看到显示名称及其类型。</span><span class="sxs-lookup"><span data-stu-id="b9e05-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="b9e05-141">通过共享连接，您允许参与者使用连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="b9e05-142">参与者在设置导出时将看到共享连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="b9e05-143">他们可以管理使用此特定连接的每个导出。</span><span class="sxs-lookup"><span data-stu-id="b9e05-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="b9e05-144">您可以更改此设置，同时保留参与者已定义的导出。</span><span class="sxs-lookup"><span data-stu-id="b9e05-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="b9e05-145">编辑连接</span><span class="sxs-lookup"><span data-stu-id="b9e05-145">Edit a connection</span></span>

1. <span data-ttu-id="b9e05-146">转到 **管理员** > **连接（预览版）**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="b9e05-147">转到 **连接** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9e05-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="b9e05-148">选择要编辑的连接的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="b9e05-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="b9e05-149">选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-149">Select **Edit**.</span></span>

1. <span data-ttu-id="b9e05-150">更改要更新的值，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="b9e05-151">删除连接</span><span class="sxs-lookup"><span data-stu-id="b9e05-151">Remove a connection</span></span>

<span data-ttu-id="b9e05-152">如果扩充或导出使用了您要删除的连接，您首先需要拆卸或删除它们。</span><span class="sxs-lookup"><span data-stu-id="b9e05-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="b9e05-153">“删除”对话框将引导您完成相关的扩充或导出。</span><span class="sxs-lookup"><span data-stu-id="b9e05-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="b9e05-154">分离的扩充和导出会变得不可用。</span><span class="sxs-lookup"><span data-stu-id="b9e05-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="b9e05-155">通过在[扩充](enrichment-hub.md)或[导出](export-destinations.md)页面上添加另一个连接，您可以重新激活它们。</span><span class="sxs-lookup"><span data-stu-id="b9e05-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="b9e05-156">转到 **管理员** > **连接（预览版）**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="b9e05-157">转到 **连接** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9e05-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="b9e05-158">选择要删除的连接的竖省略号。</span><span class="sxs-lookup"><span data-stu-id="b9e05-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="b9e05-159">此下拉菜单中选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="b9e05-160">此时会出现确认对话框。</span><span class="sxs-lookup"><span data-stu-id="b9e05-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="b9e05-161">如果有使用此连接的扩充或导出，请选择此按钮以查看使用连接的内容。</span><span class="sxs-lookup"><span data-stu-id="b9e05-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="b9e05-162">**导出：** 您可以选择删除或断开导出，以便能够删除连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="b9e05-163">要断开导出，管理员可以使用 **断开** 操作。</span><span class="sxs-lookup"><span data-stu-id="b9e05-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="b9e05-164">此操作适用于个人和多个选定的导出。</span><span class="sxs-lookup"><span data-stu-id="b9e05-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="b9e05-165">通过断开连接，您可以保留导出配置，但它不会运行，直到将另一个连接添加到其中。</span><span class="sxs-lookup"><span data-stu-id="b9e05-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="b9e05-166">**扩充：** 您可以选择删除或停用导出，以便能够删除连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="b9e05-167">连接不再有依赖项后，请返回到 **管理** > **连接** 并尝试再次删除连接。</span><span class="sxs-lookup"><span data-stu-id="b9e05-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="b9e05-168">若要确认删除，请选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="b9e05-168">To confirm the deletion, select **Remove**.</span></span>

