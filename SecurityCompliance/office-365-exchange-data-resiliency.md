---
title: Office 365 Exchange 資料恢復能力
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
ms.collection: Strat_O365_Enterprise
description: Exchange Online 與 Office 365 中的資料恢復能力的各個方面的說明。
ms.openlocfilehash: 8d0448a95f010b766faf852a374513a1c2da61fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526647"
---
# <a name="exchange-online-data-resiliency-in-office-365"></a><span data-ttu-id="5a5ed-103">Office 365 中的 Exchange Online 資料恢復能力</span><span class="sxs-lookup"><span data-stu-id="5a5ed-103">Exchange Online Data Resiliency in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="5a5ed-104">簡介</span><span class="sxs-lookup"><span data-stu-id="5a5ed-104">Introduction</span></span>
<span data-ttu-id="5a5ed-p101">有兩種可能會影響 Exchange 資料庫損毀： 實體損毀，通常由 （在特定、 儲存硬體） 的硬體問題所造成，並因其他因素而發生的邏輯損毀。一般而言，有兩種 Exchange 資料庫中可能發生的邏輯損毀類型：</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p101">There are two types of corruption that can affect an Exchange database: physical corruption, which is typically caused by hardware (in particular, storage hardware) problems, and logical corruption, which occurs due to other factors. Generally, there are two types of logical corruption that can occur within an Exchange database:</span></span> 
- <span data-ttu-id="5a5ed-p102">**資料庫邏輯損毀**-資料庫] 頁面上總和檢查碼相符項目，但] 頁面上的資料是錯誤邏輯上。便會發生此嘗試以寫入資料庫] 頁面上的資料庫引擎 (可延伸儲存引擎 (ESE)) 與即使作業系統會傳回成功訊息，資料會也永遠不寫入至磁碟或寫入錯誤的位置。這被稱為*＜ flush 遺失*。ESE 包含許多功能與設計用來防止實體損毀的資料庫與其他資料遺失案例的保護措施。若要防止遺失資料遺失排清，ESE 包含遺失清除偵測機制更正它的功能 （單一頁面還原） 以及資料庫中。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p102">**Database logical corruption** - The database page checksum matches, but the data on the page is wrong logically. This can occur when the database engine (the Extensible Storage Engine (ESE)) attempts to write a database page and even though the operating system returns a success message, the data is either never written to the disk or it's written to the wrong place. This is referred to as a *lost flush*. ESE includes numerous features and safeguards that are designed to prevent physical corruption of a database and other data loss scenarios. To prevent lost flushes from losing data, ESE includes a lost flush detection mechanism in the database along with a feature (single page restore) to correct it.</span></span> 
- <span data-ttu-id="5a5ed-p103">**存放區邏輯損毀**的資料會新增、 刪除或使用者不會預期的方式來操作。這些案例通常引起的協力廠商應用程式。通常是在使用者的損毀以檢視其意義的損毀。Exchange 儲存區會考慮產生設為一系列的有效 MAPI 作業邏輯損毀的交易。Exchange Online 中的[就地保留](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)功能提供來自存放區邏輯損毀的保護 （因為它將防止內容會永久刪除使用者或應用程式）。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p103">**Store logical corruption** - Data is added, deleted, or manipulated in a way that the user doesn't expect. These cases are generally caused by third-party applications. It's generally only corruption in the sense that the user views it as corruption. The Exchange store considers the transaction that produced the logical corruption to be a series of valid MAPI operations. The [In-Place Hold](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) features in Exchange Online provides protection from store logical corruption (because it prevents content from being permanently deleted by a user or an application).</span></span> 

