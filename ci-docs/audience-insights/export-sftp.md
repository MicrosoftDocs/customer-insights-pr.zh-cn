---
title: 将 Customer Insights 数据导出到 SFTP 主机
description: 了解如何配置与 SFTP 主机的连接。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643492"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="c9e37-103">SFTP 连接器（预览）</span><span class="sxs-lookup"><span data-stu-id="c9e37-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="c9e37-104">通过将第三方应用程序中的客户数据导出到安全文件传输协议 (SFTP) 主机，从而使用这些数据。</span><span class="sxs-lookup"><span data-stu-id="c9e37-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9e37-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="c9e37-105">Prerequisites</span></span>

- <span data-ttu-id="c9e37-106">SFTP 主机和相应凭据的可用性。</span><span class="sxs-lookup"><span data-stu-id="c9e37-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="c9e37-107">连接到 SFTP</span><span class="sxs-lookup"><span data-stu-id="c9e37-107">Connect to SFTP</span></span>

1. <span data-ttu-id="c9e37-108">转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c9e37-109">在 **SFTP** 下，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="c9e37-110">在 **显示名称** 字段中为目标指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="c9e37-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c9e37-111">提供 SFTP 帐户的 **用户名**、**密码** 和 **主机名**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="c9e37-112">示例：如果您的 SFTP 服务器的根文件夹为 /root/folder，并且您想要将数据导出到 /root/folder/ci_export_destination_folder，则该主机应该是 sftp://<server_address>/ci_export_destination_folder。</span><span class="sxs-lookup"><span data-stu-id="c9e37-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="c9e37-113">选择 **验证** 测试连接。</span><span class="sxs-lookup"><span data-stu-id="c9e37-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="c9e37-114">成功验证后，选择要导出 **压缩** 还是 **解压缩** 数据，然后为导出的文件选择 **字段分隔符**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="c9e37-115">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c9e37-116">选择 **下一步** 开始配置导出。</span><span class="sxs-lookup"><span data-stu-id="c9e37-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="c9e37-117">配置连接</span><span class="sxs-lookup"><span data-stu-id="c9e37-117">Configure the connection</span></span>

1. <span data-ttu-id="c9e37-118">选择要导出的 **客户属性**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="c9e37-119">您可以导出一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="c9e37-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="c9e37-120">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-120">Select **Next**.</span></span>

1. <span data-ttu-id="c9e37-121">选择想要导出的细分。</span><span class="sxs-lookup"><span data-stu-id="c9e37-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c9e37-122">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="c9e37-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c9e37-123">导出数据</span><span class="sxs-lookup"><span data-stu-id="c9e37-123">Export the data</span></span>

<span data-ttu-id="c9e37-124">可以[根据需要导出数据](export-destinations.md)。</span><span class="sxs-lookup"><span data-stu-id="c9e37-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c9e37-125">导出也会在每次[计划刷新](system.md#schedule-tab)时运行。</span><span class="sxs-lookup"><span data-stu-id="c9e37-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c9e37-126">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="c9e37-126">Data privacy and compliance</span></span>

<span data-ttu-id="c9e37-127">当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="c9e37-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c9e37-128">Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="c9e37-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c9e37-129">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="c9e37-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c9e37-130">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c9e37-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
