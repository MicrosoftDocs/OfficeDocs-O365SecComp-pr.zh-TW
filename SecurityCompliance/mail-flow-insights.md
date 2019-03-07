---
title: 在安全性 & 合規性中心中的郵件流程深入解析
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以了解安全性 & 合規性中心中的郵件流程儀表板。
ms.openlocfilehash: 1e18bcb381a6b557d3141c0c17b8433cfcd00049
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455145"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="2dd2b-103">在安全性 & 合規性中心中的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="2dd2b-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="2dd2b-104">系統管理員可以使用郵件流程儀表板中的安全性 & 合規性中心探索趨勢，深入了解，並採取動作，以修正與 Office 365 組織中的郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="2dd2b-105">深入了解、 報告和郵件流程儀表板中可用的 widget 如下：</span><span class="sxs-lookup"><span data-stu-id="2dd2b-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="2dd2b-106">外寄和內送的郵件流程</span><span class="sxs-lookup"><span data-stu-id="2dd2b-106">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="2dd2b-107">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="2dd2b-107">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="2dd2b-108">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="2dd2b-108">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="2dd2b-109">郵件迴圈深入解析</span><span class="sxs-lookup"><span data-stu-id="2dd2b-109">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="2dd2b-110">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="2dd2b-110">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="2dd2b-111">若要檢視的郵件流程儀表板所需權限</span><span class="sxs-lookup"><span data-stu-id="2dd2b-111">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="2dd2b-112">郵件流程儀表板的可：</span><span class="sxs-lookup"><span data-stu-id="2dd2b-112">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="2dd2b-113">**Office 365 全域系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-113">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="2dd2b-114">**Office 365 Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-114">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="2dd2b-115">安全性 & 合規性中心中的**郵件流程系統管理員角色**的成員。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-115">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="2dd2b-116">如果不是全域系統管理員或 Exchange 系統管理員角色的成員的使用者明確指派這個角色：</span><span class="sxs-lookup"><span data-stu-id="2dd2b-116">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="2dd2b-117">使用者必須登入安全性 & 合規性中心，直接在[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-117">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="2dd2b-118">使用者將只有郵件流程儀表板的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-118">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="2dd2b-119">使用者無法存取 Office 365 系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-119">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="2dd2b-120">如需有關 Office 365 全域系統管理員角色的詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-120">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

<span data-ttu-id="2dd2b-121">將安全性 & 合規性中心角色指派給使用者的詳細資訊，請參閱[授與使用者存取安全性 & 合規性中心](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76)。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-121">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="2dd2b-122">哪裡可以找到的郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="2dd2b-122">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="2dd2b-123">移至安全性 & 合規性中心，在 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-123">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="2dd2b-124">依序展開 [**郵件流程**，然後選取 [**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="2dd2b-124">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![在 Office 365 安全性 & 合規性中心中郵件流程儀表板](media/f32f5c0a-ea32-4e47-a477-d070405d4ae8.png)
