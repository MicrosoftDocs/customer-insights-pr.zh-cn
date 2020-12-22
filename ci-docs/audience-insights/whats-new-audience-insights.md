---
title: 新功能和未来的功能
description: 有关新功能、改进和 Bug 修复的信息。
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2020
ms.locfileid: "4649993"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的访问群体见解功能中的新增功能

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

我们非常激动地发布我们的最新更新！ 本文总结了公开预览功能、正式发布版本的增强和功能更新。 若要查看长期功能计划，请参阅 [Dynamics 365 和 Power Platform 发行计划](https://docs.microsoft.com/dynamics365/release-plans/)。

您还可以观看以下视频，以了解有关最近六个月的计划功能的详细信息。

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

我们将按地区推出更新。 因此，某些地区可能先于其他地区看到功能。 除非另行指定，否则您无需执行任何操作，我们会自动更新应用，无需停机。

> [!TIP]
> 若要提交功能请求和产品建议及投票，请访问 [Dynamics 365 应用程序意见门户](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。

## <a name="november-2020-updates"></a>2020 年 11 月更新

2020 年 11 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-november-2020"></a>2020 年 11 月的新功能和更新功能

#### <a name="data-enrichment"></a>数据扩充

- **通过安全文件传输协议 (SFTP) 自定义导入引入您自己的扩充数据**
  
  通过 SFTP 自定义导入，您可以导入不需要完成数据统一流程的扩充数据。 了解有关 SFTP 自定义导入的详细信息。

  有关详细信息，请参阅[使用自定义数据扩充客户配置文件（预览）](enrichment-SFTP-custom-import.md)。
 
- **使用来自 HERE Technologies 的位置数据扩充客户数据**

  通过 HERE Technologies 的数据扩充服务，您可以使用地址标准化、维度和精度提取等来更准确地了解客户的位置信息。 了解有关使用 HERE Technologies 扩充的详细信息。

  有关详细信息，请参阅[使用 HERE Technologies 扩充客户配置文件](enrichment-here.md)。

#### <a name="data-unification"></a>数据统一

- **允许对从存储帐户中选择的实体和字段进行数据分析的灵活性**

  您可以指示在您的 Azure Data Lake 存储帐户中您想要对 Common Data Model 文件夹中的哪些数据实体和字段启用数据分析作为数据引入流程的一部分。

  有关详细信息，请参阅[连接到 Common Data Model 文件夹](connect-common-data-model.md#connect-to-a-common-data-model-folder)。

#### <a name="extensibility"></a>扩展性

- **通过 Google Ads 激活您的客户细分**

  将客户细分导出到 Google Ads 访问群体列表，并使用这些列表在 Google Search、Google Display Network、YouTube 和 Gmail 上投放广告。 了解有关通过 Google Ads 激活您的客户细分的详细信息。

  有关详细信息，请参阅[用于 Google Ads 的连接器](export-google-ads.md)。

- **通过 Marketo 激活您的客户细分**

  将客户细分导出到 Marketo 访问群体，并将这些访问群体用于市场营销自动化。 了解有关通过 Marketo 激活您的客户细分的详细信息。 

  有关详细信息，请参阅[用于 Marketo 的连接器](export-marketo.md)。

- **通过 DotDigital 激活您的客户细分**

  将客户细分导出到 DotDigital，并将其用于市场营销目的。 了解有关通过 DotDigital 激活您的客户细分的详细信息。 

  有关详细信息，请参阅[用于 DotDigital 的连接器](export-dotdigital.md)。

#### <a name="predictions"></a>预测

- **预测交易流失**

  通过交易流失预测功能，您可以在没有数据科学家帮助的情况下，预测客户停止购买产品或服务的可能性。  使用预测分数，您可以合并有关客户的其他信息（例如客户价值），以创建高流失风险或高价值客户的客户细分。 使用此客户细分以通过市场营销活动、客户支持和其他方案直接面向客户，以降低流失风险。
 
  将流失定义配置为特定于业务的基于时间的时间范围，并定义何时将客户视为已流失。 例如，如果客户在过去 30 天内未购买任何商品，杂货店可能想要将该客户视为已流失。
 
  在继续创建预测时，我们将指导您需要哪些数据，并允许您将业务数据映射到预测客户流失所需的字段。 您还可以根据系统中的新信息设置计划以对模型进行重新定型，从而适应不断变化的业务环境。
 
  有关详细信息，请参阅[交易流失预测（预览）](predict-transactional-churn.md)。

#### <a name="system-administration"></a>系统管理

- **重置环境**

  将所选实例的环境中的所有内容重置为全新。

  有关详细信息，请参阅[重置现有环境](manage-environments.md#reset-an-existing-environment)。


- **使用服务主体连接到 Azure Data Lake 存储帐户**

  使用 Azure 服务主体将数据输出写入存储帐户并从中读取数据。 现有存储帐户连接可以继续使用帐户密钥。 它们还提供一个升级选项，以在继续操作时使用服务主体。 新连接将基于您的存储帐户的服务主体身份验证方法。

  有关详细信息，请参阅[针对访问群体见解使用 Azure 服务主体连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。

## <a name="october-2020-updates"></a>2020 年 10 月更新

2020 年 10 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-october-2020"></a>2020 年 10 月的新功能和更新功能

#### <a name="extensibility"></a>扩展性

- **导出到 Mailchimp**

将客户细分导出到 Mailchimp 中的现有访问群体列表，以为您的客户提供个性化的电子邮件体验。

有关详细信息，请参阅[用于 Mailchimp 的连接器](export-mailchimp.md)。

#### <a name="data-enrichment"></a>数据扩充

- **对匹配实体中的源记录执行删除重复**

针对匹配流程中使用的实体指定删除重复以标识重复的记录。 将它们合并在一个记录中，并将所有源记录链接到该合并的记录。 然后，将在跨实体匹配流程中使用此经过删除重复的记录。

有关详细信息，请参阅[在匹配实体上定义删除重复](match-entities.md#define-deduplication-on-a-match-entity)。

#### <a name="system-administration"></a>系统管理

- **业务流程：合并中的新刷新选项**

在此之前，当您运行合并流程时，系统运行的是依赖于合并和后续流程的所有下游流程。 现在，您可以验证合并流程的输出（统一的客户实体），然后在下游流程（例如客户细分或度量）中使用它。
在合并页面上，您现在可以选择仅运行合并步骤并仅运行此流程。 若要还刷新所有下游流程，您可以选择运行合并和下游流程。 

## <a name="september-2020-updates"></a>2020 年 9 月更新

2020 年 9 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-september-2020"></a>2020 年 9 月的新增功能和更新功能

#### <a name="activities"></a>活动

- **属性语义的智能预测**

此新功能预测传递到数据统一过程的输入属性的语义类型。 它使用可提高准确性和节省时间的机器学习模型。

#### <a name="enrichments"></a>扩充

- **Experian 的人口统计数据扩充**

Experian 的人口统计数据扩充现在可以预览。 Experian 是消费者和企业信用报告以及营销服务的全球领导者。 借助 [Experian 的数据扩充服务](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)，您可以通过人口统计数据（如家庭人数、收入等）扩充客户配置文件，从而加深对客户的了解。

若要使用此功能，必须有有效的 Experian 订阅。

有关详细信息，请参阅[使用来自 Experian 的人口统计数据扩充客户配置文件](enrichment-experian.md)


#### <a name="system-administration"></a>系统管理

- **任务详细信息窗格**

任务详细信息窗格可让您查看系统运行的任务的详细信息。 通过这种方式，可以轻松发现配置存在的问题并找到解决方案。
查看错误消息，了解如何解决潜在问题。
 
- **处理添加到其他页面的信息**

此改进在 **实体** 和 **客户** 页上添加了有关实体状态的信息。
 
此外，您还可以在这两个页面上找到有关流程进度的详细信息以及任务详细信息。

- **系统状态页的改进**

我们改进了查看数据导出时，**系统** > **状态** 上状态详细信息表的结构。
 
此外，**详细信息** 列中的错误现在更详细，更具可操作性。 
 
- **“取消”将作业还原到之前状态**

当您取消某个任务时（例如，在匹配过程中），它将还原到最新状态。 例如，如果匹配过程在昨天完成，您在今天将其取消，它会还原到昨天的成功状态。


## <a name="august-2020-updates"></a>2020 年 8 月更新

2020 年 8 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-august-2020"></a>2020 年 8 月的新增功能和更新功能

#### <a name="data-unification"></a>数据统一

- **改进了数据统一过程中映射阶段的体验**

  利用数据统一过程中映射阶段的体验，您可以以更加无缝的方式选择实体、属性和定义语义。

  这些更改包括：
  
  - 添加实体和字段所需的交互更少
  - 改进了映射页上的搜索功能
  - 可以轻松直观地识别建议的字段类型

#### <a name="enrichment"></a>扩充

- **兴趣相似性扩充在其他市场提供**

  我们正在将兴趣相似性扩充的使用扩大到美国以外的五个市场：加拿大、澳大利亚、英国、法国和德国。 扩大范围后，您可以使用适用于这些市场的其他兴趣来扩充您的客户数据。 我们还将使用来自 Microsoft Graph 的本地专有数据来扩充您在这些市场中的客户资料。
  有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>2020 年 7 月更新

2020 年 7 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-july-2020"></a>2020 年 7 月的新增功能和更新功能

#### <a name="extensibility"></a>扩展性

- **Power Automate 已完成统一过程触发器**

  我们扩展了 Power Automate 的触发器，允许您在统一过程（映射、匹配、合并）的刷新完成时创建通知或操作。    
  有关详细信息，请参阅 [Power Automate 连接器](export-power-automate.md)

#### <a name="enrichment"></a>扩充

- **在其他市场提供品牌相似扩充**

  我们正在将品牌相似性扩充扩展到美国以外的其他五个市场：加拿大、澳大利亚、英国、法国和德国。 通过此扩展，您可以利用这些市场的本地品牌来扩充您的客户数据。 我们还将使用来自 Microsoft Graph 的本地专有数据来扩充您在这些市场中的客户资料。
  有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>2020 年 6 月更新

2020 年 6 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-june-2020"></a>2020 年 6 月的新增功能和更新功能

#### <a name="enrichment"></a>扩充

- **使用来自 Leadspace 的公司数据扩充**
  
  在统一客户资料中定义用于从 Leadspace 查找相关公司数据的字段。 在运行扩充流程之后，B2B 资料将使用其他属性扩充，包括公司规模、位置、行业等。    
  通过这种协作，您可以利用第三方服务的输入来提高数据质量。 要使用此扩充，您需要获得 Leadspace 的许可证来访问其 B2B 公司数据。 系统将使用该许可证以使您的数据持续扩充。    
  有关详细信息，请参阅[利用 Leadspace 扩充公司资料](enrichment-leadspace.md)。

- **扩充中心页面**

  来自第一方和第三方扩充提供商的所有可用数据扩充都在同一位置进行配置。 配置数据扩充是一种无缝体验，从一个公共位置进行管理。    
  有关详细信息，请参阅[客户资料扩充](enrichment-hub.md)。

- **拆分品牌和兴趣相似性扩充**

  品牌和兴趣相似性现在可以作为两个独立扩充提供。 拆分的扩充使您可以根据业务要求或需求灵活地单独进行配置和管理。    
  有关详细信息，请参阅[利用品牌和兴趣相似性扩充客户资料](enrichment-microsoft-graph.md)。

#### <a name="extensibility"></a>扩展性

- **Dynamics 365 客户卡加载项上统一活动的可点击 URL**

  客户卡加载项中的统一活动现在显示可单击的 URL，前提是已在配置活动期间定义此类 URL。    
  有关详细信息，请参阅[客户卡加载项](customer-card-add-in.md)。

- **Dynamics 365 客户卡加载项上提供品牌和兴趣相似性**

  使用 Dynamics 365 客户卡加载项上的新控件，您可以在 Dynamics 365 中客户互动应用中的联系人上显示品牌和兴趣扩充。    
  有关详细信息，请参阅[客户卡加载项](customer-card-add-in.md)。

- **其他 Power Automate 触发器**

  我们扩展了 Power Automate 的触发器，增加了以下触发器：
  - 在自动完全刷新（数据源、统一、客户细分、度量、导出）完成时，获取通知或执行操作
  - 为业务度量定义阈值。 例如，您可以创建一个在超过定义的阈值时发送的通知。 此外，触发器还带来了一些信息，使您可以在 Power Automate 中构建更复杂的工作流。    
  有关详细信息，请参阅 [Power Automate 连接器](export-power-automate.md)

- **导出到 Facebook 广告管理器**
  
  此功能允许您将客户细分导出到 Facebook Ads Manager。 在 Facebook 市场营销活动和广告中，客户细分将导出为客户访问群体以使用统一的客户配置文件。 自定义受众也可用于通过 Facebook 广告管理器在 Instagram 上创建市场活动。    
  有关详细信息，请参阅 [Facebook 广告管理器的连接器](export-facebook.md)。

#### <a name="predictions"></a>预测

- **订阅流失预测**

  按照引导式体验，在云服务、客户成员身份和其他分区等订阅区域创建流失预测。 

  订阅流失预测功能使您可以在不依靠数据科学家的情况下，预测客户停止使用基于订阅的产品或服务的可能性。 使用预测分数，您可以结合有关客户的其他信息来创建高流失风险的客户细分。 借助此客户细分，您可以直接面向市场营销、客户支持和其他方案中的客户，以降低特定客户的流失风险，从而提高收入并降低成本。

  在此体验中，您可以将客户流失的定义配置为特定于您的业务的基于时间的窗口。 例如，具有每月订阅流程的视频流业务可能需要考虑在订阅期满 15 天后已流失的客户。

  在继续进行预测时，我们将指导您确定需要哪些数据，并使您能够将有关业务的数据映射到预测客户流失所需的字段。 随着业务信息的更改，您还可以设置时间表来重新训练系统中的新信息，以适应不断变化的业务环境。    
  有关详细信息，请参阅[订阅流失预测（预览）](predict-subscription-churn.md)。

#### <a name="segments"></a>客户细分

- **查找相似客户**
  
  使用人工智能在您的客户群中查找相似客户。 二元分类机器学习模型为扩展客户细分中的客户分配相似性分数。 分数基于与源客户细分中客户的相似性。 根据相似性分数，客户资料将添加到新创建的客户细分中。

  在数字营销中有时被称为相似建模，它使用 AI 模型通过考虑其他属性中的因素，来帮助查找与您的客户的另一个客户细分相似的客户。 它不仅允许您选择属性，还允许您指定应属于此新客户细分的最大客户数量。 然后，AI 模型将根据您选择的属性为每个客户计算相似性分数，并查找平均相似性分数较高的客户。 最终的客户细分将包括看起来与原始客户细分中的客户相似的客户。    
  有关详细信息，请参阅[相似客户](find-similar-customer-segments.md)。

- **客户细分重叠和差异**

  通过客户细分重叠，您可以查看两个或多个客户细分共有多少个客户以及哪些客户是共同的。 例如，高消费客户细分与高满意度客户细分的重叠情况，或流失客户细分与低满意度客户细分的重叠情况。 此外，您还可以根据所选择的其他属性分析重叠的变化方式。

  客户细分差异发现一个细分与其余客户或另一个客户细分之间有哪些不同。 您要做的就是确定一个客户细分，然后系统将确定资料属性和度量，来以经过排名的差异列表（从最强差异到最弱差异）的形式区分该客户细分。    
  有关详细信息，请参阅[客户细分见解（预览）](segment-insights.md)。

- **客户细分生命周期**
  
  定义激活或停用客户细分的计划。    
  有关详细信息，请参阅[管理现有客户细分](segments.md#manage-existing-segments)。

## <a name="may-2020-updates"></a>2020 年 5 月更新

2020 年 5 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-may-2020"></a>2020 年 5 月的新增功能和更新功能

#### <a name="data-ingestion"></a>数据引入

- **实时数据引入：历史记录视图**

  使用我们的 API 引入实时更新时，您可以在 30 天内看到这些更新的汇总历史记录。 您有权访问所有成功或失败的 API 调用的集合，包括它们的结果、源系统和其他有用的元数据。    
  有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。

- **实时数据引入：配置文件更新**

  实时数据引入的这种扩展使您可以在几秒钟内看到对特定用户配置文件字段的更改。    
  除了活动的实时功能外，系统还支持对配置文件字段进行低延迟更新。 配置文件字段的实时更新具有到期时间，因此不能替代计划刷新。    
  有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。

#### <a name="extensibility"></a>扩展性

- **更新了客户卡加载项上的时间线和分页**

  客户卡加载项解决方案的时间线与活动时间线相匹配。 时间线的分页进行了改进，一次最多可显示 50 个活动。 另外还允许在时间线中加载其他活动。    
  有关详细信息，请参阅[客户卡加载项](customer-card-add-in.md)。

- **用于客户细分更改的 Power Automate 触发器**

  Power Automate 的触发器定义可以从其构建流的内容。 新添加的触发器可让您定义客户细分的阈值。 例如，您可以创建一个在超过定义的阈值时发送的通知。    
  有关详细信息，请参阅 [Power Automate 连接器](export-power-automate.md)。

- **对自定义模型的多组织支持**

  使用其他 Azure 机器学习租户的 Web 服务为自定义模型配置工作流。 在为自定义模型创建新的工作流时，您可以登录到 Azure 机器学习租户。 此功能是与您自己的自定义 Azure 机器学习 Web 服务集成的现有功能的补充。    
  有关详细信息，请参阅[自定义机器学习模型](custom-models.md)。

#### <a name="segments"></a>客户细分

- **实体路径自动化**

  在创建客户细分时，用户需要定义实体路径。 此功能迈出了自动化实体路径定义的第一步，让您可以专注于要考虑的细分划分条件。    
  如果要用来细分客户的实体与统一的客户实体直接相关，则无需再定义实体路径。 但是，如果存在多个可能的实体路径，则仍然需要手动定义它。

- **对多个客户细分执行的操作**
  
  用户可以单击选择多个客户细分并对其执行操作，如刷新客户细分。    

- **刷新细分**

  用户可以刷新单个客户细分或仅选择他们想要刷新的客户细分。    

  
- **对复合客户细分的改进**

  用户可以创建、编辑和删除基于其他客户细分的客户细分。 例如，在基于其他客户细分构建的另一个客户细分的基础上构建的客户细分。    

- **客户细分列表页**

  客户细分页面的新设计使用一种列表格式，可让您一次查看更多客户细分。 添加了搜索字段可快速查找客户细分。 用户现在可以一次在多个客户细分上应用诸如下载或删除之类的操作。 引入了新的趋势体验，可以快速发现客户细分的重大变化。    
  有关详细信息，请参阅[创建和管理客户细分](segments.md)。

#### <a name="system-administration"></a>系统管理

- **Microsoft Dynamics 365 Online Government 中提供的 Customer Insights**

  交互渠道越来越多，公民数据散布在无数个系统中，导致数据孤立，掌握的公民交互信息零碎。 如果不能全面了解每个公民在各个渠道中的交互情况，政府就不可能大规模进行现代化。 Microsoft 致力于支持政府在满足公民对一致和响应式体验的期望方面的技术需求。    
  在 2020 年发行版本第 1 波中，Dynamics 365 Customer Insights 将面向政府社区云 (GCC) 提供，该环境旨在满足美国政府机构的更高合规性需求。 政府机构获得公民的统一信息，使用预构建的 AI 来获得改进交互、提升员工和改变社区的见解，同时降低 IT 复杂性并满足美国的合规性与安全标准。 Dynamics 365 Government 可以满足美国联邦风险与授权管理计划 (FedRAMP) 的严苛要求，让美国联邦机构可以从 Microsoft Cloud 节省的成本和严格的安全性中受益。

## <a name="april-2020-updates"></a>2020 年 4 月更新

2020 年 4 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="new-and-updated-features-in-april-2020"></a>2020 年 4 月的新增功能和更新功能

#### <a name="activities"></a>活动

- **将活动实体映射到标准活动类型**
  
  活动配置和存储当前基于静态设计，可以在时间线中进行查看。 活动的语义含义在 AI 模型中可能有多个用例，目前尚未完全使用。 我们计划根据活动类型和对活动的更好的语义理解，使活动时间线更加动态。 此功能用于识别 Common Data Model 中为任何一个引入的活动定义的活动类型。
  有关详细信息，请参阅[自定义活动](activities.md)。

#### <a name="data-ingestion"></a>数据引入

- **实时数据引入：活动**
  
  实时数据引入将立即提供数据以供使用，直到后续计划刷新从数据源中提取此数据。    
  有关详细信息，请参阅[实时数据引入](real-time-data-ingestion.md)。

- **对数据准备的改进**
  
  了解有关实体中引入的数据的详细信息。 通过数据摘要，您可以了解可帮助采取相应操作的数据质量特征。    
  有关详细信息，请参阅[探索实体数据](entities.md#exploring-a-specific-entitys-data)。

- **使用 Common Data Service 从 Dynamics 365 引入分析数据**
  
  Common Data Service 可用作创建数据源的一种方式。 现有 Dynamics 365 客户可以将分析实体从 Common Data Service 引入到 Customer Insights。 单个数据源可以在 Customer Insights 环境中同时使用相同的 Common Data Service 托管湖。    
  有关详细信息，请参阅[连接到 Common Data Service 托管数据湖中的数据](connect-common-data-service-lake.md)。

#### <a name="extensibility"></a>扩展性

- **导出至 LiveRamp**

  在 LiveRamp® 中激活数据，以便跨数字、社交和 TV 生态系统与超过 500 个平台连接。 利用 LiveRamp 中的数据定位、抑制和个性化广告活动。    
  有关详细信息，请参阅 [LiveRamp&reg; 连接器](export-liveramp.md)。

- **Customer Insights Teams 加载项**
  
  机器人为统一客服配置文件提供查找功能。 它将显示一张卡，其中最多可包含来自生成的客户资料的 15 个字段。 多个匹配项将返回可在其中选择配置文件的结果的列表。    
  有关详细信息，请参阅 [Customer Insights 的 Teams 机器人](export-teams-bot.md)。

#### <a name="measures"></a>度量

- **度量列表页**
  
  度量页面的改进包括对一个度量和一次多个度量执行操作的支持。 此外，您还会发现一个搜索字段，可以用来快速查找和跟踪度量。    
  有关详细信息，请参阅[创建和管理客户细分](segments.md)。

- **对复合度量的改进**
  
  用户可以创建、编辑和删除基于其他度量的度量。 例如，在基于其他度量构建的另一个度量的基础上构建的度量。

#### <a name="segments"></a>客户细分

- **其他运算符**
  
  In-set 运算符允许按几个可能的字符串值对客户进行细分。 在添加此运算符之前，您必须使用多个 OR 条件构建此类客户细分。 In-set 运算符让您可以在一个条件下执行此操作。    
  有关详细信息，请参阅[创建和管理客户细分](segments.md)。

#### <a name="system-administration"></a>系统管理

- **将配置设置复制到新环境**
  
  将您的配置从一个环境复制到另一个环境。 创建新环境时，可以选择要从中复制配置的现有环境。 当前，我们支持复制数据源、数据统一、关系、度量和客户细分。 不会复制数据源凭据和实际数据。    
  有关详细信息，请参阅[管理环境](manage-environments.md)。
