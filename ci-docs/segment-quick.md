---
title: 使用快速客户细分创建简单客户细分
description: 创建简单客户细分，以根据各种属性为客户分组。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171126"
---
# <a name="create-simple-segments-with-quick-segments"></a>使用快速客户细分创建简单客户细分

通过快速客户细分，您可以利用单个运算符快速构建简单的客户细分，以便更快地获取见解。 快速客户细分仅在 **个人客户** 环境中受支持。

## <a name="create-a-new-segment-with-quick-segments"></a>使用快速客户细分创建新客户细分

1. 转到 **客户细分**。

1. 选择 **新建** > **创建自**。
   - 若要生成基于 *统一的客户* 实体的细分，请选择 **配置文件** 选项。
   - 选择 **度量** 选项，以围绕先前创建的度量构建客户细分。
   - 选择 **智能** 以根据您使用 **预测** 或 **自定义模型** 功能生成的一个输出实体构建细分。

1. 在 **新快速客户细分** 对话框中，从 **字段** 下拉列表选择属性。 根据您的选择，系统会提供不同的值。
   - 对于分类字段，排名最靠前的 10 类客户的计数将显示。 选择一个 **值**，然后选择 **查看**。
   - 对于数值属性，系统将显示哪个属性值归入每个客户的百分比下。 选择 **运算符** 和 **值**，然后选择 **查看**。

1. 系统将提供 **估算的细分大小**。 选择要生成已定义的客户细分，还是返回选择不同的字段。

   :::image type="content" source="media/quick-segment-name.png" alt-text="快速客户细分的名称和估算。":::

1. 为客户细分提供 **名称** 和 **输出实体名称**。 （可选）添加[标记](work-with-tags-columns.md#manage-tags)。

1. 选择 **保存** 以创建细分。 **客户细分** 页将显示。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>后续步骤

[导出客户细分](export-destinations.md)和浏览 [Customer Card 集成](customer-card-add-in.md)，以便在其他应用程序中使用客户细分。

[!INCLUDE [footer-include](includes/footer-banner.md)]
