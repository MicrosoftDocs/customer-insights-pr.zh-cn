---
title: 用于 Dynamics 365 Customer Insights 的 Teams 机器人（预览）
description: 使用机器人帮助在 Microsoft Teams 中查找统一客户配置文件。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195831"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>用于 Dynamics 365 Customer Insights 的 Teams 机器人（预览）

与 Microsoft Teams 连接以使机器人能够在 Teams 渠道中查找统一客户配置文件。

:::image type="content" source="media/teams-bot.png" alt-text="Teams 机器人显示客户记录":::

## <a name="prerequisites"></a>先决条件

- 至少[添加了一个数据源](data-sources.md)。
- 完成了[统一流程](data-unification.md)。
- 向[搜索和筛选索引](search-filter-index.md)添加了字段。
- Customer Insights 和 Teams 属于同一个组织。
- 您的环境将主要目标受众设置为个人客户。 不支持企业客户。


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>配置机器人

1. 转到 **管理员** > **连接**。
1. 在 Microsoft Teams 磁贴中，选择 **设置**。
1. 将重定向到 Teams 中的 **应用** 区域。 也可以打开 Teams 并选择左下角的 **应用**，或直接选择[从 AppSource 获取](https://go.microsoft.com/fwlink/?linkid=2124104)。
1. 搜索 **Customer Insights**，然后选择该应用。
1. 选择 **添加**。
1. 登录到 Teams 中的 Customer Insights。 将显示欢迎消息。

## <a name="things-you-can-do-with-the-bot"></a>可以使用机器人执行的操作

机器人为统一客服配置文件提供查找功能。

- 输入 **搜索** 加姓名、电子邮件地址或统一客服配置文件中添加到搜索和筛选索引的其他任何字段。

  将显示一个卡，其中包含生成的客户配置文件中的最多 15 个字段。 多个匹配项将返回可在其中选择配置文件的结果的列表。 要查找精确匹配项，在双引号中添加搜索词。

- 如果您的组织在同一组织中维护多个 Customer Insights 环境，输入 **switchinstance** 以选择您要将机器人连接到的环境。

- 输入 **帮助** 可查看机器人的可用命令列表。  

[!INCLUDE [footer-include](includes/footer-banner.md)]