---
title: 新功能和未来的功能
description: 有关新功能、改进和 Bug 修复的信息。
ms.date: 05/03/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: af79c8369dd608e8ce1c14c50bb9aef3a79b9029
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833619"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 中的新增功能

我们非常激动地发布我们的最新更新！ 本文总结了公开预览功能、正式发布版本的增强和功能更新。 若要查看长期功能计划，请参阅 [Dynamics 365 和 Power Platform 发行计划](/dynamics365/release-plans/)。

我们将按地区推出更新。 因此，某些地区可能先于其他地区看到功能。 除非另行指定，否则您无需执行任何操作，我们会自动更新应用，无需停机。

> [!TIP]
> 若要提交功能请求和产品建议及投票，请访问 [Dynamics 365 应用程序意见门户](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)。


## <a name="april-2022-updates"></a>2022 年 4 月更新

2022 年 4 月的更新包括新功能、性能升级和 bug 修复。

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet 扩充（预览版）

Dun & Bradstreet 为企业提供商业数据、分析和见解。 它使那些具有公司统一客户配置文件的客户能够扩充其数据。 扩充包括 DUNS 编号、公司规模、位置、行业等属性。

有关详细信息，请参阅[通过 Dun & Bradstreet 扩充公司配置文件（预览版）](enrichment-dnb.md)。

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>在创建新度量时定义度量类型

现在您可以区分各个配置文件的度量和整个业务中的度量。 虽然业务度量显示在 Customer Insights 的主页上，但客户度量显示在详细的客户视图中。

有关详细信息，请参阅[使用度量生成器从头开始创建度量](measure-builder.md)。

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insights 文档整合

我们重新审视了我们的文档文章，并删除了参与见解和访问群体见解功能的提及内容。 将来，当我们撰写应用程序的核心功能相关内容时，我们将始终引用产品名称 Customer Insights。 此更改还导致目录、URL 结构和底层文档存储库中的文件路径的重大重组。 您的所有书签或现有链接继续有效并且会重定向到更新的 URL。

如果您想让我们知道您对更改的看法或发现某些内容未按预期工作，请[针对此页面提交反馈](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**)来告诉我们。

## <a name="march-2022-updates"></a>2022 年 3 月更新

2022 年 3 月的更新包括新功能、性能升级和 bug 修复。

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec 扩充（预览版）

LiveRamp 提供标识解析和客户数据整合。 您可以将客户数据中的个人标识符映射到 AbiliTec 标识图形，然后接收 AbiliTec ID。 然后，您可以使用这些 ID 更好地统一您的客户数据。

有关详细信息，请参阅[使用 LiveRamp 的标识数据扩充客户资料（预览）](enrichment-liveramp.md)。

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>使用标记和筛选器组织客户细分和度量

如果您的组织维护大量客户细分或度量，那么有时会感觉很难找到合适的客户细分或度量。 此新功能允许您使用标记和列组织列表。 它有助于快速轻松地查找数据并自定义视图。

有关详细信息，请参阅[使用标记和列](work-with-tags-columns.md)。

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>使用自己的存储帐户时启用与 Dataverse 共享数据

如果您的环境使用 Azure Data Lake Storage 来存储 Customer Insights 数据，启用与 Microsoft Dataverse 共享数据需要一些额外的配置。
之前，只有当您的数据存储在我们的托管数据湖中时，您才能允许与 Dataverse 共享数据。

有关详细信息，请参阅[从您自己的 Azure Data Lake Storage 启用与 Dataverse 共享数据（预览版）](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)。

### <a name="new-export-destinations-iterable-and-braze"></a>新的导出目标：Iterable 和 Braze

我们将继续通过新的连接扩展我们的导出目标生态系统。 您现在可以将客户细分导出到 Iterable 和 Braze 以使用它们的激活服务。

有关详细信息，请参阅[将客户细分导出到 Iterable（预览版）](export-iterable.md)和[将客户细分导出到 Braze（预览版）](export-braze.md)。

### <a name="improvements-to-marketo-and-google-ads-export"></a>对 Marketo 和 Google Ads 导出的改进

更改连接服务中的 API 会导致连接器更新可靠和平稳地运行。 我们已发布一些有关导出到 Marketo 和 Google Ads 服务的更新：

