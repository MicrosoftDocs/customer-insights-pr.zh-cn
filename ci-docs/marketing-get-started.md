---
title: 在 Dynamics 365 Marketing 中使用统一配置文件
description: 了解如何将统一配置文件和客户细分与 Dynamics 365 Marketing 集成。
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653703"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>在 Dynamics 365 Marketing 中使用统一客户配置文件

[Dynamics 365 Marketing](/dynamics365/marketing/overview) 可以提升客户体验，允许您跨所有接触点协调个性化旅程，以加强关系并赢得忠诚度。 Dynamics 365 Marketing 应用可与 Dynamics 365 Sales、Dynamics 365 Customer Insights、Microsoft Teams 和其他产品无缝配合使用，允许您利用数据和 AI 的功能做出更快、更好的决策。

通过将 Customer Insights 数据与 Marketing 连接，您可以：

- 定位统一客户配置文件和客户细分。 这样，您可以吸引每一个客户，而不管客户数据位于哪里。
- 电子邮件、短信和推送通知中的动态内容（如个性化令牌）基于诸如忠诚度状态、订阅续订日期、父帐户之类的度量，或您在统一的 Customer Insights 配置文件中捕获的任何其他度量。
- 将 Marketing 中的数据加载到 Customer Insights 中，并将其与来自其他源的客户数据合并。
- 应用 Customer Insights 数据清理、扩充和模糊匹配工具。


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>在实时市场营销中使用丰富的客户配置文件

通过实时市场营销，您可以创建[自定义触发器](/dynamics365/marketing/real-time-marketing-custom-triggers)，来根据任何客户操作启动客户旅程。 您的数据越个性化，您的旅程的相关性和个性化程度就越高。 这就是将 Marketing 和 Customer Insights 结合后实现强大功能的原因。 您可以[统一来自任何源的数据](data-unification.md)，然后使用这些数据来推动超个性化的客户旅程。

了解详细信息：[在实时市场营销中使用 Customer Insights 配置文件和客户细分](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>将统一的客户细分用于出站客户旅程

使用 Customer Insights，您可以从多个源提炼数据，然后将其组合，形成聚合的客户细分。 通过 [将 Customer Insights 与出站市场营销连接](export-dynamics365-marketing.md)，这些客户细分将自动出现在客户旅程设计器中 *并* 自动刷新。

了解详细信息：[将来自 Dynamics 365 Customer Insights 的客户细分与 Dynamics 365 Marketing 结合使用](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>从您自己的 Azure Data Lake Storage 拉取数据

如果您想要将 Customer Insights 数据与 Marketing 结合使用，则不只限于选择云存储。 如果您已经设置了自己的 Azure Data Lake Storage，您可以连接 Customer Insights，然后与 Marketing 应用共享数据，就像使用基于云的设置一样。

了解详细信息：[启用从您自己的 Azure Data Lake Storage 与 Dataverse 共享数据](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)