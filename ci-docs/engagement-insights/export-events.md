---
title: 导出已优化的事件
description: 如何导出已优化的事件和基本事件。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232877"
---
# <a name="export-events"></a>导出事件

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

事件表示用户行为。 它记录用户查看页面（查看事件）或与内容交互（操作事件）的时间。 当您确定要在报表中显示的数据的属性时，数据的此虚拟视图称为 *已优化的事件*。 有关详细信息，请参阅[创建和修改事件](refined-events.md)。

- 您可以将事件和已优化的事件导出到外部存储中。 
- 导出是一个转发数据流。 无法重新填充该流。 
- 导出具有固定架构。 如果您将自定义属性添加到事件，则将不会包括它们。 您需要创建新的导出。

## <a name="prerequisites"></a>先决条件

在设置导出之前，您需要具有 Azure 门户的访问权限和可用订阅。 在导出过程中，您将需要提供存储帐户信息。 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>创建 Azure Data Lake Storage Gen 2 帐户

1. 登录到 Azure 门户并[创建新的存储帐户](/azure/storage/common/storage-account-create)。 

1. 确保在 **高级** 选项卡上启用 **分层命名空间**。 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="在高级选项卡上启用分层命名空间。":::

1. 部署它之后，转到新建的存储帐户。 在导航窗格中，选择 **设置** > **访问密钥**。 

1. 复制 **帐户名称** 和 **密钥** 以在创建新的导出时使用它们。
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="存储帐户中的访问密钥。":::

## <a name="export-events"></a>导出事件

有两种方法可以调出 **导出事件** 对话： 
- 转到 **数据** > **导出** 并选择 **新建导出**。
- 转到 **数据** > **事件**，选择要导出的事件旁边的 **更多 [...]**，然后从下拉菜单中选择 **导出**。 

:::image type="content" source="media/new-export.png" alt-text="创建新导出。":::

向导会引导您完成创建导出的步骤：

1. 提供 **导出名称**，然后选择 **下一步**。

1. 在 **事件选择** 下拉列表中，选择要包括在导出中的基本事件和已优化的事件。 

1. 在 **文件结构** 部分，选择在目标存储中创建新文件的频率（每小时或每天），然后选择 **下一步**。 当事件到达时，会持续导出它们。

1. 在 **选择格式** 对话中，选择导出的格式。 在 **Common Data Model**、**CSV** 和 **JSON** 格式之间选择。 要将导出与其他 Dynamics 365 应用程序一起使用，我们建议使用 **Common Data Model** 格式。

1. 在 **选择目标** 对话中，指定 Azure Data Lake Storage Gen 2 位置。
    1. **ADLS Gen 2 帐户名称** 是要将导出保存到的存储帐户的名称。 
    1. **文件夹路径** 定义存储帐户的文件系统和目录结构中用于存储导出的位置。
    1. **共享密钥** 可从存储帐户的 Azure 门户中获得。

1. 查看并确认您的选择，完成创建。

## <a name="view-and-manage-exports"></a>查看和管理导出

设置导出后，转到 **数据** > **导出** 以查看该导出。 对于任何现有导出选择 **更多 [...]** 以编辑或删除此导出。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
