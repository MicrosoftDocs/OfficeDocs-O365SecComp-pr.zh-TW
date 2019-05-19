---
title: 使用進階電子文件中的通訊
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 進階電子文件可以輕鬆管理周圍通知 custodians 法律調查中的合法持有通知工作流程。
ms.openlocfilehash: cf5c8f5e932993255bda2cb959657c2c6ded3163
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154905"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="e6a76-103">使用進階電子文件中的通訊</span><span class="sxs-lookup"><span data-stu-id="e6a76-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="e6a76-104">進階電子文件可以讓法務部門，以簡化繞追蹤和散佈合法持有通知其處理程序。</span><span class="sxs-lookup"><span data-stu-id="e6a76-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="e6a76-105">Custodian 通訊工具可讓法務部門來管理及自動化的整個法律保留程序，從初始通知，提醒，以及擴大，所有在一個位置。</span><span class="sxs-lookup"><span data-stu-id="e6a76-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="e6a76-106">合法持有通知是什麼？</span><span class="sxs-lookup"><span data-stu-id="e6a76-106">What is a legal hold notification?</span></span>

<span data-ttu-id="e6a76-107">合法持有 （也稱為*訴訟資料暫留*） 通知是寄送給從組織的法務部門的員工、 臨時員工、 或 custodians 可能是相關法律調查的資料的通知。</span><span class="sxs-lookup"><span data-stu-id="e6a76-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="e6a76-108">這些通知指示 custodians 來保留電子儲存的資訊，以及可能是相關法律專家作用中或即將發生的任何內容。</span><span class="sxs-lookup"><span data-stu-id="e6a76-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="e6a76-109">法律小組必須知道每個 custodian 已接收、 閱讀、 瞭解並同意遵守的特定指示。</span><span class="sxs-lookup"><span data-stu-id="e6a76-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="e6a76-110">法律保留通知程序</span><span class="sxs-lookup"><span data-stu-id="e6a76-110">The legal hold notification process</span></span>

<span data-ttu-id="e6a76-111">組織有責任保留的相關資訊，當它了解即將發生訴訟資料暫留或法規的調查。</span><span class="sxs-lookup"><span data-stu-id="e6a76-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="e6a76-112">若要遵守調查的保留需求，組織應該立即通知潛在 custodians 其陪審團来保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e6a76-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="e6a76-113">使用進階電子文件，法務小組可以建立並自訂其合法持有通知工作流程。</span><span class="sxs-lookup"><span data-stu-id="e6a76-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="e6a76-114">Custodian 通訊工具可以讓法務小組設定下列通知及工作流程：</span><span class="sxs-lookup"><span data-stu-id="e6a76-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="e6a76-115">**發行請注意**： 合法持有通知會發出 （或起始） 從法務部門通知給 custodians 人員可能會有區分大小專家的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e6a76-115">**Issuance notice**: A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="e6a76-116">此通知會指示 custodians 保留探索可能需要的任何資訊。</span><span class="sxs-lookup"><span data-stu-id="e6a76-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>
   
2.  <span data-ttu-id="e6a76-117">**重新發行請注意**： 期間情況下，custodians 可能需要其他內容 （或較少的內容） 保留較先前要求。</span><span class="sxs-lookup"><span data-stu-id="e6a76-117">**Re-Issuance notice**: During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="e6a76-118">此案例中，可以更新現有的保留通知，並重新發出到 custodians。</span><span class="sxs-lookup"><span data-stu-id="e6a76-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3.  <span data-ttu-id="e6a76-119">**版本請注意**： 一旦專家會解析及 custodian 不再受到保留需求，可以從這種情況釋放 custodian。</span><span class="sxs-lookup"><span data-stu-id="e6a76-119">**Release notice**: Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="e6a76-120">此外，您可以通知 custodian 它們不再需要保留內容，並提供有關如何繼續其資料與其一般工作活動的指示。</span><span class="sxs-lookup"><span data-stu-id="e6a76-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="e6a76-121">**提醒和呈報**： 在某些情況下，只發出通知是不足以滿足法律需求。</span><span class="sxs-lookup"><span data-stu-id="e6a76-121">**Reminders and escalations**: In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="e6a76-122">與每個通知法務小組可以排程提醒和呈報工作流程，以自動停止回應 custodians 的待處理一組。</span><span class="sxs-lookup"><span data-stu-id="e6a76-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow-up with unresponsive custodians.</span></span>

    - <span data-ttu-id="e6a76-123">**提醒**： 已發出或重新發行給一群 custodians 合法持有通知之後，組織可以設定提醒，提醒回應 custodians。</span><span class="sxs-lookup"><span data-stu-id="e6a76-123">**Reminders**:  After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

    - <span data-ttu-id="e6a76-124">**擴大**： 在某些情況下，如果 custodian 即使之後提醒一組經過一段時間，仍然無法回應法律小組可以設定呈報流程通知回應 custodians 和其主管。</span><span class="sxs-lookup"><span data-stu-id="e6a76-124">**Escalations**: In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