<span data-ttu-id="5a5ed-p104">Exchange Online 檢查記錄檔與記錄檔重新顯示期間執行數個一致性檢查複寫的記錄檔。這些一致性檢查防止從系統所要複製的實體損毀。例如，記錄檢查期間有實體完整性檢查以確認記錄檔和驗證記錄檔中所記錄的總和檢查碼符合總和檢查碼產生記憶體中。此外，記錄檔標頭會檢查以確保記錄標頭中所記錄的記錄檔案簽章相符的記錄檔。在記錄檔重新顯示記錄檔進一步程無法。例如，資料庫標頭也會包含記錄檔簽章與記錄檔案的簽章以確保其符合比較。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p104">Exchange Online performs several consistency checks on replicated log files during both log inspection and log replay. These consistency checks prevent physical corruption from being replicated by the system. For example, during log inspection, there is a physical integrity check which verifies the log file and validates that the checksum recorded in the log file matches the checksum generated in memory. In addition, the log file header is examined to make sure the log file signature recorded in the log header matches that of the log file. During log replay, the log file undergoes further scrutiny. For example, the database header also contains the log signature which is compared with the log file's signature to ensure they match.</span></span> 

<span data-ttu-id="5a5ed-p105">使用 Exchange 原生資料保護運用跨多部伺服器和多個資料中心及其他應用程式層級複寫恢復策略來進行 Exchange Online 中的信箱資料損毀的保護協助保護資料免於被因損毀或其他原因而遺失的功能。這些功能包括原生功能受 Microsoft 或 Exchange Online 應用程式本身，例如：</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p105">Protection against corruption of mailbox data in Exchange Online is achieved by using Exchange Native Data Protection, a resiliency strategy that leverages application-level replication across multiple servers and multiple datacenters along with other features that help protect data from being lost due to corruption or other reasons. These features include native features that are managed by Microsoft or the Exchange Online application itself, such as:</span></span>

