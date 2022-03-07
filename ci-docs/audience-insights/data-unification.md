---
title: 数据统一
description: 了解如何统一引入的数据。
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405188"
---
# <a name="data-unification"></a>数据统一

在[设置数据源](data-sources.md)后，您可以统一数据。 数据的使用包括三个步骤：**映射**、**匹配** 和 **合并**。

数据统一过程将迥异的数据源统一为一个主数据集来提供统一的客户视图。 统一阶段必须执行，并按照以下顺序执行：

1. [映射](map-entities.md)
2. [匹配](match-entities.md)
3. [合并](merge-entities.md)

完成数据统一后，您可以选择

- [设置实体之间的关系](relationships.md)以创建精细的细分
- [扩充数据](enrichment-hub.md)以深入了解客户
- 从某些引入的属性[定义活动](activities.md)
