---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755533"
---
在引入数据后，开始数据统一过程，以创建统一的客户配置文件。 有关详细信息，请参阅[数据统一](../data-unification.md)。

### <a name="select-source-fields"></a>选择源字段

1. 引入数据后，将联系人从电子商务和忠诚度数据映射到常见数据类型。 转到 **数据** > **统一**。

1. 选择表示客户配置文件的实体 – **eCommerceContacts** 和 **loyCustomers**。

   ![统一电子商务和忠诚度数据源。](../media/unify-ecommerce-loyalty.png)

1. 选择 **ContactId** 作为 **eCommerceContacts** 的主键，选择 **LoyaltyID** 作为 **loyCustomers** 的主键。

1. 选择 **下一步**。 跳过重复记录并选择 **下一步**。

### <a name="match-conditions"></a>匹配条件

1. 选择 **eCommerceContacts : eCommerce** 作为主要实体并包括所有记录。

1. 选择 **loyCustomers : LoyaltyScheme** 并包含所有记录。

1. 添加规则：
   - 为 eCommerceContacts 和 loyCustomers 选择 **FullName**。
   - 针对 **标准化** 选择 **类型（电话、名称、地址、...）**。
   - 设置 **精度级别**：**基本** 和 **值**：**高**。
   - 为名称输入 **FullName 和电子邮件**。

1. 为电子邮件地址添加第二个条件：
   - 为 eCommerceContacts 和 loyCustomers 选择 **电子邮件**。
   - 将“标准化”留空。
   - 设置 **精度级别**：**基本** 和 **值**：**高**。

   ![统一名称和电子邮件的匹配规则。](../media/unify-match-rule.png)

1. 选择 **完成**。

1. 选择 **下一步**。

### <a name="unify-fields"></a>统一字段

1. 将 **loyCustomers** 实体的 **ContactId** 重命名为 **ContactIdLOYALTY**，以将其与其他引入的 ID 区分开来。

1. 选择 **下一步** 来查看，然后选择 **创建客户配置文件**。
