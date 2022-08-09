---
title: 使用 AI 寻找类似客户（预览版）（包含视频）
description: 使用人工智能查找相似的客户细分。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170716"
---
# <a name="find-similar-customers-with-ai-preview"></a>使用 AI 寻找类似客户（预览版）

使用人工智能在您的客户群中查找相似客户。 您需要至少创建一个客户细分才能使用此功能。 扩展现有客户细分的条件可帮助查找与该客户细分相似的客户。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *查找相似客户* 使用自动化方法评估数据，然后根据这些数据作出预测。 因此，它能够用作分析方法，因为该术语由一般数据保护条例 (“GDPR”) 定义。 客户在使用此功能处理数据时，应该遵守 GDPR 或其他法律或法规。 您有责任确保在使用 Dynamics 365 Customer Insights（包括预测）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。

## <a name="find-similar-customers"></a>查找相似客户

1. 转到 **客户细分**，选择新客户细分所基于的客户细分。 即您的 *源客户细分*。

1. 选择 **查找相似客户**。

1. 查看新客户细分的建议名称，并在必要时进行更改。

1. 或者，也可以向新客户细分添加[标记](work-with-tags-columns.md#manage-tags)。

1. 查看定义新客户细分的字段。 这些字段定义系统尝试查找与您的源客户细分相似的客户所基于的基础。 默认情况下，系统会选择推荐的字段。 如果需要，添加更多字段。
  可能会大大降低模型性能的字段会被自动排除：
  
   - 具有以下数据类型的字段：StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType
   - 基数（字段中的元素数）小于 2 或大于 30 的字段

1. 选择是要在新客户细分中包括除源客户细分以外的 **所有客户**，还是仅包括 **其他客户细分** 中的客户。

1. 默认情况下，系统建议输出中仅包含目标访问群体人数的 20%。 根据需要编辑此阈值。 增加阈值会降低精度。

1. 通过选中 **包括来源客户细分中的成员以及具有相似属性的客户** 复选框，来包括来源客户细分中的客户。

1. 选择页面底部的 **运行** 启动[二元分类任务](#about-similarity-scores)（一种机器学习方法），此任务将分析数据集。

## <a name="view-the-similar-segment"></a>查看相似客户细分

处理完相似客户细分后，您会在 **客户细分** 页面上找到列出的新客户细分，类型为 **扩展**。

选择 **视图** 在 **客户细分成员预览** 下查看[相似性分数](#about-similarity-scores)和相似性分数值的结果分布。

:::image type="content" source="media/expanded-segment.png" alt-text="相似客户细分。":::

## <a name="manage-a-similar-segment"></a>管理相似客户细分

像处理其他客户细分一样[处理和管理相似客户细分](segments.md#manage-existing-segments)。 例如，导出客户细分或生成度量值。

编辑、刷新、重命名、下载和删除相似客户细分。 编辑相似客户细分将重新处理数据。 先前创建的客户细分将使用刷新的数据更新。

## <a name="about-similarity-scores"></a>关于相似性分数

二元分类机器学习模型为相似客户细分中的客户分配分数。 分数基于与源客户细分中客户的相似性。

- 低于 0.55 的相似性分数是系统分类为与源客户细分中的客户 *不相似* 的客户
- 0.55 – 0.7 之间的相似性分数分类为 *有些相似*
- 0.7 – 0.85 之间的相似性分数分类为 *相似*
- 0.85 – 1 之间的相似性分数是系统分类为 *非常相似* 的客户

模型输出中不包括相似性分数低于 0.4 的客户。 系统认为它们与源客户细分的相似度不够。

[!INCLUDE [footer-include](includes/footer-banner.md)]
