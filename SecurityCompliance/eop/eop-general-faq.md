---
title: EOP 一般常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：
ms.openlocfilehash: 00618618d251e1478cb0dc0a0fbb116db2565fad
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693192"
---
# <a name="eop-general-faq"></a>EOP 一般常見問題集

在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：
  
- [EOP 排入佇列、延後和退回的訊息常見問題集](eop-queued-deferred-and-bounced-messages-faq.md)
    
- [委派管理常見問題集](delegated-administration-faq.md)
    
- [反垃圾郵件保護常見問題集](../anti-spam-protection-faq.md)
    
- [安全寄件者和封鎖的寄件者會列出在 Exchange Online](../safe-sender-and-blocked-sender-lists-faq.md)
    
- [隔離常見問題集](../quarantine-faq.md)
    
- [反惡意程式碼保護常見問題集](../anti-malware-protection-faq-eop.md)
    
- [Message Trace FAQ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx)
    
- [FOPE to EOP Transition FAQ](http://technet.microsoft.com/library/e0e76b89-b0d3-4c0a-bfc8-137b579e983b.aspx)
    
 **問：EOP 是什麼？**
  
答：EOP 是雲端電子郵件篩選服務，專門用來保護客戶遠離垃圾郵件與惡意程式碼，以及執行自訂原則規則。
  
 **問：如何註冊 EOP 試用版或購買 EOP？**
  
答：可透過以下網址註冊 EOP 試用版或購買 EOP：[Exchange Online Protection 首頁](https://go.microsoft.com/fwlink/p/?LinkId=279912)。請注意，試用購買的功能與付費訂閱版相同，但另外包含 [Exchange Enterprise CAL with Services](https://go.microsoft.com/fwlink/p/?LinkId=320619) 訂閱方案提供的其他功能。 
  
 **問：EOP 如何定價？**
  
答：EOP 是依使用者授權。如需最新定價資訊，請參閱 [Exchange Online Protection 首頁](https://go.microsoft.com/fwlink/p/?LinkId=279912)。
  
 **問：將 EOP 放入實際執行環境需時多久？**
  
答：當您依照[設定 EOP 服務](set-up-your-eop-service.md)中所述步驟變更 MX 記錄，以及透過 EOP 變更郵件流程，就會立即開始進行篩選。MX 記錄可能需要 24-48 個小時，以透過 DNS 進行傳播。在處理過程中，您隨時可以在 Exchange 系統管理中心 (EAC) 中微調您的保護設定。
  
 **問：我必須使用 Microsoft Office 365 的所有功能才能使用 EOP 嗎？如果我只想要 EOP 保護呢？**
  
答：您可以使用 EOP 保護您的內部部署信箱，而不需使用 Office 365 的任何其他功能。這也稱為獨立訂閱。[Exchange Online Protection 服務描述](https://go.microsoft.com/fwlink/p/?LinkId=320619)會提供 EOP 功能的清單。
  
 **問：透過 EOP 註冊電子郵件篩選時，為什麼需要 Office 365 租用戶？**
  
答：Office 365 是提供給一組可透過 Office 365 租用戶存取的產品和服務名稱。請將 Office 365 租用戶想像成新增授權以篩選電子郵件的起點。
  
 **問：EOP 是否有通訊入口網站可讓我了解已知問題和預期的解決方案？有哪些新功能？**
  
答：是。 在 Microsoft 365 系統管理中心會有一些這項資訊。 如果您受影響的服務層級事件接著您應該會看到通訊警示 （通常伴隨著鈴鐺圖示） 之後登入 Microsoft 365 系統管理中心。 建議您詳讀內容並採取適當的行動。
  
關於新的 EOP 功能，[商務用 Office 365 導覽圖](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)是很好的資源，可以在其中尋找新功能的相關資訊。我們也會在 [Office 部落格](https://go.microsoft.com/fwlink/p/?LinkId=392724)網站上發表關於新功能的部落格文章。 
  
 **問：此服務可與舊版 Exchange (例如 Exchange Server 2010) 和非 Exchange 環境搭配使用嗎？**
  
答：可以，此服務與伺服器無關，可與任何 SMTP 郵件傳輸代理程式共用。
  
 **問：哪種組織規模可以使用此項服務？**
  
問：所有規模都可以。無論您組織的成長速度多快，EOP 網路都有足夠容量可容納成長。
  
 **我需要哪些權限才能設定 EOP？**
  
若要設定 EOP，您必須是 Office 365 全域管理員或 Exchange 公司管理員 (組織管理角色群組)。
  
 **問：我如何確定我的資料和私人資訊是安全的？**
  
答：若想深入了解我們為了確保您的資料和私人資訊之安全所採取的措施，包括服務等級協定 (SLA) 的相關資訊，請前往 [Office 365 信任中心](https://go.microsoft.com/fwlink/p/?LinkId=285405)。
  
 **問：是否有我應該知道的任何限制，例如郵件大小限制？**
  
答：是。如需 EOP 限制的詳細資訊，請參閱＜[Exchange Online Protection 限制](https://go.microsoft.com/fwlink/p/?LinkId=402617)＞。 
  
 **問：EOP 支援遠端 Windows PowerShell 嗎？**
  
答：是。透過遠端 Windows PowerShell 可使用完整的 EOP 功能。如需詳細資訊，請參閱＜[Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)＞。
  

