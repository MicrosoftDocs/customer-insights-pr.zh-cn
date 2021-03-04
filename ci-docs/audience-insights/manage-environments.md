---
title: 创建和管理环境
description: 了解如何注册服务以及如何管理环境。
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270101"
---
# <a name="manage-environments"></a>管理环境

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

本文介绍如何创建新的组织以及如何预配环境。

## <a name="sign-up-and-create-an-organization"></a>注册和创建组织

1. 转到 [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 网站。

2. 选择 **开始**。

3. 选择首选注册方案，然后选择相应链接。

4. 接受条款和条件，然后选择 **继续** 开始创建组织。

5. 环境创建后，您将被重定向到 [Customer Insights](https://home.ci.ai.dynamics.com)。

6. 使用演示环境探索该应用，或者按照下一节中的步骤创建一个新的环境。

7. 指定环境设置之后，选择 **创建**。

8. 您将在成功创建环境后登录。

## <a name="create-an-environment-in-an-existing-organization"></a>在现有组织中创建环境

创建新环境的方式包含以下两种： 您可以指定一个全新的配置，也可以复制现有环境的一些配置设置。

创建环境：

1. 选择应用标题中的 **环境** 选择器。

1. 选择 **新建**。

   > [!div class="mx-imgBorder"]
   > ![环境设置](media/environment-settings-dialog.png)

1. 在 **创建新环境** 对话框中，选择 **新建环境**。

   如果要 [从当前环境复制数据](#additional-considerations-for-copy-configuration-preview)，请选择 **从现有环境复制**。 您将看到组织中可以从中复制数据的所有可用环境的列表。

1. 提供以下详细信息：
   - **名称**：此环境的名称。 如果已从现有环境中复制，则此字段已填写，但可以更改。
   - **区域**：要在其中部署和托管该服务的区域。
   - **类型**：选择是要创建生产环境还是沙盒环境。

2. 或者，您可以选择 **高级设置**：

   - **保存所有数据到**：指定要存储从 Customer Insights 生成的输出数据的位置。 有两个选项：**Customer Insights 存储**（Customer Insights 团队托管的 Azure Data Lake）和 **Azure Data Lake Storage Gen2**（您自己的 Azure Data Lake Storage）。 默认情况下已选择 Customer Insights 存储选项。

   > [!NOTE]
   > 将数据保存到 Azure Data Lake Storage，即表示您同意将数据传输到适合该 Azure 存储帐户的地理位置并存储在其中，此位置可能与 Dynamics 365 Customer Insights 中存储数据的位置不同。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)
   >
   > 现在，引入的实体始终存储在 Customer Insights 托管数据湖中。
   > 我们仅支持在创建环境时选择的同一 Azure 区域中的 Azure Data Lake Gen2 存储帐户。
   > 我们仅支持 Azure Data Lake Gen2 分层命名空间 (HNS) 支持的存储帐户。

   - 对于 Azure Data Lake Storage Gen2 选项，在进行身份验证时，您可以在基于资源的选项和基于订阅的选项之间进行选择。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 **容器** 名称不可更改，该名称将为“customerinsights”。
   
   - 如果您希望使用 [预测](predictions.md)或基于 Microsoft Dataverse 配置与应用程序和解决方案的数据共享，请在 **配置与 Microsoft Dataverse 的数据共享并启用其他功能** 下面提供 Microsoft Dataverse 环境 URL。 选择 **启用数据共享** 以与 Microsoft Dataverse 托管 Data Lake 共享 Customer Insights 输出数据。

     > [!NOTE]
     > - 将所有数据保存到自己的 Azure Data Lake Storage 时，当前不支持与 Microsoft Dataverse 托管 Data Lake 共享数据。
     > - 启用与 Microsoft Dataverse 托管 Data Lake 的数据共享时，当前不支持[预测实体中缺少的值 ](predictions.md)。

     > [!div class="mx-imgBorder"]
     > ![用于启用与 Microsoft Dataverse 的数据共享的配置选项](media/Datasharing-with-DataverseMDL.png)

   当您运行流程（例如数据引入或客户细分创建）时，将在上述指定的存储帐户中创建相应的文件夹。 数据文件和 model.json 文件将根据您运行的流程创建并添加到相应的子文件夹中。

   如果您创建了多个 Customer Insights 环境并选择将这些环境中的输出实体保存在存储帐户中，将为容器中具有 ci_<environmentid> 的每个环境创建单独的文件夹。

### <a name="additional-considerations-for-copy-configuration-preview"></a>复制配置的其他注意事项（预览）

复制以下配置设置：

- 功能配置
- 引入/导入的数据源
- 数据统一（映射、匹配、合并）配置
- 客户细分
- 度量
- 关系
- 活动
- 搜索和筛选索引
- 导出目标
- 计划刷新
- 扩充
- 模型管理
- 角色分配

*不* 复制以下设置：

- 客户配置文件。
- 数据源凭据。 您必须为每个数据源提供凭据，并手动刷新数据源。
- Common Data Model 文件夹和 Common Data Service 托管湖中的数据源。 您必须使用与源环境中相同的名称手动创建这些数据源。

复制环境时，您会看到一条确认消息，显示新环境已创建。 选择 **转到数据源** 查看数据源的列表。

所有数据源都将显示 **需要凭据** 状态。 编辑数据源并输入凭据来刷新。

> [!div class="mx-imgBorder"]
> ![数据源已复制](media/data-sources-copied.png)

刷新数据源后，请转到 **数据** > **统一**。 在这里，您将找到源环境中的设置。 根据需要进行编辑，或选择 **运行** 启动数据统一流程，创建统一的客户实体。

当数据统一完成时，再转到 **度量** 和 **细分** 进行刷新。

## <a name="edit-an-existing-environment"></a>编辑现有环境

您可以编辑现有环境的某些详细信息。

1.  选择应用标题中的 **环境** 选择器。

2.  选择 **编辑** 图标。

3. 在 **编辑环境** 框中，可以更新环境的 **显示名称**，但不能更改 **区域** 或 **类型**。

4. 如果环境配置为在Azure Data Lake Storage Gen2 中存储数据，则可以更新 **帐户密钥**。 但是，您不能更改 **帐户名称** 或 **容器** 名称。

5. 或者，您可以从基于帐户密钥的连接更新到基于资源或基于订阅的连接。 升级后，您将无法在更新后还原到帐户密钥。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 在更新连接时，无法更改 **容器** 信息。

## <a name="reset-an-existing-environment"></a>重置现有环境

作为管理员，如果您想要删除所有配置并删除引入的数据，可以将环境重置为空状态。

1.  选择应用标题中的 **环境** 选择器。 

2.  选择要重置的环境，并选择省略号 **...**。 

3. 选择 **重置** 选项。 

4.  若要确认删除，请输入环境名称并选择 **重置**。

## <a name="delete-an-existing-environment-available-only-for-admins"></a>删除现有环境（仅适用于管理员）

作为管理员，您可以删除您管理的环境。

1.  选择应用标题中的 **环境** 选择器。

2.  选择要重置的环境，并选择省略号 **...**。 

3. 选择 **删除** 选项。 

4.  若要确认删除，请输入环境名称，然后选择 **删除**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]