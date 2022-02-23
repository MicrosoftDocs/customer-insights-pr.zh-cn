---
title: 创建和管理环境
description: 了解如何注册服务以及如何管理环境。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8251cac9f95455b61eb0300b6c72cd4ab2969591
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046322"
---
# <a name="manage-environments"></a>管理环境



## <a name="switch-environments"></a>切换环境

选择页面右上角中的 **环境** 控件以更改环境。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="用于切换环境的控件的屏幕截图。":::

管理员可以[创建](create-environment.md)和管理环境。

## <a name="edit-an-existing-environment"></a>编辑现有环境

您可以编辑现有环境的某些详细信息。

1.  选择应用标题中的 **环境** 选择器。

2.  选择 **编辑** 图标。

3. 在 **编辑环境** 框中，可以更新环境设置。

有关环境设置的详细信息，请参阅[创建新环境](create-environment.md)。

## <a name="connect-to-microsoft-dataverse"></a>连接到 Microsoft Dataverse
   
**Microsoft Dataverse** 步骤让您可以将 Customer Insights 与您的 Dataverse 环境相连接。

要使用[现成的预测模型](predictions-overview.md#out-of-box-models)，请配置与 Dataverse 的数据共享。 或者，您可以启用来自本地数据源的数据引入，提供您的组织管理的 Microsoft Dataverse 环境 URL。 选择 **启用数据共享** 以与 Dataverse 托管数据湖共享 Customer Insights 输出数据。

> [!IMPORTANT]
> Customer Insights 和 Dataverse 必须在同一区域才能启用数据共享。

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="用于启用与 Microsoft Dataverse 的数据共享的配置选项。":::

> [!NOTE]
> Customer Insights 不支持以下数据共享场景：
> - 如果您将所有数据保存到自己的 Azure Data Lake Storage，将无法启用与 Dataverse 托管数据湖的数据共享。
> - 如果您启用与 Dataverse 的数据共享，那么您将无法[在实体中创建预测值或缺失值](predictions.md)。

## <a name="copy-the-environment-configuration"></a>复制环境配置

创建新环境时，您可以选择从现有环境复制配置。 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="环境设置中的设置选项的屏幕截图。":::

您将看到组织中可以从中复制数据的所有可用环境的列表。

复制以下配置设置：

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

*不* 会复制以下数据：

- 客户配置文件。
- 数据源凭据。 您必须为每个数据源提供凭据，并手动刷新数据源。

- Common Data Model 文件夹和 Dataverse 托管数据湖中的数据源。 您必须使用与源环境中相同的名称手动创建这些数据源。

复制环境时，您会看到一条确认消息，显示新环境已创建。 选择 **转到数据源** 查看数据源的列表。

所有数据源都将显示 **需要凭据** 状态。 编辑数据源并输入凭据来刷新。

:::image type="content" source="media/data-sources-copied.png" alt-text="已复制并需要验证的数据源列表。":::

刷新数据源后，请转到 **数据** > **统一**。 在这里，您将找到源环境中的设置。 根据需要进行编辑，或选择 **运行** 启动数据统一流程，创建统一的客户实体。

当数据统一完成时，再转到 **度量** 和 **细分** 进行刷新。

## <a name="reset-an-existing-environment"></a>重置现有环境

作为管理员，如果您想要删除所有配置并删除引入的数据，可以将环境重置为空状态。

1.  选择应用标题中的 **环境** 选择器。 

2.  选择要重置的环境，并选择省略号 (**...**)。 

3. 选择 **重置** 选项。 

4.  若要确认删除，请输入环境名称并选择 **重置**。

## <a name="delete-an-existing-environment"></a>删除现有环境

作为管理员，您可以删除您管理的环境。

1.  选择应用标题中的 **环境** 选择器。

2.  选择要重置的环境，并选择省略号 (**...**)。 

3. 选择 **删除** 选项。 

4.  若要确认删除，请输入环境名称，然后选择 **删除**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
