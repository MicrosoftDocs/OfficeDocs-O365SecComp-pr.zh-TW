---
title: 安全性 & 規範中心中的郵件流程觀點
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可了解安全性 & 規範中心中的郵件流程儀表板。
ms.openlocfilehash: 481815430a91413cc96b92c074bd2d62771751ee
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685382"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="be539-103">安全性 & 規範中心中的郵件流程觀點</span><span class="sxs-lookup"><span data-stu-id="be539-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="be539-104">系統管理員可以使用郵件流程儀表板中安全性 & 規範中心可探索觀點的趨勢，並採取動作以修正與 Office 365 組織中的郵件流程相關的問題。</span><span class="sxs-lookup"><span data-stu-id="be539-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="be539-105">觀點、 報告及郵件流程儀表板中可用的 widget 是：</span><span class="sxs-lookup"><span data-stu-id="be539-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="be539-106">輸出及輸入郵件流程</span><span class="sxs-lookup"><span data-stu-id="be539-106">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="be539-107">佇列提醒和佇列</span><span class="sxs-lookup"><span data-stu-id="be539-107">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="be539-108">自動轉寄郵件報告</span><span class="sxs-lookup"><span data-stu-id="be539-108">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="be539-109">郵件迴圈洞察力</span><span class="sxs-lookup"><span data-stu-id="be539-109">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="be539-110">慢速郵件流程規則洞察力</span><span class="sxs-lookup"><span data-stu-id="be539-110">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="be539-111">若要檢視郵件流程儀表板所需的權限</span><span class="sxs-lookup"><span data-stu-id="be539-111">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="be539-112">郵件流程儀表板是提供：</span><span class="sxs-lookup"><span data-stu-id="be539-112">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="be539-113">**Office 365 全域管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="be539-113">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="be539-114">**Office 365 Exchange 系統管理員**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="be539-114">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="be539-p101">安全性 & 規範中心中的**郵件流程系統管理員角色**的成員。如果此角色會明確地指派給使用者不是全域管理員或 Exchange 系統管理員角色的成員：</span><span class="sxs-lookup"><span data-stu-id="be539-p101">Members of the **Mail flow administrator role** in the Security & Compliance Center. If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="be539-117">使用者必須登入直接在 「 安全性 & 規範中心[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="be539-117">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="be539-118">使用者只會有郵件流程儀表板唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="be539-118">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="be539-119">使用者不會有存取 Office 365 系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="be539-119">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="be539-120">如需 Office 365 全域管理員角色的詳細資訊，請參閱 ＜[關於 Office 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="be539-120">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

<span data-ttu-id="be539-121">如需將安全性 & 規範中心角色指派給使用者，請參閱[授與使用者存取安全性 & 規範中心](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76)。</span><span class="sxs-lookup"><span data-stu-id="be539-121">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="be539-122">郵件流程儀表板的所在位置</span><span class="sxs-lookup"><span data-stu-id="be539-122">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="be539-123">移至 [安全性 & 規範中心[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="be539-123">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="be539-124">依序展開 [**郵件流程**，然後選取 [**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="be539-124">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 安全性 & 規範中心的郵件流程儀表板](media/f32f5c0a-ea32-4e47-a477-d070405d4ae8.png)
