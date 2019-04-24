---
title: 進階電子文件 （預覽） 的版本資訊
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文包含 release notes for 進階電子文件 （預覽）。
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240938"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a><span data-ttu-id="6b66f-103">進階電子文件 （預覽） 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="6b66f-103">Release notes for Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="6b66f-104">進階電子文件的公開預覽程式是搶先即將推出的功能和更新的方式。</span><span class="sxs-lookup"><span data-stu-id="6b66f-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="6b66f-105">若要搶先使用最新功能，剛建立，並在 Office 365 安全性 & 合規性中心中使用進階電子文件 （預覽） 案例。</span><span class="sxs-lookup"><span data-stu-id="6b66f-105">To get early access to the newest features, just create and use an Advanced eDiscovery (Preview) case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="6b66f-106">請參閱[建立新的案例](create-new-ediscovery-case.md)。</span><span class="sxs-lookup"><span data-stu-id="6b66f-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="6b66f-107">已知問題</span><span class="sxs-lookup"><span data-stu-id="6b66f-107">Known issues</span></span>

<span data-ttu-id="6b66f-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="6b66f-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="6b66f-109">在進階電子文件 （預覽） 中使用 「 搜尋 」 工具來搜尋 custodian 信箱時，將無法搜尋資料對應在 2019 年 1 月 31 日之前建立的表單。</span><span class="sxs-lookup"><span data-stu-id="6b66f-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="6b66f-110">建立要用於搜尋此日期之後的表單。</span><span class="sxs-lookup"><span data-stu-id="6b66f-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="6b66f-111">即使刪除建立表單的使用者表單，建立由使用者仍然可以收到回應。</span><span class="sxs-lookup"><span data-stu-id="6b66f-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="6b66f-112">不過，這些回應 （發生之後 custodian 信箱已刪除） 的相對應的資料不會搜尋在進階電子文件 （預覽） 中使用 「 搜尋 」 工具來搜尋 custodian 信箱時。</span><span class="sxs-lookup"><span data-stu-id="6b66f-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span>
 
<span data-ttu-id="6b66f-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="6b66f-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="6b66f-114">在進階電子文件 （預覽） 中使用 「 搜尋 」 工具來搜尋 custodian 信箱時，如果使用者編輯 sway 剛之前的擁有者的使用者帳戶的刪除 sway，則這些變更可能不是可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="6b66f-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="6b66f-115">Sway 區塊變更 sway，只要該函數會收到已刪除帳戶的訊號。</span><span class="sxs-lookup"><span data-stu-id="6b66f-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="6b66f-116">不過，沒有小型機率之前收到此訊號，是否可以編輯 sway。</span><span class="sxs-lookup"><span data-stu-id="6b66f-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="6b66f-117">在此版本修正的問題</span><span class="sxs-lookup"><span data-stu-id="6b66f-117">Issues fixed in this release</span></span>

- <span data-ttu-id="6b66f-118">DCR： 例外處理未編製索引的項目和孤立的項目</span><span class="sxs-lookup"><span data-stu-id="6b66f-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="6b66f-119">DCR： 保留通知</span><span class="sxs-lookup"><span data-stu-id="6b66f-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="6b66f-120">在 eDiscovery DCR: Custodians</span><span class="sxs-lookup"><span data-stu-id="6b66f-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="6b66f-121">新功能</span><span class="sxs-lookup"><span data-stu-id="6b66f-121">What’s new</span></span>

- <span data-ttu-id="6b66f-122">**安全性 & 合規性中心中的 Redesigned 導覽**– 進階電子文件 （預覽） 有新的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="6b66f-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery (Preview) has a new look and feel.</span></span> <span data-ttu-id="6b66f-123">使用進階電子文件 （預覽） 來管理多個案例的工作流程。</span><span class="sxs-lookup"><span data-stu-id="6b66f-123">Use Advanced eDiscovery (Preview) to manage more of your case workflow.</span></span>

- <span data-ttu-id="6b66f-124">**專案管理**– 沒有其他支援新案例的類型。</span><span class="sxs-lookup"><span data-stu-id="6b66f-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="6b66f-125">您也可以選取並儲存您最近和最愛的情況。</span><span class="sxs-lookup"><span data-stu-id="6b66f-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="6b66f-126">追蹤及監視活動內及其的情況下，使用新的儀表板。</span><span class="sxs-lookup"><span data-stu-id="6b66f-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="6b66f-127">**Custodian 管理**-新增和移除案例內的資料 custodians 使用者。</span><span class="sxs-lookup"><span data-stu-id="6b66f-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="6b66f-128">**Exchange、 OneDrive 及 microsoft Teams 整合**– 自動將使用者的目前信箱、 OneDrive for Business 帳戶及 Microsoft Teams 網站新增至案例。</span><span class="sxs-lookup"><span data-stu-id="6b66f-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="6b66f-129">**Custodian 通訊**– 傳送和管理您的組織代表的合法持有通知。</span><span class="sxs-lookup"><span data-stu-id="6b66f-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="6b66f-130">**Custodian 入口網站**-新的入口網站的存取其 active custodians 保留通知。</span><span class="sxs-lookup"><span data-stu-id="6b66f-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="6b66f-131">**深編製索引**– 重新編目已局部編製索引項目依需求。</span><span class="sxs-lookup"><span data-stu-id="6b66f-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="6b66f-132">**錯誤修復**– 修復或下載處理錯誤;這包含大型檔案類型、 密碼保護檔案，以及更多的補救支援。</span><span class="sxs-lookup"><span data-stu-id="6b66f-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="6b66f-133">**若要搜尋的增強功能**– 建立由識別 custodians 及/或位置的搜尋。</span><span class="sxs-lookup"><span data-stu-id="6b66f-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="6b66f-134">**工作集**– 管理、 追蹤，並將靜態的稽核設定的文件。</span><span class="sxs-lookup"><span data-stu-id="6b66f-134">**Working sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="6b66f-135">**檢閱**– 使用原生、 文字和附近原生檢視檢閱文件新增至您的工作集。</span><span class="sxs-lookup"><span data-stu-id="6b66f-135">**Review** – Use a native, text, and near-native view to review documents added to your working set.</span></span>

- <span data-ttu-id="6b66f-136">**Redact，加上標籤，並加上註解**– Redact 文字、 套用標記，以及當您檢閱文件註釋。</span><span class="sxs-lookup"><span data-stu-id="6b66f-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="6b66f-137">**分析供電檢閱**– 利用電子文件探索分析得以尋找、 搜尋及 cull 工作集內的結果。</span><span class="sxs-lookup"><span data-stu-id="6b66f-137">**Analytics-powered review**– Leverage eDiscovery analytics to find, search, and cull results within a working set.</span></span>

- <span data-ttu-id="6b66f-138">**工作**– 長時間執行程序的追蹤狀態。</span><span class="sxs-lookup"><span data-stu-id="6b66f-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="6b66f-139">**新增稽核的活動**– 追蹤和檢視新的稽核進階電子文件的活動。</span><span class="sxs-lookup"><span data-stu-id="6b66f-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