- [<span data-ttu-id="5a5ed-125">資料可用性群組</span><span class="sxs-lookup"><span data-stu-id="5a5ed-125">Data Availability Groups</span></span>](https://docs.microsoft.com/exchange/back-up-email)
- <span data-ttu-id="5a5ed-126">單一位元校正</span><span class="sxs-lookup"><span data-stu-id="5a5ed-126">Single Bit Correction</span></span> 
- <span data-ttu-id="5a5ed-127">掃描的線上資料庫</span><span class="sxs-lookup"><span data-stu-id="5a5ed-127">Online Database Scanning</span></span> 
- <span data-ttu-id="5a5ed-128">遺失清除偵測</span><span class="sxs-lookup"><span data-stu-id="5a5ed-128">Lost Flush Detection</span></span> 
- <span data-ttu-id="5a5ed-129">單一頁面還原</span><span class="sxs-lookup"><span data-stu-id="5a5ed-129">Single Page Restore</span></span> 
- <span data-ttu-id="5a5ed-130">信箱複寫服務</span><span class="sxs-lookup"><span data-stu-id="5a5ed-130">Mailbox Replication Service</span></span> 
- <span data-ttu-id="5a5ed-131">記錄檔檢查</span><span class="sxs-lookup"><span data-stu-id="5a5ed-131">Log File Checks</span></span> 
- <span data-ttu-id="5a5ed-132">彈性檔案系統上的部署</span><span class="sxs-lookup"><span data-stu-id="5a5ed-132">Deployment on Resilient File System</span></span> 

<span data-ttu-id="5a5ed-p106">如以上所列的原生功能的詳細資訊，在上面的超連結、 按一下 [並查看下方的其他資訊以及沒有超連結的項目詳細資料。除了這些原生功能、 Exchange Online 也包含客戶可以管理、 例如的資料恢復功能：</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p106">For more information on the native features listed above, click on the above hyperlinks, and see below for additional information and for details on items without hyperlinks. In addition to these native features, Exchange Online also includes data resiliency features that customers can manage, such as:</span></span> 
- [<span data-ttu-id="5a5ed-135">（預設為啟用） 的單一項目復原</span><span class="sxs-lookup"><span data-stu-id="5a5ed-135">Single Item Recovery (enabled by default)</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [<span data-ttu-id="5a5ed-136">就地保留和訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="5a5ed-136">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [<span data-ttu-id="5a5ed-137">已刪除的項目保留與 Soft-Deleted 信箱 （兩者皆預設啟用）</span><span class="sxs-lookup"><span data-stu-id="5a5ed-137">Deleted Item Retention and Soft-Deleted Mailboxes (both enabled by default)</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a><span data-ttu-id="5a5ed-138">資料庫可用性群組</span><span class="sxs-lookup"><span data-stu-id="5a5ed-138">Database Availability Groups</span></span> 
<span data-ttu-id="5a5ed-p107">Office 365 中的每個信箱資料庫是架設在[資料庫可用性群組 (DAG)](https://docs.microsoft.com/exchange/back-up-email)和複寫到相同的區域中的地理位置不同資料中心。最常見的設定是四個資料庫副本的四個資料中心;不過，某些區域有較少的資料中心 （資料庫已複寫至印度] 中的三個資料中心兩個資料中心澳洲和日本中的）。但在所有的情況下，每個信箱資料庫有分散於多個資料中心，進而確認信箱資料受到保護的軟體、 硬體及即使資料中心失敗的四個副本。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p107">Every mailbox database in Office 365 is hosted in a [database availability group (DAG)](https://docs.microsoft.com/exchange/back-up-email) and replicated to geographically-separate datacenters within the same region. The most common configuration is four database copies in four datacenters; however, some regions have fewer datacenters (databases are replicated to three datacenters in India, and two datacenters in Australia and Japan). But in all cases, every mailbox database has four copies that are distributed across multiple datacenters, thereby ensuring that mailbox data is protected from software, hardware, and even datacenter failures.</span></span> 

<span data-ttu-id="5a5ed-p108">不在下列四個副本的它們三個設定為高度可用。第四個副本被設定為[延遲資料庫副本](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies)。延遲的資料庫副本不得為個別的信箱復原] 或 [復原的信箱項目。及其用途是提供極罕見的整體系統、 災難性邏輯損毀事件復原機制。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p108">Out of these four copies, three of them are configured as highly available. The fourth copy is configured as a [lagged database copy](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies). The lagged database copy is not intended for individual mailbox recovery or mailbox item recovery. Its purpose is to provide a recovery mechanism for the rare event of system-wide, catastrophic logical corruption.</span></span> 

<span data-ttu-id="5a5ed-p109">七天記錄檔重新顯示延遲時間來設定 Exchange Online 中的延遲信箱的資料庫副本。另外，Exchange 重新執行延隔管理員能夠提供動態記錄檔減少的延遲的副本允許自我修復及管理記錄檔案成長延遲信箱的資料庫副本。雖然延遲的資料庫副本可用 Exchange Online 中，務必了解這些不保證的時間點備份。Exchange Online 中的延遲信箱的資料庫副本具有可用性臨界值，通常是筆 90%，因為包含延遲的副本的磁碟遺失由於磁碟故障，延遲的副本變成高度可用的期間 （由於自動播放向下），以及將複製為延遲的資料庫副本重新建立記錄檔所在的期間重新顯示佇列。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p109">Lagged database copies in Exchange Online are configured with a seven-day log file replay lag time. In addition, the Exchange Replay Lag Manager is enabled to provide dynamic log file play down for lagged copies to allow lagged database copies to self-repair and manage log file growth. Although lagged database copies are used in Exchange Online, it is important to understand that they are not a guaranteed point-in-time backup. Lagged database copies in Exchange Online have an availability threshold, typically around 90%, due to periods where the disk containing a lagged copy is lost due to disk failure, the lagged copy becoming a highly-available copy (due to automatic play down), as well as the periods where the lagged database copy is re-building the log replay queue.</span></span> 

## <a name="transport-resilience"></a><span data-ttu-id="5a5ed-150">傳輸台回復性</span><span class="sxs-lookup"><span data-stu-id="5a5ed-150">Transport Resilience</span></span> 
<span data-ttu-id="5a5ed-p110">Exchange Online 包含兩個主要傳輸台回復性功能： 陰影備援能力與安全網。陰影備援都會保留郵件的重複複本中傳輸時。安全網保留郵件的重複複本之後成功傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p110">Exchange Online includes two primary transport resilience features: Shadow Redundancy and Safety Net. Shadow Redundancy keeps a redundant copy of a message while it is in transit. Safety Net keeps a redundant copy of a message after the message is successfully delivered.</span></span> 

<span data-ttu-id="5a5ed-p111">陰影備援與每個 Exchange Online 傳輸伺服器會建立它收到之前它認可成功接收郵件至傳送伺服器的每個郵件的複本。這會使所有郵件傳輸管線中傳送過程中變得多餘。如果 Exchange Online 判定原始郵件已遺失傳送過程中，已重新傳遞郵件的重複複本。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p111">With Shadow Redundancy, each Exchange Online transport server makes a copy of each messages it receives before it acknowledges successfully receiving the message to the sending server. This makes all messages in the transport pipeline redundant while in transit. If Exchange Online determines the original message was lost in transit, a redundant copy of the message is redelivered.</span></span> 

<span data-ttu-id="5a5ed-p112">安全網是相關聯的信箱伺服器上的傳輸服務中的傳輸佇列。此佇列會儲存郵件已成功處理的伺服器複本。當失敗的信箱資料庫或伺服器需要啟動過期的信箱資料庫複本時，安全網佇列中的郵件會自動重新提交至新的作用中信箱資料庫複本。安全網也是設為備援，進而帶來傳輸為單一失敗點。它會使用主要安全網與陰影 Safety Net 的概念移位，其中如果超過 12 小時無法使用主要 Safety Net、 重新提交要求成為陰影重新提交要求、 與郵件會重新已從陰影 Safety Net 傳遞。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p112">Safety Net is a transport queue that is associated with the Transport service on a Mailbox server. This queue stores copies of messages that were successfully processed by the server. When a mailbox database or server failure requires activating an out-of-date copy of the mailbox database, messages in the Safety Net queue are automatically resubmitted to the new active copy of the mailbox database. Safety Net is also redundant, thereby eliminating transport as a single point of failure. It uses the concept of a Primary Safety Net and a Shadow Safety Net wherein if the Primary Safety Net is unavailable for more than 12 hours, resubmit requests become shadow resubmit requests, and messages are re-delivered from the Shadow Safety Net.</span></span>

<span data-ttu-id="5a5ed-p113">從 Safety Net 的訊息 resubmissions 會自動由啟動管理 Dag 和信箱的 Microsoft Exchange 複寫服務的 Active Manager 元件資料庫副本。若要重新提交郵件從 Safety Net 時不需要任何手動執行動作。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p113">Message resubmissions from Safety Net are automatically initiated by the Active Manager component of the Microsoft Exchange Replication service that manages DAGs and mailbox database copies. No manual actions are required to resubmit messages from Safety Net.</span></span> 

## <a name="single-bit-correction"></a><span data-ttu-id="5a5ed-164">單一位元校正</span><span class="sxs-lookup"><span data-stu-id="5a5ed-164">Single Bit Correction</span></span> 
<span data-ttu-id="5a5ed-p114">ESE 包括偵測及解決單一位元 CRC 錯誤 （亦即單一位元翻轉） 的硬體錯誤結果的機制 （與因此及其所代表實體損毀）。當發生這些錯誤時，ESE 自動修正這些並將事件記錄在事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p114">ESE includes a mechanism to detect and resolve single-bit CRC errors (aka single-bit flips) that are the result of hardware errors (and as such they represent physical corruption). When these errors occur, ESE automatically corrects them and logs an event in the event log.</span></span> 

## <a name="online-database-scanning"></a><span data-ttu-id="5a5ed-167">掃描的線上資料庫</span><span class="sxs-lookup"><span data-stu-id="5a5ed-167">Online Database Scanning</span></span> 
<span data-ttu-id="5a5ed-p115">線上掃描 (也稱為*資料庫 checksumming*) 的資料庫是其中 ESE 使用讀取每個頁面並檢查] 頁面上損毀的資料庫一致性檢查的程序。主要目的是要偵測實體損毀和可能不取得偵測到的交易式作業的遺失排清。掃描資料庫也會執行後續的存放區損毀作業。可以因為當機次數，遺漏空間和線上資料庫掃描會尋找並復原遺失的空間。系統的設計與每個資料庫會完全掃描一次每七天期望。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p115">Online database scanning (also known as *database checksumming*) is the process where an ESE uses a database consistency checker to read each page and check for page corruption. The primary purpose is to detect physical corruption and lost flushes that may not be getting detected by transactional operations. Database scanning also performs post-store crash operations. Space can be leaked due to crashes, and online database scanning finds and recovers lost space. The system is designed with the expectation that every database is fully scanned once every seven days.</span></span> 

## <a name="lost-flush-detection"></a><span data-ttu-id="5a5ed-173">遺失清除偵測</span><span class="sxs-lookup"><span data-stu-id="5a5ed-173">Lost Flush Detection</span></span> 
<span data-ttu-id="5a5ed-p116">遺失的 flush 發生時的磁碟子系統/操作系統傳回為已完成資料庫寫入作業沒有沒有實際取得寫入至磁碟，或已寫入錯誤的位置。遺失清除事件可以在資料庫邏輯損毀，如此可防止遺失排清資料遺失，ESE 所產生的結果包括遺失清除偵測機制。為資料庫頁面會寫入被動副本，核取被執行的主動副本上遺失排清。如果偵測到遺失的清除時，ESE 可以修復使用修補程序] 頁面上的程序。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p116">A lost flush occurs when a database write operation that the disk subsystem/operating system returned as completed did not actually get written to disk, or was written in the wrong location. Lost flush incidents can result in database logical corruption, so to prevent lost flushes from resulting in lost data, ESE includes a lost flush detection mechanism. As database pages are written to passive copies, a check is performed for lost flushes on the active copy. If a lost flush is detected, ESE can repair the process using a page patching process.</span></span> 

## <a name="single-page-restore"></a><span data-ttu-id="5a5ed-178">單一頁面還原</span><span class="sxs-lookup"><span data-stu-id="5a5ed-178">Single Page Restore</span></span> 
<span data-ttu-id="5a5ed-p117">單一頁面還原，亦即*修補頁面*，是從狀況良好的複本的正常副本其中取代損毀的資料庫頁面的自動處理程序。主動或被動資料庫副本的是否定損毀] 頁面上的修復程序。當作用中資料庫副本遇到損毀的頁面時，它可以複製] 頁面上其複本，其中一個提供它會複製頁面是完全最新狀態。這被藉由放入為基礎的信箱資料庫複寫記錄資料流的要求] 頁面。一旦複本遇到頁面要求它回應] 頁面上的複本傳送到要求的資料庫副本。單一頁面還原也提供非同步通訊機制的使用中的要求] 頁面上的複本，即使複本目前為離線狀態。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p117">Single page restore, aka *page patching*, is an automatic process where corrupt database pages are replaced by healthy copies from a healthy replica. The repair process for a corrupt page depends on whether the database copy is active or passive. When an active database copy encounters a corrupted page, it can copy a page from one of its replicas, provided the page it copies is completely up-to-date. This is accomplished by putting a request for the page into the log stream, which is the basis of mailbox database replication. As soon as a replica encounters the page request it responds by sending a copy of the page to the requesting database copy. Single page restore also provides an asynchronous communication mechanism for the active to request a page from replicas, even if the replicas are currently offline.</span></span> 

