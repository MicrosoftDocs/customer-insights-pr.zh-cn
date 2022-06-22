---
title: 将 Common Data Model 数据连接到 Azure Data Lake 帐户
description: 使用 Azure Data Lake Storage 处理 Common Data Model 数据。
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011546"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>在 Azure Data Lake Storage 中连接到数据

使用您的 Azure Data Lake Storage Gen2 帐户将数据引入 Dynamics 365 Customer Insights。 数据引入可以是完整的或增量的。

## <a name="prerequisites"></a>先决条件

- 数据引入仅支持 Azure Data Lake Storage *Gen2* 帐户。 您不能使用 Data Lake Storage Gen1 帐户引入数据。

- Azure Data Lake Storage 帐户必须[已启用分层命名空间](/azure/storage/blobs/data-lake-storage-namespace)。 数据必须以分层文件夹格式存储，该格式定义根文件夹，每个实体都有子文件夹。 子文件夹可以有完整数据或增量数据文件夹。

- 若要使用 Azure 服务主体进行身份验证，请确保已在您的租户中配置它。 有关详细信息，请参阅[使用 Azure 服务主体连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。

- 您要从其连接和引入数据的 Azure Data Lake Storage 必须与 Dynamics 365 Customer Insights 环境位于同一 Azure 区域中。 不支持从不同的 Azure 区域中的 Data Lake 连接到 Common Data Model 文件夹。 若要了解该环境的 Azure 区域，请在 Customer Insights 中转到 **管理** > **系统** > **关于**

- 联机服务中存储的数据可以存储在与在 Dynamics 365 Customer Insights 中处理或存储数据不同的位置。导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心](https://www.microsoft.com/trust-center)。

- Customer Insights 服务主体必须具有以下角色之一才能访问存储帐户。 有关详细信息，请参阅[向服务主体授予访问存储帐户的权限](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account)。
  - 存储 Blob 数据读取器
  - 存储 Blob 数据负责人
  - 存储 Blob 数据参与者

- Data Lake Storage 中的数据应遵循 Common Data Model 标准来存储数据，并应具有 Common Data Model 清单来表示数据文件的架构（*.csv 或 *.parquet）。 清单必须提供实体的详细信息，如实体列和数据类型，以及数据文件位置和文件类型。 有关详细信息，请参阅 [Common Data Model 清单](/common-data-model/sdk/manifest)。 如果清单不存在，具有存储 Blob 数据负责人或存储 Blob 数据参与者访问权限的管理员用户可以在引入数据时定义架构。

## <a name="connect-to-azure-data-lake-storage"></a>连接到 Azure Data Lake Storage

1. 转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **Azure data lake storage**。

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="用于输入 Azure Data Lake 的连接详细信息的对话框。" lightbox="media/data_sources_ADLS.png":::

1. 为数据源输入 **名称** 和 **说明**（可选）。 名称唯一标识数据源，将在下游流程中引用且无法更改。

1. 为 **连接存储使用的是** 选择以下选项之一。 有关详细信息，请参阅[使用 Azure 服务主体将 Customer Insights 连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。

   - **Azure 资源**：输入 **资源 ID**。或者，如果要通过 Azure 专用链接从存储帐户引入数据，选择 **启用专用链接**。 有关详细信息，请参阅[专用链接](security-overview.md#private-links-tab)。
   - **Azure 订阅**：选择 **订阅**，然后选择 **资源组** 和 **存储帐户**。 或者，如果要通过 Azure 专用链接从存储帐户引入数据，选择 **启用专用链接**。 有关详细信息，请参阅[专用链接](security-overview.md#private-links-tab)。
  
   > [!NOTE]
   > 您需要容器或存储帐户的以下角色之一来创建数据源：
   >
   >  - 存储 Blob 数据读取器足以从存储帐户读取数据并将数据引入 Customer Insights。 
   >  - 如果您要直接在 Customer Insights 中编辑清单文件，则必须是存储 Blob 数据参与者或负责人。  
  
1. 选择包含要从中导入数据的数据和架构（model.json 或 manifest.json 文件）的 **容器** 的名称，然后选择 **下一步**。
   > [!NOTE]
   > 与环境中其他数据源相关联的任何 model.json 或 manifest.json 文件都不会显示在列表中。 但是，相同的 model.json 或 manifest.json 文件可用于多个环境中的数据源。

1. 要创建新架构，请转到[创建新架构文件](#create-a-new-schema-file)。

1. 要使用现有架构，请导航到包含 model.json 或 manifest.cdm.json 文件的文件夹。 您可以在目录中搜索来查找该文件。

1. 选择 json 文件，然后选择 **下一步**。 可用实体列表将显示。

   :::image type="content" source="media/review-entities.png" alt-text="要选择的实体列表的对话框":::

1. 选择要包括的实体。

   :::image type="content" source="media/ADLS_required.png" alt-text="主键显示&quot;必需&quot;的对话框":::

   > [!TIP]
   > 要在 JSON 编辑界面中编辑实体，选择 **显示更多** > **编辑架构文件**。 进行更改，然后选择 **保存**。

1. 对于需要增量引入的选定实体，**增量刷新** 下会显示 **必需**。 对于每个实体，请参阅[为 Azure Data Lake 数据源配置增量刷新](incremental-refresh-data-sources.md)。

1. 对于未定义主键的选定实体，**主键** 下将显示 **必需**。 对于每个实体：
   1. 选择 **必需**。 **编辑实体** 面板将显示。
   1. 选择 **主键**。 主键是实体所特有的属性。 若要使属性成为有效主键，它不应包括重复值、缺少值或 null 值。 支持将字符串、整数和 GUID 数据类型属性作为主键。
   1. 或者，更改分区模式。
   1. 选择 **关闭** 保存并关闭面板。

1. 为每个包含的实体选择 **属性** 数量。 **管理属性** 页面将显示。

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="用于选择数据分析的对话框。":::

   1. 创建新属性，编辑或删除现有属性。 您可以更改名称、数据格式或添加语义类型。
   1. 要启用分析和其他功能，为整个实体或特定属性选择 **数据分析**。 默认情况下，不会为数据分析启用任何实体。
   1. 选择 **完成**。

1. 选择 **保存**。 **数据源** 页面将打开，显示处于 **正在刷新** 状态的新数据源。

### <a name="create-a-new-schema-file"></a>创建新架构文件

1. 选择 **新建架构文件**。

1. 为文件输入名称，然后选择 **保存**。

1. 选择 **新建实体**。 **新建实体** 面板将显示。

1. 输入实体名称并选择 **数据文件位置**。
   - **多个 .csv 或 .parquet 文件**：浏览到根文件夹，选择模式类型，然后输入表达式。
   - **单个 .csv 或 .parquet 文件**：浏览到 .csv 或 .parquet 文件，选择该文件。

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="用于创建新实体的对话框，突出显示数据文件位置。":::

1. 选择 **保存**。

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="用于定义或自动生成属性的对话框。":::

1. 选择 **定义属性** 手动添加属性，或选择 **自动生成属性**。 要定义属性，输入名称，然后选择数据格式和可选语义类型。 对于自动生成的属性：

   1. 属性自动生成后，选择 **查看属性**。 **管理属性** 页面将显示。

   1. 确保每个属性的数据格式都是正确的。

   1. 要启用分析和其他功能，为整个实体或特定属性选择 **数据分析**。 默认情况下，不会为数据分析启用任何实体。

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="用于选择数据分析的对话框。":::

   1. 选择 **完成**。 **选择实体** 页面将显示。

1. 继续添加实体和属性（如果适用）。

1. 添加所有实体后，选择 **包括** 在数据源引入中包括实体。

   :::image type="content" source="media/ADLS_required.png" alt-text="主键显示&quot;必需&quot;的对话框":::

1. 对于需要增量引入的选定实体，**增量刷新** 下会显示 **必需**。 对于每个实体，请参阅[为 Azure Data Lake 数据源配置增量刷新](incremental-refresh-data-sources.md)。

1. 对于未定义主键的选定实体，**主键** 下将显示 **必需**。 对于每个实体：
   1. 选择 **必需**。 **编辑实体** 面板将显示。
   1. 选择 **主键**。 主键是实体所特有的属性。 若要使属性成为有效主键，它不应包括重复值、缺少值或 null 值。 支持将字符串、整数和 GUID 数据类型属性作为主键。
   1. 或者，更改分区模式。
   1. 选择 **关闭** 保存并关闭面板。

1. 选择 **保存**。 **数据源** 页面将打开，显示处于 **正在刷新** 状态的新数据源。


## <a name="edit-an-azure-data-lake-storage-data-source"></a>编辑 Azure Data Lake Storage 数据源

您可以更新 *连接存储帐户使用的是* 选项。 有关详细信息，请参阅[使用 Azure 服务主体将 Customer Insights 连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 若要连接到除存储帐户之外的容器，或更改帐户名称，应[创建新的数据源连接](#connect-to-azure-data-lake-storage)。

1. 转到 **数据** > **数据源**。

1. 在要更新的数据源旁边，选择 **编辑**。

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="用于编辑 Azure Data Lake 数据源的对话框。":::

1. 更改以下任一信息：

   - **说明**
   - **连接存储使用的是** 和连接信息。 在更新连接时，无法更改 **容器** 信息。
      > [!NOTE]
      > 必须将以下角色之一分配给存储帐户或容器：
        > - 存储 Blob 数据读取器
        > - 存储 Blob 数据负责人
        > - 存储 Blob 数据参与者

   - 如果要通过 Azure 专用链接从存储帐户引入数据，**启用专用链接**。 有关详细信息，请参阅[专用链接](security-overview.md#private-links-tab)。

1. 选择 **下一步**。
1. 更改以下任一信息：
   - 导航到具有来自容器的不同实体集的不同 model.json 或 manifest.json 文件。
   - 要添加将要引入的其他实体，选择 **新建实体**。
   - 如果没有依赖关系，要删除任何已选择的实体，选择该实体，然后选择 **删除**。
      > [!IMPORTANT]
      > 如果现有 model.json 或 manifest.json 文件以及实体集上存在依赖项，则会看到错误消息，并且无法选择其他 model.json 或 manifest.json 文件。 在更改 model.json 或 manifest.json 文件或使用想要避免删除依赖项的 model.json 或 manifest.json 文件创建新数据源之前，请删除这些依赖项。
   - 要更改数据文件位置或主键，选择 **编辑**。
   - 要更改增量引入数据，请参阅[为 Azure Data Lake 数据源配置增量刷新](incremental-refresh-data-sources.md)

1. 选择 **属性** 添加或更改属性，或启用数据分析。 然后选择 **完成**。

1. 单击 **保存** 应用您的更改并返回到 **数据源** 页面。
