---
title: Microsoft Teams 的机器人
description: 使用机器人帮助在 Microsoft Teams 中查找统一客户配置文件。
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032471"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>用于 Dynamics 365 Customer Insights 的 Teams 机器人（预览）

与 Microsoft Teams 连接以使机器人能够在 Teams 渠道中查找统一客户配置文件。

> [!div class="mx-imgBorder"]
> ![Teams 机器人显示客户记录。](media/teams-bot.png "Teams 机器人显示客户记录")

## <a name="prerequisites"></a>先决条件

若要设置和配置机器人，必须满足以下先决条件：

- 至少[添加了一个数据源](data-sources.md)。
- 完成了[统一流程](data-unification.md)。
- 向[搜索和筛选索引](search-filter-index.md)添加了字段。
- Customer Insights 和 Teams 属于同一个组织。

## <a name="configure-the-bot"></a>配置机器人

1. 在访问群体见解中，转到 **管理员** > **导出目标**。
1. 在 Microsoft Teams 磁贴中，选择 **设置**。
1. 将重定向到 Teams 中的 **应用** 区域。 也可以打开 Teams 并选择左下角的 **应用**，或直接选择[从 AppSource 获取](https://go.microsoft.com/fwlink/?linkid=2124104)。
1. 搜索 **Customer Insights**，然后选择该应用。
1. 选择 **添加**。
1. 在 Teams 中登录 Customer Insights 之后，将看到欢迎消息，并且可以开始进行操作。

## <a name="things-you-can-do-with-the-bot"></a>可以使用机器人执行的操作

机器人为统一客服配置文件提供查找功能。

- 输入 **搜索** 加姓名、电子邮件地址或统一客服配置文件中添加到搜索和筛选索引的其他任何字段。

  将显示一个卡，其中包含生成的客户配置文件中的最多 15 个字段。 多个匹配项将返回可在其中选择配置文件的结果的列表。 可以添加使用双引号引起来的搜索词查找精确匹配项。

- 如果您的组织在同一组织中维护多个 Customer Insights 环境，您可以输入 **switchinstance** 以选择您要将机器人连接到的环境。

- 输入 **帮助** 可查看机器人的可用命令列表。  


[!INCLUDE[footer-include](../includes/footer-banner.md)]