<span data-ttu-id="5a5ed-p118">發生損毀的被動資料庫副本，包括延遲的資料庫副本，因為這些副本一律後方其作用中副本，是一定都安全作用中副本的任何頁面複製至被動副本。被動資料庫副本是由高度可用的性質因此期間修補程序] 頁面上，記錄檔重新顯示已擱置，但是記錄複製作業會繼續進行。被動資料庫副本從作用中副本擷取一份損毀的頁面中，會等候直到符合需求所需的最大記錄檔產生記錄檔複製並檢查，且再修補程式損毀的頁面。一旦已經修補] 頁面上，繼續記錄重新顯示。程序只是相同的延遲的資料庫副本，延遲的資料庫前會重新顯示所有記錄檔所需達到 patchable 狀態。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p118">In case of corruption in a passive database copy, including a lagged database copy, because these copies are always behind their active copy, it is always safe to copy any page from the active copy to a passive copy. A passive database copy is by nature highly available, so during the page patching process, log replaying is suspended, but log copying continues. The passive database copy retrieves a copy of the corrupted page from the active copy, waits until the log file which meets the maximum required log generation requirement is copied and inspected, and then patches the corrupt page. Once the page has been patched, log replay resumes. The process is the same for the lagged database copy, except that the lagged database first replays all log files that are necessary to achieve a patchable state.</span></span> 

