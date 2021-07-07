---
title: 将 Customer Insights 数据导出到 Salesforce Marketing Cloud
description: 了解如何配置连接和导出到 Salesforce Marketing Cloud。
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314582"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="6f151-103">将客户细分和其他数据导出到 Salesforce Marketing Cloud（预览）</span><span class="sxs-lookup"><span data-stu-id="6f151-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="6f151-104">通过安全文件传输协议 (SFTP) 位置导出客户数据以在 Salesforce Marketing Cloud 中使用它们。</span><span class="sxs-lookup"><span data-stu-id="6f151-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6f151-105">连接的先决条件</span><span class="sxs-lookup"><span data-stu-id="6f151-105">Prerequisites for connection</span></span>

- <span data-ttu-id="6f151-106">SFTP 主机和相应的管理员凭据的可用性。</span><span class="sxs-lookup"><span data-stu-id="6f151-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="6f151-107">如何为 Salesforce Marketing Cloud 设置 SFTP 位置</span><span class="sxs-lookup"><span data-stu-id="6f151-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="6f151-108">已知限制</span><span class="sxs-lookup"><span data-stu-id="6f151-108">Known limitations</span></span>

- <span data-ttu-id="6f151-109">导出的运行时间取决于系统性能。</span><span class="sxs-lookup"><span data-stu-id="6f151-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="6f151-110">建议将两个 CPU 内核和 1 GB 内存作为服务器的最低配置。</span><span class="sxs-lookup"><span data-stu-id="6f151-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="6f151-111">在使用建议的最低配置时，导出具有最多 1 亿个客户配置文件的实体可能需要 90 分钟。</span><span class="sxs-lookup"><span data-stu-id="6f151-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="6f151-112">设置与 Salesforce Marketing Cloud 的连接</span><span class="sxs-lookup"><span data-stu-id="6f151-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="6f151-113">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="6f151-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6f151-114">选择 **添加连接** 并选择 **Salesforce Marketing Cloud** 以配置连接。</span><span class="sxs-lookup"><span data-stu-id="6f151-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="6f151-115">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="6f151-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6f151-116">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="6f151-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6f151-117">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="6f151-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6f151-118">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="6f151-118">Choose who can use this connection.</span></span> <span data-ttu-id="6f151-119">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="6f151-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6f151-120">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="6f151-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6f151-121">提供 SFTP 帐户的 **用户名**、**密码**、**主机名** 和 **导出文件夹**。</span><span class="sxs-lookup"><span data-stu-id="6f151-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="6f151-122">选择 **验证** 测试连接。</span><span class="sxs-lookup"><span data-stu-id="6f151-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="6f151-123">选择 **我同意** 确认 **数据隐私与合规性**。</span><span class="sxs-lookup"><span data-stu-id="6f151-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6f151-124">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="6f151-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6f151-125">配置导出</span><span class="sxs-lookup"><span data-stu-id="6f151-125">Configure an export</span></span>

<span data-ttu-id="6f151-126">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="6f151-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6f151-127">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="6f151-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6f151-128">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="6f151-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6f151-129">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="6f151-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6f151-130">在 **导出连接** 字段中，从 SFTP 部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="6f151-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="6f151-131">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="6f151-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6f151-132">选择要为导出的文件导出 **已进行 gzip 压缩** 的数据还是 **已解压缩** 的数据，以及是否导出 **字段分隔符**。</span><span class="sxs-lookup"><span data-stu-id="6f151-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="6f151-133">选择要导出的实体，如客户细分。</span><span class="sxs-lookup"><span data-stu-id="6f151-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6f151-134">导出后，每个选定实体最多将拆分成五个输出文件。</span><span class="sxs-lookup"><span data-stu-id="6f151-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="6f151-135">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="6f151-135">Select **Save**.</span></span>

<span data-ttu-id="6f151-136">保存导出不会立即运行导出。</span><span class="sxs-lookup"><span data-stu-id="6f151-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6f151-137">每次进行[预定的刷新 ](system.md#schedule-tab)时，都会运行导出。</span><span class="sxs-lookup"><span data-stu-id="6f151-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6f151-138">您也可以[按需导出数据](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="6f151-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="6f151-139">将 Customer Insights 数据从 SFTP 位置导入到 Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="6f151-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="6f151-140">[在 Salesforce Marketing Cloud 中创建数据扩展](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)以从 SFTP 位置导入 Customer Insights 数据文件。</span><span class="sxs-lookup"><span data-stu-id="6f151-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="6f151-141">[将数据从 SFTP 位置导入](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)到 Salesforce Marketing Cloud 数据扩展。</span><span class="sxs-lookup"><span data-stu-id="6f151-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="6f151-142">设置自动化以将数据导入到数据扩展。</span><span class="sxs-lookup"><span data-stu-id="6f151-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="6f151-143">了解有关[文件拖放自动化和计划自动化](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f151-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="6f151-144">定义[文件拖放自动化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)或[计划自动化](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)。</span><span class="sxs-lookup"><span data-stu-id="6f151-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="6f151-145">下面是[使用 SFTP 的自动化](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)的示例。</span><span class="sxs-lookup"><span data-stu-id="6f151-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6f151-146">数据隐私与合规性</span><span class="sxs-lookup"><span data-stu-id="6f151-146">Data privacy and compliance</span></span>

<span data-ttu-id="6f151-147">当您启用 Dynamics 365 Customer Insights 以通过 SFTP 传输数据时，您允许在 Dynamics 365 Customer Insights 的合规性边界之外传输数据，包括诸如个人数据的潜在敏感数据。</span><span class="sxs-lookup"><span data-stu-id="6f151-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6f151-148">Microsoft 将在您的指导下传输此类数据，但您有责任确保导出目标满足您可能需遵守的任何隐私或安全义务。</span><span class="sxs-lookup"><span data-stu-id="6f151-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6f151-149">有关详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=396732)。</span><span class="sxs-lookup"><span data-stu-id="6f151-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6f151-150">您的 Dynamics 365 Customer Insights 管理员可以随时删除此导出目标来中止使用此功能。</span><span class="sxs-lookup"><span data-stu-id="6f151-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
