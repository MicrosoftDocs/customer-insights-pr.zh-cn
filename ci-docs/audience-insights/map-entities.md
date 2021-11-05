---
title: 为数据统一映射实体和属性
description: 选择实体、属性、主键和语义类型来将数据映射到统一客户配置文件。
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673252"
---
# <a name="map-entities-and-attributes"></a>映射实体和属性

**映射** 是访问群体见解的数据统一流程中的第一阶段。 映射包含三个阶段：

- *选择实体*：确定将生成包含有关客户的更完整信息的数据集的可合并实体。
- *选择属性*：为每个实体确定要在 *匹配* 和 *合并* 阶段合并和协调的列。 这些列称为 *属性*。
- *主键和语义类型选择*：对于每个实体，确定要定义为该实体的主键的属性，对于每个属性，确定最能描述该属性的语义类型。

有关一般的数据统一流程的详细信息，请参阅[统一](data-unification.md)。

## <a name="select-the-first-entities"></a>选择第一个实体

1. 在访问群体见解中，转到 **数据** > **统一** > **映射**。

2. 通过选择 **选择实体** 开始执行映射阶段。

3. 选择要在 *匹配* 和 *合并* 阶段使用的实体和属性。 您可以通过选择实体级别的 **包括所有字段** 复选框，从实体中单独选择所需的属性，或包含实体中的所有属性。 建议至少选择两个实体，以便利用数据统一过程。

   > [!div class="mx-imgBorder"]
   > ![添加实体示例。](media/data-manager-configure-map-add-entities-example.png "添加实体示例")

   在此示例中，我们要添加 **eCommerceContacts** 和 **loyCustomers** 实体。 通过选择这些实体，您可以得出有关哪些在线业务客户是忠诚度计划成员的见解。
   
   您可以在所有属性和实体中搜索关键字，来选择要映射的所需属性。
   
     > [!div class="mx-imgBorder"]
   > ![搜索字段示例。](media/data-manager-configure-map-search-fields-example.png "搜索字段示例")

4. 选择 **应用** 确认您的选择。

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>为属性选择主键和语义类型

选择实体后，**映射** 页将列出所选实体，供您查看。 定义实体的主键并确定实体中属性的语义类型。

- **主键**：为每个实体选择一个属性作为主键。 若要使属性成为有效主键，它不应包括重复值、缺少值或 null 值。 字符串、整数和 GUID 数据类型属性被作为主键支持，将显示在一个字段中供您选择。

- **属性语义类型**：属性的类别，如电子邮件地址或姓名。 要将 AI 模型用于语义智能预测，节省时间并提高准确性，请将 **智能映射** 设置为 **开**。 智能映射在 **类型** 字段中突出显示基于 AI 的语义建议。 如果将其设置为 **关**，您将看到我们的常规映射建议。 您可以从可用的选项列表中选择任意一种语义类型，来替代建议的选择。

> [!div class="mx-imgBorder"]
> ![属性类型和语义预测。](media/data-manager-configure-map-add-attributes-semantic-prediction.png "属性类型和语义预测")

还可以添加自定义语义类型。 选择属性的类型字段，然后键入自定义语义类型名称。 这样，您还可以更改系统确定的属性类型。

将自动识别其语义类型的所有属性都在 **查看映射字段** 部分分组。 查看这些属性及其语义类型，因为它们将用于在数据统一的合并步骤中合并您的实体。

不会自动映射到语义类型的属性在 **在未映射字段中定义数据** 部分进行分组。 选择未映射属性的语义类型字段，或输入您的自定义属性类型名称。

> [!div class="mx-imgBorder"]
> ![主键和属性类型。](media/data-manager-configure-map-add-attributes.png "主键和属性类型")

> [!NOTE]
> 应将一个字段映射到语义类型 Person. FullName 以填充客户卡中的客户名称。 否则，客户卡将显示为无名称。 

## <a name="add-and-remove-attributes-and-entities"></a>添加和删除属性和实体

1. 在 **统一** > **映射** 中，选择 **编辑字段**。

2. 在 **编辑字段** 窗格中，添加或删除属性和实体。 使用搜索或滚动查找和选择您感兴趣的属性和实体。 如果属性或实体已经匹配，则无法将其删除。

   > [!div class="mx-imgBorder"]
   > ![添加或删除属性。](media/configure-data-map-edit.png "添加或删除属性")

3. 选择 **应用**。

## <a name="add-images-to-profiles"></a>向配置文件添加图像

如果实体中包含 URL 以公开发布配置文件图像或徽标，可以将其添加到统一客户配置文件。

选择实体并查找其中包含配置文件图像的 URL 的字段。 在 **类型** 输入字段中，手动输入以下值： 
- 对于个人：Person.ProfileImage
- 对于组织：Organization.LogoImage

继续执行统一步骤，并确保在[合并](merge-entities.md)步骤中也添加了包含图像 URL 的属性。

## <a name="set-attributes-for-organizations"></a>设置组织的属性

对于组织（预览），属性类型应该映射到“Organization.Name”
> [!div class="mx-imgBorder"]
> ![企业到企业主键和属性类型。](media/configure-data-map-edit-b2b.png "企业到企业主键和属性类型")

## <a name="next-step"></a>下一步

在数据统一过程中，转到 **匹配** 页。 访问 [**匹配**](match-entities.md)以了解此阶段。

> [!TIP]
> 观看以下视频：[入门：创建统一的客户配置文件](https://youtu.be/oBfGEhucAxs)。


[!INCLUDE[footer-include](../includes/footer-banner.md)]