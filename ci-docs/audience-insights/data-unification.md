---
title: 数据统一
description: 了解如何统一引入的数据。
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539058"
---
# <a name="data-unification-overview"></a>数据统一概述

在[设置数据源](data-sources.md)后，您可以统一数据。 数据的使用包括三个步骤：**映射**、**匹配** 和 **合并**。

数据统一过程将迥异的数据源统一为一个主数据集来提供统一的客户视图。 统一阶段必须执行，并按照以下顺序执行：

1. [映射](map-entities.md)
2. [匹配](match-entities.md)
3. [合并](merge-entities.md)

完成数据统一后，您可以选择

- [设置实体之间的关系](relationships.md)以创建精细的细分
- [扩充数据](enrichment-hub.md)以深入了解客户
- 从某些引入的属性[定义活动](activities.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]