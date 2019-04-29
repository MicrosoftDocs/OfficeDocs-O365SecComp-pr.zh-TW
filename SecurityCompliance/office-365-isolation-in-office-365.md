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
ms.openlocfilehash: 748da21f5b5048bb4ae4c14700ed482fd6d0058c
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402891"
---
# <a name="isolation-and-access-control-in-office-365"></a>Office 365 中的隔離與存取控制

Azure Active Directory 和 Office 365 使用高度複雜的資料模型，其中包含數萬個服務，數百個實體，千分位的關聯性和數以萬計的屬性。 在較高層級、 Azure Active Directory 與服務目錄會是租用戶和保持同步處理使用狀態為基礎的複寫通訊協定的收件者容器。 除了 Azure Active Directory 內保留的目錄資訊，每個服務工作負載有自己的目錄服務基礎結構。
 
![Office 365 租用戶資料同步處理](media/office-365-isolation-tenant-data-sync.png)

此模型內沒有任何單一資料來源的目錄。 特定系統自己的個別資料，但沒有單一系統會保留所有的資料。 Office 365 服務一起合作與 Azure Active Directory 中，以這種資料模型。 Azure Active Directory 是通常是由每個服務所使用的小型和靜態資料的共用資料的 「 系統真偽 」。 使用 Office 365 和 Azure Active Directory 中的同盟的模型提供資料的共用] 檢視。

Office 365 使用實體儲存裝置和 Azure 雲端儲存空間。 Exchange Online （包括 Exchange Online Protection） 和商務用 Skype 使用自己的儲存體的客戶資料。 SharePoint Online 會使用 SQL Server 儲存區與 Azure 儲存體，因此需要客戶資料的額外隔離儲存層級。

## <a name="exchange-online"></a>Exchange Online

Exchange Online 儲存信箱內的客戶資料。 稱為信箱資料庫的可延伸儲存引擎 (ESE) 資料庫中裝載的信箱。 這包括使用者信箱、 連結的信箱、 共用的信箱及公用資料夾信箱。 使用者信箱中也包含儲存的 Skype for Business 的內容，例如交談歷程記錄。

使用者信箱內容包括：

- 電子郵件和電子郵件附件
- 行事曆及空閒/忙碌資訊
- Contacts
- 工作
- 附註
- 群組
- 推斷資料

在 Exchange Online 內每個信箱資料庫包含多個承租人的信箱。 授權程式碼保護每個信箱，包括在租用戶內。 根據預設，只有指派的使用者存取信箱。 保護信箱的存取控制清單 (ACL) 包含由 Azure Active Directory 租用戶層級驗證身分識別。 每個租用戶的信箱會受限於對租用戶的驗證提供者，其中包含只從該租用戶的使用者驗證的身分識別。 在租用戶的內容無法以任何方式取得租用戶 B 中的使用者所除非明確核准的租用戶 a。

## <a name="skype-for-business"></a>商務用 Skype

商務用 Skype 會將資料儲存在不同位置：

- 使用者與帳戶資訊，其中包含連線端點，租用戶識別碼，撥號對應表，漫遊設定、 目前狀態、 連絡人清單等等，儲存在商務 Active Directory 伺服器，商務用 Skype 和各種 Skype for Business 資料庫伺服器。 如果已對使用者啟用兩項產品，或在 Skype 商務伺服器如果使用者不是連絡人清單儲存在使用者的 Exchange Online 信箱。 Skype for Business 資料庫伺服器不已分割的每個承租人，但是透過角色型存取控制 (RBAC) 強制執行多重租用隔離的資料。
- 會議內容以及上傳的資料會儲存在分散式檔案系統 (DFS) 共用。 此內容可以也封存在 Exchange Online 如果已啟用。 DFS 共用不分割每個租用戶。 使用 Acl 保護內容的安全，多重租用透過 RBAC 強制執行。
- 詳細通話記錄，也就是活動歷程記錄，例如通話記錄、 IM 工作階段、 應用程式共用、 IM 歷程記錄等等，也可以儲存在 Exchange Online 中，但是大部分的通話詳細記錄會暫時儲存通話詳細記錄 (CDR) 伺服器上。 每個租用戶，未分割的內容，但多重租用透過 RBAC 強制執行。

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online 有幾個獨立的機制，提供資料隔離。 它會將物件儲存為抽象應用程式資料庫中的程式碼。 比方說，當使用者將檔案上傳至 SharePoint Online，檔案會反組譯、 轉譯成應用程式的程式碼，並儲存在多個資料表中跨多個資料庫。

如果使用者無法直接存取其中包含的資料儲存區，內容不解譯 human 或任何以外的 SharePoint Online 的系統。 這些機制包括安全性存取控制和屬性。 SharePoint Online 的所有資源都受到租用戶內包含的 RBAC 原則與授權程式碼。 保護資源的存取控制清單 (ACL) 包含在租用戶層級驗證身分識別。 SharePoint Online 租用戶資料僅限於驗證租用戶的驗證提供者的身分識別。

除了 Acl，租用戶層級屬性，指定驗證提供者 （也就是租用戶特定的 Azure Active Directory），一次撰寫，且無法一次設定變更。 一旦針對租用戶設定 [驗證提供者] 租用戶屬性，就無法變更使用公開給租用戶的任何 Api。

唯一*SubscriptionId*用於每個租用戶。 客戶的所有網站所擁有的租用戶，並指派給租用戶的*SubscriptionId*唯一。 *SubscriptionId*屬性在網站上的一次撰寫，而且是永久性。 一旦指派給租用戶，網站無法移至不同的租用戶。 *SubscriptionId*是用來建立驗證提供者安全性範圍的索引鍵，並繫結至租用戶。

SharePoint Online 使用 SQL Server 和 Azure 儲存體內容的中繼資料存放區。 內容存放區的磁碟分割索引鍵是*SiteId* SQL 中。 當執行 SQL 查詢，SharePoint Online 會使用驗證的租用戶層級*SubscriptionId*檢查一部分*SiteId* 。

SharePoint Online 中 Microsoft Azure blob 儲存加密的檔案內容。 每個 SharePoint Online 的伺服器陣列有它自己的 Microsoft Azure 帳戶及個別 SQL 內容存放區中的機碼會使用加密儲存在 Azure 中的所有 blob。 加密金鑰的授權層保護在程式碼中，而且不直接公開到使用者。 SharePoint Online 具有即時監視偵測時的 HTTP 要求會讀取或寫入一個以上的租用戶的資料。 要求身分*SubscriptionId*追蹤對*SubscriptionId*的存取資源。 由使用者時，應該不會發生要求存取多個租用戶的資源。 在多承租人環境中的服務要求是唯一的例外狀況。 例如，搜尋編目程式會一次提取整個資料庫的內容變更。 這通常是牽涉到查詢中的單一服務要求，為了效率原因的多個租用戶的網站。
