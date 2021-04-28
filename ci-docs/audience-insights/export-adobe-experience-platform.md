---
title: 将 Customer Insights 数据导出到 Adobe 体验平台
description: 了解如何在 Adobe 体验平台中使用访问群体见解客户细分。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760090"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="20f1d-103">在 Adobe 体验平台（预览版）中使用 Customer Insights 客户细分。</span><span class="sxs-lookup"><span data-stu-id="20f1d-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="20f1d-104">作为 Dynamics 365 Customer Insights 访问群体见解的用户，您可能创建了多个客户细分，以通过确定目标访问群体来提高市场营销活动效率。</span><span class="sxs-lookup"><span data-stu-id="20f1d-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="20f1d-105">要使用 Adobe 体验平台和应用程序（如 Adobe Campaign Standard）内访问群体见解中的客户细分，您需要执行本文中概述的几个步骤。</span><span class="sxs-lookup"><span data-stu-id="20f1d-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="本文中概述的步骤的流程图。":::

## <a name="prerequisites"></a><span data-ttu-id="20f1d-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="20f1d-107">Prerequisites</span></span>

-   <span data-ttu-id="20f1d-108">Dynamics 365 Customer Insights 许可证</span><span class="sxs-lookup"><span data-stu-id="20f1d-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="20f1d-109">Adobe 体验平台许可证</span><span class="sxs-lookup"><span data-stu-id="20f1d-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="20f1d-110">Adobe Campaign Standard 许可证</span><span class="sxs-lookup"><span data-stu-id="20f1d-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="20f1d-111">Azure Blob 存储帐户</span><span class="sxs-lookup"><span data-stu-id="20f1d-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="20f1d-112">市场活动概述</span><span class="sxs-lookup"><span data-stu-id="20f1d-112">Campaign Overview</span></span>

<span data-ttu-id="20f1d-113">为了更好地了解如何使用 Adobe 体验平台内访问群体见解中的客户细分，我们来看看虚构的示例活动。</span><span class="sxs-lookup"><span data-stu-id="20f1d-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="20f1d-114">假设贵公司每月为美国客户提供基于订阅的服务。</span><span class="sxs-lookup"><span data-stu-id="20f1d-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="20f1d-115">您希望确定其订阅应在未来八天内续订但尚未续订的客户。</span><span class="sxs-lookup"><span data-stu-id="20f1d-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="20f1d-116">为了留住这些客户，您希望使用 Adobe 体验平台通过电子邮件向他们发送促销优惠。</span><span class="sxs-lookup"><span data-stu-id="20f1d-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="20f1d-117">在此示例中，我们希望运行一次促销电子邮件活动。</span><span class="sxs-lookup"><span data-stu-id="20f1d-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="20f1d-118">本文不涵盖多次运行活动的用例。</span><span class="sxs-lookup"><span data-stu-id="20f1d-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="20f1d-119">确定目标访问群体</span><span class="sxs-lookup"><span data-stu-id="20f1d-119">Identify your target audience</span></span>

<span data-ttu-id="20f1d-120">在我们的情景中，我们假设客户的电子邮件地址在访问群体见解中可用，并分析了他们的促销偏好，以确定该客户细分的成员。</span><span class="sxs-lookup"><span data-stu-id="20f1d-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="20f1d-121">[您在访问群体见解中定义的客户细分](segments.md)称为 **ChurnProneCustomers**，您计划向这些客户发送电子邮件促销。</span><span class="sxs-lookup"><span data-stu-id="20f1d-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="一个其中创建了 ChurnProneCustomers 客户细分的客户细分页的屏幕截图。":::

<span data-ttu-id="20f1d-123">您要发出的优惠电子邮件将包含客户的名、姓和订阅结束日期。</span><span class="sxs-lookup"><span data-stu-id="20f1d-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="20f1d-124">它告知客户，如果他们在订阅结束前续订其订阅，他们将获得折扣。</span><span class="sxs-lookup"><span data-stu-id="20f1d-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="20f1d-125">导出目标访问群体</span><span class="sxs-lookup"><span data-stu-id="20f1d-125">Export your target audience</span></span>

<span data-ttu-id="20f1d-126">通过确定目标访问群体，我们可以配置从访问群体见解导出到 Azure Blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="20f1d-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="20f1d-127">配置连接</span><span class="sxs-lookup"><span data-stu-id="20f1d-127">Configure a connection</span></span>

1. <span data-ttu-id="20f1d-128">转到 **管理员** > **连接**。</span><span class="sxs-lookup"><span data-stu-id="20f1d-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="20f1d-129">选择 **添加连接**，并在 **Azure Blob 存储** 磁贴中选择 **Azure Blob 存储** 或选择 **设置**：</span><span class="sxs-lookup"><span data-stu-id="20f1d-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob 存储的配置磁贴。"::: <span data-ttu-id="20f1d-131">以配置连接。</span><span class="sxs-lookup"><span data-stu-id="20f1d-131">to configure the connection.</span></span>

