---
title: Dynamics 365 Customer Insights 可用性区域
description: 了解有关服务部署到的区域和地理区域的更多信息。
author: mkisel11
ms.reviewer: mhart
ms.author: mkisel
ms.date: 09/28/2021
ms.service: customer-insights
ms.topic: article
ms.manager: shellyha
ms.openlocfilehash: d4ae7a085ba68c482372868e75376b6f769325d7
ms.sourcegitcommit: ce2c011f06999dba2e886b8804d3439fbf67074d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2021
ms.locfileid: "7564583"
---
# <a name="regional-availability-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的区域可用性

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

参与见解是 Dynamics 365 Customer Insights 的一项功能，逐渐引入到了客户可以选择在其中存储数据的更多区域。 管理员可在[创建新的环境](manage-environments-workspaces.md#create-an-environment)时选择区域。 

第一次设置参与见解时，可以在运行[引导式首次运行体验](quickstart.md)时选择区域。 以后，每个新环境都允许您选择将用于存储数据的区域。

当前，我们支持美国和欧洲地理区域。 用户可以在以下区域之间进行选择：美国西部、美国东部、北欧和西欧。

组织可以维护不同区域中的环境。 例如，环境 A 将数据存储在美国西部，环境 B 将数据存储在北欧。

> [!NOTE]
> 在创建环境期间选择区域后，您将无法更改该设置。 要更改区域，环境管理员必须[删除环境](manage-environments-workspaces.md#delete-an-environment)，并使用更新的区域设置创建新环境。


[!INCLUDE[footer-include](../includes/footer-banner.md)]