---
title: 访问群体见解中的主页
description: 开始浏览主页上的应用。
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597224"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="4f92b-103">创建新环境</span><span class="sxs-lookup"><span data-stu-id="4f92b-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="4f92b-104">创建试用环境</span><span class="sxs-lookup"><span data-stu-id="4f92b-104">Create a trial environment</span></span>

<span data-ttu-id="4f92b-105">您可以在[试用注册页](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)注册试用。</span><span class="sxs-lookup"><span data-stu-id="4f92b-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="4f92b-106">试用将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="4f92b-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="4f92b-107">选择 **注册免费试用** 选项，然后选择 **立即注册**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="4f92b-108">提供您的工作或学校电子邮件地址，告诉我们有关您个人的更多信息，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="用于注册试用实例的对话框":::

1. <span data-ttu-id="4f92b-110">为您的新环境提供一个 **名称**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="4f92b-111">选择试用类型。</span><span class="sxs-lookup"><span data-stu-id="4f92b-111">Select the trial type.</span></span>

1. <span data-ttu-id="4f92b-112">选择环境的 **区域**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="4f92b-113">（可选）对于 Dynamics 365 组织的管理员：选择 **高级设置**，提供您组织的 URL，以使用预测功能（如客户流失）。</span><span class="sxs-lookup"><span data-stu-id="4f92b-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="4f92b-114">选择 **创建**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-114">Select **Create**.</span></span> 

<span data-ttu-id="4f92b-115">环境创建后，您将看到 **演示** 环境，您可以使用它来探索使用虚构数据的应用。</span><span class="sxs-lookup"><span data-stu-id="4f92b-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="4f92b-116">您可以根据您的行业更改示例数据。</span><span class="sxs-lookup"><span data-stu-id="4f92b-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="4f92b-117">选择标题中的 **设置** 图标，然后选择 **演示设置**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="4f92b-118">此外，您还可以更改视觉主题。</span><span class="sxs-lookup"><span data-stu-id="4f92b-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="4f92b-119">您[切换到在注册过程中创建的环境](#switch-environments)来使用您自己的数据。</span><span class="sxs-lookup"><span data-stu-id="4f92b-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="4f92b-120">创建新的生产或沙盒环境</span><span class="sxs-lookup"><span data-stu-id="4f92b-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="4f92b-121">在您的环境中，选择应用程序标题中的 **环境** 选择器，然后选择 **新建**。</span><span class="sxs-lookup"><span data-stu-id="4f92b-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="4f92b-122">请按照步骤操作，就像[创建试用环境](#create-a-trial-environment)一样。</span><span class="sxs-lookup"><span data-stu-id="4f92b-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="4f92b-123">默认情况下，数据存储在 Customer Insights 托管的数据湖中。</span><span class="sxs-lookup"><span data-stu-id="4f92b-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="4f92b-124">选择 **高级设置** 时将出现一个在您自己的 Azure Data Lake 中存储数据的额外选项。</span><span class="sxs-lookup"><span data-stu-id="4f92b-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="4f92b-125">提供您的帐户名称和帐户密钥以建立与您的 Azure Data Lake 的连接。</span><span class="sxs-lookup"><span data-stu-id="4f92b-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4f92b-126">将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输到适合该 Azure 存储帐户的地理位置并存储在其中，此位置可能与 Dynamics 365 Customer Insights 中存储数据的位置不同。</span><span class="sxs-lookup"><span data-stu-id="4f92b-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="4f92b-127">有关详细信息，请访问 Microsoft 信任中心。</span><span class="sxs-lookup"><span data-stu-id="4f92b-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="4f92b-128">浏览主页</span><span class="sxs-lookup"><span data-stu-id="4f92b-128">Explore the home page</span></span>

<span data-ttu-id="4f92b-129">您可以在以下 URL 上从 [Dynamics 365 Customer Insights 访问访问群体见解](https://home.ci.ai.dynamics.com/)：[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/)。</span><span class="sxs-lookup"><span data-stu-id="4f92b-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="4f92b-130">完成 [映射](map-entities.md)、[匹配](match-entities.md)和 [合并](merge-entities.md)阶段后，**主页** 页面会显示客户细分、度量和扩充数据（如果已配置）的概述。</span><span class="sxs-lookup"><span data-stu-id="4f92b-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="4f92b-131">![主页中的见解](media/home-page-insights.png "主页中的见解")</span><span class="sxs-lookup"><span data-stu-id="4f92b-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="4f92b-132">在 **最近客户细分** 下，您将看到基于您定义的人口统计、行为或事务属性的客户组。</span><span class="sxs-lookup"><span data-stu-id="4f92b-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="4f92b-133">[创建客户细分](segments.md)有助于您对客户群进行分组，并更好地确定您的目标业务活动。</span><span class="sxs-lookup"><span data-stu-id="4f92b-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="4f92b-134">**最近的度量** 显示带有您定义的[关键绩效指标 (KPI)](measures.md) 的磁贴。</span><span class="sxs-lookup"><span data-stu-id="4f92b-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="4f92b-135">例如，客户流失的平均可能性或每个客户联机花费的平均时间。</span><span class="sxs-lookup"><span data-stu-id="4f92b-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="4f92b-136">**最近扩充** 部分列出最近完成的扩充运行的结果。</span><span class="sxs-lookup"><span data-stu-id="4f92b-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="4f92b-137">[扩充](enrichment-hub.md)添加有关客户群的信息。</span><span class="sxs-lookup"><span data-stu-id="4f92b-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="4f92b-138">例如，通过了解与其有相关性的兴趣和品牌。</span><span class="sxs-lookup"><span data-stu-id="4f92b-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="4f92b-139">切换环境</span><span class="sxs-lookup"><span data-stu-id="4f92b-139">Switch environments</span></span>

<span data-ttu-id="4f92b-140">选择页面右上角中的 **环境** 控件以更改环境。</span><span class="sxs-lookup"><span data-stu-id="4f92b-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="4f92b-141">![切换环境](media/home-page-environment-switcher.png "切换环境")</span><span class="sxs-lookup"><span data-stu-id="4f92b-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="4f92b-142">管理员可以创建和管理[多个环境](manage-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="4f92b-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="4f92b-143">例如，如果您的组织在国际范围内运营，并且您需要以不同的方式隔离数据和见解，则维护多个环境可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="4f92b-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f92b-144">下一步</span><span class="sxs-lookup"><span data-stu-id="4f92b-144">Next step</span></span>

<span data-ttu-id="4f92b-145">若要在主页上查看您自己的见解，您首先需要[添加数据源](data-sources.md)并[统一](data-unification.md)数据以构建客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="4f92b-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]