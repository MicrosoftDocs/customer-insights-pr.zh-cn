---
title: 创建和管理环境
description: 了解如何注册服务以及如何管理环境。
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034166"
---
# <a name="manage-environments"></a>管理环境

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>切换环境

选择页面右上角中的 **环境** 控件以更改环境。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="用于切换环境的控件的屏幕截图。":::

管理员可以[创建](get-started-paid.md)和管理环境。

## <a name="edit-an-existing-environment"></a>编辑现有环境

您可以编辑现有环境的某些详细信息。

1.  选择应用标题中的 **环境** 选择器。

2.  选择 **编辑** 图标。

3. 在 **编辑环境** 框中，可以更新环境的 **显示名称**，但不能更改 **区域** 或 **类型**。

4. 如果环境配置为在 Azure Data Lake Storage 中存储数据，您可以更新 **帐户密钥**。 但是，您不能更改 **帐户名称** 或 **容器** 名称。

5. 或者，您可以从基于帐户密钥的连接更新到基于资源或基于订阅的连接。 升级后，您将无法在更新后还原到帐户密钥。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 在更新连接时，无法更改 **容器** 信息。

6. （可选）您可以在 **配置与 Microsoft Dataverse 的数据共享并启用其他功能** 下面提供 Microsoft Dataverse 环境 URL。 这些功能包括基于应用和解决方案与 Microsoft Dataverse 共享数据、本地数据源数据引入或使用[预测](predictions.md)。 选择 **启用数据共享** 以与 Microsoft Dataverse 托管 Data Lake 共享 Customer Insights 输出数据。

   > [!NOTE]
   > - 将所有数据保存到自己的 Azure Data Lake Storage 时，当前不支持与 Microsoft Dataverse 托管 Data Lake 共享数据。
   > - 当您允许与 Microsoft Dataverse 托管 Data Lake 共享数据时，当前不支持访问群体见解中的[预测实体中缺少的值](predictions.md)和 PowerBI Embedded 报表（如果在您的环境中已启用）。

   启用与 Microsoft Dataverse 的数据共享后，将开始数据源和其他流程的完全刷新。 如果流程当前正在运行，则您看不到用于启用与 Microsoft Dataverse 共享数据的选项。 请等待这些流程完成或取消它们，以启用数据共享。 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="用于启用与 Microsoft Dataverse 的数据共享的配置选项。":::
   
   当您运行流程（例如数据引入或客户细分创建）时，将在上述指定的存储帐户中创建相应的文件夹。 数据文件和 model.json 文件将创建并添加到相应的子文件夹中，具体取决于您运行的流程。

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
- Common Data Model 文件夹和 Dataverse 托管的 Data Lake 中的数据源。 您必须使用与源环境中相同的名称手动创建这些数据源。

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
