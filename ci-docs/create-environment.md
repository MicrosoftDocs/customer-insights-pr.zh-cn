---
title: 创建新环境
description: 用于在 Dynamics 365 Customer Insights 中创建环境的步骤。
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304232"
---
# <a name="create-a-new-environment"></a>创建新环境

[购买 Dynamics 365 Customer Insights 的订阅许可证](paid-license.md)后，Microsoft 365 租户的全局管理员会收到一封电子邮件，邀请他们创建环境。 转到 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) 以开始使用。 在此方案中，从[步骤 1：提供基本信息](#step-1-provide-basic-information)开始。

创建第一个环境后，Microsoft 365 租户的全局管理员可以[将用户组织中的用户添加为管理员](permissions.md)。 然后，这些管理员可以管理用户和环境。 如果您的组织购买多个 Customer Insights 许可证，请[联系我们的支持团队](https://go.microsoft.com/fwlink/?linkid=2079641)增加可用环境的数量。 有关产能和附加产能的详细信息，请参阅 [Dynamics 365 许可指南](https://go.microsoft.com/fwlink/?LinkId=866544)。 在您能够创建其他环境后，转到[启动环境创建过程](#start-the-environment-creation-process)。

> [!TIP]
> 如果您要试用此服务，请参阅[设置试用环境](trial-signup.md)。

## <a name="prerequisites"></a>先决条件

Customer Insights 的[管理员权限](permissions.md)

## <a name="start-the-environment-creation-process"></a>启动环境创建过程

1. 打开环境选择器，并选择 **+ 新建**。
  
   :::image type="content" source="media/environment-picker.png" alt-text="选择环境选取器。":::

1. 按照以下部分中概述的指导经验，提供新环境所需的所有信息。

## <a name="step-1-provide-basic-information"></a>步骤 1：提供基本信息

1. 选择是从头创建环境还是复制其他环境的数据。 [从其他环境复制数据](#copy-the-environment-configuration)需要执行额外步骤。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="用于创建新 Customer Insights 环境的对话框。":::

1. 提供以下详细信息：

   - **名称**：此环境的名称。 如果已从现有环境中复制，则此字段已填写，但可以更改。
   - **选择业务**：新环境的主要访问群体：个人消费者（企业对客户）或[企业客户](work-with-business-accounts.md)（企业对企业）。 如果您的组织主要与个人开展业务，例如零售商或咖啡店，请选择个人消费者。 如果您的主要访问群体是其他公司，例如汽车制造商或造纸公司，请选择企业客户。
   - **类型**：环境类型：生产或沙盒。 沙盒环境不允许进行计划的数据刷新，而是用于预实施和测试。 沙盒环境使用与当前选择的生产环境相同的主要访问群体。
   - **区域**：要在其中部署和托管该服务的区域。 要[使用您自己的 Azure Data Lake Storage 帐户](own-data-lake-storage.md)或[连接到现有 Microsoft Dataverse 组织](customer-insights-dataverse.md)，Customer Insights 环境必须在同一区域。

1. 选择 **下一步**。

## <a name="step-2-configure-data-storage"></a>步骤 2：配置数据存储

1. 选择存储 Customer Insights 数据的位置：

   - **Customer Insights 存储**：数据存储被自动管理。 这是默认选项，除非有关于将数据存储在您自己的存储帐户中的特定要求，否则我们建议使用此选项。
   - **Azure Data Lake Storage**：您自己的存储数据的 Azure Data Lake Storage 帐户，让您可以完全控制数据的存储位置。 按照[使用您自己的 Azure Data Lake Storage 帐户](own-data-lake-storage.md)中的步骤操作。

   :::image type="content" source="media/data-storage-environment.png" alt-text="选择用于存储您的数据的首选选项。":::

1. 选择 **下一步**。

## <a name="step-3-connect-to-microsoft-dataverse"></a>步骤 3：连接到 Microsoft Dataverse

如果您有 Dataverse 环境，请连接 Customer Insights。 与 Dataverse 共享数据，以便与基于 Dataverse 的业务应用程序（例如 Dynamics 365 Marketing 或 Power Apps 中的模型驱动应用程序）一起使用数据。

1. 按照[使用 Microsoft Dataverse 中的 Customer Insights 数据](customer-insights-dataverse.md)中的步骤操作。

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="为净新环境自动启用了与 Microsoft Dataverse 的数据共享。":::

1. 选择 **下一步**。

## <a name="step-4-finalize-the-settings"></a>步骤 4：完成设置

查看指定设置。 当全部设置看上去都已经完成后，选择 **创建** 设置环境。

要在以后更改某些设置，请参阅[管理环境](manage-environments.md)。

## <a name="work-with-your-new-environment"></a>使用新环境

请查看以下文章来帮助您开始配置 Customer Insights：

- [添加更多用户和分配权限](permissions.md)。
- [引入您的数据源](data-sources.md)并通过[数据统一过程](data-unification.md)运行它们，以获得[统一的客户配置文件](customer-profiles.md)。
- [扩充统一的客户配置文件](enrichment-hub.md)或[运行预测模型](predictions-overview.md)。
- [创建客户细分](segments.md)以对客户进行分组，创建[度量](measures.md)以评价 KPI。
- [设置连接](connections.md)和[导出](export-destinations.md)，处理其他应用程序中的数据子集。

## <a name="copy-the-environment-configuration"></a>复制环境配置

作为管理员，如果您选择从现有环境中复制配置，请从组织中所有可用环境的列表中进行选择。

:::image type="content" source="media/environment-settings-dialog.png" alt-text="环境设置中的设置选项的屏幕截图。":::

复制以下配置设置：

- 通过 Power Query 导入的数据源
- 数据统一配置
- Segments
- 度量
- 关系
- 活动
- 搜索和筛选索引
- 导出
- 刷新计划
- 扩充
- 预测模型
- 角色分配

### <a name="set-up-a-copied-environment"></a>设置复制的环境

复制环境配置时，会在创建复制的环境时显示确认消息。 执行以下步骤确认凭据。

1. 选择 **转到数据源** 查看数据源的列表。 所有数据源都将显示 **需要凭据** 状态。

   :::image type="content" source="media/data-sources-copied.png" alt-text="已复制并需要验证的数据源列表。":::

1. 编辑数据源并输入凭据来刷新。 Common Data Model 文件夹和 Dataverse 中的数据源必须手动创建，名称与源环境中的名称相同。

1. 刷新数据源后，请转到 **数据** > **统一**。 在这里，您将找到源环境中的设置。 根据需要进行编辑，或选择 **统一** > **统一客户配置文件和依赖项** 启动数据统一流程，创建统一的客户实体。

   > [!TIP]
   > 对于客户和联系人，选择 **统一客户** > **统一配置文件和依赖项**。

1. 当数据统一完成时，转到 **度量** 和 **细分** 进行刷新。

1. 转到 **管理** > **连接** 重新验证新环境中的连接。

1. 转到 **数据** > **扩充** 和 **数据** > **导出** 重新激活它们。

[!INCLUDE [footer-include](includes/footer-banner.md)]
