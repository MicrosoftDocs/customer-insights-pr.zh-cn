---
title: 将 Customer Insights 数据导出到 Adobe Campaign Standard
description: 了解如何在 Adobe Campaign Standard 中使用访问群体见解客户细分。
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596304"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="da807-103">在 Adobe Campaign Standard（预览版）中使用 Customer Insights 客户细分。</span><span class="sxs-lookup"><span data-stu-id="da807-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="da807-104">作为 Dynamics 365 Customer Insights 访问群体见解的用户，您可能创建了多个客户细分，以通过确定目标访问群体来提高市场营销活动效率。</span><span class="sxs-lookup"><span data-stu-id="da807-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="da807-105">要使用 Adobe 体验平台和应用程序（如 Adobe Campaign Standard）内访问群体见解中的客户细分，您需要执行本文中概述的几个步骤。</span><span class="sxs-lookup"><span data-stu-id="da807-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="本文中概述的步骤的流程图。":::

## <a name="prerequisites"></a><span data-ttu-id="da807-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="da807-107">Prerequisites</span></span>

-   <span data-ttu-id="da807-108">Dynamics 365 Customer Insights 许可证</span><span class="sxs-lookup"><span data-stu-id="da807-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="da807-109">Adobe Campaign Standard 许可证</span><span class="sxs-lookup"><span data-stu-id="da807-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="da807-110">Azure Blob 存储帐户</span><span class="sxs-lookup"><span data-stu-id="da807-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="da807-111">市场活动概述</span><span class="sxs-lookup"><span data-stu-id="da807-111">Campaign Overview</span></span>

<span data-ttu-id="da807-112">为了更好地了解如何使用 Adobe 体验平台内访问群体见解中的客户细分，我们来看看虚构的示例活动。</span><span class="sxs-lookup"><span data-stu-id="da807-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="da807-113">假设贵公司每月为美国客户提供基于订阅的服务。</span><span class="sxs-lookup"><span data-stu-id="da807-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="da807-114">您希望确定其订阅应在未来八天内续订但尚未续订的客户。</span><span class="sxs-lookup"><span data-stu-id="da807-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="da807-115">为了留住这些客户，您希望使用 Adobe Campaign Standard 通过电子邮件向他们发送促销优惠。</span><span class="sxs-lookup"><span data-stu-id="da807-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="da807-116">在此示例中，我们希望运行一次促销电子邮件活动。</span><span class="sxs-lookup"><span data-stu-id="da807-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="da807-117">本文不涵盖多次运行活动的用例。</span><span class="sxs-lookup"><span data-stu-id="da807-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="da807-118">但是，访问群体见解和 Adobe Campaign Standard 也可以配置为适用于经常性活动场景。</span><span class="sxs-lookup"><span data-stu-id="da807-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="da807-119">确定目标访问群体</span><span class="sxs-lookup"><span data-stu-id="da807-119">Identify your target audience</span></span>

<span data-ttu-id="da807-120">在我们的情景中，我们假设客户的电子邮件地址在访问群体见解中可用，并分析了他们的促销偏好，以确定该客户细分的成员。</span><span class="sxs-lookup"><span data-stu-id="da807-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="da807-121">[您在访问群体见解中定义的客户细分](segments.md)称为 **ChurnProneCustomers**，您计划向这些客户发送电子邮件促销。</span><span class="sxs-lookup"><span data-stu-id="da807-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="一个其中创建了 ChurnProneCustomers 客户细分的客户细分页的屏幕截图。":::

<span data-ttu-id="da807-123">您要发出的优惠电子邮件将包含客户的名、姓和订阅结束日期。</span><span class="sxs-lookup"><span data-stu-id="da807-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="da807-124">它告知客户，如果他们在订阅结束前续订其订阅，他们将获得折扣。</span><span class="sxs-lookup"><span data-stu-id="da807-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="da807-125">导出目标访问群体</span><span class="sxs-lookup"><span data-stu-id="da807-125">Export your target audience</span></span>

<span data-ttu-id="da807-126">通过确定目标访问群体，我们可以配置从访问群体见解导出到 Azure Blob 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="da807-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="da807-127">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="da807-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="da807-128">在 **Adobe Campaign** 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="da807-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard 的配置磁贴。":::

1. <span data-ttu-id="da807-130">为这个新的导出目的地提供 **显示名称**，然后输入您希望将该客户细分导出到的 Azure Blob 存储帐户的 **帐户名称**、**帐户密钥** 和 **容器**。</span><span class="sxs-lookup"><span data-stu-id="da807-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="存储帐户配置的屏幕截图。"::: 

   - <span data-ttu-id="da807-132">若要了解有关如何查找 Azure Blob 存储账户名称和帐户密钥的详细信息，请参阅[管理 Azure 门户中的存储帐户设置](/azure/storage/common/storage-account-manage)。</span><span class="sxs-lookup"><span data-stu-id="da807-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="da807-133">若要了解如何创建容器，请参阅[创建容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。</span><span class="sxs-lookup"><span data-stu-id="da807-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="da807-134">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="da807-134">Select **Next**.</span></span>

1. <span data-ttu-id="da807-135">选择您要导出的客户细分。</span><span class="sxs-lookup"><span data-stu-id="da807-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="da807-136">在这个例子中，它是 **ChurnProneCustomers**。</span><span class="sxs-lookup"><span data-stu-id="da807-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 客户细分已选定的客户细分选择用户界面的屏幕截图。":::

