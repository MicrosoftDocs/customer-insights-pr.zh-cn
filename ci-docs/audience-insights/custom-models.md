---
title: 自定义机器学习模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用来自 Azure 机器学习的自定义模型。
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668892"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="f2f02-103">自定义机器学习模型</span><span class="sxs-lookup"><span data-stu-id="f2f02-103">Custom machine learning models</span></span>

<span data-ttu-id="f2f02-104">**智能** > **自定义模型** 允许您基于 Azure 机器学习模型管理工作流。</span><span class="sxs-lookup"><span data-stu-id="f2f02-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="f2f02-105">工作流帮助您选择要从中生成见解的数据，并将结果映射到统一客户数据。</span><span class="sxs-lookup"><span data-stu-id="f2f02-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="f2f02-106">有关生成自定义 ML 模型的详细信息，请参阅[使用基于 Azure 机器学习的模型](azure-machine-learning-experiments.md)。</span><span class="sxs-lookup"><span data-stu-id="f2f02-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="f2f02-107">负责 AI</span><span class="sxs-lookup"><span data-stu-id="f2f02-107">Responsible AI</span></span>

<span data-ttu-id="f2f02-108">预测提供创建更好的客户体验、改进业务功能和创收流的功能。</span><span class="sxs-lookup"><span data-stu-id="f2f02-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="f2f02-109">强烈建议您在预测针对其影响的价值以及以道德方式引入的偏见之间进行权衡。</span><span class="sxs-lookup"><span data-stu-id="f2f02-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="f2f02-110">了解有关 Microsoft 如何[处理负责 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2f02-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="f2f02-111">您还可以了解特定于 Azure 机器学习的[负载机器学习的技术和流程](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml)。</span><span class="sxs-lookup"><span data-stu-id="f2f02-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f2f02-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="f2f02-112">Prerequisites</span></span>

- <span data-ttu-id="f2f02-113">当前，此功能支持通过[机器学习工作室（经典）](https://studio.azureml.net)和 [Azure 机器学习批处理管道](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines)发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="f2f02-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="f2f02-114">您需要与 Azure Studio 实例关联的 Azure Data Lake Gen2 存储帐户才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="f2f02-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="f2f02-115">有关详细信息，请参阅[创建 Azure Data Lake Storage Gen2 存储帐户](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="f2f02-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="f2f02-116">添加新工作流</span><span class="sxs-lookup"><span data-stu-id="f2f02-116">Add a new workflow</span></span>

1. <span data-ttu-id="f2f02-117">转到 **智能** > **自定义模型** 并选择 **新工作流**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="f2f02-118">在 **名称** 字段中为自定义模型指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="f2f02-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f2f02-119">![“新建工作流”窗格的屏幕截图](media/new-workflowv2.png "“新建工作流”窗格的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="f2f02-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="f2f02-120">在 **包含 Web 服务的租户** 中，选择包含 Web 服务的组织。</span><span class="sxs-lookup"><span data-stu-id="f2f02-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="f2f02-121">如果您的 Azure 机器学习订阅与 Customer Insights 在不同的租户中，请为所选组织选择使用您的凭据 **登录**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="f2f02-122">选择与您的 Web 服务相关联的 **工作区**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="f2f02-123">其中列出了两个部分，一个用于 Azure 机器学习 v1（机器学习工作室（经典）），另一个用于 Azure 机器学习 v2（Azure 机器学习）。</span><span class="sxs-lookup"><span data-stu-id="f2f02-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="f2f02-124">如果您不确定哪个工作区适合您的机器学习工作室（经典）Web 服务，请选择 **任意**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="f2f02-125">在 **包含您的模型的 Web 服务** 下拉菜单中选择机器学习工作室（经典）Web 服务或 Azure 机器学习管道。</span><span class="sxs-lookup"><span data-stu-id="f2f02-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="f2f02-126">然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="f2f02-127">了解有关[在机器学习工作室（经典）中发布 Web 服务](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)的详细信息</span><span class="sxs-lookup"><span data-stu-id="f2f02-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="f2f02-128">了解有关[使用设计器在 Azure 机器学习中发布管道](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)或使用 [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 进行发布的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2f02-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="f2f02-129">您的管道必须在[管道终结点](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)下发布。</span><span class="sxs-lookup"><span data-stu-id="f2f02-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="f2f02-130">对于每个 **Web 服务输入**，从访问群体见解中选择匹配的 **实体**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f2f02-131">![配置工作流](media/intelligence-screen2-updated.png "配置工作流")</span><span class="sxs-lookup"><span data-stu-id="f2f02-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="f2f02-132">在 **模型输出参数** 步骤中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f2f02-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="f2f02-133">机器学习工作室（经典）</span><span class="sxs-lookup"><span data-stu-id="f2f02-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="f2f02-134">输入您希望 Web 服务输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="f2f02-135">Azure 机器学习</span><span class="sxs-lookup"><span data-stu-id="f2f02-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="f2f02-136">输入您希望管道输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="f2f02-137">从下拉列表中选择批处理管道的 **输出数据存储参数名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="f2f02-138">从下拉列表中选择批处理管道的 **输出路径参数名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f2f02-139">![模型输出参数窗格](media/intelligence-screen3-outputparameters.png "模型输出参数窗格")</span><span class="sxs-lookup"><span data-stu-id="f2f02-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="f2f02-140">从 **结果中的客户 ID** 下拉列表中选择标识客户的匹配属性，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f2f02-141">![将结果与客户数据关联窗格](media/intelligence-screen4-relatetocustomer.png "将结果与客户数据关联窗格")</span><span class="sxs-lookup"><span data-stu-id="f2f02-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="f2f02-142">您将看到 **已保存工作流** 屏幕，其中包含有关工作流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2f02-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="f2f02-143">如果您为 Azure 机器学习管道配置了工作流，访问群体见解将附加到包含该管道的工作区。</span><span class="sxs-lookup"><span data-stu-id="f2f02-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="f2f02-144">访问群体见解将在 Azure 工作区上获取 **参与者** 角色。</span><span class="sxs-lookup"><span data-stu-id="f2f02-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="f2f02-145">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-145">Select **Done**.</span></span>

1. <span data-ttu-id="f2f02-146">现在，您可以从 **自定义模型** 页面运行工作流。</span><span class="sxs-lookup"><span data-stu-id="f2f02-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="f2f02-147">编辑工作流</span><span class="sxs-lookup"><span data-stu-id="f2f02-147">Edit a workflow</span></span>

1. <span data-ttu-id="f2f02-148">在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="f2f02-149">您可以在 **显示名称** 字段中更新工作流的可识别名称，但不能更改已配置的 Web 服务或管道。</span><span class="sxs-lookup"><span data-stu-id="f2f02-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="f2f02-150">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-150">Select **Next**.</span></span>

1. <span data-ttu-id="f2f02-151">对于每个 **Web 服务输入**，您可以从访问群体见解中更新匹配的 **实体**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="f2f02-152">然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="f2f02-153">在 **模型输出参数** 步骤中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f2f02-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="f2f02-154">机器学习工作室（经典）</span><span class="sxs-lookup"><span data-stu-id="f2f02-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="f2f02-155">输入您希望 Web 服务输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="f2f02-156">Azure 机器学习</span><span class="sxs-lookup"><span data-stu-id="f2f02-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="f2f02-157">输入您希望管道输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="f2f02-158">选择测试管道的 **输出数据存储参数名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="f2f02-159">选择测试管道的 **输出路径参数名称**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="f2f02-160">从 **结果中的客户 ID** 下拉列表中选择标识客户的匹配属性，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="f2f02-161">您需要从包含类似于客户实体的客户 ID 的值的推理输出中选择一个属性。</span><span class="sxs-lookup"><span data-stu-id="f2f02-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="f2f02-162">如果您的数据集中没有这样的列，请选择可唯一标识该行的属性。</span><span class="sxs-lookup"><span data-stu-id="f2f02-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="f2f02-163">运行工作流</span><span class="sxs-lookup"><span data-stu-id="f2f02-163">Run a workflow</span></span>

1. <span data-ttu-id="f2f02-164">在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="f2f02-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="f2f02-165">选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="f2f02-165">Select **Run**.</span></span>

<span data-ttu-id="f2f02-166">您的工作流也会在每次计划刷新后自动运行。</span><span class="sxs-lookup"><span data-stu-id="f2f02-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="f2f02-167">了解有关[设置计划刷新](system.md#schedule-tab)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2f02-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="f2f02-168">删除工作流</span><span class="sxs-lookup"><span data-stu-id="f2f02-168">Delete a workflow</span></span>

1. <span data-ttu-id="f2f02-169">在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="f2f02-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="f2f02-170">选择 **删除**，然后确认删除。</span><span class="sxs-lookup"><span data-stu-id="f2f02-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="f2f02-171">将删除您的工作流。</span><span class="sxs-lookup"><span data-stu-id="f2f02-171">Your workflow will be deleted.</span></span> <span data-ttu-id="f2f02-172">您创建工作流时创建的 [实体](entities.md)将保留，并且可以从 **实体** 页查看。</span><span class="sxs-lookup"><span data-stu-id="f2f02-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
