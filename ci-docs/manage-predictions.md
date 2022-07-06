---
title: 管理预测
description: 了解如何对预测进行管理、疑难解答和改进。
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a180f6462452d9830d0daa150a35a9d0acad925a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080933"
---
# <a name="manage-predictions"></a>管理预测

本文讨论了大多数预测方案都具有的某些任务。

## <a name="troubleshoot-a-failed-prediction"></a>解决失败的预测

1. 转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。

1. 选择要查看其错误日志的预测旁边的垂直省略号。

1. 选择 **日志**。

1. 查看所有错误。 可能会出现几种类型的错误，这些类型描述了导致错误的原因。 例如，因数据不足而无法准确预测的错误通常通过将其他数据加载到 Customer Insights 中来解决。

## <a name="input-data-usability-report"></a>输入数据可用性报表

输入数据可用性报告提供了现成预测可能会生成的错误和警告的综合视图。 它还就如何提高模型性能提出了建议。

该报表在模型完成训练过程后可用。 无论是否成功完成训练，都会单独为每个模型创建报表。

### <a name="view-the-input-data-usability-report"></a>查看输入数据可用性报表

现成模型完成其训练步骤后，请查看报表：
- 选择模型名称旁边的椭圆，然后选择 **输入数据可用性报表**。
- 选择模型的状态，然后在侧窗格中选择 **查看输入数据可用性报表**。
- 选择列表中的模型之一，并在命令栏中选择 **输入数据可用性报表**。
- 打开模型结果页面，并在命令栏中选择 **输入数据可用性报表**。

### <a name="information-in-the-input-data-usability-report"></a>输入数据可用性报表中的信息

报表中的以下列包含有用的信息，用于改进模型的数据。

:::image type="content" source="media/input-data-usability-report.png" alt-text="输入数据可用性报表的示例，其中显示了带有错误、警告和建议的表。":::

- **名称：** 错误、警告或建议的描述性名称。
- **步骤：** 信息所引用的模型阶段、训练或分数。
- **状态：** 信息的严重性（错误、警告、建议）。
- **列名称：** 需要修改以提高模型性能的实体中的列。
- **实体名称：** 需要修改以提高模型性能的实体的名称。
- **详细信息：** 有关错误、警告或建议的详细信息。

## <a name="refresh-a-prediction"></a>刷新预测

预测将按照设置中配置的相同[数据刷新计划](system.md#schedule-tab)自动刷新。 您也可以手动刷新它们。

1. 转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。

1. 选择要刷新的预测旁边的垂直省略号。

1. 选择 **刷新**。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>删除预测

删除预测还会删除其输出实体。

1. 转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。

1. 选择要删除的预测旁边的垂直省略号。

1. 选择 **删除**。
