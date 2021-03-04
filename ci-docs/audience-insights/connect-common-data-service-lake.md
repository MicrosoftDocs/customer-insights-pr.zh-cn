---
title: 连接到 Common Data Service 托管湖中的实体
description: 从 Common Data Service 托管数据湖导入数据。
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267792"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>连接到 Common Data Service 托管数据湖中的数据

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

本文提供有关现有 Dynamics 365 客户如何快速连接他们到 Common Data Service 托管湖中的分析实体的信息。 您必须是 Common Data Service 组织的管理员才能继续和查看托管湖中提供的实体列表。

## <a name="important-considerations"></a>重要考虑因素

可以将联机服务（如 Azure Data Lake Storage）中存储的数据存储到 Dynamics 365 Customer Insights 中处理或存储数据之外的位置。导入或连接到联机服务中存储的数据即表示您同意可将数据传输到和存储到 Dynamics 365 Customer Insights。 [有关详细信息，请访问 Microsoft 信任中心。](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>连接到 Common Data Service 托管湖

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择 **添加数据源**。

3. 选择 **连接到 Common Data Service**，然后选择 **下一步**。

4. 输入数据源的 **名称**，然后选择 **下一步**。 命名准则： 
   - 以字母开头。
   - 只能使用字母和数字。 不允许使用特殊字符和空格。
   - 使用 3 至 64 个字符。

5. 提供您的 Common Data Service 组织的 **服务器地址**，然后选择 **登录**。

   > [!div class="mx-imgBorder"]
   > ![用于输入 Common Data Service 服务器地址的对话框](media/enter-CDS-org-details.png)

6. 选择您希望从可用列表中引入的实体。    

   > [!NOTE]
   > 如果已经选择了某些实体，其他 Dynamics 365 应用程序（例如 Dynamics 365 Sales Insights 或 Customer Service Insights）可能会使用它们。 您不能更改此选择。 这些实体在创建数据源后即可供使用。

   > [!div class="mx-imgBorder"]
   > ![显示 Common Data Service 组织中的实体列表的对话框](media/select-analytical-entities.png)

7. 保存您的选择以开始将所选实体同步到 Common Data Service 托管湖。 您将在 **数据源** 页上找到新添加的连接。 它将排队等待刷新，显示实体计数为 0，直到所有实体都同步为止。

仅环境中的一个数据源可以同时使用相同的 Common Data Service 托管湖。

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>编辑 Common Data Service 托管湖数据源

您仅在创建数据源之后才编辑对实体的选择。 例如，如果其他实体被添加到 Common Data Service 中，并且您也希望导入它们。    
要连接到其他 Common Data Service，请[创建新数据源](#connect-to-a-common-data-service-managed-lake)。

1. 在访问群体见解中，转到 **数据** > **数据源**。

2. 选择要更新的数据源旁边的省略号。

3. 从列表中选择 **编辑** 选项。

4. 从可用实体列表中选择其他实体，然后选择 **保存**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]