## <a name="mailbox-replication-service"></a><span data-ttu-id="5a5ed-190">信箱複寫服務</span><span class="sxs-lookup"><span data-stu-id="5a5ed-190">Mailbox Replication Service</span></span> 
<span data-ttu-id="5a5ed-p119">移動信箱是管理大型的電子郵件服務的重要部分。一定是更新的技術書寫如何處理，所以會擁有完善節流處理可讓我們工程師來完成這項工作時保持信箱的系統的軟硬體版本升級透明的使用者 （依確定它們留線上整個程序） 是金鑰並確定該程序的比例，調整正常為信箱取得較大和更大。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p119">Moving mailboxes is a key part of managing a large-scale email service. There are always updated technologies and hardware and version upgrades to deal with, so having a robust, throttled system that enables our engineers to accomplish this work while keeping the mailbox moves transparent to users (by making sure they stay online throughout the process) is key and making sure that the process scales up gracefully as mailboxes get larger and larger.</span></span> 

<span data-ttu-id="5a5ed-p120">Exchange 信箱複寫服務 (MRS) 負責資料庫之間移動信箱。移動期間 MRS 執行一致性檢查信箱內的所有項目。如果有找到一致性問題、 MRS 將更正此問題，或略過損毀的項目，進而從信箱移除損毀。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p120">The Exchange Mailbox Replication Service (MRS) is responsible for moving mailboxes between databases. During the move, MRS performs a consistency check on all items within the mailbox. If a consistency issue is found, MRS will either correct the problem, or skip the corrupted items, thereby removing the corruption from the mailbox.</span></span> 

