---
title: 新功能和未来的功能
description: 有关新功能、改进和 Bug 修复的信息。
ms.date: 07/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 3412213bcf3a4174baf28c6b4d38f5febded18707c355d236d5082698c4c0db7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035952"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 的访问群体见解功能中的新增功能

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

我们非常激动地发布我们的最新更新！ 本文总结了公开预览功能、正式发布版本的增强和功能更新。 若要查看长期功能计划，请参阅 [Dynamics 365 和 Power Platform 发行计划](/dynamics365/release-plans/)。

我们将按地区推出更新。 因此，某些地区可能先于其他地区看到功能。 除非另行指定，否则您无需执行任何操作，我们会自动更新应用，无需停机。

> [!TIP]
> 若要提交功能请求和产品建议及投票，请访问 [Dynamics 365 应用程序意见门户](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。

## <a name="june-2021-updates"></a>2021 年 6 月更新

2021 年 6 月的更新中包括多项功能、性能升级和 Bug 修复。

### <a name="data-ingestion"></a>数据引入

- **改进的数据统一进度更新** 您现在可以在[数据统一过程](data-unification.md)步骤中查看更精细、改进的动态状态更新。 通过此功能，您可以跟踪详细进度，以了解流程，并在任何步骤需要关注时采取措施。

### <a name="extensibility"></a>扩展性

- **将客户细分和其他数据导出到 Salesforce Marketing Cloud** 我们已扩展导出目的地以包括 [Salesforce Marketing Cloud](export-salesforce.md)。 您现在可以通过品牌化 SFTP 导出将客户细分和其他类型的数据导出到 Salesforce Marketing Cloud。 数据导入可以在 Salesforce 中完全自动化，并用于创建更有效的市场营销活动。  
 
- **将客户细分导出到 ActiveCampaign** 我们已扩展导出目的地以包括[可用市场活动](export-active-campaign.md)。 您现在可以导出客户细分，以在 ActiveCampaign 中生成营销活动、运行电子邮件市场营销，以及与特定客户组合作。
 
- **将客户细分导出到 Sendinblue** 我们已扩展导出目的地以包括 [Sendinblue](export-sendinblue.md)。 您现在可以导出客户细分，以通过 Sendinblue 生成营销活动、运行电子邮件市场营销，以及与特定客户组合作。
 
### <a name="ux-updates"></a>UX 更新 

- **新的和增强的客户页面和配置文件详细信息页面** 我们重新设计了客户页面和配置文件详细信息页面，以改善用户体验和提升性能。 这些更改使您可以查看、排序、搜索和筛选客户。 筛选器现在显示在 URL 中，以便与其他用户无缝共享搜索结果。 搜索结果也可以保存为客户细分。    
  客户配置文件的详细信息页现在按各个子节（例如人口统计数据、ID 和其他配置文件属性）对数据进行分组，以提高可读性。 现在，配置文件详细信息页上的其他节更具交互性。 例如，“活动”节现在允许进行筛选和排序。


## <a name="may-2021-updates"></a>2021 年 5 月更新

2021 年 5 月中的更新包括多项功能、性能升级和错误修复。

### <a name="data-ingestion"></a>数据引入

- **在附加 Azure Data Lake Storage 中的数据时查看或修改元数据或实体定义** 在 Azure Data Lake Storage 中附加 Common Data Model 文件夹中的数据时，现在可以在访问群体见解中查看和编辑元数据或实体定义。 此功能会提供实时反馈、模型验证和错误检查。 它允许您无缝编辑 model.json 和 manifest.json。

### <a name="extensibility"></a>扩展性

- **改进了客户细分导出、自定义计划和重复** 您现在可以在列表中[查看特定客户细分的所有导出](export-destinations.md#view-exports-and-export-details)。 此新视图有助于管理特定客户细分的使用方式，并调整现有导出或创建新导出。    
  您可以同时为个别导出或多个导出[定义自定义刷新计划](export-destinations.md#schedule-and-run-exports)。 到目前为止，每次系统刷新时都会运行所有导出。    
  与其从头开始创建新的导出，不如从现有导出开始创建，这样可以节省一些时间。

- **将客户细分导出到 Microsoft Advertising** 我们已扩展导出目的地，以包括 Microsoft Advertising。 使用统一客户配置文件数据在 Microsoft Advertising 上创建客户匹配访问群体，并将这些访问群体用于广告市场活动。 有关更多信息，请参阅[将客户细分导出到 Microsoft Advertising](export-microsoft-advertising.md)。

- **将客户细分导出到 LinkedIn Ads** 我们已扩展导出目标，以包括 LinkedIn Ads，并通过出口统一客户配置文件数据，使您能够通过 LinkedIn 解锁“确定目标联系人”和“确定目标公司”。 有关更多信息，请参阅[将客户细分导出到 LinkedIn Ads](export-linkedin-ads.md)。


- **将客户细分导出到 Omnisend** 我们已扩展导出目标，以包括 Omnisend。 使用在访问群体见解中创建的客户细分来生成市场活动，提供电子邮件市场营销材料，并通过 Omnisend 使用特定客户组。 有关更多信息，请参阅[将客户细分导出到 Omnisend](export-omnisend.md)

### <a name="predictions"></a>预测

- **输入数据可用性报表** 输入数据可用性报表提供了现成预测可能会产生的错误和警告的综合视图。 它还就如何提高模型性能提出了建议。    
  该报表在模型完成训练过程后可用。 无论是否成功完成，系统都将单独为每个模型创建此报表。
  目前，此功能仅适用于交易流失模型。 有关更多信息，请参阅[输入数据可用性报表](manage-predictions.md#input-data-usability-report)。

### <a name="relationships"></a>关系

- **关系可视化工具** 利用关系可视化工具视图，您可以查看实体与其基数之间的所有现有关系。 现在按组来组织关系：用户创建、系统和继承关系。 您还可以将视图导出为图像。 有关详细信息，请参阅[查看关系](relationships.md#view-relationships)。 

## <a name="april-2021-updates"></a>2021 年 4 月更新

2021 年 4 月中的更新包括多项功能、性能升级和错误修复。

### <a name="data-unification"></a>数据统一
 
- **增强的数据统一合并体验**    
  
   现在，我们在数据统一过程的合并配置中增强了用户体验。 这些更改包括直观排序合并字段以及合并和单一字段的详细统计信息。

- **实体重新排序并将所有源记录配置到客户实体中**  
      
   现在，您可以在数据统一过程中重新排序和删除现有实施规划中的实体。 系统提供了根据业务需求在匹配过程中对实体进行重新排序的灵活性。 此外，我们允许将所有不匹配的记录包括到最终 *客户* 实体中，这使他们可以进行客户配置文件数据集定义。

### <a name="enrichments"></a>扩充

 - **新扩充：增强型地址**    
  
   我们很高兴推出用于增强客户数据中的地址的新扩充功能。 数据中的地址可能无结构、不完整或不正确。 此功能使用 Microsoft 的模型按 Common Data Model 格式标准化并扩充您的地址，以获得更佳的准确性和见解。
 
   有关详细信息，请参阅[使用增强的地址扩充客户配置文件](enrichment-enhanced-addresses.md)。

- **扩充的引导式配置体验**    
  
   我们用简单的引导式体验重新感受了扩充的配置体验。 现在，您具有一个用于创建和编辑扩充的清晰分步流程。
 
   此外，我们分离了第三方扩充功能的连接配置，以使多个扩充功能可以使用同一连接。 只有管理员才能配置新的连接，但创建的连接可供管理员和参与者使用。    

   有关详细信息，请参阅[连接概述](connections.md)。

- **相同类型的多项扩充**    
  
   现在，我们允许用户创建和管理相同扩充类型的多个扩充。 例如，您现在可以创建两个单独的地址扩充，以扩充两个不同的客户细分。 关于可以创建多少个相同类型的扩充，具有一些限制，具体取决于扩充类型。
  
   有关详细信息，请参阅[客户资料扩充](enrichment-hub.md)。

## <a name="march-2021-updates"></a>2021 年 3 月更新

2021 年 3 月中的更新包括多项功能、性能升级和错误修复。

### <a name="activities"></a>活动

- **活动向导和语义类型**

   我们改进和更新了活动映射体验，以指导和简化活动映射的创建过程。 在这种新体验中，用户将获得引导式体验，以帮助完成流程的每一步。 在活动映射步骤中，除了从许多活动类型中进行选择外，用户还可以选择在语义上将 *订阅* 和/或 *SalesOrderLine* 的数据映射到行业标准架构，这些架构可用于下游消费。   

   有关详细信息，请参阅[自定义活动](activities.md)。

### <a name="data-ingestion"></a>数据引入

- **使用 Power Platform 数据流和网关连接到本地数据源** 我们很高兴地宣布将使用 Customer Insights 中的网关以及关联的 Power Platform 或 Dataverse 环境来预览 Power Platform 数据流和本地连接。 在具有链接的 Dataverse 环境的 Customer Insights 环境中创建的任何新数据源都将默认为 Power Platform 数据流，此数据流将引入本地数据连接以及一组丰富的连接器和转换功能。

### <a name="extensibility"></a>扩展性

- **在连接和导出中组织的导出** 我们已将 **导出目标** 页面的名称更改为 **连接**，并添加了单独的 **导出** 页面。 在此更新过程中，我们会将现有的导出转换为连接和导出（使用该连接）对。 管理员现在可以在 **连接** 页面上更清晰地了解传出数据。 所有用户角色都有权访问 **导出** 页面，但只有管理员可以选择允许参与者使用共享连接编辑特定的导出。     
  有关更多信息，请参阅[连接概述](connections.md)和[导出概述](export-destinations.md)。

- **将客户细分导出到 Campaign Monitor** 我们已扩展导出目标，以包括 Campaign Monitor。 现在，您可以将客户细分从 Customer Insights 导出到 Campaign Monitor列表，并将其用作市场营销活动的基线。    
   有关详细信息，请参阅[将数据导出至 Campaign Monitor](export-campaign-monitor.md)。

- **将客户细分导出到 Constant Contact** 我们已扩展导出目标，以包括 Constant Contact。 现在，您可以将客户细分从 Customer Insights 导出到 Constant Contact 列表，并将其用作市场营销活动的基线。   
   有关详细信息，请参阅[将数据导出至 Constant Contact](export-constant-contact.md)。

- **将客户细分导出到 RollWorks** 我们已扩展导出目标，以包括 RollWorks。 现在，您可以将客户细分从 Customer Insights 导出到 RollWorks 受众，并将其用作 B2B 广告的基线。    
   有关详细信息，请参阅[将数据导出至 RollWorks](export-rollworks.md)。

- **将客户细分导出到 Snapchat** 我们已扩展导出目标，以包括 Snapchat。 现在，您可以将客户细分从 Customer Insights 导出到 Snapchat 受众，并将其用作广告的基线。     
   有关详细信息，请参阅[将数据导出至 Snapchat](export-snapchat.md)。

### <a name="predictions"></a>预测

- **在预测产品建议中使用产品筛选器** 我们已在产品建议模型中添加了使用产品筛选器的功能。 现在，您可以创建仅使用产品子集的预测。    
   有关更多信息，请参阅[配置产品筛选器](predict-product-recommendation.md#configure-product-filters)。

- **从模型预测创建客户细分** 我们添加了使用预测模型结果创建客户细分的快速方法。 从模型结果页面中，您可以通过选择新的 **创建客户细分** 选项来轻松创建新客户细分。    
  有关更多信息，请参阅[基于预测模型创建一个客户细分](prediction-based-segment.md)。

- **产品建议的解释** 我们添加了信息，以解释 AI 模型为生成产品建议而了解的关键因素，以及这些因素对产品推荐的影响程度。 此信息已添加到模型结果屏幕。    
   有关详细信息，请参阅[审阅预测状态和结果](predict-product-recommendation.md#review-a-prediction-status-and-results)。

## <a name="february-2021-updates"></a>2021 年 2 月更新

2021 年 2 月的更新中包括多项功能、性能升级和 Bug 修复。

#### <a name="extensibility"></a>扩展性

- **将客户细分导出到 AdRoll**

  我们已扩展了导出目标以包括 AdRoll。 现在，您可以将 Customer Insights 中的客户细分导出到 AdRoll 访问群体，并使用它们作为广告的基线。 有关详细信息，请参阅[用于 AdRoll 的连接器](export-adroll.md)。

#### <a name="segments"></a>客户细分
 
- **复制客户细分**
  
  若要基于现有客户细分创建新客户细分，现在可以复制某个客户细分，并编辑复制的客户细分以进一步优化该客户细分。 

- **向客户细分添加其他属性**

  现在，您可以将属性包括在客户细分输出中，即使这些属性不是客户配置文件的一部分。 例如，在客户细分中包括订阅 ID，即使它是与客户实体具有 M:1 关系的订阅实体的一部分。 只要属性属于与客户实体相关的实体，就可以包括这些属性。  

#### <a name="predictions"></a>预测

- **创建预测产品建议**

  了解客户的购买兴趣是什么是通过个性化和参与提高业务收入和建立客户忠诚度所需的第一步。 如果推荐的产品不符合客户的兴趣，会使客户与您的企业之间产生脱节感，从而最终限制整体潜在收入和客户的体验。 

  现在您可以使用您自己的数据预测客户将来可能会购买的产品。 有关详细信息，请参阅[产品建议预测](predict-product-recommendation.md)。

#### <a name="system-administration"></a>系统管理

- **复制环境支持更多类型的数据源**

  管理员可以将环境配置复制到同一组织的新环境中。 对于使用基于 Microsoft Dataverse 托管 Data Lake 或 Common Data Model 文件夹的数据源的情况，此功能扩展了复制环境功能。

## <a name="january-2021-updates"></a>2021 年 1 月更新

2021 年 1 月的更新中包括多项功能、性能升级和 Bug 修复。

#### <a name="extensibility"></a>扩展性

- **SFTP 导出的扩展功能和增强性能**：现在，您可以将所有输出实体从 Customer Insights 导出到 SFTP 主机。 以前，导出仅限于客户细分实体。 此外，SFTP 导出的性能可以在更短时间内导出更多数据量，具体取决于 SFTP 主机的性能。    
  有关详细信息，请参阅[用于 SFTP 的连接器（预览版）](export-sftp.md)。  

#### <a name="segments"></a>客户细分

- **由机器学习提供支持的建议客户细分可以改进指标**：有一种发现和创建客户细分的新方法。 系统使用 AI 模型来建议可以帮助改进您已在跟踪的 KPI（度量）的客户细分。 我们将显示您选择的属性对度量或其他主要属性的影响程度。 此信息有助于查找提供商机的潜在客户细分。    
  有关详细信息，请参阅[建议的客户细分（预览版）](suggested-segments.md)。

#### <a name="data-unification"></a>数据统一

- **增强的匹配体验**：在数据统一区域中更新了匹配体验。 它允许您配置和查看匹配规则，包括详细统计信息，以进一步解释匹配的工作方式。 有一些选项可禁用匹配规则，以便在保留配置、拖放匹配规则等时该规则不再处于活动状态。
  有关详细信息，请参阅[匹配实体](match-entities.md)。

- **匹配过程中的删除重复输出可用作实体**：现在，匹配过程中的删除重复过程输出可以写入到单独的实体中，以进行进一步分析。 该实体由删除重复过程中使用的字段、入选记录以及与入选记录合并的相应备用记录组成。
  有关详细信息，请参阅[实体形式的删除重复输出](match-entities.md#deduplication-output-as-an-entity)。

#### <a name="system-administration"></a>系统管理

- **将数据与 Microsoft Dataverse 无缝共享**：现在，您可以使用 Microsoft Dataverse 托管 Data Lake 与 Microsoft Dataverse 应用程序共享 Customer Insights 输出。 将 Dataverse 环境与 Customer Insights 关联后，便可以选择启用数据共享。
  有关详细信息，请参阅[管理环境](manage-environments.md)。




[!INCLUDE[footer-include](../includes/footer-banner.md)]