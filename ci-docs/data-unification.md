---
title: 数据统一概述
description: 使用您的数据完成数据统一过程，创建单一的统一的客户配置文件数据集。
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139468"
---
# <a name="data-unification-overview"></a>数据统一概述

在[设置数据源](data-sources.md)后，您可以统一数据。 数据统一允许您将以前分散的数据源统一到单个主数据集中，从而提供该数据的统一视图。 对于数据以个人为中心的个人消费者（企业对客户），统一提供了客户的统一视图。 对于数据以客户为中心的企业客户（企业对企业），统一提供了客户的统一视图。

可以对单个实体或多个实体统一数据。 统一按以下顺序执行：

1. [源字段](map-entities.md)（以前称为映射）：在源字段步骤中，选择要包括在统一流程中的实体和字段。 将字段映射到描述字段用途的常见语义类型。

1. [重复记录](remove-duplicates.md)（以前是匹配的一部分）：在重复的记录步骤中，可以有选择性地定义用于从每个实体中删除重复客户记录的规则。

1. [匹配条件](match-entities.md)（以前称为“匹配）：在匹配条件步骤中，定义在实体之间匹配客户记录的规则。 在两个或多个实体中找到客户时，将创建一个合并记录，该记录包含每个实体的所有列和数据。

1. [统一客户字段](merge-entities.md)（以前称为“合并”）：在统一客户字段步骤中，确定应包括、排除或合并到统一的客户配置文件中的源字段。  

1. [查看](review-unification.md)并创建统一配置文件。

完成数据统一后，您可以选择：

- [设置实体之间的关系](relationships.md)以创建精细的细分。
- [扩充数据](enrichment-hub.md)以深入了解客户。
- 从某些引入的属性[定义活动](activities.md)。
- [生成度量](measures.md)以更好地了解客户行为和业务绩效。

[!INCLUDE [footer-include](includes/footer-banner.md)]
