---
title: 使用 AI 查找相似客户
description: 使用人工智能查找相似的客户细分。
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405212"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="13816-103">相似客户（预览）</span><span class="sxs-lookup"><span data-stu-id="13816-103">Similar Customers (preview)</span></span>

<span data-ttu-id="13816-104">此功能使您可以使用人工智能在客户群中查找相似客户。</span><span class="sxs-lookup"><span data-stu-id="13816-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="13816-105">您需要至少创建一个客户细分才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="13816-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="13816-106">扩展现有客户细分的条件可帮助查找与该客户细分相似的客户。</span><span class="sxs-lookup"><span data-stu-id="13816-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="13816-107">*查找相似客户* 使用自动方法评估数据并基于该数据作出预测，因此如一般数据保护条例 (“GDPR”) 所定义的术语，能够用作探查方法。</span><span class="sxs-lookup"><span data-stu-id="13816-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="13816-108">客户在使用此功能处理数据时，应该遵守 GDPR 或其他法律或法规。</span><span class="sxs-lookup"><span data-stu-id="13816-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="13816-109">您有责任确保在使用 Dynamics 365 Customer Insights（包括预测）时遵守所有适用的法律和法规，包括与隐私、个人数据、生物特征数据、数据保护和通信保密相关的法律。</span><span class="sxs-lookup"><span data-stu-id="13816-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="13816-110">查找相似客户</span><span class="sxs-lookup"><span data-stu-id="13816-110">Finding similar customers</span></span>

1. <span data-ttu-id="13816-111">在访问群体见解中，转到 **客户细分**，然后选择您希望新的客户细分所基于的客户细分。</span><span class="sxs-lookup"><span data-stu-id="13816-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="13816-112">即您的 *源客户细分*。</span><span class="sxs-lookup"><span data-stu-id="13816-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="13816-113">在操作栏中，选择 **查找相似客户**。</span><span class="sxs-lookup"><span data-stu-id="13816-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="13816-114">查看新客户细分的建议名称，并在必要时进行更改。</span><span class="sxs-lookup"><span data-stu-id="13816-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="13816-115">查看定义新客户细分的字段。</span><span class="sxs-lookup"><span data-stu-id="13816-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="13816-116">这些字段定义系统尝试查找与您的源客户细分相似的客户所基于的基础。</span><span class="sxs-lookup"><span data-stu-id="13816-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="13816-117">默认情况下，系统会选择推荐的字段。</span><span class="sxs-lookup"><span data-stu-id="13816-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="13816-118">可能会大大降低模型性能的字段会被自动排除：</span><span class="sxs-lookup"><span data-stu-id="13816-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="13816-119">具有以下数据类型的字段：StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType</span><span class="sxs-lookup"><span data-stu-id="13816-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="13816-120">基数（字段中的元素数）小于 2 或大于 30 的字段</span><span class="sxs-lookup"><span data-stu-id="13816-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="13816-121">选择是要在新客户细分中包括 **所有客户** 还是仅包括 **特定现有客户细分** 中的客户。</span><span class="sxs-lookup"><span data-stu-id="13816-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="13816-122">通过选中 **排除源客户细分中的所有人** 复选框，排除源客户细分中的客户。</span><span class="sxs-lookup"><span data-stu-id="13816-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="13816-123">默认情况下，系统建议输出中仅包含目标访问群体人数的 20%。</span><span class="sxs-lookup"><span data-stu-id="13816-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="13816-124">根据需要编辑此阈值。</span><span class="sxs-lookup"><span data-stu-id="13816-124">Edit this threshold as needed.</span></span> <span data-ttu-id="13816-125">增加阈值会降低精度。</span><span class="sxs-lookup"><span data-stu-id="13816-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="13816-126">选择页面底部的 **运行** 启动二元分类任务（一种机器学习方法），此任务将分析数据集。</span><span class="sxs-lookup"><span data-stu-id="13816-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="13816-127">查看相似客户细分</span><span class="sxs-lookup"><span data-stu-id="13816-127">View the similar segment</span></span>

