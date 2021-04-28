---
title: 将 Customer Insights 数据导出到 SFTP 主机
description: 了解如何配置连接和导出到 SFTP 位置。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760408"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="e69b7-103">将客户细分列表和其他数据导出到 SFTP（预览版）</span><span class="sxs-lookup"><span data-stu-id="e69b7-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="e69b7-104">将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 位置，以使用这些数据。</span><span class="sxs-lookup"><span data-stu-id="e69b7-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e69b7-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="e69b7-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e69b7-106">SFTP 主机的可用性和相应的凭据。</span><span class="sxs-lookup"><span data-stu-id="e69b7-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e69b7-107">已知限制</span><span class="sxs-lookup"><span data-stu-id="e69b7-107">Known limitations</span></span>

- <span data-ttu-id="e69b7-108">导出的运行时间取决于系统性能。</span><span class="sxs-lookup"><span data-stu-id="e69b7-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="e69b7-109">建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。</span><span class="sxs-lookup"><span data-stu-id="e69b7-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="e69b7-110">在使用建议的两个 CPU 内核和 1 GB 内存这种最低配置时，导出具有多达 1 亿个客户配置文件的实体可能需要 90 分钟。</span><span class="sxs-lookup"><span data-stu-id="e69b7-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="e69b7-111">设置与 SFTP 的连接</span><span class="sxs-lookup"><span data-stu-id="e69b7-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="e69b7-112">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e69b7-113">选择 **添加连接** 并选择 **SFTP** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="e69b7-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="e69b7-114">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="e69b7-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e69b7-115">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="e69b7-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e69b7-116">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="e69b7-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e69b7-117">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="e69b7-117">Choose who can use this connection.</span></span> <span data-ttu-id="e69b7-118">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="e69b7-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e69b7-119">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="e69b7-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e69b7-120">提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="e69b7-121">选择 **验证** 测试连接。</span><span class="sxs-lookup"><span data-stu-id="e69b7-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e69b7-122">选择要为导出的文件导出 **已进行 gzip 压缩** 的数据还是 **已解压缩** 的数据，以及是否导出 **字段分隔符**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e69b7-123">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e69b7-124">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="e69b7-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e69b7-125">配置导出</span><span class="sxs-lookup"><span data-stu-id="e69b7-125">Configure an export</span></span>

<span data-ttu-id="e69b7-126">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="e69b7-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e69b7-127">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="e69b7-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e69b7-128">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e69b7-129">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e69b7-130">在 **导出连接** 字段中，从 SFTP 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="e69b7-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="e69b7-131">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="e69b7-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e69b7-132">选择要导出的实体，如客户细分。</span><span class="sxs-lookup"><span data-stu-id="e69b7-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e69b7-133">导出后，每个选定实体最多将拆分成五个输出文件。</span><span class="sxs-lookup"><span data-stu-id="e69b7-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="e69b7-134">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="e69b7-134">Select **Save**.</span></span>

<span data-ttu-id="e69b7-135">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="e69b7-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e69b7-136">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="e69b7-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e69b7-137">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="e69b7-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e69b7-138">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="e69b7-138">Data privacy and compliance</span></span>

<span data-ttu-id="e69b7-139">当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="e69b7-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e69b7-140">Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="e69b7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e69b7-141">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="e69b7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e69b7-142">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="e69b7-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
