---
title: 创建统一客户视图
description: 使用您的数据完成数据统一过程，创建单一的客户配置文件主数据集。
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304416"
---
# <a name="data-unification-overview"></a>数据统一概述

在[设置数据源](data-sources.md)后，您可以统一数据。 数据统一允许您将以前分散的数据源统一到单个主数据集中，从而提供该数据的统一视图。

对于数据以个人为中心的个人消费者（企业对客户），统一提供了客户的统一视图。 对于数据以客户为中心的企业客户（企业对企业），统一提供了客户的统一视图。 [联系人统一（预览）](data-unification-contacts.md)允许这些客户的联系人单独统一并与客户关联。

可以对单个实体或多个实体统一数据。

# <a name="individual-consumers-b-to-c"></a>[单个消费者(企业对客户)](#tab/b2c)

统一过程从您的数据源映射客户数据、删除重复项、跨实体匹配数据并创建统一配置文件。 统一按以下顺序执行：

1. [源字段](map-entities.md)（以前称为映射）：在源字段步骤中，选择要包括在统一流程中的实体和字段。 将字段映射到描述字段用途的常见语义类型。

1. [重复记录](remove-duplicates.md)（以前是匹配的一部分）：在重复的记录步骤中，可以有选择性地定义用于从每个实体中删除重复客户记录的规则。

1. [匹配条件](match-entities.md)（以前称为“匹配）：在匹配条件步骤中，定义在实体之间匹配客户记录的规则。 在两个或多个实体中找到客户时，将创建一个合并记录，该记录包含每个实体的所有列和数据。

1. [统一客户字段](merge-entities.md)（以前称为“合并”）：在统一客户字段步骤中，确定应包括、排除或合并到统一的客户配置文件中的源字段。  

1. [查看](review-unification.md)并创建统一配置文件。

# <a name="business-accounts-b-to-b"></a>[企业帐户(企业对企业)](#tab/b2b)

统一流程从您的数据源映射客户数据、删除重复项、跨实体匹配数据并创建统一配置文件。 统一按以下顺序执行：

1. [源字段](map-entities.md)（以前称为映射）：在源字段步骤中，选择要包括在统一客户流程中的实体和字段。 将字段映射到描述字段用途的常见语义类型。

1. [重复记录](remove-duplicates.md)（以前是匹配的一部分）：在重复的记录步骤中，可以有选择性地定义用于从每个实体中删除重复客户记录的规则。

1. [匹配条件](match-entities.md)（以前称为“匹配）：在匹配条件步骤中，定义在实体之间匹配客户记录的规则。 在两个或多个实体中找到客户时，将创建一个合并记录，该记录包含每个实体的所有列和数据。

1. [统一客户字段](merge-entities.md)（以前称为“合并”）：在统一客户字段步骤中，确定应包括、排除或合并到统一的客户配置文件中的源字段。  

1. [查看](review-unification.md)并创建统一配置文件。

统一客户后，您可以选择为这些客户[统一联系人（预览）](data-unification-contacts.md)并将统一的联系人链接到统一客户。

---

完成数据统一后，您可以选择：

- [设置实体之间的关系](relationships.md)以创建精细的细分。
- [扩充数据](enrichment-hub.md)以深入了解客户。
- 从某些引入的属性[定义活动](activities.md)。
- [生成度量](measures.md)以更好地了解客户行为和业务绩效。

[!INCLUDE [footer-include](includes/footer-banner.md)]
