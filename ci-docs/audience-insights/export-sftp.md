---
title: 将 Customer Insights 数据导出到 SFTP 主机
description: 了解如何配置与 SFTP 主机的连接。
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267987"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="75cbb-103">SFTP 连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="75cbb-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="75cbb-104">通过将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 主机，从而使用这些数据。</span><span class="sxs-lookup"><span data-stu-id="75cbb-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75cbb-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="75cbb-105">Prerequisites</span></span>

- <span data-ttu-id="75cbb-106">SFTP 主机的可用性和相应的凭据。</span><span class="sxs-lookup"><span data-stu-id="75cbb-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="75cbb-107">连接到 SFTP</span><span class="sxs-lookup"><span data-stu-id="75cbb-107">Connect to SFTP</span></span>

1. <span data-ttu-id="75cbb-108">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="75cbb-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="75cbb-109">在 **SFTP** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="75cbb-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="75cbb-110">在 **显示名称** 字段中为目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="75cbb-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="75cbb-111">提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。</span><span class="sxs-lookup"><span data-stu-id="75cbb-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="75cbb-112">选择 **验证** 测试连接。</span><span class="sxs-lookup"><span data-stu-id="75cbb-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="75cbb-113">成功验证后，选择是要导出 **已进行 gzip 压缩** 还是 **已解压缩** 的数据，然后为导出的文件选择 **字段分隔符**。</span><span class="sxs-lookup"><span data-stu-id="75cbb-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="75cbb-114">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="75cbb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="75cbb-115">选择 **下一步** 开始配置导出。</span><span class="sxs-lookup"><span data-stu-id="75cbb-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="75cbb-116">配置导出</span><span class="sxs-lookup"><span data-stu-id="75cbb-116">Configure the export</span></span>

1. <span data-ttu-id="75cbb-117">选择要导出的实体，如客户细分。</span><span class="sxs-lookup"><span data-stu-id="75cbb-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="75cbb-118">导出后，每个选定实体最多将有五个输出文件。</span><span class="sxs-lookup"><span data-stu-id="75cbb-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="75cbb-119">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="75cbb-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="75cbb-120">导出数据</span><span class="sxs-lookup"><span data-stu-id="75cbb-120">Export the data</span></span>

<span data-ttu-id="75cbb-121">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="75cbb-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="75cbb-122">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="75cbb-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="75cbb-123">已知限制</span><span class="sxs-lookup"><span data-stu-id="75cbb-123">Known limitations</span></span>

- <span data-ttu-id="75cbb-124">导出的运行时间取决于系统性能。</span><span class="sxs-lookup"><span data-stu-id="75cbb-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="75cbb-125">建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。</span><span class="sxs-lookup"><span data-stu-id="75cbb-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="75cbb-126">在使用建议的两个 CPU 内核和 1 GB 内存这种最低配置时，导出具有多达 1 亿个客户配置文件的实体可能需要 90 分钟。</span><span class="sxs-lookup"><span data-stu-id="75cbb-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="75cbb-127">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="75cbb-127">Data privacy and compliance</span></span>

<span data-ttu-id="75cbb-128">当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="75cbb-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="75cbb-129">Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="75cbb-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="75cbb-130">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="75cbb-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="75cbb-131">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="75cbb-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]