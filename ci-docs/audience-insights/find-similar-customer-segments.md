---
title: 使用 AI 寻找类似客户（视频）
description: 使用人工智能查找相似的客户细分。
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7999c4964773c3b5c49537027a2ed67f0ad57ec5
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903878"
---
# <a name="similar-customers-preview"></a>相似客户（预览）

此功能使您可以使用人工智能在客户群中查找相似客户。 您需要至少创建一个客户细分才能使用此功能。 扩展现有客户细分的条件可帮助查找与该客户细分相似的客户。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *查找相似客户* 使用自动方法评估数据并基于该数据作出预测，因此如一般数据保护条例 (“GDPR”) 所定义的术语，能够用作探查方法。 客户在使用此功能处理数据时，应该遵守 GDPR 或其他法律或法规。 您有责任确保在使用 Dynamics 365 Customer Insights（包括预测）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。

## <a name="finding-similar-customers"></a>查找相似客户

1. 在访问群体见解中，转到 **客户细分**，然后选择您希望新的客户细分所基于的客户细分。 即您的 *源客户细分*。

1. 在操作栏中，选择 **查找相似客户**。

1. 查看新客户细分的建议名称，并在必要时进行更改。

1. 查看定义新客户细分的字段。 这些字段定义系统尝试查找与您的源客户细分相似的客户所基于的基础。 默认情况下，系统会选择推荐的字段。
  可能会大大降低模型性能的字段会被自动排除：
  
   - 具有以下数据类型的字段：StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType
   - 基数（字段中的元素数）小于 2 或大于 30 的字段

1. 选择是要在新客户细分中包括 **所有客户** 还是仅包括 **特定现有客户细分** 中的客户。

1. 通过选中 **排除源客户细分中的所有人** 复选框，排除源客户细分中的客户。

1. 默认情况下，系统建议输出中仅包含目标访问群体人数的 20%。 根据需要编辑此阈值。 增加阈值会降低精度。

1. 选择页面底部的 **运行** 启动二元分类任务（一种机器学习方法），此任务将分析数据集。

## <a name="view-the-similar-segment"></a>查看相似客户细分

处理完相似客户细分后，您会在 **客户细分** 页面上找到列出的新客户细分。

> [!div class="mx-imgBorder"]
> ![相似客户细分。](media/expanded-segment.png "相似客户细分")

在操作栏中选择 **视图** 打开客户细分详细信息。 此视图包含有关[相似性分数](#about-similarity-scores)之间的结果分布的信息。 您还会在 **客户细分成员预览** 中找到相似性分数值。

## <a name="use-the-output-of-a-similar-segment"></a>使用相似客户细分的输出

您可以像处理其他客户细分一样[处理相似客户细分的输出](segments.md)。 例如，导出客户细分或生成度量值。

## <a name="refresh-and-edit-a-similar-segment"></a>刷新和编辑相似客户细分

要刷新相似客户细分，请在 **客户细分** 页面上将其选中，然后在操作栏中选择 **刷新**。

编辑相似客户细分将重新处理数据。 先前创建的客户细分将使用刷新的数据更新。    
要编辑相似客户细分，请在 **客户细分** 页面上将其选中，然后在操作栏中选择 **编辑**。 应用更改并选择 **运行** 开始处理。

## <a name="delete-a-similar-segment"></a>删除相似客户细分

在 **客户细分** 页面上选择客户细分，然后在操作栏中选择 **删除**。 然后，确认删除。

## <a name="about-similarity-scores"></a>关于相似性分数

二元分类机器学习模型为相似客户细分中的客户分配分数。 分数基于与源客户细分中客户的相似性。

- 低于 0.55 的相似性分数是系统分类为与源客户细分中的客户 *不相似* 的客户
- 0.55 – 0.7 之间的相似性分数分类为 *有些相似*
- 0.7 – 0.85 之间的相似性分数分类为 *相似*
- 0.85 – 1 之间的相似性分数是系统分类为 *非常相似* 的客户

模型输出中不包括相似性分数低于 0.4 的客户。 系统认为它们与源客户细分的相似度不够。


[!INCLUDE[footer-include](../includes/footer-banner.md)]