- Google Ads：新版本的 Google Ads 导出连接器简化了身份验证体验，现在，您可以自动创建新的 Google Ads 受众。 
- Marketo：新版本的 Marketo 导出连接器支持 Marketo ID，从而使您能够避免数据重复、更新现有记录以及在 Marketo 中创建新记录。 

## <a name="february-2022-updates"></a>2022 年 2 月更新

2022 年 2 月的更新包括新功能、性能升级和 bug 修复。

### <a name="general-availability-for-prediction-models"></a>预测模型的正式发布

现成可用的预测模型（包括 **订阅流失**、**交易流失** 和 **客户生命周期价值 (CLV)**）将作为 Customer Insights 的一部分正式发布。 

有关详细信息，请参阅[预测概述](predictions-overview.md)。

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>新数据源：与 Azure Synapse Analytics 集成（预览）

Azure Synapse Analytics 是一项企业分析服务，可加快跨数据仓库和大数据系统获取见解的速度。

已使用 Azure Synapse Analytics 的组织可以将数据引入到 Customer Insights 中。 

有关详细信息，请参阅[连接 Azure Synapse 数据源（预览）](connect-synapse.md)。

### <a name="liveramp-enrichment-preview"></a>LiveRamp 扩充（预览）

LiveRamp 提供标识解析和客户数据整合。 您可以将客户数据中的个人标识符映射到 AbiliTec 标识图形，然后接收 AbiliTec ID。 然后，您可以使用这些 ID 更好地统一您的客户数据。

有关详细信息，请参阅[使用 LiveRamp 的标识数据扩充客户资料（预览）](enrichment-liveramp.md)。

### <a name="enrichment-for-data-sources-preview"></a>数据源扩充（预览）

在进行数据统一之前，使用来自 Microsoft 和其他合作伙伴等来源的数据扩充您的客户数据。 数据源扩充有助于提高数据完整性和质量，可以帮助在您统一数据后获得更好的结果。

有关详细信息，请参阅[数据源扩充（预览）](data-sources-enrichment.md)。

### <a name="change-owner-of-environment"></a>更改环境负责人

虽然多个用户可以在 Customer Insights 中具有管理员权限，但只有一个用户是环境的负责人。 改进的体验使您可以更改环境的负责人，并可以在前负责人离开组织时认领所有权。 

有关详细信息，请参阅[更改环境负责人](manage-environments.md#change-the-owner-of-an-environment)。

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>数据准备过程列出损坏记录的损坏原因

数据准备功能现在显示所有数据损坏的字段的损坏原因。 该信息在个人记录级别提供，以便于识别。 

有关详细信息，请参阅[损坏的数据源](entities.md#corrupted-data-sources)。

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>参与见解功能中报告功能的预览结束

Dynamics 365 Customer Insights 参与见解功能预览已于 2022 年 2 月 15 日结束。  
此更改意味着 Customer Insights 试用体验不再包括渠道创建功能或其他报告功能。

我们邀请您探索和评估 [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)（Microsoft 客户数据平台 (CDP)）的许多其他功能。    
 
在过渡期内，现有的预览参与者仍然可以访问一些预览功能：

- 获取代码以检测网站或移动应用 
- 查看事件和事件属性 
- 通过引入和优化的事件增强统一的配置文件，以从客户数据的全部价值中受益
  
在转换期间，捕获的事件仍会流式传输到连接的 Data Lake。 关闭此功能后，数据共享将停止，并且不会向连接的存储发送新事件。
如果您对功能预览结束有任何疑问，请直接与您的 Microsoft 帐户团队联系。 您的帐户团队将让您及时了解即将进行的发布的最新信息。 

## <a name="january-2022-updates"></a>2022 年 1 月更新

2022 年 1 月的更新包括新功能、性能升级和 bug 修复。

### <a name="sentiment-analysis-of-your-customers-feedback"></a>客户反馈的情绪分析

Customer Insights 提供了一项新的 AI 支持功能来整合客户情绪并将特定业务方面识别为有针对性的改进机会。 通过分析客户的书面反馈，您可以以较低成本获得准确的见解。 由针对每个客户 ID 生成两个派生见解的自然语言处理 (NLP) 模型提供支持的情绪分析。 情绪评分（–5 到 5）和适用业务方面的列表。 

有关详细信息，请参阅[分析客户反馈中的情绪（预览版）](sentiment-analysis.md)。


[!INCLUDE [footer-include](includes/footer-banner.md)]