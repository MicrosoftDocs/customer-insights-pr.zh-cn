---
title: 将 Customer Insights 数据导出到 Adobe 体验平台
description: 了解如何在 Adobe 体验平台中使用访问群体见解客户细分。
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596258"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="c0c71-103">在 Adobe 体验平台（预览版）中使用 Customer Insights 客户细分。</span><span class="sxs-lookup"><span data-stu-id="c0c71-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="c0c71-104">作为 Dynamics 365 Customer Insights 访问群体见解的用户，您可能创建了多个客户细分，以通过确定目标访问群体来提高市场营销活动效率。</span><span class="sxs-lookup"><span data-stu-id="c0c71-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c0c71-105">要使用 Adobe 体验平台和应用程序（如 Adobe Campaign Standard）内访问群体见解中的客户细分，您需要执行本文中概述的几个步骤。</span><span class="sxs-lookup"><span data-stu-id="c0c71-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="本文中概述的步骤的流程图。":::

## <a name="prerequisites"></a><span data-ttu-id="c0c71-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="c0c71-107">Prerequisites</span></span>

-   <span data-ttu-id="c0c71-108">Dynamics 365 Customer Insights 许可证</span><span class="sxs-lookup"><span data-stu-id="c0c71-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c0c71-109">Adobe 体验平台许可证</span><span class="sxs-lookup"><span data-stu-id="c0c71-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="c0c71-110">Adobe Campaign Standard 许可证</span><span class="sxs-lookup"><span data-stu-id="c0c71-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c0c71-111">Azure Blob 存储帐户</span><span class="sxs-lookup"><span data-stu-id="c0c71-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c0c71-112">市场活动概述</span><span class="sxs-lookup"><span data-stu-id="c0c71-112">Campaign Overview</span></span>

<span data-ttu-id="c0c71-113">为了更好地了解如何使用 Adobe 体验平台内访问群体见解中的客户细分，我们来看看虚构的示例活动。</span><span class="sxs-lookup"><span data-stu-id="c0c71-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c0c71-114">假设贵公司每月为美国客户提供基于订阅的服务。</span><span class="sxs-lookup"><span data-stu-id="c0c71-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c0c71-115">您希望确定其订阅应在未来八天内续订但尚未续订的客户。</span><span class="sxs-lookup"><span data-stu-id="c0c71-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c0c71-116">为了留住这些客户，您希望使用 Adobe 体验平台通过电子邮件向他们发送促销优惠。</span><span class="sxs-lookup"><span data-stu-id="c0c71-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="c0c71-117">在此示例中，我们希望运行一次促销电子邮件活动。</span><span class="sxs-lookup"><span data-stu-id="c0c71-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c0c71-118">本文不涵盖多次运行活动的用例。</span><span class="sxs-lookup"><span data-stu-id="c0c71-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c0c71-119">确定目标访问群体</span><span class="sxs-lookup"><span data-stu-id="c0c71-119">Identify your target audience</span></span>

<span data-ttu-id="c0c71-120">在我们的情景中，我们假设客户的电子邮件地址在访问群体见解中可用，并分析了他们的促销偏好，以确定该客户细分的成员。</span><span class="sxs-lookup"><span data-stu-id="c0c71-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c0c71-121">[您在访问群体见解中定义的客户细分](segments.md)称为 **ChurnProneCustomers**，您计划向这些客户发送电子邮件促销。</span><span class="sxs-lookup"><span data-stu-id="c0c71-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="一个其中创建了 ChurnProneCustomers 客户细分的客户细分页的屏幕截图。":::

<span data-ttu-id="c0c71-123">您要发出的优惠电子邮件将包含客户的名、姓和订阅结束日期。</span><span class="sxs-lookup"><span data-stu-id="c0c71-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c0c71-124">它告知客户，如果他们在订阅结束前续订其订阅，他们将获得折扣。</span><span class="sxs-lookup"><span data-stu-id="c0c71-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c0c71-125">导出目标访问群体</span><span class="sxs-lookup"><span data-stu-id="c0c71-125">Export your target audience</span></span>

<span data-ttu-id="c0c71-126">通过确定目标访问群体，我们可以配置从访问群体见解导出到 Azure Blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="c0c71-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="c0c71-127">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="c0c71-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c0c71-128">在 **Azure Blob 存储** 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="c0c71-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob 存储的配置磁贴。":::