<span data-ttu-id="5a5ed-p121">由於 MRS 是 Exchange Online 的元件，我們可以對位址新表單的損毀未來偵測到其程式碼中進行變更。例如，如果我們偵測 MRS 不是可以修正的一致性問題，我們可以分析損毀、 MRS 程式碼變更並更正不一致 (如果我們了解如何)。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p121">Because MRS is a component of Exchange Online, we can make changes in its code to address new forms of corruption that are detected in the future. For example, if we detect a consistency issue that MRS is not able to fix, we can analyze the corruption, change the MRS code and correct the inconsistency (if we understand how to).</span></span> 

## <a name="log-file-checks"></a><span data-ttu-id="5a5ed-198">記錄檔檢查</span><span class="sxs-lookup"><span data-stu-id="5a5ed-198">Log File Checks</span></span> 
<span data-ttu-id="5a5ed-p122">Exchange 資料庫所產生的所有交易記錄檔、 都經歷數種形式的一致性檢查。建立記錄檔之後，先完成是撰寫的位元模式和再執行一系列的記錄檔寫入數。這可讓 Exchange Online 執行一系列的檢查 （遺失的 flush、 CRC 和其他檢查） 以確認每個記錄檔寫入，並再次如已複寫。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p122">All transaction log files generated by an Exchange database undergo several forms of consistency checks. When a log file is created, the first thing done is a bit pattern is written and then a series of log writes is performed. This enables Exchange Online to execute a series of checks (lost flush, CRC and other checks) to validate each log file as it is written, and again as it is replicated.</span></span> 

## <a name="deployment-on-resilient-file-system"></a><span data-ttu-id="5a5ed-202">彈性檔案系統上的部署</span><span class="sxs-lookup"><span data-stu-id="5a5ed-202">Deployment on Resilient File System</span></span> 
<span data-ttu-id="5a5ed-p123">若要協助防止發生在檔案系統層級的損毀，Exchange Online 正在部署提供改善的復原能力的彈性檔案系統 (ReFS) 分割區上。ReFS 是設計主要是針對資料損毀進而最大化資料可用性和完整性更彈性檔案系統的 Windows Server 2012 及更新版本。尤其是 ReFS 會改善方式在該中繼資料會更新以提供更好的資料保護和減少資料損毀的情況。它也會使用總和檢查碼來確認資料檔案的完整性及輕鬆找到並修復確保該資料損毀的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p123">To help prevent corruption from occurring at the file system level, Exchange Online is being deployed on Resilient File System (ReFS) partitions to provide improved recovery capabilities. ReFS is a file system in Windows Server 2012 and later that is designed to be more resilient against data corruption thereby maximizing data availability and integrity. Specifically, ReFS brings improvements in the way that metadata is updated which offers better protection for data and reduces data corruption cases. It also uses checksums to verify the integrity of file data and metadata ensuring that data corruption is easily found and repaired.</span></span> 