## <a name="role-groups-and-permissions"></a><span data-ttu-id="e6a76-125">角色群組和權限</span><span class="sxs-lookup"><span data-stu-id="e6a76-125">Role groups and permissions</span></span> 

<span data-ttu-id="e6a76-126">法律小組可以控制及隔離他們使用安全性 & 合規性中心的 eDiscovery 相關的角色群組和權限的案例活動。</span><span class="sxs-lookup"><span data-stu-id="e6a76-126">Legal teams can control and segregate their case activity using eDiscovery-related role groups and permissions in the Security & Compliance Center.</span></span> 

<span data-ttu-id="e6a76-127">若要建立及管理合法持有通知，使用者必須是下列角色群組的一部分：</span><span class="sxs-lookup"><span data-stu-id="e6a76-127">To create and manage legal hold notifications, a user must be part of the following role groups:</span></span>

- <span data-ttu-id="e6a76-128">**eDiscovery 管理員**這個角色群組的成員可以建立及管理 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="e6a76-128">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases.</span></span> <span data-ttu-id="e6a76-129">他們可以新增和移除成員，放置 custodians 及內容的位置上保留、 管理合法持有通知、 建立及編輯與案例相關聯的內容搜尋、 匯出內容搜尋結果，以及準備進階中分析的搜尋結果eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="e6a76-129">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="e6a76-130">有兩個此角色群組中的子群組。</span><span class="sxs-lookup"><span data-stu-id="e6a76-130">There are two sub-groups in this role group.</span></span> <span data-ttu-id="e6a76-131">這些子群組之間的差異根據範圍。</span><span class="sxs-lookup"><span data-stu-id="e6a76-131">The difference between these subgroups is based on scope.</span></span>

  - <span data-ttu-id="e6a76-132">**eDiscovery 管理員**-可檢視及管理 eDiscovery 案例他們建立或成員。</span><span class="sxs-lookup"><span data-stu-id="e6a76-132">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="e6a76-133">如果其他 eDiscovery 管理員會建立案例，但不會將第二個 eDiscovery 管理員新增為該案例的成員，第二個 eDiscovery 管理員無法檢視或在安全性 & 合規性中心中開啟 [eDiscovery] 頁面上的案例。</span><span class="sxs-lookup"><span data-stu-id="e6a76-133">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="e6a76-134">eDiscovery 管理員也可以存取其執行分析工作的進階電子文件中的案例。</span><span class="sxs-lookup"><span data-stu-id="e6a76-134">eDiscovery Managers can also access their cases in Advanced eDiscovery to perform analysis tasks.</span></span>

  - <span data-ttu-id="e6a76-135">**eDiscovery 系統管理員**-可以執行 eDiscovery 管理員可以執行的所有案例的管理工作。</span><span class="sxs-lookup"><span data-stu-id="e6a76-135">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="e6a76-136">此外，eDiscovery 系統管理員可以：</span><span class="sxs-lookup"><span data-stu-id="e6a76-136">Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="e6a76-137">檢視 [eDiscovery] 頁面上列出的所有案例。</span><span class="sxs-lookup"><span data-stu-id="e6a76-137">View all cases that are listed on the eDiscovery page.</span></span>
    - <span data-ttu-id="e6a76-138">在自行新增為案例的成員之後管理組織中的任何案例。</span><span class="sxs-lookup"><span data-stu-id="e6a76-138">Manage any case in the organization after they add themselves as a member of the case.</span></span>
    - <span data-ttu-id="e6a76-139">存取組織中任何案例的進階電子文件中的案例資料。</span><span class="sxs-lookup"><span data-stu-id="e6a76-139">Access case data in Advanced eDiscovery for any case in the organization.</span></span>

<span data-ttu-id="e6a76-140">如需詳細資訊，請參閱[指派安全性 & 合規性中心中的 eDiscovery 權限](../assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e6a76-140">For more information, see [Assign eDiscovery permissions in the Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>