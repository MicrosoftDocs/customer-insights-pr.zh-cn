---
title: 通过 SFTP 自定义导入扩充
description: 有关 SFTP 自定义导入扩充的常规信息。
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269595"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="0e3cd-103">使用自定义数据扩充客户配置文件（预览）</span><span class="sxs-lookup"><span data-stu-id="0e3cd-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="0e3cd-104">通过安全文件传输协议 (SFTP) 自定义导入，您可以导入不需要完成数据统一流程的数据。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="0e3cd-105">这是一种灵活、安全和方便的数据引入方式。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="0e3cd-106">SFTP 自定义导入可与 [SFTP 导出](export-sftp.md)结合使用，后者允许您导出扩充所需的客户配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="0e3cd-107">然后可以处理和扩充该数据，SFTP 自定义导入可用于将扩充的数据重新导入到 Dynamics 365 Customer Insights 的访问群体见解功能。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0e3cd-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="0e3cd-108">Prerequisites</span></span>

<span data-ttu-id="0e3cd-109">若要配置 SFTP 自定义导入，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="0e3cd-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0e3cd-110">您具有要从中导入数据的 SFTP 位置的用户凭据（用户名和密码）。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="0e3cd-111">您具有 STFP 主机的 URL 和端口号（通常为 22）。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="0e3cd-112">您具有要在 SFTP 主机上导入的文件的文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="0e3cd-113">存在一个 *model.json* 文件，用于指定要导入的数据的架构。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="0e3cd-114">此文件必须与要导入的文件位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="0e3cd-115">您具有[管理员](permissions.md#administrator)权限。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="0e3cd-116">配置</span><span class="sxs-lookup"><span data-stu-id="0e3cd-116">Configuration</span></span>

1. <span data-ttu-id="0e3cd-117">转到 **数据** > **扩充**，选择 **发现** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="0e3cd-118">在 **SFTP 自定义导入磁贴** 上，选择 **扩充我的数据**。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e3cd-119">![SFTP 自定义导入磁贴](media/SFTP_Custom_Import_tile.png "SFTP 自定义导入磁贴")</span><span class="sxs-lookup"><span data-stu-id="0e3cd-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="0e3cd-120">选择 **入门**，并提供 SFTP 服务器的凭据和地址。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="0e3cd-121">例如，sftp://mysftpserver.com:22。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="0e3cd-122">如果文件未在根文件夹中，输入包含数据的文件的名称以及该文件在 SFTP 服务器上的路径。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="0e3cd-123">通过选择 **连接到自定义导入** 确认所有输入。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e3cd-124">![SFTP 自定义导入配置弹出项目](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP 自定义导入配置弹出项目")</span><span class="sxs-lookup"><span data-stu-id="0e3cd-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="0e3cd-125">正在定义字段映射</span><span class="sxs-lookup"><span data-stu-id="0e3cd-125">Defining field mappings</span></span> 

<span data-ttu-id="0e3cd-126">包含要在 SFTP 服务器上导入的文件的目录也必须包含 *model.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="0e3cd-127">此文件定义用于导入数据的架构。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="0e3cd-128">架构必须使用 [Common Data Model](https://docs.microsoft.com/common-data-model/) 才能指定字段映射。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="0e3cd-129">Model.json 文件的一个简单示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e3cd-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="0e3cd-130">扩充结果</span><span class="sxs-lookup"><span data-stu-id="0e3cd-130">Enrichment results</span></span>

<span data-ttu-id="0e3cd-131">要开始扩充过程，请从命令栏中选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="0e3cd-132">您还可以让系统在[计划刷新](system.md#schedule-tab)过程中自动运行扩充。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0e3cd-133">处理时间将取决于要导入的数据的大小和与 SFTP 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="0e3cd-134">完成扩充流程后，您可以在 **我的扩充** 下查看新导入的自定义扩充数据。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="0e3cd-135">此外，您还会看到上次更新的时间和扩充的配置文件的数量。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0e3cd-136">您可以选择 **查看扩充的数据** 来访问每个扩充的配置文件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0e3cd-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0e3cd-137">Next steps</span></span>

<span data-ttu-id="0e3cd-138">基于扩充的客户数据构建。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0e3cd-139">创建[细分](segments.md)、[度量](measures.md)和[导出数据](export-destinations.md)以为客户提供个性化的体验。</span><span class="sxs-lookup"><span data-stu-id="0e3cd-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]