<span data-ttu-id="5a5ed-207">Exchange Online 利用有幾個 ReFS 優點：</span><span class="sxs-lookup"><span data-stu-id="5a5ed-207">Exchange Online takes advantage of several ReFS benefits:</span></span> 
- <span data-ttu-id="5a5ed-p124">更多恢復功能資料完整性表示較少資料損毀事件。減少損毀事件數目表示較少的不必要的資料庫進行重新植入。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p124">More resiliency in data integrity means fewer data corruption incidents. Reducing the number of corruption incidents means fewer unnecessary database reseeds.</span></span> 
- <span data-ttu-id="5a5ed-210">總和檢查碼執行提前及更多決定性地啟用偵測損毀的情況下，讓我們修正客戶資料的中繼資料損毀之前發生資料磁碟區上的灰色失敗。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-210">Checksum running on metadata enabling detections of corruption cases sooner and more deterministically, allowing us to fix customer data corruption before grey failures occur on data volumes.</span></span>
- <span data-ttu-id="5a5ed-211">設計旨在與極大型資料集以及 — petabytes 及較大 — 不效能的影響</span><span class="sxs-lookup"><span data-stu-id="5a5ed-211">Designed to work well with extremely large data sets—petabytes and larger—without performance impact</span></span>
- <span data-ttu-id="5a5ed-212">使用 Exchange Online 中，例如 BitLocker 加密其他功能的支援。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-212">Support for other features used by Exchange Online, such as BitLocker encryption.</span></span> 

<span data-ttu-id="5a5ed-213">Exchange Online 也受益其他 ReFS 功能：</span><span class="sxs-lookup"><span data-stu-id="5a5ed-213">Exchange Online also benefits from other ReFS features:</span></span> 
- <span data-ttu-id="5a5ed-p125">**完整性 （完整性資料流）** ReFS 儲存的資料保護從許多常見的錯誤通常會導致資料遺失的方式。Office 365 搜尋會使用以協助早期磁碟損毀偵測與總和檢查碼檔案內容的完整性資料流。此功能也會減少損毀事件而造成 「 裂寫入"（時寫入作業未完成因為電源中斷等。）。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p125">**Integrity (Integrity Streams)** - ReFS stores data in a way that protects it from many of the common errors that can normally cause data loss. Office 365 Search uses Integrity Streams to help with early disk corruption detection and checksums of file content. The feature also reduces corruption incidents caused by “Torn Writes” (when a write operation does not complete due to power outages, etc.).</span></span> 
- <span data-ttu-id="5a5ed-p126">**可用性 （殘）** ReFS 設定優先順序資料的可用性。在過去，檔案系統已通常容易就需要採取離線修復系統的資料損毀。雖然極少，如果沒有發生損毀，ReFS 實作搶救，一種功能，實際的磁碟區上的命名空間會移除損毀的資料與可確保良好的資料不有不良影響的非可損毀的資料。套用殘功能及隔離至 Exchange Online 的資料庫磁碟區的資料損毀表示我們可以保持非受影響資料庫損毀的磁碟區上正常之間損毀及修復動作的時間。這會增加通常由這類磁碟損毀問題受影響資料庫的可用性。</span><span class="sxs-lookup"><span data-stu-id="5a5ed-p126">**Availability (Salvage)** - ReFS prioritizes the availability of data. Historically, file systems were often susceptible to data corruption that would require the system to be taken offline for repair. Although rare, if corruption does occur, ReFS implements salvage, a feature that removes the corrupt data from the namespace on a live volume and ensures that good data is not adversely affected by non-repairable corrupt data. Applying the Salvage feature and isolating data corruption to Exchange Online database volumes means that we can keep non-affected databases on a corrupted volume healthy between the time of corruption and repair action. This increases the availability of databases that would normally be affected by such disk corruption issues.</span></span> 