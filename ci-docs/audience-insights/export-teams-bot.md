---
title: Microsoft Teams 的机器人
description: 使用机器人帮助在 Microsoft Teams 中查找统一客户配置文件。
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405213"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="7ea79-103">用于 Dynamics 365 Customer Insights 的 Teams 机器人（预览）</span><span class="sxs-lookup"><span data-stu-id="7ea79-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="7ea79-104">与 Microsoft Teams 连接以使机器人能够在 Teams 渠道中查找统一客户配置文件。</span><span class="sxs-lookup"><span data-stu-id="7ea79-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7ea79-105">![Teams 机器人显示客户记录](media/teams-bot.png "Teams 机器人显示客户记录")</span><span class="sxs-lookup"><span data-stu-id="7ea79-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ea79-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="7ea79-106">Prerequisites</span></span>

<span data-ttu-id="7ea79-107">若要设置和配置机器人，必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="7ea79-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7ea79-108">至少[添加了一个数据源](data-sources.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea79-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="7ea79-109">完成了[统一流程](data-unification.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea79-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="7ea79-110">向[搜索和筛选索引](search-filter-index.md)添加了字段。</span><span class="sxs-lookup"><span data-stu-id="7ea79-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="7ea79-111">Customer Insights 和 Teams 属于同一个组织。</span><span class="sxs-lookup"><span data-stu-id="7ea79-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="7ea79-112">配置机器人</span><span class="sxs-lookup"><span data-stu-id="7ea79-112">Configure the bot</span></span>

1. <span data-ttu-id="7ea79-113">在访问群体见解中，转到 **管理员** > **导出目标**。</span><span class="sxs-lookup"><span data-stu-id="7ea79-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="7ea79-114">在 Microsoft Teams 磁贴中，选择 **设置**。</span><span class="sxs-lookup"><span data-stu-id="7ea79-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="7ea79-115">将重定向到 Teams 中的 **应用** 区域。</span><span class="sxs-lookup"><span data-stu-id="7ea79-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="7ea79-116">也可以打开 Teams 并选择左下角的 **应用**，或直接选择[从 AppSource 获取](https://go.microsoft.com/fwlink/?linkid=2124104)。</span><span class="sxs-lookup"><span data-stu-id="7ea79-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="7ea79-117">搜索 **Customer Insights**，然后选择该应用。</span><span class="sxs-lookup"><span data-stu-id="7ea79-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="7ea79-118">选择 **添加**。</span><span class="sxs-lookup"><span data-stu-id="7ea79-118">Select **Add**.</span></span>
1. <span data-ttu-id="7ea79-119">在 Teams 中登录 Customer Insights 之后，将看到欢迎消息，并且可以开始进行操作。</span><span class="sxs-lookup"><span data-stu-id="7ea79-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="7ea79-120">可以使用机器人执行的操作</span><span class="sxs-lookup"><span data-stu-id="7ea79-120">Things you can do with the bot</span></span>

<span data-ttu-id="7ea79-121">机器人为统一客服配置文件提供查找功能。</span><span class="sxs-lookup"><span data-stu-id="7ea79-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="7ea79-122">输入 **搜索** 加姓名、电子邮件地址或统一客服配置文件中添加到搜索和筛选索引的其他任何字段。</span><span class="sxs-lookup"><span data-stu-id="7ea79-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="7ea79-123">将显示一个卡，其中包含生成的客户配置文件中的最多 15 个字段。</span><span class="sxs-lookup"><span data-stu-id="7ea79-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="7ea79-124">多个匹配项将返回可在其中选择配置文件的结果的列表。</span><span class="sxs-lookup"><span data-stu-id="7ea79-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="7ea79-125">可以添加使用双引号引起来的搜索词查找精确匹配项。</span><span class="sxs-lookup"><span data-stu-id="7ea79-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="7ea79-126">如果您的组织在同一组织中维护多个 Customer Insights 环境，您可以输入 **switchinstance** 以选择您要将机器人连接到的环境。</span><span class="sxs-lookup"><span data-stu-id="7ea79-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="7ea79-127">输入 **帮助** 可查看机器人的可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="7ea79-127">Enter **help** to see a list of available commands for the bot.</span></span>  
