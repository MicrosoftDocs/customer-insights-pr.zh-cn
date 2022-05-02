---
title: 试用常见问题 - Dynamics 365 Customer Insights
description: 与 Customer Insights 试用设置和管理相关的常见问题的解决方法。 了解如何解决特定于平台和应用的问题。
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 4a269a223efa08f71db09eef2ec9a8f8a077f7a7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641797"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Dynamics 365 Customer Insights 试用常见问题

## <a name="sign-up"></a>注册

### <a name="what-are-the-system-requirements-for-the-trial"></a>试用的系统要求是什么？

此应用是一项基于云的服务，此服务只需要最新的 Web 浏览器，而不需要特殊软件，但有一些限制。 为获得最佳试用体验，请避免以无痕浏览模式访问试用站点，并选择离您最近的试用位置。 [了解有关 Web 应用程序要求的详细信息。](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>如何在没有 Microsoft 365 租户的情况下注册试用？

您可以输入非工作电子邮件地址，我们将为您创建一个帐户和租户。

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>我是否可以注册多个 Dynamics 365 应用，例如 Sales、Marketing 和 Customer Service？

是，可以。 若要查看所有可用试用，请[访问试用中心页面](https://dynamics.microsoft.com/dynamics-365-free-trial)。 您可以使用同一个电子邮件帐户注册不同的试用。 但是，同一个试用站点上不能有多个应用。 每个试用将位于不同的组织和 URL。 试用数据不会跨应用共享。

## <a name="trial-app"></a>试用应用

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>注册后我未收到试用详细信息电子邮件，我应该怎么做？

当您注册试用时，您将收到一封包含试用详细信息的电子邮件。 如果您在收件箱中没有看到此电子邮件，请检查您的垃圾邮件文件夹。 或者，使用以下步骤访问您的应用：

1. 转到试用站点，选择 **免费试用**。
1. 输入您用于注册试用的电子邮件 ID。 您将重定向到您的试用应用。

### <a name="how-do-i-add-more-users-to-a-trial"></a>如何将更多用户添加到试用中？

若要添加用户，请使用试用管理员帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。 按照[管理中心指南](/microsoft-365/admin/add-users/add-users)添加用户，数量不能超过试用许可证限制。 如果您添加的用户已经有 Microsoft 365 帐户，请在试用组织中为他们分派相应的安全角色。有关详细信息，请参阅[为用户分派安全角色](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user)。

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>我可以将多少用户添加到我的试用环境中？

您可以将无限数量的用户添加到试用环境中。

### <a name="how-do-i-reset-the-trial-environment"></a>如何重置试用环境？

您无法重置试用环境。 但是，您可以等待试用期结束，然后重新注册新试用。

## <a name="trial-expiration-and-extension"></a>试用到期和延长

### <a name="how-do-i-extend-the-trial"></a>如何延长试用？

您可以直接在应用中延长试用。 您可以延长一次试用。

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>我是否可以将试用转换为付费许可证？

通常，我们建议在升级到 Customer Insights 的付费版本时使用您自己的数据重新开始。 

或者，如果您仅使用 Customer Insights，可以在购买 Customer Insights 后从试用环境复制数据。 您必须是 Customer Insights 试用版的管理员和 Microsoft 365 租户的全局管理员，或者是您组织中的 Dynamics 365 管理员，才能将设置从试用环境迁移到付费环境。 

首次登录 Customer Insights 的付费实例后，系统会要求您创建一个新环境。 在此过程中，您可以选择从现有环境复制配置并迁移大部分设置。 如果您拥有上述权限，试用环境将显示在此列表中。 有关详细信息，请参阅[复制环境配置](manage-environments.md#copy-the-environment-configuration)。

### <a name="what-are-the-trial-limits-and-quotas"></a>试用限制和配额是多少？

- 在 Customer Insights 试用期间，您不能使用自己的 Azure Data Lake Storage 帐户存储输出数据。 但是，您可以通过 Data Lake 存储帐户来引入数据。
- 您可以在 Dataverse 环境中存储最多 3 GB 的数据，在您开始试用 Customer Insights 时会自动预配该环境。

## <a name="customer-insights-specific-questions"></a>Customer Insights 特定问题

### <a name="how-do-i-start-using-the-trial"></a>我如何开始使用试用？

注册试用后，您将进入应用的主屏幕。 主屏幕提供指向用户指南和教程的链接。 要了解详细信息，请访问试用注册页面上[其他资源](trial-signup.md#additional-resources)中的链接。

### <a name="what-features-are-available-in-the-trial"></a>试用版中有哪些可用功能?

Customer Insights 功能的大多数功能在试用中都可用。

以下功能 **不可用**： 
- 不能创建使用您自己的 Azure Data Lake Storage 帐户的新环境。
- 您无法删除试用环境。 

### <a name="how-long-does-the-trial-last"></a>试用持续多长时间？

Customer Insights 试用期为 30 天。 您可以在登录试用环境 23 天后延长试用一次。

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>如何从试用中删除示例数据？

不能从试用中删除示例数据。
