---
title: 安全性與合規性中心內的郵件流程深入解析
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以了解安全性 & 合規性中心中的郵件流程儀表板。
ms.openlocfilehash: 402fcf0ac29ecd67c9ecbc2e46c47d9a6392eedd
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598899"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="ff6b5-103">安全性與合規性中心內的郵件流程深入解析</span><span class="sxs-lookup"><span data-stu-id="ff6b5-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="ff6b5-104">系統管理員可以使用郵件流程儀表板中的安全性 & 合規性中心探索趨勢，深入了解，並採取動作，以修正與 Office 365 組織中的郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="ff6b5-105">深入了解、 報告和郵件流程儀表板中可用的 widget 如下：</span><span class="sxs-lookup"><span data-stu-id="ff6b5-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="ff6b5-106">郵件流程地圖報表</span><span class="sxs-lookup"><span data-stu-id="ff6b5-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="ff6b5-107">網域郵件流程狀態深入解析</span><span class="sxs-lookup"><span data-stu-id="ff6b5-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="ff6b5-108">SMTP 驗證的用戶端報告</span><span class="sxs-lookup"><span data-stu-id="ff6b5-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="ff6b5-109">寄件者網域深入解析</span><span class="sxs-lookup"><span data-stu-id="ff6b5-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="ff6b5-110">未傳遞報告</span><span class="sxs-lookup"><span data-stu-id="ff6b5-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="ff6b5-111">非公認的網域報表</span><span class="sxs-lookup"><span data-stu-id="ff6b5-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="ff6b5-112">外寄和內送的郵件流程</span><span class="sxs-lookup"><span data-stu-id="ff6b5-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="ff6b5-113">佇列的警示和佇列</span><span class="sxs-lookup"><span data-stu-id="ff6b5-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="ff6b5-114">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="ff6b5-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="ff6b5-115">郵件迴圈深入解析</span><span class="sxs-lookup"><span data-stu-id="ff6b5-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="ff6b5-116">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="ff6b5-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="ff6b5-117">若要檢視的郵件流程儀表板所需權限</span><span class="sxs-lookup"><span data-stu-id="ff6b5-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="ff6b5-118">郵件流程儀表板的可：</span><span class="sxs-lookup"><span data-stu-id="ff6b5-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="ff6b5-119">**Office 365 全域系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="ff6b5-120">**Office 365 Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="ff6b5-121">安全性 & 合規性中心中的**郵件流程系統管理員角色**的成員。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="ff6b5-122">如果不是全域系統管理員或 Exchange 系統管理員角色的成員的使用者明確指派這個角色：</span><span class="sxs-lookup"><span data-stu-id="ff6b5-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="ff6b5-123">使用者必須登入安全性 & 合規性中心，直接在[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="ff6b5-124">使用者將只有郵件流程儀表板的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="ff6b5-125">使用者無法存取 Office 365 系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="ff6b5-126">如需有關 Office 365 全域系統管理員角色的詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ff6b5-127">將安全性 & 合規性中心角色指派給使用者的詳細資訊，請參閱[授與使用者存取安全性 & 合規性中心](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="ff6b5-128">哪裡可以找到的郵件流程儀表板</span><span class="sxs-lookup"><span data-stu-id="ff6b5-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="ff6b5-129">移至安全性 & 合規性中心，在 [ [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="ff6b5-130">依序展開 [**郵件流程**，然後選取 [**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="ff6b5-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![在 Office 365 安全性 & 合規性中心中郵件流程儀表板](media/mail-flow-dashboard-v2.png)
