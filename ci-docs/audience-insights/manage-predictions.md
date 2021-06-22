---
title: 预测方案的共享任务
description: 了解如何对预测进行管理、疑难解答和改进。
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095690"
---
# <a name="manage-predictions"></a><span data-ttu-id="4acdb-103">管理预测</span><span class="sxs-lookup"><span data-stu-id="4acdb-103">Manage predictions</span></span>

<span data-ttu-id="4acdb-104">本文讨论了大多数预测方案都具有的某些任务。</span><span class="sxs-lookup"><span data-stu-id="4acdb-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="4acdb-105">解决失败的预测</span><span class="sxs-lookup"><span data-stu-id="4acdb-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="4acdb-106">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4acdb-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4acdb-107">选择要查看其错误日志的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="4acdb-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="4acdb-108">选择 **日志**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-108">Select **Logs**.</span></span>

1. <span data-ttu-id="4acdb-109">查看所有错误。</span><span class="sxs-lookup"><span data-stu-id="4acdb-109">Review all the errors.</span></span> <span data-ttu-id="4acdb-110">可能会出现几种类型的错误，这些类型描述了导致错误的原因。</span><span class="sxs-lookup"><span data-stu-id="4acdb-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="4acdb-111">例如，因数据不足而无法准确预测的错误通常通过将其他数据加载到 Customer Insights 中来解决。</span><span class="sxs-lookup"><span data-stu-id="4acdb-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="4acdb-112">输入数据可用性报表</span><span class="sxs-lookup"><span data-stu-id="4acdb-112">Input data usability report</span></span>

<span data-ttu-id="4acdb-113">输入数据可用性报告提供了现成预测可能会生成的错误和警告的综合视图。</span><span class="sxs-lookup"><span data-stu-id="4acdb-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="4acdb-114">它还就如何提高模型性能提出了建议。</span><span class="sxs-lookup"><span data-stu-id="4acdb-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="4acdb-115">该报表在模型完成训练过程后可用。</span><span class="sxs-lookup"><span data-stu-id="4acdb-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="4acdb-116">无论是否成功完成训练，都会单独为每个模型创建报表。</span><span class="sxs-lookup"><span data-stu-id="4acdb-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="4acdb-117">目前，此功能仅适用于交易流失模型。</span><span class="sxs-lookup"><span data-stu-id="4acdb-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="4acdb-118">查看输入数据可用性报表</span><span class="sxs-lookup"><span data-stu-id="4acdb-118">View the input data usability report</span></span>

<span data-ttu-id="4acdb-119">现成模型完成其训练步骤后，请查看报表：</span><span class="sxs-lookup"><span data-stu-id="4acdb-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="4acdb-120">选择模型名称旁边的椭圆，然后选择 **输入数据可用性报表**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="4acdb-121">选择模型的状态，然后在侧窗格中选择 **查看输入数据可用性报表**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="4acdb-122">选择列表中的模型之一，并在命令栏中选择 **输入数据可用性报表**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="4acdb-123">打开模型结果页面，并在命令栏中选择 **输入数据可用性报表**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="4acdb-124">输入数据可用性报表中的信息</span><span class="sxs-lookup"><span data-stu-id="4acdb-124">Information in the input data usability report</span></span>

<span data-ttu-id="4acdb-125">报表中的以下列包含有用的信息，用于改进模型的数据。</span><span class="sxs-lookup"><span data-stu-id="4acdb-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="输入数据可用性报表的示例，其中显示了带有错误、警告和建议的表。":::

- <span data-ttu-id="4acdb-127">名称：错误、警告或建议的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4acdb-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="4acdb-128">步骤：信息所引用的模型阶段、训练或分数。</span><span class="sxs-lookup"><span data-stu-id="4acdb-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="4acdb-129">状态：信息的严重性（错误、警告、建议）。</span><span class="sxs-lookup"><span data-stu-id="4acdb-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="4acdb-130">列名称：需要修改以提高模型性能的实体中的列。</span><span class="sxs-lookup"><span data-stu-id="4acdb-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="4acdb-131">实体名称：需要修改以提高模型性能的实体的名称。</span><span class="sxs-lookup"><span data-stu-id="4acdb-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="4acdb-132">详细信息：有关错误、警告或建议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4acdb-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="4acdb-133">刷新预测</span><span class="sxs-lookup"><span data-stu-id="4acdb-133">Refresh a prediction</span></span>

<span data-ttu-id="4acdb-134">预测将按照设置中配置的相同[数据刷新计划](system.md#schedule-tab)自动刷新。</span><span class="sxs-lookup"><span data-stu-id="4acdb-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="4acdb-135">您也可以手动刷新它们。</span><span class="sxs-lookup"><span data-stu-id="4acdb-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="4acdb-136">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4acdb-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4acdb-137">选择要刷新的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="4acdb-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="4acdb-138">选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="4acdb-139">删除预测</span><span class="sxs-lookup"><span data-stu-id="4acdb-139">Delete a prediction</span></span>

<span data-ttu-id="4acdb-140">删除预测还会删除其输出实体。</span><span class="sxs-lookup"><span data-stu-id="4acdb-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="4acdb-141">转到 **智能** > **预测**，然后选择 **我的预测** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4acdb-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4acdb-142">选择要删除的预测旁边的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="4acdb-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="4acdb-143">选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="4acdb-143">Select **Delete**.</span></span>
