---
title: 在 Customer Insights 中创建环境
description: 使用 Dynamics 365 Customer Insights 的许可订阅创建环境的步骤。
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354084"
---
# <a name="create-an-environment-in-audience-insights"></a>在访问群体见解中创建环境

本文介绍在您的组织购买 Dynamics 365 Customer Insights 订阅后如何创建新环境。 

组织可以为每个 Customer Insights 许可证创建 *两个* 环境。 如果您的组织购买多个许可证，请[联系我们的支持团队](https://go.microsoft.com/fwlink/?linkid=2079641)增加可用环境的数量。 有关产能和附加产品产能的详细信息，请下载 [Dynamics 365 许可指南](https://go.microsoft.com/fwlink/?LinkId=866544)。

> [!NOTE]
> 如果您要试用此服务，请参阅[设置试用环境](../trial-signup.md)。

## <a name="create-a-new-environment"></a>创建新环境

购买 Customer Insights 的订阅许可证后，Microsoft 365 租户的全局管理员会收到一封电子邮件，邀请他们创建环境。 转到 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) 以开始使用。 

引导式体验帮助您完成所需步骤来收集新环境必需的所有信息。 您需要访问群体见解中的[管理员权限](permissions.md)来创建或管理环境。

1. 在访问群体见解中，打开环境选取器，选择 **+ 新建**。
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="选择环境选取器。":::

1. 请按照以下各节中概括的引导式体验操作。

### <a name="step-1-provide-environment-information"></a>步骤 1：提供环境信息

在 **基本信息** 步骤中，选择是从头创建环境还是[复制其他环境的数据](manage-environments.md#copy-the-environment-configuration)。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="用于创建新 Customer Insights 环境的对话框。":::

提供以下详细信息：
   - **名称**：此环境的名称。 如果已从现有环境中复制，则此字段已填写，但可以更改。
   - **选择业务**：选择新环境的主要访问群体。 您可以处理单个客户（企业到客户）或[企业客户](work-with-business-accounts.md)（企业到企业）。
   - **类型**：选择是要创建生产环境还是沙盒环境。 沙盒环境不允许进行计划的数据刷新，而是用于预实施和测试。 沙盒环境使用与当前选择的生产环境相同的主要访问群体。
   - **区域**：要在其中部署和托管该服务的区域。

### <a name="step-2-configure-data-storage"></a>步骤 2：配置数据存储

在 **数据存储** 步骤中，选择存储来自访问群体见解的数据的位置。

您将有两个选项：**Customer Insights 存储**（由 Customer Insights 团队管理的 Azure 数据湖）和 **Azure Data Lake Storage**（您自己的 Azure Data Lake Storage）。 默认情况下已选择 Customer Insights 存储选项。

:::image type="content" source="media/data-storage-environment.png" alt-text="选择用于存储您的访问群体见解数据的 Azure Data Lake Storage。":::

将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输并存储到该 Azure 存储帐户的适当地理位置。 此位置可能与 Dynamics 365 Customer Insights 中的数据存储位置不同。 在 [Microsoft 信任中心](https://www.microsoft.com/trust-center)了解更多信息。

> [!NOTE]
> Customer Insights 当前支持以下各项：
> - 从存储在 Microsoft Dataverse 管理的 Data Lake 中的 Power BI 数据流引入的实体。  
> - 来自您在创建环境时选择的同一 Azure 区域的 Azure Data Lake Storage 帐户。
> - 本身为 Gen2 并且启用了 *分层命名空间* 的 Azure Data Lake Storage 帐户。 Azure Data Lake Gen1 存储帐户不受支持。

对于 Azure Data Lake Storage 选项，您可以在基于资源的选项和基于订阅的选项之间选择以进行身份验证。 有关详细信息，请参阅使用 Azure 服务主体[连接到 Azure Data Lake Storage 帐户](connect-service-principal.md)。 **容器** 名称将是 `customerinsights`，无法更改。

当数据引入等系统流程完成时，系统会在您指定的存储帐户内创建相应的文件夹。 将根据流程名称创建数据文件和 *model.json* 文件并将其添加到文件夹中。

如果您创建多个 Customer Insights 环境并选择将这些环境中的输出实体保存到您的存储帐户，Customer Insights 将为容器中具有 `ci_environmentID` 的每个环境创建单独的文件夹。

### <a name="step-3-connect-to-microsoft-dataverse"></a>步骤 3：连接到 Microsoft Dataverse
   
**Microsoft Dataverse** 步骤让您可以将 Customer Insights 与您的 Dataverse 环境相连接。

提供您自己的 Microsoft Dataverse 环境，以便与基于 Dataverse 的业务应用程序（例如 Dynamics 365 Marketing 或 Power Apps 中的模型驱动应用程序）共享数据（配置文件和见解）。 如果您没有自己的 Dataverse 环境，请将此字段留空，我们将设置一个环境。

通过连接到 Dataverse 环境，您还可以[使用 Power Platform 数据流和网关从本地数据源中引入数据](data-sources.md#add-data-from-on-premises-data-sources)。 您还可以通过连接到 Dataverse 环境来使用[现成的预测模型](predictions-overview.md?tabs=b2c#out-of-box-models)。

> [!IMPORTANT]
> Customer Insights 和 Dataverse 必须在同一区域才能启用数据共享。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="为净新实例自动启用了与 Microsoft Dataverse 的数据共享。":::

> [!NOTE]
> Customer Insights 不支持以下数据共享场景：
> - 如果您将所有数据保存到自己的 Azure Data Lake Storage，将无法启用与 Dataverse 托管数据湖的数据共享。
> - 如果您启用与 Dataverse 的数据共享，那么您将无法[在实体中创建预测值或缺失值](predictions.md)。

### <a name="step-4-finalize-the-settings"></a>步骤 4：完成设置

在 **检查** 步骤中，查看所有指定的设置。 当全部设置看上去都已经完成后，选择 **创建** 设置环境。 

您可以在以后更改大部分设置。 有关详细信息，请参阅[管理环境](manage-environments.md)。

## <a name="work-with-your-new-environment"></a>使用新环境

请查看以下文章来帮助您开始配置 Customer Insights： 

- [添加更多用户和分配权限](permissions.md)。
- [引入您的数据源](data-sources.md)并通过[数据统一过程](data-unification.md)运行它们，以获得[统一的客户配置文件](customer-profiles.md)。
- [扩充统一的客户配置文件](enrichment-hub.md)或[运行预测模型](predictions-overview.md)。
- [创建客户细分](segments.md)以对客户进行分组，创建[度量](measures.md)以评价 KPI。
- [设置连接](connections.md)和[导出](export-destinations.md)，处理其他应用程序中的数据子集。