1. <span data-ttu-id="20f1d-132">在 **显示名称** 字段中为连接指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="20f1d-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="20f1d-133">连接的名称和类型描述了此连接。</span><span class="sxs-lookup"><span data-stu-id="20f1d-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="20f1d-134">我们建议选择一个名称来解释此连接的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="20f1d-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="20f1d-135">选择可使用此连接的人员。</span><span class="sxs-lookup"><span data-stu-id="20f1d-135">Choose who can use this connection.</span></span> <span data-ttu-id="20f1d-136">如果不采取任何行动，默认值将是管理员。</span><span class="sxs-lookup"><span data-stu-id="20f1d-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="20f1d-137">有关更多信息，请参阅[允许参与者使用连接进行导出](connections.md#allow-contributors-to-use-a-connection-for-exports)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="20f1d-138">输入要将客户细分导出到的 Azure Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="20f1d-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。"::: 
   
    - <span data-ttu-id="20f1d-140">若要了解如何查找 Blob 存储帐户名称和帐户密钥，请参阅[在 Azure 门户中管理存储帐户设置](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="20f1d-141">若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="20f1d-142">选择 **保存** 以完成连接。</span><span class="sxs-lookup"><span data-stu-id="20f1d-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="20f1d-143">配置导出</span><span class="sxs-lookup"><span data-stu-id="20f1d-143">Configure an export</span></span>

<span data-ttu-id="20f1d-144">如果您有权访问此类类型的连接，则可以配置此导出。</span><span class="sxs-lookup"><span data-stu-id="20f1d-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="20f1d-145">有关更多信息，请参阅[配置导出所需的权限](export-destinations.md#set-up-a-new-export)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="20f1d-146">转到 **数据** > **导出**。</span><span class="sxs-lookup"><span data-stu-id="20f1d-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20f1d-147">要创建新导出，请选择 **添加导出**。</span><span class="sxs-lookup"><span data-stu-id="20f1d-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="20f1d-148">在 **导出连接** 字段中，从 Azure Blob 存储部分选择连接。</span><span class="sxs-lookup"><span data-stu-id="20f1d-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="20f1d-149">如果您没有看到此部分名称，则您无法使用此类型的连接。</span><span class="sxs-lookup"><span data-stu-id="20f1d-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="20f1d-150">选择您要导出的客户细分。</span><span class="sxs-lookup"><span data-stu-id="20f1d-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="20f1d-151">在这个例子中，它是 **ChurnProneCustomers**。</span><span class="sxs-lookup"><span data-stu-id="20f1d-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. <span data-ttu-id="20f1d-153">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="20f1d-153">Select **Save**.</span></span>

<span data-ttu-id="20f1d-154">保存导出目标后，您可以在 **数据** > **导出** 上找到该导出目标。</span><span class="sxs-lookup"><span data-stu-id="20f1d-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="20f1d-155">现在，您可以[按需导出客户细分](export-destinations.md#run-exports-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="20f1d-156">导出也会在每次[计划刷新](system.md)时运行。</span><span class="sxs-lookup"><span data-stu-id="20f1d-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20f1d-157">确保导出的客户细分的记录数量在 Adobe Campaign Standard 许可证的允许限度内。</span><span class="sxs-lookup"><span data-stu-id="20f1d-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="20f1d-158">导出的数据存储在上面配置的 Azure Blob 存储容器中。</span><span class="sxs-lookup"><span data-stu-id="20f1d-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="20f1d-159">系统在您的容器中自动创建了以下文件夹路径：</span><span class="sxs-lookup"><span data-stu-id="20f1d-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="20f1d-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="20f1d-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="20f1d-161">示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="20f1d-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="20f1d-162">导出实体的 *model.json* 位于 *%ExportDestinationName%* 级别。</span><span class="sxs-lookup"><span data-stu-id="20f1d-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="20f1d-163">示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="20f1d-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="20f1d-164">在 Adobe 体验平台中定义体验数据模型 (XDM) </span><span class="sxs-lookup"><span data-stu-id="20f1d-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="20f1d-165">在 Adobe 体验平台中使用访问群体见解中的导出数据之前，您需要定义“体验数据模型”架构并[配置实时客户配置文件的数据](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="20f1d-166">了解 [XDM 是什么](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，并了解[架构组合的基础知识](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="20f1d-167">将数据导入 Adobe 体验平台</span><span class="sxs-lookup"><span data-stu-id="20f1d-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="20f1d-168">现在一切都准备好了，我们需要将访问群体见解中准备好的访问群体数据导入到 Adobe 体验平台。</span><span class="sxs-lookup"><span data-stu-id="20f1d-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="20f1d-169">首先，[创建 Azure Blob 存储源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="20f1d-170">定义源连接后，为云存储批处理连接[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)，以将访问群体见解中的客户细分输出导入到 Adobe 体验平台中。</span><span class="sxs-lookup"><span data-stu-id="20f1d-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="20f1d-171">在 Adobe Campaign Standard 中创建访问群体</span><span class="sxs-lookup"><span data-stu-id="20f1d-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="20f1d-172">为了发送此市场活动的电子邮件，我们将使用 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="20f1d-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="20f1d-173">将数据导入到 Adobe 体验平台后，我们需要使用 Adobe 体验平台中的数据在 Adobe Campaign Standard 中[创建一个访问群体](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。</span><span class="sxs-lookup"><span data-stu-id="20f1d-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="20f1d-174">了解如何在 Adobe Campaign Standard 中[使用客户细分生成器](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment)，以基于 Adobe 体验平台中的数据定义访问群体。</span><span class="sxs-lookup"><span data-stu-id="20f1d-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="20f1d-175">使用 Adobe Campaign Standard 创建和发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="20f1d-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="20f1d-176">创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。</span><span class="sxs-lookup"><span data-stu-id="20f1d-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中的包含续订优惠的样本电子邮件。":::