1. <span data-ttu-id="c0c71-130">为这个新的导出目的地提供 **显示名称**，然后输入您希望将该客户细分导出到的 Azure Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="c0c71-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。"::: 

   - <span data-ttu-id="c0c71-132">若要了解有关如何查找 Azure Blob 存储账户名称和帐户密钥的详细信息，请参阅[管理 Azure 门户中的存储帐户设置](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="c0c71-133">若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c0c71-134">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c0c71-134">Select **Next**.</span></span>

1. <span data-ttu-id="c0c71-135">选择您要导出的客户细分。</span><span class="sxs-lookup"><span data-stu-id="c0c71-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="c0c71-136">在这个例子中，它是 **ChurnProneCustomers**。</span><span class="sxs-lookup"><span data-stu-id="c0c71-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. <span data-ttu-id="c0c71-138">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="c0c71-138">Select **Save**.</span></span>

<span data-ttu-id="c0c71-139">保存导出目的地后，您可以在 **管理** > **导出** > **我的导出目的地** 中找到它。</span><span class="sxs-lookup"><span data-stu-id="c0c71-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="包含导出列表和突出显示的示例客户细分的屏幕截图。":::

<span data-ttu-id="c0c71-141">现在，您可以[按需导出客户细分](export-destinations.md#export-data-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="c0c71-142">导出也会在每次[计划刷新](system.md)时运行。</span><span class="sxs-lookup"><span data-stu-id="c0c71-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c0c71-143">确保导出的客户细分的记录数量在 Adobe Campaign Standard 许可证的允许限度内。</span><span class="sxs-lookup"><span data-stu-id="c0c71-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c0c71-144">导出的数据存储在上面配置的 Azure Blob 存储容器中。</span><span class="sxs-lookup"><span data-stu-id="c0c71-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c0c71-145">系统在您的容器中自动创建了以下文件夹路径：</span><span class="sxs-lookup"><span data-stu-id="c0c71-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c0c71-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="c0c71-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="c0c71-147">示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="c0c71-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="c0c71-148">导出实体的 *model.json* 位于 *%ExportDestinationName%* 级别。</span><span class="sxs-lookup"><span data-stu-id="c0c71-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="c0c71-149">示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="c0c71-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="c0c71-150">在 Adobe 体验平台中定义体验数据模型 (XDM) </span><span class="sxs-lookup"><span data-stu-id="c0c71-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="c0c71-151">在 Adobe 体验平台中使用访问群体见解中的导出数据之前，您需要定义“体验数据模型”架构并[配置实时客户配置文件的数据](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="c0c71-152">了解 [XDM 是什么](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，并了解[架构组合的基础知识](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="c0c71-153">将数据导入 Adobe 体验平台</span><span class="sxs-lookup"><span data-stu-id="c0c71-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="c0c71-154">现在一切都准备好了，我们需要将访问群体见解中准备好的访问群体数据导入到 Adobe 体验平台。</span><span class="sxs-lookup"><span data-stu-id="c0c71-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="c0c71-155">首先，[创建 Azure Blob 存储源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="c0c71-156">定义源连接后，为云存储批处理连接[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)，以将访问群体见解中的客户细分输出导入到 Adobe 体验平台中。</span><span class="sxs-lookup"><span data-stu-id="c0c71-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c0c71-157">在 Adobe Campaign Standard 中创建访问群体</span><span class="sxs-lookup"><span data-stu-id="c0c71-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c0c71-158">为了发送此市场活动的电子邮件，我们将使用 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="c0c71-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="c0c71-159">将数据导入到 Adobe 体验平台后，我们需要使用 Adobe 体验平台中的数据在 Adobe Campaign Standard 中[创建一个访问群体](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)。</span><span class="sxs-lookup"><span data-stu-id="c0c71-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="c0c71-160">了解如何在 Adobe Campaign Standard 中[使用客户细分生成器](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment)，以基于 Adobe 体验平台中的数据定义访问群体。</span><span class="sxs-lookup"><span data-stu-id="c0c71-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c0c71-161">使用 Adobe Campaign Standard 创建和发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="c0c71-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c0c71-162">创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c0c71-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中的包含续订优惠的样本电子邮件。":::