<span data-ttu-id="13816-128">处理完相似客户细分后，您会在 **客户细分** 页面上找到列出的新客户细分。</span><span class="sxs-lookup"><span data-stu-id="13816-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="13816-129">![相似客户细分](media/expanded-segment.png "相似客户细分")</span><span class="sxs-lookup"><span data-stu-id="13816-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="13816-130">在操作栏中选择 **视图** 打开客户细分详细信息。</span><span class="sxs-lookup"><span data-stu-id="13816-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="13816-131">此视图包含有关[相似性分数](#about-similarity-scores)之间的结果分布的信息。</span><span class="sxs-lookup"><span data-stu-id="13816-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="13816-132">您还会在 **客户细分成员预览** 中找到相似性分数值。</span><span class="sxs-lookup"><span data-stu-id="13816-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="13816-133">使用相似客户细分的输出</span><span class="sxs-lookup"><span data-stu-id="13816-133">Use the output of a similar segment</span></span>

<span data-ttu-id="13816-134">您可以像处理其他客户细分一样[处理相似客户细分的输出](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="13816-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="13816-135">例如，导出客户细分或生成度量值。</span><span class="sxs-lookup"><span data-stu-id="13816-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="13816-136">刷新和编辑相似客户细分</span><span class="sxs-lookup"><span data-stu-id="13816-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="13816-137">要刷新相似客户细分，请在 **客户细分** 页面上将其选中，然后在操作栏中选择 **刷新**。</span><span class="sxs-lookup"><span data-stu-id="13816-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="13816-138">编辑相似客户细分将重新处理数据。</span><span class="sxs-lookup"><span data-stu-id="13816-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="13816-139">先前创建的客户细分将使用刷新的数据更新。</span><span class="sxs-lookup"><span data-stu-id="13816-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="13816-140">要编辑相似客户细分，请在 **客户细分** 页面上将其选中，然后在操作栏中选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="13816-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="13816-141">应用更改并选择 **运行** 开始处理。</span><span class="sxs-lookup"><span data-stu-id="13816-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="13816-142">删除相似客户细分</span><span class="sxs-lookup"><span data-stu-id="13816-142">Delete a similar segment</span></span>

<span data-ttu-id="13816-143">在 **客户细分** 页面上选择客户细分，然后在操作栏中选择 **删除**。</span><span class="sxs-lookup"><span data-stu-id="13816-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="13816-144">然后，确认删除。</span><span class="sxs-lookup"><span data-stu-id="13816-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="13816-145">关于相似性分数</span><span class="sxs-lookup"><span data-stu-id="13816-145">About similarity scores</span></span>

<span data-ttu-id="13816-146">二元分类机器学习模型为相似客户细分中的客户分配分数。</span><span class="sxs-lookup"><span data-stu-id="13816-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="13816-147">分数基于与源客户细分中客户的相似性。</span><span class="sxs-lookup"><span data-stu-id="13816-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="13816-148">低于 0.55 的相似性分数是系统分类为与源客户细分中的客户 *不相似* 的客户</span><span class="sxs-lookup"><span data-stu-id="13816-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="13816-149">0.55 – 0.7 之间的相似性分数分类为 *有些相似*</span><span class="sxs-lookup"><span data-stu-id="13816-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="13816-150">0.7 – 0.85 之间的相似性分数分类为 *相似*</span><span class="sxs-lookup"><span data-stu-id="13816-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="13816-151">0.85 – 1 之间的相似性分数是系统分类为 *非常相似* 的客户</span><span class="sxs-lookup"><span data-stu-id="13816-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="13816-152">模型输出中不包括相似性分数低于 0.4 的客户。</span><span class="sxs-lookup"><span data-stu-id="13816-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="13816-153">系统认为它们与源客户细分的相似度不够。</span><span class="sxs-lookup"><span data-stu-id="13816-153">The system doesn't consider them similar enough to the source segment.</span></span>
