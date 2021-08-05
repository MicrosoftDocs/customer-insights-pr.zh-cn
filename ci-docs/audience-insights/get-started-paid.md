---
title: 创建和配置 Customer Insights 的付费许可证
description: 用于获取 Dynamics 365 Customer Insights 许可订阅并对其进行配置的步骤。
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650450"
---
# <a name="get-started-with-a-paid-subscription"></a>开始使用付费订阅

本文介绍在您的组织购买 Dynamics 365 Customer Insights 订阅后如何创建新环境。 如果您想购买 Customer Insights，那么 [Dynamics 365 Customer Insights 网站](https://dynamics.microsoft.com/ai/customer-insights/)上会列出我们的联系方式。 

如果您想试用该服务和功能，请参阅[设置试用环境](get-started-trial.md)。

## <a name="create-an-environment-in-an-existing-organization"></a>在现有组织中创建环境

购买 Customer Insights 订阅许可证后，Microsoft 365 租户的全局管理员会收到一封电子邮件，此电子邮件邀请他们创建环境。 转到 [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) 以开始使用。 

Customer Insights 并非按用户许可，因此它不会显示在“许可证”区域中。 如果您正在 Microsoft 365 管理中心寻找许可证，请转到 **您的产品**。 

> [!NOTE]
> 组织可以为每个 Customer Insights 许可证创建 *两个* 环境。 如果您的组织购买了多个许可证，请[联系我们的支持团队](https://go.microsoft.com/fwlink/?linkid=2079641)，以增加可用环境的数量。 有关产能和附加产品产能的详细信息，请下载 [Dynamics 365 许可指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

创建环境：

1. 在 **创建环境** 对话框中，选择 **新建环境**。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="用于创建新 Customer Insights 环境的对话框。":::

   我们建议从头开始设置环境。 但是，如果您是试用环境的管理员或成员，则可以 [从另一个环境复制数据](manage-environments.md#copy-the-environment-configuration)，方法是选择 **从现有环境复制**。 您将看到组织中可以从中复制数据的所有可用环境的列表。

1. 提供以下详细信息：
   - **名称**：此环境的名称。 如果已从现有环境中复制，则此字段已填写，但可以更改。
   - **区域**：要在其中部署和托管该服务的区域。
   - **类型**：选择是要创建生产环境还是沙盒环境。 沙盒环境不允许进行计划的数据刷新，而是用于预实施和测试。
   
1. 或者，您可以选择 **高级设置**：

   - **保存所有数据到**：指定要存储从 Customer Insights 生成的输出数据的位置。 您将有两个选项：**Customer Insights 存储**（由 Customer Insights 团队管理的 Azure Data Lake）和 **Azure Data Lake Storage**（您自己的 Azure Data Lake Storage）。 默认情况下已选择 Customer Insights 存储选项。

     > [!NOTE]
     > 将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输到适合该 Azure 存储帐户的地理位置并存储在其中，此位置可能与 Dynamics 365 Customer Insights 中存储数据的位置不同。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)
     >
     > 目前，从 Power BI 数据流中引入的实体存储在 Microsoft Dataverse 托管 Data Lake 中。 
     > 
     > 我们仅支持您在创建环境时选择的来自同一 Azure 区域的 Azure Data Lake Storage 帐户。 
     > 
     > 我们仅支持启用了分层命名空间的 Azure Data Lake Storage 帐户。


   - 对于 Azure Data Lake Storage 选项，您可以在基于资源的选项和基于订阅的选项之间选择以进行身份验证。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 **容器** 名称不能更改，并且将是 `customerinsights`。
   
   - 如果要使用 [现成模型](predictions-overview.md#out-of-box-models)，请配置与 Microsoft Dataverse 的数据共享，或允许从本地数据源引入数据，并在 **配置与 Microsoft Dataverse 的数据共享并启用其他功能** 下面提供 Microsoft Dataverse URL。 选择 **启用数据共享** 以与 Microsoft Dataverse 托管 Data Lake 共享 Customer Insights 输出数据。

     > [!NOTE]
     > - 将所有数据保存到自己的 Azure Data Lake Storage 时，当前不支持与 Microsoft Dataverse 托管 Data Lake 共享数据。
     > - 当您启用与 Microsoft Dataverse 托管 Data Lake 的数据共享时，当前不支持[预测实体中缺少的值](predictions.md)。

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="用于启用与 Microsoft Dataverse 的数据共享的配置选项。":::

   当数据引入等系统进程完成后，系统会在您指定的存储帐户中创建相应的文件夹。 根据进程名称创建了数据文件和 model.json 文件并将其添加到了文件夹中。

   如果您创建了多个 Customer Insights 环境并选择将这些环境中的输出实体保存在存储帐户中，将为容器中具有 ci_<environmentid> 的每个环境创建单独的文件夹。

1. 选择 **创建** 以设置环境。 

## <a name="configure-an-environment"></a>配置环境

查看以下文章以帮助您开始配置 Customer Insights。 

- [添加更多用户和分配权限](permissions.md)。
- [引入您的数据源](data-sources.md)并通过[数据统一过程](data-unification.md)运行它们，以获得[统一的客户配置文件](customer-profiles.md)。
- [扩充统一的客户配置文件](enrichment-hub.md)或[运行预测模型](predictions-overview.md)。
- 创建[客户细分](segments.md)以为客户分组并[衡量](measures.md)评价 KPI。
- 设置[连接](connections.md)和[导出](export-destinations.md)，以处理其他应用程序中的数据子集。
