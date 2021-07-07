---
title: 通过 SFTP 自定义导入扩充
description: 有关 SFTP 自定义导入扩充的常规信息。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304639"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="7da4c-103">使用自定义数据扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="7da4c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="7da4c-104">通过安全文件传输协议 (SFTP) 自定义导入，您可以导入不需要完成数据统一流程的数据。</span><span class="sxs-lookup"><span data-stu-id="7da4c-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="7da4c-105">这是一种灵活、安全和方便的数据引入方式。</span><span class="sxs-lookup"><span data-stu-id="7da4c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="7da4c-106">SFTP 自定义导入可与 [SFTP 导出](export-sftp.md)结合使用，后者允许您导出扩充所需的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="7da4c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="7da4c-107">然后，可以处理和扩充数据，SFTP 自定义导入可用于将扩充的数据引入回 Dynamics 365 Customer Insights 的访问群体见解功能。</span><span class="sxs-lookup"><span data-stu-id="7da4c-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7da4c-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="7da4c-108">Prerequisites</span></span>

<span data-ttu-id="7da4c-109">若要配置 SFTP 自定义导入，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="7da4c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7da4c-110">您将具有要在 SFTP 主机上导入的文件的文件名和位置（路径）。</span><span class="sxs-lookup"><span data-stu-id="7da4c-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="7da4c-111">有一个 *model.json* 文件，用于为要导入的数据指定 [Common Data Model 架构](/common-data-model/)。</span><span class="sxs-lookup"><span data-stu-id="7da4c-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="7da4c-112">此文件必须与要导入的文件位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="7da4c-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="7da4c-113">管理员已配置 SFTP 连接，*或者* 您拥有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="7da4c-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="7da4c-114">对于要从中导入数据的 SFTP 位置，您将需要用户凭据、URL 和端口号。</span><span class="sxs-lookup"><span data-stu-id="7da4c-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="7da4c-115">配置导入</span><span class="sxs-lookup"><span data-stu-id="7da4c-115">Configure the import</span></span>

1. <span data-ttu-id="7da4c-116">转到 **数据** > **扩充**，选择 **发现** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7da4c-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="7da4c-117">在 **SFTP 自定义导入磁贴** 上，选择 **扩充我的数据**，然后选择 **开始**。</span><span class="sxs-lookup"><span data-stu-id="7da4c-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 自定义导入磁贴。":::

1. <span data-ttu-id="7da4c-119">从下拉列表中选择[连接](connections.md)。</span><span class="sxs-lookup"><span data-stu-id="7da4c-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="7da4c-120">如果没有连接可用，请联系管理员。</span><span class="sxs-lookup"><span data-stu-id="7da4c-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="7da4c-121">如果您是管理员，可以通过选择 **添加连接** 并从下拉列表中选择 **SFTP 自定义导入** 来创建连接。</span><span class="sxs-lookup"><span data-stu-id="7da4c-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="7da4c-122">选择 **连接到自定义导入** 以确认选择的连接。</span><span class="sxs-lookup"><span data-stu-id="7da4c-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="7da4c-123">选择 **下一步**，然后输入您要导入的数据文件的 **路径** 和 **文件名**。</span><span class="sxs-lookup"><span data-stu-id="7da4c-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="输入数据位置时的屏幕截图。":::

1. <span data-ttu-id="7da4c-125">选择 **下一步** 并提供扩充的名称和输出实体的名称。</span><span class="sxs-lookup"><span data-stu-id="7da4c-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="7da4c-126">在查看您的选择后选择 **保存扩充**。</span><span class="sxs-lookup"><span data-stu-id="7da4c-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="7da4c-127">配置 SFTP 自定义导入的连接</span><span class="sxs-lookup"><span data-stu-id="7da4c-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="7da4c-128">您必须是管理员才能配置连接。</span><span class="sxs-lookup"><span data-stu-id="7da4c-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="7da4c-129">配置扩充时选择 **添加连接**，*或* 转到 **管理员** > **连接**，然后在自定义导入磁贴上选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="7da4c-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="7da4c-130">在 **显示名称** 框中输入连接的名称。</span><span class="sxs-lookup"><span data-stu-id="7da4c-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="7da4c-131">输入要导入的数据所在的 SFTP 服务器的有效用户名、密码和主机 URL。</span><span class="sxs-lookup"><span data-stu-id="7da4c-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="7da4c-132">进行查看，然后选中 **我同意** 复选框以同意 **数据隐私和合规性**。</span><span class="sxs-lookup"><span data-stu-id="7da4c-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="7da4c-133">选择 **验证** 以验证配置。</span><span class="sxs-lookup"><span data-stu-id="7da4c-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="7da4c-134">验证完成后，可以通过选择 **保存** 来保存连接。</span><span class="sxs-lookup"><span data-stu-id="7da4c-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7da4c-135">![Experian 连接配置页面](media/enrichment-SFTP-connection.png "Experian 连接配置页面")</span><span class="sxs-lookup"><span data-stu-id="7da4c-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="7da4c-136">正在定义字段映射</span><span class="sxs-lookup"><span data-stu-id="7da4c-136">Defining field mappings</span></span> 

<span data-ttu-id="7da4c-137">包含要在 SFTP 服务器上导入的文件的目录也必须包含 *model.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="7da4c-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="7da4c-138">此文件定义用于导入数据的架构。</span><span class="sxs-lookup"><span data-stu-id="7da4c-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="7da4c-139">架构必须使用 [Common Data Model](/common-data-model/) 指定字段映射。</span><span class="sxs-lookup"><span data-stu-id="7da4c-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="7da4c-140">Model.json 文件的一个简单示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="7da4c-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="7da4c-141">扩充结果</span><span class="sxs-lookup"><span data-stu-id="7da4c-141">Enrichment results</span></span>

<span data-ttu-id="7da4c-142">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="7da4c-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7da4c-143">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="7da4c-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7da4c-144">处理时间将取决于要导入的数据的大小和与 SFTP 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="7da4c-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="7da4c-145">完成扩充流程后，您可以在 **我的扩充** 下查看新导入的自定义扩充数据。</span><span class="sxs-lookup"><span data-stu-id="7da4c-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="7da4c-146">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="7da4c-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7da4c-147">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="7da4c-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7da4c-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7da4c-148">Next steps</span></span>

<span data-ttu-id="7da4c-149">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="7da4c-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7da4c-150">创建[细分](segments.md)和[度量](measures.md)并[导出数据](export-destinations.md)，以向客户提供个性化体验。</span><span class="sxs-lookup"><span data-stu-id="7da4c-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
