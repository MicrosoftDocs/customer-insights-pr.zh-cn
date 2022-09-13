---
title: 为数据统一选择源字段
description: 统一过程中的第一步是选择实体、属性、主键和语义类型，以将数据映射到统一的客户配置文件。
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304554"
---
# <a name="select-source-fields-for-data-unification"></a>为数据统一选择源字段

统一中的第一步是选择数据集中要统一的实体和字段。 选择包含与客户相关的详细信息（如名称、地址、电话号码和电子邮件）的实体。 您可以选择一个或多个实体。

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>选择实体和字段

1. 转到 **数据** > **统一**。

   对于个人客户（企业对客户），**统一** 登陆页将显示，在第一步 **源字段** 显示 **开始**。

   :::image type="content" source="media/m3_unify_land.png" alt-text="个人客户首次运行体验的统一登陆页的屏幕截图。":::

   对于企业客户（企业对企业），**统一** 登陆页将显示 **统一客户**，在第一步 **源字段** 显示 **开始**。 **统一联系人（预览）** 步骤是可选的，等待完成客户统一。

   :::image type="content" source="media/b2b_unify_land.png" alt-text="企业客户首次运行体验的统一登陆页的屏幕截图。":::

1. 选择 **开始**。

1. 在 **源字段** 页上，选择 **选择实体和字段**。 此时将显示 **选择实体和字段** 窗格。

1. 至少选择一个实体。

1. 对于每个选择的实体，请标识要用于匹配客户记录的字段，以及要包括在统一配置文件中的字段。 这些字段称为 *属性*。 您可以从实体中单独选择所需的属性，也可以通过在实体级别选中复选框来包含实体中的所有属性。 您可以在所有属性和实体中搜索关键字，来选择要映射的所需属性。

   :::image type="content" source="media/m3_select_entities.png" alt-text="所选实体和属性的屏幕截图。":::

   在此示例中，我们要添加 **eCommerceContacts** 和 **loyCustomer** 实体。 通过选择这些实体，您可以得出有关哪些在线业务客户是忠诚度计划成员的见解。

1. 选择 **应用** 确认您的选择。 此时将显示所选实体和属性。

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>为属性选择主键和语义类型

   :::image type="content" source="media/m3_select_primary.png" alt-text="未选择主键的选定实体的屏幕截图。" lightbox="media/m3_select_primary.png":::

对于每个实体，请执行以下步骤。

1. 选择 **主键**。 主键是实体所特有的属性。 若要使属性成为有效主键，它不应包括重复值、缺少值或 null 值。 支持将字符串、整数和 GUID 数据类型属性作为主键。

1. 要使用可以节省时间并提高准确性的 AI 模型进行语义智能预测，请确保 **智能映射** 已开启。 智能映射在 **类型** 字段中提供基于 AI 的语义建议。

1. 对于每个属性，请选择能最好地说明该属性的语义 **类型**，例如名称、市/县或电子邮件地址。

   > [!NOTE]
   > 在企业对客户中，一个字段应映射到语义类型 *Person.FullName* 以填充客户卡中的客户名称。 在企业对企业中，客户名称应映射到 *Organization.Name*。 否则，客户卡将显示为无名称。

   1. 要替代系统识别的属性类型，请选择另一个选项。 如果该类型不存在，请通过选择属性的 **类型** 字段并输入您的自定义语义类型名称来创建自定义语义类型。

   1. 要将包含 URL 的属性添加到公开可用的个人资料图像或徽标，请选择包含此 URL 的实体和字段。 在 **类型** 字段中，输入以下操作：
      - 对于个人：Person.ProfileImage
      - 对于组织：Organization.LogoImage

1. 查看自动标识语义类型的属性。 这些属性列在 **查看映射的字段** 下面。 在 **统一客户字段** 步骤中只能合并相同类型的属性。 语义类型用于自动建议见解。 请确保您选择的类型在所有选定实体中都一致。

1. 对于未自动映射到语义类型的属性，请选择语义类型字段，输入您的自定义属性类型名称，或将其保留为未映射。 这些属性列在 **定义未映射字段中的数据** 下面。

1. 完成每个实体的步骤后，选择 **保存源字段**。

1. 选择 **下一步**。

> [!div class="nextstepaction"]
> [下一步：删除重复项](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]