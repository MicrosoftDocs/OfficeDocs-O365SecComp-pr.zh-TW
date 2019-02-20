---
title: Office 365 Skype 為商務資料刪除的
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 說明在 Skype 資料刪除 for Business。
ms.openlocfilehash: 191b78befb114f4c10335490d298d968a4fda2c4
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090925"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="814f4-103">Office 365 中的商務資料刪除的 Skype</span><span class="sxs-lookup"><span data-stu-id="814f4-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="814f4-p101">適用於企業的 Skype 提供對等立即訊息、 多方立即訊息和會議中的內容上傳活動的封存。封存功能需要 Exchange 管理及控制由使用者的 Exchange 信箱就地保留 」 屬性、 商務內容封存電子郵件和 Skype 的。</span><span class="sxs-lookup"><span data-stu-id="814f4-p101">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings. The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="814f4-p102">Skype for Business 中的所有封存會被視為"使用者層級封存 」 因為啟用或停用它的一或多個特定使用者或使用者群組建立、 設定及套用這些使用者的使用者層級封存原則。封存中的設定商務系統管理中心 Skype 沒有直接控制。</span><span class="sxs-lookup"><span data-stu-id="814f4-p102">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users. There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="814f4-108">下列類型的內容不會封存中的商務 Skype：</span><span class="sxs-lookup"><span data-stu-id="814f4-108">The following types of content are not archived in Skype for Business:</span></span> 
- <span data-ttu-id="814f4-109">端對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="814f4-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="814f4-110">端對端即時訊息與會議的音訊／影片</span><span class="sxs-lookup"><span data-stu-id="814f4-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="814f4-111">端對端即時訊息與會議的應用程式分享</span><span class="sxs-lookup"><span data-stu-id="814f4-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="814f4-112">會議註釋</span><span class="sxs-lookup"><span data-stu-id="814f4-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="814f4-113">會議內容保留</span><span class="sxs-lookup"><span data-stu-id="814f4-113">Meeting Content Retention</span></span>
<span data-ttu-id="814f4-p103">使用 Skype for Business 的客戶可以將內容上傳至 Skype 商務會議做為附件，例如 PowerPoint 簡報、 OneNote 檔案及其他檔案。已上傳至會議內容保留期間是如下：</span><span class="sxs-lookup"><span data-stu-id="814f4-p103">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files. The retention period for content that has been uploaded to a meeting is as follows:</span></span>
- <span data-ttu-id="814f4-116">**一次性會議**內容會保留 15 天開始從最後一個人離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="814f4-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="814f4-p104">**週期性會議**內容會保留 15 天後最後一個人離開會議的最後一個工作階段。保留計時器重設如果某人加入 15 天內相同的會議工作階段。例如，假設 Skype 商務會議排定要根據每週發生一年和檔案上載至會議期間的第一個執行個體。如果至少一個人加入會議工作階段每週，該檔案會保留在 Skype 商務線上伺服器一整年 plus 15 天後最後一個人離開數列的最後一個會議的時間。</span><span class="sxs-lookup"><span data-stu-id="814f4-p104">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting. The retention timer resets if someone joins the same meeting session within 15 days. For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance. If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="814f4-121">**立即開會會議**-內容會保留在會議結束時間之後的 8 小時。</span><span class="sxs-lookup"><span data-stu-id="814f4-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="814f4-122">如果使用者是未授權或停用 （例如，如果**msrtcsip-userenabled**設*為 False*），並再重新授權或重新啟用功能、 會議內容不會 」 保留。</span><span class="sxs-lookup"><span data-stu-id="814f4-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="814f4-123">會議到期</span><span class="sxs-lookup"><span data-stu-id="814f4-123">Meeting Expiration</span></span>
<span data-ttu-id="814f4-124">使用者可以在特定會議結束之後存取該會議，但需注意下列到期時段：</span><span class="sxs-lookup"><span data-stu-id="814f4-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>
- <span data-ttu-id="814f4-125">**一次性會議**-會議會在排定的會議結束時間後的 14 天到期。</span><span class="sxs-lookup"><span data-stu-id="814f4-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="814f4-126">**具有結束日期的週期性會議**-會議會的最後一個會議之排定的結束時間後的 14 天到期。</span><span class="sxs-lookup"><span data-stu-id="814f4-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="814f4-127">**立即開會會議**-會議會在 8 小時後到期。</span><span class="sxs-lookup"><span data-stu-id="814f4-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="814f4-128">白板共同作業</span><span class="sxs-lookup"><span data-stu-id="814f4-128">Whiteboard Collaboration</span></span>
<span data-ttu-id="814f4-p105">白板上進行註解將會看到所所有參與者。當儲存白板、 白板和所有註會儲存在 Skype Business server 並將會保留在根據會議內容到期原則管理員所設定之伺服器上。</span><span class="sxs-lookup"><span data-stu-id="814f4-p105">Annotations made on whiteboards will be seen by all participants. When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="814f4-131">音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="814f4-131">Audio Test Service</span></span>
<span data-ttu-id="814f4-p106">語音 short （大約 5 秒） 範例會記錄音訊測試服務通話期間。語音範例是由您用來檢查及 （或） 確認您 Skype 商務通話品質的錄製為基礎的聲音品質。當音訊測試服務通話結束時，會刪除語音範例。</span><span class="sxs-lookup"><span data-stu-id="814f4-p106">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call. The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording. When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="814f4-135">持續性群組聊天</span><span class="sxs-lookup"><span data-stu-id="814f4-135">Persistent Group Chat</span></span>
<span data-ttu-id="814f4-p107">持續 Group Chat 儲存群組聊天交談的內容。若啟用，系統管理員可以控制保留期間，此資訊會儲存的伺服器，如果群組聊天歷程記錄封存的規範或其他用途，和管理/修改在會議室的任何屬性。使用不同的角色的使用者具有不同保存的資料存取，如下所示：</span><span class="sxs-lookup"><span data-stu-id="814f4-p107">Persistent Group Chat stores the content of group chat conversations. If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room. Users with different roles have different access to the persisted data, as follows:</span></span>
- <span data-ttu-id="814f4-p108">管理員可以刪除任何聊天室保留從大幅增加資料庫的大小較舊的內容 （例如張貼特定日期之前的內容）。或可移除或取代郵件被視為不適當的給定的聊天室 （或被視為不適用）。</span><span class="sxs-lookup"><span data-stu-id="814f4-p108">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly. Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="814f4-141">使用者，包括訊息作者無法刪除任何聊天室的內容。</span><span class="sxs-lookup"><span data-stu-id="814f4-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="814f4-p109">聊天室管理員可以停用的聊天室，但是無法刪除聊天室。會在建立之後只有系統管理員可以刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="814f4-p109">Chat room managers can disable rooms but cannot delete rooms. Only administrators can delete a chat room after it is created.</span></span>