1. <span data-ttu-id="da807-138">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="da807-138">Select **Next**.</span></span>

1. <span data-ttu-id="da807-139">现在，我们将访问群体见解客户细分中的 **源** 字段映射到 Adobe Campaign Standard 配置文件架构中的 **目标** 字段名称。</span><span class="sxs-lookup"><span data-stu-id="da807-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 连接器的字段映射。":::

   <span data-ttu-id="da807-141">如果要添加更多属性，请选择 **添加属性**。</span><span class="sxs-lookup"><span data-stu-id="da807-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="da807-142">目标名称可能与源字段名称不同，因此，如果字段在两个系统中具有不同的名称，则仍可以将访问群体见解中的客户细分输出映射到 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="da807-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="da807-143">电子邮件地址用作标识字段，但您可以使用访问群体见解客户配置文件中的任何其他标识符将数据映射到 Adobe Campaign Standard。</span><span class="sxs-lookup"><span data-stu-id="da807-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="da807-144">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="da807-144">Select **Save**.</span></span>

<span data-ttu-id="da807-145">保存导出目的地后，您可以在 **管理** > **导出** > **我的导出目的地** 中找到它。</span><span class="sxs-lookup"><span data-stu-id="da807-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="包含导出列表和突出显示的示例客户细分的屏幕截图。":::

<span data-ttu-id="da807-147">现在，您可以[按需导出客户细分](export-destinations.md#export-data-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="da807-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="da807-148">导出也会在每次[计划刷新](system.md)时运行。</span><span class="sxs-lookup"><span data-stu-id="da807-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="da807-149">确保导出的客户细分的记录数量在 Adobe Campaign Standard 许可证的允许限度内。</span><span class="sxs-lookup"><span data-stu-id="da807-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="da807-150">导出的数据存储在上面配置的 Azure Blob 存储容器中。</span><span class="sxs-lookup"><span data-stu-id="da807-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="da807-151">系统在您的容器中自动创建了以下文件夹路径：</span><span class="sxs-lookup"><span data-stu-id="da807-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="da807-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="da807-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="da807-153">示例：Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="da807-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="da807-154">配置 Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="da807-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="da807-155">导出访问群体见解的客户细分时，它包含您在前一步中定义导出目的地时选择的列。</span><span class="sxs-lookup"><span data-stu-id="da807-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="da807-156">此数据可用于[在 Adobe Campaign Standard 中创建配置文件](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)。</span><span class="sxs-lookup"><span data-stu-id="da807-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="da807-157">要使用 Adobe Campaign Standard 中的客户细分，我们需要扩展 Adobe Campaign Standard 中的配置文件架构，以包括另外两个字段。</span><span class="sxs-lookup"><span data-stu-id="da807-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="da807-158">了解如何在 Adobe Campaign Standard 中使用新字段[扩展配置文件资源](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)。</span><span class="sxs-lookup"><span data-stu-id="da807-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="da807-159">在我们的示例中，这些字段是 *客户细分名称和客户细分日期（可选）。*</span><span class="sxs-lookup"><span data-stu-id="da807-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="da807-160">我们将使用这些字段来识别 Adobe Campaign Standard 中我们想要针对此活动的配置文件。</span><span class="sxs-lookup"><span data-stu-id="da807-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="da807-161">如果 Adobe Campaign Standard 中除了要导入的内容之外没有其他记录，您可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="da807-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="da807-162">将数据导入 Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="da807-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="da807-163">现在一切都准备好了，我们需要将访问群体见解中准备好的访问群体数据导入到 Adobe Campaign Standard，以创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="da807-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="da807-164">了解[如何在 Adobe Campaign Standard 中导入配置文件](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)。</span><span class="sxs-lookup"><span data-stu-id="da807-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="da807-165">下图中的导入工作流已配置为每 8 小时运行一次，并且会查找导出的访问群体见解客户细分（Azure Blob 存储中的 .csv 文件）。</span><span class="sxs-lookup"><span data-stu-id="da807-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="da807-166">此工作流按指定的列顺序提取 .csv 文件内容。</span><span class="sxs-lookup"><span data-stu-id="da807-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="da807-167">此工作流已构建以执行基本错误处理，并确保在 Adobe Campaign Standard 中冻结数据之前每个记录都有一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="da807-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="da807-168">此工作流还会从文件名中提取客户细分名称，然后再插入到 ACS 配置文件数据中。</span><span class="sxs-lookup"><span data-stu-id="da807-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 用户界面中导入工作流的屏幕截图。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="da807-170">在 Adobe Campaign Standard 中检索访问群体</span><span class="sxs-lookup"><span data-stu-id="da807-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="da807-171">一旦将数据导入到 Adobe Campaign Standard，您就 [可以创建一个工作流](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)，并根据 *客户细分名称* 和 *客户细分日期*[查询](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)客户，以选择为我们的示例活动确定的配置文件。</span><span class="sxs-lookup"><span data-stu-id="da807-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="da807-172">使用 Adobe Campaign Standard 创建和发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="da807-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="da807-173">创建电子邮件内容，然后[测试并发送](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)电子邮件。</span><span class="sxs-lookup"><span data-stu-id="da807-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard 中的包含续订优惠的样本电子邮件。":::