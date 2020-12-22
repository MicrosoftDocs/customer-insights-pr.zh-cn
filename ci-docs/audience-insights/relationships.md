---
title: 实体和实体路径之间的关系
description: 创建和管理来自多个数据源的实体之间的关系。
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405226"
---
# <a name="relationships-between-entities"></a>实体之间的关系

当实体共用可在实体之间引用的通用标识（外键）时，关系可帮助您连接实体和生成数据图。 可通过连接的实体基于多个数据源定义细分和度量。

关系有两种。 不可编辑系统关系（这是自动创建的），以及用户创建和配置的自定义关系。

匹配和合并过程中，将基于智能匹配在后台创建系统关系。 这些关系可以帮助将客户配置文件记录与其他相应实体的记录关联。 下图演示当客户实体与更多实体匹配以生成最终客户配置文件实体时，创建三个系统关系。

> [!div class="mx-imgBorder"]
> ![关系创建](media/relationships-entities-merge.png "关系创建")

- 创建了客户实体与联系人实体之间的 ***CustomerToContact* 关系**。 客户实体获取了键字段 **Contact_contactId**，以便关联到联系人实体键字段 **contactId**。
- 创建了客户实体与帐户实体之间的 **_CustomerToAccount_ 关系**。 客户实体获取了键字段 **Account_accountId**，以便关联到帐户实体键字段 **accountId**。
- 创建了客户实体与 WebAccount 实体之间的 **_CustomerToWebAccount_ 关系**。 客户实体获取了键字段 **WebAccount_webaccountId**，以便关联到 WebAccount 实体键字段 **webaccountId**。

## <a name="create-a-relationship"></a>创建关系

自定义关系在 **关系** 页中定义。 每个关系包含一个源实体（该实体中包含外键）和一个目标实体（这是源实体的外键指向的实体）。

1. 在访问群体见解中，转到 **数据** > **关系**。

2. 选择 **新建关系**。

3. 在 **添加关系** 窗格中，提供以下信息：

   > [!div class="mx-imgBorder"]
   > ![输入关系详细信息](media/relationships-add.png "输入关系详细信息")

   - **关系名称**：用于体现关系用途的名称（例如，**AccountWebLogs**）。
   - **说明**：关系的说明。
   - **源实体**：选择用作关系中的源的实体（例如，WebLog）。
   - **基数**：选择源实体记录的基数。 例如，“大量”表示多个 Weblog 记录与一个 WebAccount 关联。
   - **源键字段**：表示源实体中的外键字段。 例如，WebLog 的外键字段为 **accountId**。
   - **目标实体**：选择用作关系中的目标的实体（例如，WebAccount）。
   - **目标基数**：选择目标实体记录的基数。 例如，“一个”表示多个 Weblog 记录与一个 WebAccount 关联。
   - **目标键字段**：此字段表示目标实体的键字段。 例如，WebAccount 的键字段为 **accountId**。

> [!NOTE]
> 仅支持多对一和一对一关系。 可以使用两个多对一关系和一个链接实体（用于连接源实体和目标实体的实体）创建多对多关系。

## <a name="delete-a-relationship"></a>删除关系

1. 在访问群体见解中，转到 **数据** > **关系**。

2. 选中要删除的关系的复选框。

3. 选择 **关系** 表顶部的 **删除**。

4. 确认删除。

## <a name="next-step"></a>下一步

系统关系和自定义关系用于基于多个数据源创建不再分散的细分。 有关详细信息，请参阅[细分](segments.md)。
