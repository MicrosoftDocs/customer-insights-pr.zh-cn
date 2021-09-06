---
title: 将 Common Data Model 数据连接到 Azure Data Lake 帐户
description: 使用 Azure Data Lake Storage 处理 Common Data Model 数据。
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 93871f8029053d4ed4a116d3af3550b7684ee11ea8633e937138245e193a44e6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033115"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>使用 Azure Data Lake 帐户连接到 Common Data Model 文件夹

本文提供有关如何使用 Azure Data Lake Storage Gen2 帐户从 Common Data Model 文件夹中引入数据的信息。

## <a name="important-considerations"></a>重要考虑因素

- Azure Data Lake 中的数据需要遵守 Common Data Model 标准。 目前不支持其他格式。

- 数据引入将以独占方式支持 Azure Data Lake *Gen2* 存储帐户。 您不能使用 Azure Data Lake Gen1 存储帐户来引入数据。

- 若要使用 Azure 服务主体进行身份验证，请确保已在您的租户中配置它。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。

- 您想要从中连接和引入数据的 Azure Data Lake 必须位于 Dynamics 365 Customer Insights 环境所在的同一 Azure 区域中。 不支持从不同的 Azure 区域中的 Data Lake 连接到 Common Data Model 文件夹。 若要了解环境的 Azure 区域，请在访问群体见解中转到 **管理员** > **系统** > **关于**。

- 联机服务中存储的数据可以存储在与在 Dynamics 365 Customer Insights 中处理或存储数据不同的位置。导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>连接到 Common Data Model 文件夹

1. 在访问群体见解中，转到 **数据** > **数据源**。

1. 选择 **添加数据源**。

1. 选择 **连接到 Common Data Model 文件夹**，输入数据源的 **名称**，然后选择 **下一步**。 命名准则： 
   - 以字母开头。
   - 只能使用字母和数字。 不允许使用特殊字符和空格。
   - 使用 3 至 64 个字符。

1. 您可以在使用基于资源的选项进行身份验证和基于订阅的选项进行身份验证之间进行选择。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 输入 **容器** 信息并选择 **下一步**。
   > [!div class="mx-imgBorder"]
   > ![用于输入 Azure Data Lake 的新连接详细信息的对话框。](media/enter-new-storage-details.png)
   > [!NOTE]
   > 您需要具有下列角色之一才能连接到上面所引用的容器或存储帐户，以及创建数据源：
   >  - 存储 Blob 数据读取器
   >  - 存储 Blob 数据负责人
   >  - 存储 Blob 数据参与者

1. 在 **选择 Common Data Model 文件夹** 对话框中，选择要从中导入数据的 model.json 或 manifest.json 文件，然后选择 **下一步**。
   > [!NOTE]
   > 与环境中其他数据源相关联的任何 model.json 或 manifest.json 文件都不会显示在列表中。

1. 您将获得所选 model.json 或 manifest.json 文件中可用实体的列表。 您可以查看并从可用实体列表中进行选择，然后选择 **保存**。 将从新的数据源中引入所有选定实体。
   > [!div class="mx-imgBorder"]
   > ![其中显示了 model.json 文件中的实体列表的对话框。](media/review-entities.png)

8. 指示想要哪些数据实体启用数据分析，然后选择 **保存**。 数据分析可启用分析和其他功能。 您可以选择整个实体（选择实体中的所有属性），也可以选择所选的某些属性。 默认情况下，不会为数据分析启用任何实体。
   > [!div class="mx-imgBorder"]
   > ![显示数据分析的对话框。](media/dataprofiling-entities.png)

9. 保存所作选择后，**数据源** 页面将打开。 现在，您应该会看到作为数据源的 Common Data Model 文件夹连接。

> [!NOTE]
> Model.json 或 manifest.json 文件只能与同一环境中的一个数据源相关联。 但是，相同的 model.json 或 manifest.json 文件可用于多个环境中的数据源。

## <a name="edit-a-common-data-model-folder-data-source"></a>编辑 Common Data Model 文件夹数据源

您可以更新包含 Common Data Model 文件夹的存储帐户的访问密钥。 您也可以更改 model.json 或 manifest.json 文件。 若要连接到除存储帐户之外的容器，或更改帐户名称，应[创建新的数据源连接](#connect-to-a-common-data-model-folder)。

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择要更新的数据源旁边的省略号。

3. 从列表中选择 **编辑** 选项。

4. （可选）更新 **访问密钥**，然后选择 **下一步**。

   ![用于编辑和更新现有数据源的访问密钥的对话框。](media/edit-access-key.png)

5. 或者，您可以从帐户密钥连接更新到基于资源或基于订阅的连接。 有关详细信息，请参阅[使用 Azure 服务主体将访问群体见解连接到 Azure Data Lake Storage Gen2 帐户](connect-service-principal.md)。 在更新连接时，无法更改 **容器** 信息。
   > [!div class="mx-imgBorder"]

   > ![用于输入 Azure Data Lake 到现有存储帐户的连接详细信息的对话框。](media/enter-existing-storage-details.png)

   > [!NOTE]
   > 您需要具有下列角色之一才能连接到上面所引用的容器或存储帐户，以及创建数据源：
   >  - 存储 Blob 数据读取器
   >  - 存储 Blob 数据负责人
   >  - 存储 Blob 数据参与者


6. （可选）从容器中选择另一个具有不同实体集的 model.json 或 manifest.json 文件。

7. 或者，您可以选择要引入的其他实体。 如果没有任何依赖项，还可以删除任何已选定的实体。

   > [!IMPORTANT]
   > 如果现有 model.json 或 manifest.json 文件以及实体集上存在依赖项，则会看到错误消息，并且无法选择其他 model.json 或 manifest.json 文件。 在更改 model.json 或 manifest.json 文件或使用想要避免删除依赖项的 model.json 或 manifest.json 文件创建新数据源之前，请删除这些依赖项。

8. 或者，您可以选择其他属性或实体以启用数据分析或禁用所选项。   


[!INCLUDE[footer-include](../includes/footer-banner.md)]