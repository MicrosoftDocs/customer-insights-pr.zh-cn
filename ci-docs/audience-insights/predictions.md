---
title: 使用预测填写部分数据
description: 使用预测填写不完整的客户数据。
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268261"
---
# <a name="complete-your-partial-data-with-predictions"></a>使用预测填写部分数据

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

可通过预测轻松创建预测值，用于增强对客户的了解。 在 **智能** > **预测** 页面上，您可以选择 **我的预测** 以查看您在访问群体见解的其他部分中配置的预测，并允许您进一步自定义它们。

> [!NOTE]
> 如果您的环境使用 Azure Data Lake Gen 2 存储，则不能使用此功能。
>
> 预测功能使用自动化方法评估数据，并根据这些数据进行预测，因此可以用作探查方法，而该术语是一般数据保护条例 (GDPR) 定义的。 客户在使用此功能处理数据时，应该遵守 GDPR 或其他法律或法规。 您有责任确保在使用 Dynamics 365 Customer Insights（包括预测）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。

## <a name="prerequisites"></a>先决条件

若要让组织可以使用预测功能，必须满足以下先决条件：

1. 您的组织有[在 Common Data Service 中设置](https://docs.microsoft.com/ai-builder/build-model#prerequisites)的实例，它与 Customer Insights 位于同一组织中。

2. 您的环境将附加到 Common Data Service 实例。

如果您在 [创建新环境](manage-environments.md)，请在 **创建环境** 对话框中配置该环境，然后选择 **高级**。 如果您已经创建了环境，请转到其设置并选择 **高级**。 在任一情况下，在 **使用预测** 部分中，输入您想要将环境附加到的 Common Data Service 实例 URL。

## <a name="create-a-prediction-in-the-customer-entity"></a>在客户实体中创建预测

1. 在访问群体见解中，转到 **数据** > **实体**。

2. 选择 **客户** 实体。

3. 在 **客户：CustomerInsights** 实体中，在 **字段** 选项卡上进行选择。

4. 找到要预测其值的属性名，然后在 **摘要** 列中选择 **概览** 图标。
   > [!div class="mx-imgBorder"]
   > ![“概览”图标](media/intelligence-overviewicon.png "“概览”图标")

5. 如果属性的缺失值比例较高，请选择 **预测缺失值** 继续进行预测。
   > [!div class="mx-imgBorder"]
   > ![“概览”状态，并且显示了预测缺失值按钮](media/intelligence-overviewpredictmissingvalues.png "“概览”状态，并且显示了预测缺失值按钮")

6. 为预测的结果提供 **显示名称** 和 **输出实体名称**。

7. 预填充的选项列表将显示可在何处将值映射到预测的类别。 在此情况下，您的类别选项只能是 0 或 1，因为它们映射到 true/false 或预测的二进制特征。 在“类别”列，请将要在最终预测中归类为“0”的字段值映射到“0”，并将要在最终预测中归类为“1”的项映射到“1”。
   > [!div class="mx-imgBorder"]
   > ![显示字段值映射到类别的示例](media/intelligence-categorymapping.png "显示字段值映射到类别的示例")

8. 选择 **完成**，然后将处理预测。 处理需要一些时间，具体取决于数据的大小和复杂程度。 将根据您创建的预测的 **输出实体名称** 在新实体中提供结果。

## <a name="create-a-prediction-while-creating-a-segment"></a>创建细分时创建预测

创建细分时，也可以预测所选特定属性的缺失值。 特别是，当您根据统一的客户实体或客户度量实体快速创建细分时。

在此流程中，您将选择要充当细分基础的特定属性，如客户满意度或购买量。 在创建细分后，系统将建议一种方法，用于预测此属性的所有缺失值。

1. 在访问群体见解中，转到 **客户细分** 并选择 **配置文件** 磁贴。

2. 选择要充当细分的创建基础的 **字段**，选择 **运算符**，然后选择 **审阅**。

3. 为细分提供 **名称** 和 **显示名称**。

4. 选择 **保存**。

5. 如果您创建的细分在源字段中的数据不完整，可以选择预测缺失值。
   > [!div class="mx-imgBorder"]
   > ![“预测”按钮](media/segments-predictoption.png "“预测”按钮")

6. 为预测的结果提供 **显示名称** 和 **输出实体名称**。

7. 选择 **完成**。 您的预测将很快在使用您为 **输出实体名称** 提供的名称的新实体中生成。

## <a name="view-a-prediction"></a>查看预测

1. 在访问群体见解中，转到 **智能** > **预测** > **我的预测**。

2. 选择要查看的预测。

3. 选择 **操作** 列中的省略号，然后选择 **查看**。

4. 将在预测的视图中看到一些数据点。
   > [!div class="mx-imgBorder"]
   > ![“预测”页面](media/intelligence-predictionsviewpage.png "“预测”页面")

   - **预测值** 显示您在“字段值到类别映射”阶段创建的映射。 这些是您的数据集中已映射到特定类别的值。
   -**主要影响因素** 是数据集内最有可能影响正在映射到特定类别的字段值的预测置信度的因素。
   - **性能** 指示预测的表现。 选择此链接可了解更多信息。
   - **预览** 显示预测的输出数据集和预测值的可能性，也称为置信度（0 是不确定，1 是确定）的示例。

## <a name="update-a-prediction"></a>更新预测

1. 在访问群体见解中，转到 **智能** > **预测** > **我的预测**。

2. 选择要更新的预测，然后选择 **更新** 图标。

3. 将计划处理预测。 可以在 **预测** 页的 **更新时间** 列中查看其上次更新时间。

## <a name="edit-a-prediction"></a>编辑预测

创建预测之后，可以在 AI Builder 中自定义模型以提高模型的效率。  

1. 在访问群体见解中，转到 **智能** > **预测** > **我的预测**。

2. 选择要编辑的预测。

3. 选择 **操作** 列中的省略号，然后选择 **查看**。

4. 选择 **在 AI Builder 中自定义**。

5. 在 AI Builder 中更新模型。 [了解有关在 AI Builder 中管理模型的详细信息](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models)。

下次运行预测将使用您已创建的更新后模型。

> [!NOTE]
> 在 AI Builder 中创建的新模型不会显示在访问群体见解中，除非已从上面列出的体验中创建该模型。

## <a name="remove-a-prediction"></a>删除预测

1. 在访问群体见解中，转到 **智能** > **预测** > **我的预测**。

2. 选择要删除的预测。

3. 选择 **操作** 列中的省略号，然后选择 **删除**。

4. 确认删除。

## <a name="troubleshooting"></a>疑难解答​​

如果因为错误无法完成附加 Common Data Service 流程，可尝试手动完成此流程。 附加流程中可能发生两种已知问题。

- 未安装客户卡加载项解决方案。
    1. 按照说明[安装和配置解决方案](customer-card-add-in.md)。

- 未授予应用权限。
    1. 转至 [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)。
    1. 选择 **环境**。
    1. 选择要向其添加权限的环境旁边的省略号，然后选择 **设置**。
    1. 展开 **用户 + 权限**，然后选择 **用户**。
    1. 选择 **+ 新建**，然后选择 **用户**。
    1. 选择 **应用程序用户**（如果尚未选择），然后输入以下信息：
        - **用户名：**cihelp@microsoft.com
        - **应用程序 ID：** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **名：** Customer
        - **姓：** Insights
        - **主要电子邮件**：cihelp@microsoft.com
    1. 选择 **保存并关闭**。
    1. 选择您刚创建的用户。
    1. 选择顶部菜单栏中的 **管理角色**。
    1. 选择 **系统管理员**，然后选择 **确定**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]