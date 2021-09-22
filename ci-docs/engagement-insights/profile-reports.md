---
title: 启用现成的配置文件报表
description: 如何创建按性别、年龄、国家/地区或原籍分组的现成配置文件报表。
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033941"
---
# <a name="out-of-box-profile-reports"></a>现成的配置文件报表

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

报表是一个数据可视化项集合，可以帮助您了解用户的行为方式。 通过连接到 Customer Insights 访问群体见解，参与见解可以显示包含有关统一客户配置文件的信息的报表。 此报表包括您具有的按性别、年龄和地理位置分组的配置文件数量。

## <a name="prerequisites"></a>先决条件

访问群体见解环境必须将数据存储在客户管理的 Azure Data Lake Storage 帐户中。

如果您要在 Customer Insights 托管数据湖中使用访问群体见解功能或环境的试用版，请[与我们联系](https://go.microsoft.com/fwlink/?linkid=2145734)以寻求帮助。  


## <a name="enable-the-customer-profile-report"></a>启用客户配置文件报表

环境管理员必须[创建与访问群体见解的连接](configure-connections.md)。

指定连接详细信息后，管理员可以向组织中的其他用户授予查看报表的权限。 设置连接的环境管理员会自动具有报表访问权限。 

连接完成后，将在左侧导航窗格中使用 **配置文件** 功能。 

- 请转到 **发现** > **配置文件** 以查看报表。

**配置文件** 报表包含有关已连接客户配置文件中的性别、年龄和地理位置的可视化项。

:::image type="content" source="media/customer-profiles.png" alt-text="客户配置文件报表。":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]