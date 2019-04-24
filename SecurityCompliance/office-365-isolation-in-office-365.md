---
title: Office 365 隔離和 Office 365 中的存取控制
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
description: 摘要： 在 Office 365 的各種應用程式內的隔離和存取控制的說明。
ms.openlocfilehash: c4328539f8cca5cb7e76c4a3175cfab0a01b42cf
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262618"
---
# <a name="isolation-and-access-control-in-office-365"></a>Office 365 中的隔離與存取控制

Azure Active Directory 和 Office 365 使用高度複雜的資料模型，其中包含數萬個服務，數百個實體，千分位的關聯性和數萬個屬性 （實體、 關係和屬性都通常特定應用程式）。 在高的層級，Azure Active Directory 服務目錄的租用戶和收件者] 容器，且他們會保持同步處理使用狀態為基礎的複寫通訊協定。 除了 Azure Active Directory 內保留的目錄資訊，每個服務也會有自己的目錄服務基礎結構 （例如，Exchange Online 的目錄服務、 SharePoint Online Directory Services 等）。 
 
![Office 365 租用戶資料同步處理](media/office-365-isolation-tenant-data-sync.png)

此模型內沒有任何單一資料來源的目錄。 每個個別的一段資料擁有特定系統使用，但沒有單一系統保留的所有資料。 Office 365 服務互相合作與 Azure Active Directory 来實現資料模型。 Azure Active Directory 是 」 的系統真偽 」 通常是通常每個服務所使用的小型和靜態資料的共用資料。 使用 Office 365 和 Azure Active Directory 中的同盟的模型提供資料的共用] 檢視。

Office 365 使用實體儲存裝置和 Azure 雲端儲存空間。 Exchange Online （包括 Exchange Online Protection） 和商務用 Skype 使用自己的儲存體的客戶資料。 SharePoint Online 會運用其 SQL Server 儲存與 Azure 儲存體，區間儲存層級的客戶資料的額外隔離的需要。

## <a name="exchange-online"></a>Exchange Online
Exchange Online 儲存名為的信箱資料庫的可延伸儲存引擎 (ESE) 資料庫中裝載的信箱內的客戶資料。 這包括使用者信箱、 連結的信箱、 共用的信箱和公用資料夾信箱。 使用者信箱也可能會包含已儲存的 Skype for Business 內容，例如交談歷程記錄。 使用者信箱的內容包含電子郵件和電子郵件附件、 行事曆及空閒/忙碌資訊、 連絡人、 工作、 記事、 群組和推斷資料。

在 Exchange Online 內每個信箱資料庫包含多個承租人的信箱。 所有信箱都受到授權程式碼，包括在租用戶內。 做為內部部署的 Exchange，預設只指派的使用者已存取至信箱。 保護信箱的存取控制清單 (ACL) 包含由 Azure Active Directory 租用戶層級驗證身分識別。 指定租用戶的信箱會受限於的身分識別驗證依據該租用戶的驗證提供者，其中包含從該租用戶的唯一使用者。 內容屬於 TenantA 無法以任何方式取得 TenantB 中, 使用者所除非明確 TenantA 經過核准。

## <a name="skype-for-business"></a>商務用 Skype
商務用 Skype 會將資料儲存在各種不同的位置：
- 使用者與帳戶資訊，其中包含連線端點，租用戶識別碼，撥號對應表，漫遊設定、 目前狀態、 連絡人清單等等，會儲存在 Skype for Business Active Directory 伺服器，以及各種 skype for Business 資料庫一部伺服器。 如果已對使用者啟用兩項產品，或在 Skype 商務伺服器如果使用者不是連絡人清單儲存在使用者的 Exchange Online 信箱。 Skype 商務資料庫伺服器不是分割每位租用戶，但透過 RBAC 強制執行多重租用隔離的資料。
- 會議內容，例如商務會議內容的使用者上傳期間 Skype 會儲存在分散式檔案系統的共用。 也可以將此內容封存在 Exchange Online 中，提供啟用封存。 DFS 共用分割每個租用戶，但使用 Acl 保護內容的安全且多重租用透過 RBAC 強制執行。
- 詳細通話記錄，也就是活動歷程記錄，例如通話記錄、 IM 工作階段、 應用程式共用、 IM 歷程記錄等等，也可以儲存在 Exchange Online 中，但是大部分的通話詳細記錄會暫時儲存通話詳細記錄 (CDR) 伺服器上。 每個租用戶，未分割的內容，但多重租用透過 RBAC 強制執行。

## <a name="sharepoint-online"></a>SharePoint Online
有唯一的 SharePoint Online 提供資料隔離的幾個獨立的機制。 SharePoint Online 會將物件儲存為抽象應用程式資料庫中的程式碼。 例如，當使用者將檔案上傳至 SharePoint Online，該檔案是反組譯轉譯成應用程式程式碼和多個資料庫儲存在多個資料表中。

如果使用者無法直接存取其中包含的資料儲存區，不會解譯 human 或 SharePoint Online 以外的任何系統的內容。 這些機制包括安全性存取控制和屬性。 如前所述，SharePoint Online 的所有資源都受到租用戶內包含的 RBAC 原則與授權程式碼。 保護資源的存取控制清單 (ACL) 包含在租用戶層級驗證身分識別。 如同 Exchange Online 中，在 SharePoint Online 中，指定租用戶資料僅限於的身分識別驗證依據該租用戶的驗證提供者，其中包含從該租用戶的唯一使用者。

除了 Acl，租用戶層級屬性，指定驗證提供者 （也就是租用戶特定的 Azure Active Directory），一次撰寫，且無法一次設定變更。 一旦針對租用戶設定 [驗證提供者] 租用戶屬性，就無法變更使用公開給租用戶的任何 Api。

唯一*SubscriptionId*也可用於每個租用戶。 客戶的所有網站擁有的租用戶，並指派*SubscriptionId*唯一至租用戶。 在網站上的*SubscriptionId*屬性寫入一次，且無法變更。 一旦網站指派給租用戶，它無法移至不同的租用戶，稍後再使用的內容儲存區 API。 *SubscriptionId*也是用來建立驗證提供者的安全性範圍和繫結至租用戶的索引鍵。

SharePoint Online 會使用 SQL Server 和 Azure 儲存體來儲存內容。 在 SQL 層級，內容存放區的磁碟分割索引鍵是*SiteId*。 當執行 SQL 查詢，SharePoint Online 使用已經驗證*SiteId*做為租用戶層級*SubscriptionId*檢查的一部分。

SharePoint Online 在 Microsoft Azure 中儲存檔案二進位 blob （例如，檔案資料流）。 每個 SharePoint Online 的伺服器陣列有它自己的 Microsoft Azure 帳戶，並儲存在 Azure 中的所有 blob 存加密個別使用儲存在 SQL 內容存放區中的機碼。 加密金鑰不會公開直接給一般使用者而言，而且在程式碼中受到授權層。 最後，SharePoint Online 已準備就緒可以偵測時的 HTTP 要求會讀取或寫入的多個承租人資料的即時監視。 它會追蹤*SubscriptionId*針對*SubscriptionId*所存取的資源要求身分識別。 存取多個租用戶的資源要求不應該發生的使用者。 它可以雖然發生在多承租人環境中，服務要求。 例如，搜尋編目程式會一次提取整個資料庫的內容變更。 這通常是牽涉到查詢中的單一服務要求，為了效率原因的多個租用戶的網站。
