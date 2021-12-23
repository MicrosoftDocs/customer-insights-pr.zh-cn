---
title: 激活客户细分同意规则
description: 按照这些步骤在访问群体见解中链接同意数据和激活同意检查。 管理员还可以禁用同意检查。
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884063"
---
# <a name="activate-consent-rules"></a>激活同意规则

[同意中心（预览版）](../consent-management/overview.md)可帮助您协调来自不同来源的同意数据。 使用统一 *同意* 实体应用默认同意检查。 在将同意数据导入同意中心并配置数据规则后，*同意* 实体会自动同步到访问群体见解。

## <a name="enable-consent-checks"></a>启用同意检查

将同意数据导入到同意中心（预览版）并设置规则后，您可以启用同意检查。 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="访问群体见解设置中具有激活的同意数据的同意选项卡。":::

1. 在访问群体见解中，转到 **管理员** > **系统**。

1. 选择 **同意(预览版)** 选项卡。

1. 在 **启用同意检查** 部分，对要启用的所有区域将切换开关设置为 **开**。

1. 选中 **允许替代默认同意规则** 复选框，以删除在特定客户细分上强制实施的默认同意检查。 

1. 在下拉菜单中，选择要允许替代的位置。     

1. 在 **将同意链接到客户配置文件** 部分，选择用作标识符的属性，以将同意数据链接到客户数据。 这很可能是电话号码或电子邮件地址。 

1. 选择 **保存** 以应用您的设置。

## <a name="disable-consent-checks"></a>禁用同意检查

为了在访问群体见解中停止使用同意数据，管理员必须相应地更新系统设置。

1. 在访问群体见解中，转到 **管理员** > **系统**。

1. 选择 **同意(预览版)** 选项卡。

1. 在 **启用同意检查** 部分，将切换开关设置为 **关**。

> [!TIP]
> 若要停止使用同意管理功能，请参阅[同意中心中的系统设置（预览版）](../consent-management/system-settings.md)。
