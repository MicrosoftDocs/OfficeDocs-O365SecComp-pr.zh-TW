---
title: Office 365 隔離與 Office 365 中的存取控制
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
description: 摘要： 在 Office 365 的各種應用程式內的隔離及存取控制說明。
ms.openlocfilehash: c1989bc546df357740ea963a1a241dfa14557931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527305"
---
# <a name="isolation-and-access-control-in-office-365"></a>Office 365 中的隔離與存取控制

Azure Active Directory 與 Office 365 使用高度複雜的資料模型包含數十萬服務、 數百個實體，數千的關係，以及數萬個屬性 （實體、 關係和屬性都是常特定應用程式）。在高層級、 Azure Active Directory 和服務目錄是租用戶和收件者的容器與他們會保留不同步使用狀態式複寫通訊協定。保留在 Azure Active Directory 中的目錄資訊，以及每個服務也有他們自己的目錄服務基礎結構 （例如 Exchange Online 的目錄服務、 SharePoint Online 的目錄服務、 等）。 
 
![Office 365 租用戶資料同步處理](media/office-365-isolation-tenant-data-sync.png)

在此模型中，有任何單一資料來源的目錄。每個個別資料的一部分擁有特定的系統，但沒有單一系統保留所有資料。Office 365 服務合作以了解資料模型的 Azure Active Directory。Azure Active Directory 是通常是通常由每個服務的小型和靜態資料的共用資料的 「 系統真偽"。使用 Office 365 和 Azure Active Directory 內的同盟的模型會提供共用的資料的檢視。

Office 365 使用實體儲存裝置與 Azure 雲端儲存。Exchange Online （包括 Exchange Online Protection） 和 Skype 的商務使用自己的存放區的客戶資料。SharePoint Online 如何運用其 SQL Server 儲存體與 Azure 存放區，而強制執行需要藉助的其他資料隔離的客戶儲存層級。

## <a name="exchange-online"></a>Exchange Online
Exchange Online 可儲存主控呼叫信箱資料庫的可延伸儲存引擎 (ESE) 資料庫中的信箱內的客戶資料。這包括使用者信箱、 連結的信箱、 共用的信箱和公用資料夾信箱。使用者信箱可能也會包含已儲存的 Skype 商務內容，例如交談歷程記錄。使用者信箱的內容包括電子郵件和電子郵件附件、 行事曆及空閒/忙碌資訊、 連絡人、 工作、 備忘稿、 群組及推斷資料。

在 Exchange Online 中的每個信箱資料庫包含多個承租人的信箱。授權程式碼、 租用中包括保護所有的信箱。為 Exchange 內部部署預設指派的使用者才會擁有存取信箱。保護信箱的存取控制清單 (ACL) 包含驗證租用戶層級的 Azure Active Directory 的身分識別。限制識別驗證對該用戶驗證提供者，其中包括從該租用戶的唯一使用者是指定承租人的信箱。屬於 TenantA 的內容不能以任何方法可取得使用者 TenantB，除非明確核准 TenantA。

## <a name="skype-for-business"></a>商務用 Skype
適用於企業的 Skype 將資料儲存各種位置：
- 在商務 Active Directory 伺服器 Skype 以及各種 Skype 商務資料庫中儲存使用者與帳戶資訊，其中包含連線的端點租用戶識別碼、 撥號對應表、 漫遊設定、 目前狀態、 連絡人清單、 等伺服器。如果使用者已啟用這兩個產品，或在 Skype 商務伺服器如果使用者不是連絡人清單儲存在使用者的 Exchange Online 信箱。Skype 商務資料庫伺服器的已分割每位租用戶，但資料的多重租用隔離透過 RBAC 強制執行。
- 會議內容，例如商務會議內容的使用者上傳 Skype 期間會儲存在分散式檔案系統共用。也可以將此內容封存 Exchange Online 中，提供啟用封存。DFS 共用不是已分割的每個承租人但與 Acl 保護內容的安全與多重租用透過 RBAC 強制執行。
- 詳細通話記錄，這是活動歷程記錄，例如來電記錄、 IM 工作階段、 應用程式共用、 IM 歷程記錄等，也可以儲存在 Exchange Online 中，但是大部分詳細通話記錄會暫時儲存在通話詳細記錄 (CDR) 伺服器上。每位租用戶、 未分割的內容，但多重租用透過 RBAC 強制執行。

## <a name="sharepoint-online"></a>SharePoint Online
有數個獨立的機制唯一 to SharePoint Online 提供資料隔離。SharePoint Online 為抽象應用程式資料庫中的程式碼儲存物件。例如，當使用者上傳至 SharePoint Online 檔案，該檔案是反組譯轉譯成應用程式碼與跨多個資料庫儲存在多個資料表中。

如果使用者無法直接存取含有資料的存放區，就無法解譯人力資源或 SharePoint Online 以外的任何系統內容。這些機制包括安全性存取控制及屬性。如前文所述，授權程式碼及租用內包含的 RBAC 原則所保護所有 SharePoint Online 的資源。保護資源的存取控制清單 (ACL) 包含租用戶層級驗證身分識別。與 Exchange Online、 SharePoint Online 中指定承租人的資料限於對該用戶驗證提供者驗證識別身分包括該承租人的唯一使用者。

除了 Acl、 指定驗證提供者 （這是承租人特定 Azure Active Directory） 的租用戶層級屬性一次寫入，而且無法一次設定變更。驗證提供者租用戶屬性已設定租用戶之後, 就無法變更使用公開給租用戶任何 Api。

唯一*SubscriptionId*也用於每個租用戶。客戶的所有網站擁有的租用戶和*SubscriptionId*唯一指派給租用戶。在網站上的*SubscriptionId*屬性會寫入一次，且無法變更。一旦站台已指派給租用戶，它不能移至不同的租用戶稍後使用的內容儲存區 API。*SubscriptionId*也是用來建立驗證提供者安全性範圍並已繫結至租用戶金鑰。

SharePoint Online 的內容儲存使用 SQL Server 與 Azure 儲存空間。在 SQL 層級的內容存放區的分割區金鑰*SiteId*。當執行 SQL 查詢，SharePoint Online 使用已經過驗證*SiteId*租用戶層級*SubscriptionId* ] 核取的一部分。

SharePoint Online in Microsoft Azure 儲存檔案二進位 blob （例如檔案資料流）。每個 SharePoint Online 的伺服器陣列有其本身的 Microsoft Azure 帳戶和個別使用儲存在 SQL 內容存放區中的機碼加密儲存在 Azure 中的所有 blob 存。加密金鑰不會公開給使用者，直接與程式碼中的授權層會受到保護。最後，SharePoint Online 已備妥来偵測的 HTTP 要求都可讀取或寫入資料的多個用戶時的即時監視。其執行方法追蹤對*SubscriptionId*所存取的資源要求 identity *SubscriptionId* 。存取多個承租人的資源要求不應該發生的使用者。它可以上述發生在多承租人環境中的服務要求。例如，搜尋編目程式提取整個資料庫的內容變更一次。這通常會查詢中完成的效率原因的單一服務要求的多個承租人的網站。
