---
title: 自定义机器学习模型 | Microsoft Docs
description: 在 Dynamics 365 Customer Insights 中使用来自 Azure 机器学习的自定义模型。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700657"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="0d5ec-103">自定义机器学习模型</span><span class="sxs-lookup"><span data-stu-id="0d5ec-103">Custom machine learning models</span></span>

<span data-ttu-id="0d5ec-104">**智能** > **自定义模型** 允许您基于 Azure 机器学习模型管理工作流。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="0d5ec-105">工作流帮助您选择要从中生成见解的数据，并将结果映射到统一客户数据。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="0d5ec-106">有关生成自定义 ML 模型的详细信息，请参阅[使用基于 Azure 机器学习的模型](azure-machine-learning-experiments.md)。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="0d5ec-107">负责 AI</span><span class="sxs-lookup"><span data-stu-id="0d5ec-107">Responsible AI</span></span>

<span data-ttu-id="0d5ec-108">预测提供创建更好的客户体验、改进业务功能和创收流的功能。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="0d5ec-109">强烈建议您在预测针对其影响的价值以及以道德方式引入的偏见之间进行权衡。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="0d5ec-110">了解有关 Microsoft 如何[处理负责 AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="0d5ec-111">您还可以了解特定于 Azure 机器学习的[负载机器学习的技术和流程](/azure/machine-learning/concept-responsible-ml)。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d5ec-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="0d5ec-112">Prerequisites</span></span>

- <span data-ttu-id="0d5ec-113">当前，此功能支持通过[机器学习工作室（经典）](https://studio.azureml.net)和 [Azure 机器学习批处理管道](/azure/machine-learning/concept-ml-pipelines)发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="0d5ec-114">您需要与 Azure Studio 实例关联的 Azure Data Lake Gen2 存储帐户才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="0d5ec-115">有关详细信息，请参阅[创建 Azure Data Lake Storage Gen2 存储帐户](/azure/storage/blobs/data-lake-storage-quickstart-create-account)。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="0d5ec-116">对于具有管道的 Azure 机器学习工作区，您需要具有针对 Azure 机器学习工作区的负责人或用户访问管理员权限。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d5ec-117">数据是在 Customer Insights 实例和工作流中的所选 Azure Web 服务或管道之间传输的。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="0d5ec-118">将数据传输至 Azure 服务时，请确保服务已配置为按照所需的方式和位置处理数据，以符合组织数据的任何法律或法规要求。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="0d5ec-119">添加新工作流</span><span class="sxs-lookup"><span data-stu-id="0d5ec-119">Add a new workflow</span></span>

1. <span data-ttu-id="0d5ec-120">转到 **智能** > **自定义模型** 并选择 **新工作流**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="0d5ec-121">在 **名称** 字段中为自定义模型指定易于识别的名称。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d5ec-122">![“新建工作流”窗格的屏幕截图](media/new-workflowv2.png "“新建工作流”窗格的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="0d5ec-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="0d5ec-123">在 **包含 Web 服务的租户** 中，选择包含 Web 服务的组织。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="0d5ec-124">如果您的 Azure 机器学习订阅与 Customer Insights 在不同的租户中，请为所选组织选择使用您的凭据 **登录**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="0d5ec-125">选择与您的 Web 服务相关联的 **工作区**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="0d5ec-126">其中列出了两个部分，一个用于 Azure 机器学习 v1（机器学习工作室（经典）），另一个用于 Azure 机器学习 v2（Azure 机器学习）。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="0d5ec-127">如果您不确定哪个工作区适合您的机器学习工作室（经典）Web 服务，请选择 **任意**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="0d5ec-128">在 **包含您的模型的 Web 服务** 下拉菜单中选择机器学习工作室（经典）Web 服务或 Azure 机器学习管道。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="0d5ec-129">然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="0d5ec-130">了解有关[在机器学习工作室（经典）中发布 Web 服务](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)的详细信息</span><span class="sxs-lookup"><span data-stu-id="0d5ec-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="0d5ec-131">了解有关[使用设计器在 Azure 机器学习中发布管道](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)或使用 [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 进行发布的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="0d5ec-132">您的管道必须在[管道终结点](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)下发布。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="0d5ec-133">对于每个 **Web 服务输入**，从访问群体见解中选择匹配的 **实体**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0d5ec-134">自定义模型工作流将应用启发式方法，根据字段的名称和数据类型将 Web 服务输入字段映射到实体属性。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="0d5ec-135">如果 Web 服务字段无法映射到实体，将出现错误。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d5ec-136">![配置工作流](media/intelligence-screen2-updated.png "配置工作流")</span><span class="sxs-lookup"><span data-stu-id="0d5ec-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="0d5ec-137">在 **模型输出参数** 步骤中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="0d5ec-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="0d5ec-138">机器学习工作室（经典）</span><span class="sxs-lookup"><span data-stu-id="0d5ec-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="0d5ec-139">输入您希望 Web 服务输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="0d5ec-140">Azure 机器学习</span><span class="sxs-lookup"><span data-stu-id="0d5ec-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="0d5ec-141">输入您希望管道输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="0d5ec-142">从下拉列表中选择批处理管道的 **输出数据存储参数名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="0d5ec-143">从下拉列表中选择批处理管道的 **输出路径参数名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="0d5ec-144">![模型输出参数窗格](media/intelligence-screen3-outputparameters.png "模型输出参数窗格")</span><span class="sxs-lookup"><span data-stu-id="0d5ec-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="0d5ec-145">从 **结果中的客户 ID** 下拉列表中选择标识客户的匹配属性，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d5ec-146">![将结果与客户数据关联窗格](media/intelligence-screen4-relatetocustomer.png "将结果与客户数据关联窗格")</span><span class="sxs-lookup"><span data-stu-id="0d5ec-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="0d5ec-147">您将看到 **已保存工作流** 屏幕，其中包含有关工作流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="0d5ec-148">如果您为 Azure 机器学习管道配置了工作流，访问群体见解将附加到包含该管道的工作区。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="0d5ec-149">访问群体见解将在 Azure 工作区上获取 **参与者** 角色。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="0d5ec-150">选择 **完成**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-150">Select **Done**.</span></span>

1. <span data-ttu-id="0d5ec-151">现在，您可以从 **自定义模型** 页面运行工作流。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="0d5ec-152">编辑工作流</span><span class="sxs-lookup"><span data-stu-id="0d5ec-152">Edit a workflow</span></span>

1. <span data-ttu-id="0d5ec-153">在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="0d5ec-154">您可以在 **显示名称** 字段中更新工作流的可识别名称，但不能更改已配置的 Web 服务或管道。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="0d5ec-155">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-155">Select **Next**.</span></span>

1. <span data-ttu-id="0d5ec-156">对于每个 **Web 服务输入**，您可以从访问群体见解中更新匹配的 **实体**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="0d5ec-157">然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="0d5ec-158">在 **模型输出参数** 步骤中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="0d5ec-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="0d5ec-159">机器学习工作室（经典）</span><span class="sxs-lookup"><span data-stu-id="0d5ec-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="0d5ec-160">输入您希望 Web 服务输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="0d5ec-161">Azure 机器学习</span><span class="sxs-lookup"><span data-stu-id="0d5ec-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="0d5ec-162">输入您希望管道输出结果流入的输出 **实体名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="0d5ec-163">选择测试管道的 **输出数据存储参数名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="0d5ec-164">选择测试管道的 **输出路径参数名称**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="0d5ec-165">从 **结果中的客户 ID** 下拉列表中选择标识客户的匹配属性，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="0d5ec-166">从包含类似于客户实体的客户 ID 列的值的推理输出中选择一个属性。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="0d5ec-167">如果您的数据集中没有这样的列，请选择可唯一标识该行的属性。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="0d5ec-168">运行工作流</span><span class="sxs-lookup"><span data-stu-id="0d5ec-168">Run a workflow</span></span>

1. <span data-ttu-id="0d5ec-169">在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="0d5ec-170">选择 **运行**。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-170">Select **Run**.</span></span>

<span data-ttu-id="0d5ec-171">您的工作流也会在每次计划刷新后自动运行。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="0d5ec-172">了解有关[设置计划刷新](system.md#schedule-tab)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="0d5ec-173">删除工作流</span><span class="sxs-lookup"><span data-stu-id="0d5ec-173">Delete a workflow</span></span>

1. <span data-ttu-id="0d5ec-174">在 **自定义模型** 页中，选择之前创建的工作流旁边 **操作** 列内的垂直省略号。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="0d5ec-175">选择 **删除**，然后确认删除。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="0d5ec-176">将删除您的工作流。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-176">Your workflow will be deleted.</span></span> <span data-ttu-id="0d5ec-177">您创建工作流时创建的 [实体](entities.md)将保留，并且可以从 **实体** 页查看。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="0d5ec-178">结果​​</span><span class="sxs-lookup"><span data-stu-id="0d5ec-178">Results</span></span>

<span data-ttu-id="0d5ec-179">工作流的结果存储在模型输出参数阶段中配置的实体中。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="0d5ec-180">您可以通过[实体页](entities.md)或 [API 访问](apis.md)来访问此数据。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="0d5ec-181">API 访问</span><span class="sxs-lookup"><span data-stu-id="0d5ec-181">API Access</span></span>

<span data-ttu-id="0d5ec-182">对于从自定义模型实体获取数据的特定 OData 查询，请使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="0d5ec-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="0d5ec-183">将 `<your instance id>` 替换为您的 Customer Insights 环境的 ID，该 ID 可在访问 Customer Insights 时在浏览器的地址栏中找到。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="0d5ec-184">用您在此自定义模型配置的“模型输出参数”步骤中提供的实体名称替换 `<custom model output entity>`。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="0d5ec-185">用要访问其记录的客户的客户 ID 替换 `<guid value>`。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="0d5ec-186">通常可在[客户配置文件页](customer-profiles.md)上的 CustomerID 字段中找到此 ID。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="0d5ec-187">常见问题</span><span class="sxs-lookup"><span data-stu-id="0d5ec-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="0d5ec-188">为什么在设置自定义模型工作流时看不到我的管道？</span><span class="sxs-lookup"><span data-stu-id="0d5ec-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="0d5ec-189">此问题通常由于管道中的配置问题所导致。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="0d5ec-190">确保[配置了输入参数](azure-machine-learning-experiments.md#dataset-configuration)，并且还配置了[输出数据存储和路径参数](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights)。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="0d5ec-191">“无法保存智能工作流”错误是什么意思？</span><span class="sxs-lookup"><span data-stu-id="0d5ec-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="0d5ec-192">如果用户对工作区没有“负责人”或“用户访问管理员”特权，则通常会看到此错误消息。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="0d5ec-193">用户需要更高级别的权限才能使 Customer Insights 能够将工作流作为服务处理，而非使用用户凭据处理工作流的后续运行。</span><span class="sxs-lookup"><span data-stu-id="0d5ec-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
