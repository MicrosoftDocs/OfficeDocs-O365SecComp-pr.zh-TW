---
title: Office 365 Skype for Business 資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 商務用 skype 資料刪除說明。
ms.openlocfilehash: ca48a4bc57cdba7301a51cc6404a7d402166ffb0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261301"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="03b77-103">Office 365 中的商務資料刪除商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="03b77-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="03b77-104">商務用 Skype 提供封存的端對端即時訊息、 多方立即訊息和會議中的內容上傳活動。</span><span class="sxs-lookup"><span data-stu-id="03b77-104">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings.</span></span> <span data-ttu-id="03b77-105">封存功能，需要 Exchange，而且由使用者的 Exchange 信箱原有範圍暫止屬性，其封存電子郵件與 Skype for Business 內容所控制。</span><span class="sxs-lookup"><span data-stu-id="03b77-105">The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="03b77-106">商務用 Skype 中的所有封存會被視為 「 使用者層級封存 」 因為您啟用或停用它的一或多個特定使用者或群組的使用者建立、 設定及套用這些使用者的封存使用者層級原則。</span><span class="sxs-lookup"><span data-stu-id="03b77-106">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users.</span></span> <span data-ttu-id="03b77-107">從 [Skype 商務版系統管理中心內的封存設定沒有直接控制項。</span><span class="sxs-lookup"><span data-stu-id="03b77-107">There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="03b77-108">下列內容類型未封存於商務用 Skype:</span><span class="sxs-lookup"><span data-stu-id="03b77-108">The following types of content are not archived in Skype for Business:</span></span> 
- <span data-ttu-id="03b77-109">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="03b77-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="03b77-110">對等立即訊息和會議的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="03b77-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="03b77-111">應用程式共用的端對端即時訊息與會議</span><span class="sxs-lookup"><span data-stu-id="03b77-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="03b77-112">會議註釋</span><span class="sxs-lookup"><span data-stu-id="03b77-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="03b77-113">會議內容保留</span><span class="sxs-lookup"><span data-stu-id="03b77-113">Meeting Content Retention</span></span>
<span data-ttu-id="03b77-114">使用商務用 Skype 的客戶可以將內容上傳到 Skype 會議做為附件，例如 PowerPoint 簡報、 OneNote 檔案，以及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="03b77-114">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files.</span></span> <span data-ttu-id="03b77-115">上傳至會議的內容有如下的保留期：</span><span class="sxs-lookup"><span data-stu-id="03b77-115">The retention period for content that has been uploaded to a meeting is as follows:</span></span>
- <span data-ttu-id="03b77-116">**一次性會議**內容會保留 15 天從最後一個人離開會議的時間開始。</span><span class="sxs-lookup"><span data-stu-id="03b77-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="03b77-117">**週期性會議**內容會保留 15 天後最後一個人離開會議的最後一個工作階段。</span><span class="sxs-lookup"><span data-stu-id="03b77-117">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting.</span></span> <span data-ttu-id="03b77-118">如果某人加入相同的會議工作階段，15 天內，重設為保留計時器。</span><span class="sxs-lookup"><span data-stu-id="03b77-118">The retention timer resets if someone joins the same meeting session within 15 days.</span></span> <span data-ttu-id="03b77-119">例如，假設 Skype 會議排程進行每週為一年，而且檔案上傳至會議期間的第一個執行個體。</span><span class="sxs-lookup"><span data-stu-id="03b77-119">For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance.</span></span> <span data-ttu-id="03b77-120">如果至少一位人員加入會議工作階段每週，檔案會保留在 Skype for Business Online 伺服器一整年 plus 最後一個人離開最後一個數列的會議之後的 15 天。</span><span class="sxs-lookup"><span data-stu-id="03b77-120">If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="03b77-121">**立即開會會議**的內容會保留在會議結束時間之後的 8 小時。</span><span class="sxs-lookup"><span data-stu-id="03b77-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="03b77-122">如果使用者是未經授權或停用 （例如，如果**包含 userenabled**設為*False*），並再重新授權或之後，無法保留會議內容。</span><span class="sxs-lookup"><span data-stu-id="03b77-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="03b77-123">會議到期</span><span class="sxs-lookup"><span data-stu-id="03b77-123">Meeting Expiration</span></span>
<span data-ttu-id="03b77-124">使用者可以在特定會議結束之後存取該會議，但需注意下列到期時段：</span><span class="sxs-lookup"><span data-stu-id="03b77-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>
- <span data-ttu-id="03b77-125">**一次性會議**的會議排定的會議結束時間後的 14 天到期。</span><span class="sxs-lookup"><span data-stu-id="03b77-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="03b77-126">**具有結束日期的週期性會議**的會議的最後一個會議之排定的結束時間後的 14 天到期。</span><span class="sxs-lookup"><span data-stu-id="03b77-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="03b77-127">**立即開會會議**的會議會在 8 小時後到期。</span><span class="sxs-lookup"><span data-stu-id="03b77-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="03b77-128">白板共同作業</span><span class="sxs-lookup"><span data-stu-id="03b77-128">Whiteboard Collaboration</span></span>
<span data-ttu-id="03b77-129">在白板上所做的註釋，所有參與者都看得到。</span><span class="sxs-lookup"><span data-stu-id="03b77-129">Annotations made on whiteboards will be seen by all participants.</span></span> <span data-ttu-id="03b77-130">當儲存白板、 白板和所有註解將會儲存在 Skype for Business server，它會保留在根據會議內容到期原則管理員所設定的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="03b77-130">When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="03b77-131">音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="03b77-131">Audio Test Service</span></span>
<span data-ttu-id="03b77-132">您的聲音短 （大約 5 秒） 範例會記錄音訊測試服務通話期間。</span><span class="sxs-lookup"><span data-stu-id="03b77-132">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call.</span></span> <span data-ttu-id="03b77-133">語音範例是由您用來檢查及/或確認您 Skype for Business 呼叫根據錄製的品質的聲音品質。</span><span class="sxs-lookup"><span data-stu-id="03b77-133">The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording.</span></span> <span data-ttu-id="03b77-134">音訊測試服務呼叫結束時，會刪除語音範例。</span><span class="sxs-lookup"><span data-stu-id="03b77-134">When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="03b77-135">持續性群組聊天</span><span class="sxs-lookup"><span data-stu-id="03b77-135">Persistent Group Chat</span></span>
<span data-ttu-id="03b77-136">常設 Group Chat 儲存群組聊天交談的內容。</span><span class="sxs-lookup"><span data-stu-id="03b77-136">Persistent Group Chat stores the content of group chat conversations.</span></span> <span data-ttu-id="03b77-137">如果啟用，系統管理員可以控制在保留期間，這項資訊會儲存的伺服器，如果群組聊天歷程記錄封存的符合性或其他用途，並管理/修改會議室的任何屬性。</span><span class="sxs-lookup"><span data-stu-id="03b77-137">If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room.</span></span> <span data-ttu-id="03b77-138">具有不同角色的使用者有不同的存取權的保存的資料，如下所示：</span><span class="sxs-lookup"><span data-stu-id="03b77-138">Users with different roles have different access to the persisted data, as follows:</span></span>
- <span data-ttu-id="03b77-139">系統管理員可以保留資料庫的大小變得很大的差異任何聊天室中刪除舊內容 （例如，在特定日期之前發佈的內容）。</span><span class="sxs-lookup"><span data-stu-id="03b77-139">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly.</span></span> <span data-ttu-id="03b77-140">或者，他們可以移除或取代的訊息視為不適用於指定的聊天室 （或被視為不適用）。</span><span class="sxs-lookup"><span data-stu-id="03b77-140">Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="03b77-141">使用者，包括訊息作者無法刪除任何聊天室中的內容。</span><span class="sxs-lookup"><span data-stu-id="03b77-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="03b77-142">聊天室管理員可以停用聊天室，但是無法刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="03b77-142">Chat room managers can disable rooms but cannot delete rooms.</span></span> <span data-ttu-id="03b77-143">建立後，只有系統管理員可以刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="03b77-143">Only administrators can delete a chat room after it is created.</span></span>