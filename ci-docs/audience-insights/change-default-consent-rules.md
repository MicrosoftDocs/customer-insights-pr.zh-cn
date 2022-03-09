---
title: 管理客户细分的默认同意规则
description: 使用同意管理功能，您可以在启用了替代的情况下禁用或更改默认同意规则。
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228928"
---
# <a name="disable-or-change-default-consent-rules"></a>禁用或更改默认同意规则

如果您的组织将[同意管理功能](../consent-management/overview.md)与访问群体见解结合使用，则[管理员可以对客户细分强制执行同意规则](activate-consent.md)。 

在客户细分区域中强制实施同意规则后，每个客户细分都会通知同意检查和规则的状态。 如果允许替代，则会对特定客户细分禁用默认同意规则。 除了默认规则之外，客户细分的每位创建者都可以为该客户细分添加更多同意规则。 

## <a name="for-administrators"></a>针对管理员

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="带有同意规则选项的客户细分生成器。":::

**停用默认同意规则：**

1. 在 **同意规则** 通知中，选择 **查看详细信息**。 

1. 将 **默认同意规则** 切换开关设置为 **关**。

**添加更多同意规则：**

1. 在 **同意规则** 通知中，选择 **查看详细信息**。 

1. 选择 **添加同意规则**，然后从 **选择同意数据类型** 下拉列表中选择一个同意规则。

1. 选择 **保存** 以将新规则应用于此客户细分。

## <a name="for-contributors"></a>对于参与者

若要在无强制实施的同意规则的情况下创建客户细分，您必须与管理员合作以对您的客户细分禁用它们。 但是，您可以将自己的同意规则添加到您负责和管理的客户细分中。

这是一个三步过程： 
1. 在访问群体见解中[创建客户细分](segments.md)并保存该客户细分。 

1. 与管理员共享客户细分名称，并请求他们[为客户细分启用替代](activate-consent.md)。 

1. 再次打开您的客户细分。 在 **同意规则** 通知中，选择 **查看详细信息** 并添加要应用的同意规则。 然后，**保存** 并 **运行** 您的客户细分。



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
