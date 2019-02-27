---
title: Office 365 電子郵件反垃圾郵件保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 了解反垃圾郵件設定和篩選可協助您避免在 Exchange Online 與 Office 365 中的垃圾郵件。取得 Office 365 太多垃圾郵件吗？您可以自訂您的垃圾郵件篩選和反垃圾郵件原則設定。
ms.openlocfilehash: f4d32bb0efae0a38fdc6789feef73bd5014eb75b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296316"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 電子郵件反垃圾郵件保護

您擔心太多 Office 365 中的垃圾郵件吗？我們已內建多個垃圾郵件篩選您的 Office 365 或 Exchange Online Protection (EOP) 服務，因此從您會收到您第一封郵件可用來保護電子郵件。以協助防止 Office 365 中的垃圾郵件，您可能會想要變更保護設定來處理您的組織中的特定問題 — 說出您要接收來自特定寄件者許多的垃圾郵件例如 — 或至只可調整您的設定，讓它們自訂最佳開會組織的需求。為達成此目的，您可以變更 Office 365 安全性的反垃圾郵件設定&amp;規範中心。
  
本文適用於 Office 365 系統管理員的。如果您不是系統管理員，但您是 Office 365 使用者，您想要了解如何處理垃圾郵件您收到這不是您在這裡尋找文章。但是，如果您使用的 PC Outlook 或 Outlook for Mac，開始使用[垃圾郵件篩選工具的概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。如果您使用 Outlook web 上的，開始使用[了解垃圾郵件和網路釣魚](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)。
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>這些選項可協助您避免在 Office 365 中的垃圾郵件

 **連線篩選。** 當您使用的連線篩選時，Office 365 檢查允許取得訊息之前的寄件者信譽。您可以建立的 [允許] 清單或安全的寄件者] 清單中，以確保您收到來自特定 IP 位址或 IP 位址範圍傳送給您每封郵件。您也可以建立用來封鎖郵件，稱為封鎖清單中的 IP 位址清單。如需詳細資訊，請參閱[設定連線篩選原則](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)。如果您擔心在 Office 365 中的垃圾郵件，請使用連線以協助防止垃圾郵件篩選。
  
如有 Office 365 企業版 E5 或已購買進階威脅保護 (ATP) 授權客戶、 連線篩選用以詐騙智慧建立允許與封鎖的寄件者詐騙網域的清單。如需詳細資訊，請參閱[了解更多關於詐騙智慧](https://go.microsoft.com/fwlink/?LinkID=735009)。
  
 **垃圾郵件篩選。** Office 365 的郵件特性與垃圾郵件一致使用檢查垃圾郵件篩選。您可以變更會被識別為垃圾郵件的郵件上進行，並選擇是否要篩選以特定語言編寫或寄自特定國家或地區的郵件的動作。您也可以開啟進階垃圾郵件篩選選項，如果您想要執行及垃圾郵件篩選不積極方法。此外，您可以設定使用者垃圾郵件通知時對象為他們的訊息傳送至隔離區改用通知使用者。（將郵件傳送至隔離區是其中一個可設定的動作）。從這些通知，使用者可以釋出誤判並向 Microsoft 報告進行分析。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](https://go.microsoft.com/fwlink/p/?LinkId=617147)。若要協助防止 Office 365 中的垃圾郵件，請使用垃圾郵件篩選，如果您擔心太多 Office 365 中的垃圾郵件、 使用連線以協助防止垃圾郵件篩選。
  
> [!NOTE]
> 如 EOP 獨立版客戶： 根據預設，EOP 垃圾郵件篩選器將垃圾郵件偵測到的郵件傳送至每個收件者的垃圾郵件] 資料夾。不過，以確保**將郵件移至 [垃圾郵件] 資料夾**動作將會使用內部部署信箱，您必須設定兩個 Exchange 傳輸規則來偵測垃圾郵件標頭新增 EOP 的內部部署伺服器上。如需詳細資訊，請參閱[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)。 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>如果您在 Office 365 中收到太多垃圾郵件的額外資訊

下列視訊提供設定垃圾郵件篩選 EOP 中的概觀。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
如需詳細資訊，請參閱 ＜ [Configure 垃圾郵件篩選器原則](https://go.microsoft.com/fwlink/p/?LinkId=617147)主題。
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>檢查您的外寄郵件以避免在 Office 365 中的垃圾郵件

 **輸出篩選。** Office 365 也進行檢查以確認您的使用者對外傳送垃圾郵件。例如，使其傳送垃圾郵件，讓我們建立呼叫*輸出篩選*的理想的惡意程式碼可能會取得感染使用者的電腦。您無法關閉輸出篩選，但是您可以設定[設定輸出垃圾郵件原則](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)所述的設定。如果您擔心太多 Office 365 中的垃圾郵件，用於輸出篩選協助防止在 Exchange Online 中的垃圾郵件。
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>超過基本概念： 若要防止在 Office 365 中的垃圾郵件更多的方式

 **郵件流程規則。** 如果您想要超越內建的垃圾郵件篩選及建立自訂規則的企業原則、*[郵件流程規則](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*，也稱為*傳輸規則*根據、 會協助您的另一個篩選器會防止在 Office 365 中的垃圾郵件。例如，您可用於郵件流程規則中[使用設定垃圾郵件信賴等級 (SCL) 中的郵件的郵件流程規則](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx)所述設定的垃圾郵件信賴等級 (SCL) 值符合特定條件的郵件。
  
 **電子郵件的驗證。** 使用網域名稱系統 (DNS) 將可驗證資訊新增至相關的電子郵件寄件者的電子郵件訊息的技術稱為電子郵件的驗證。系統管理員可以進行更進階的 Office 365 使用這些電子郵件的驗證方法：
  
- **寄件者原則架構 (SPF)。** SPF 驗證確認對 alleged 的傳送端網域擁有者的寄件者的 IP 位址的電子郵件訊息的原點而言。快速介紹 SPF 以及要取得其快速地設定，請參閱[Set up SPF 避免詐騙的 Office 365 中](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。更深入了解 Office 365 如何使用 SPF，或者例如混合部署的疑難排解或非標準部署開始使用[Office 365 如何使用寄件者原則架構 (SPF) 若要防止詐騙](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。

- **DomainKeys 識別郵件 (DKIM)。** DKIM 可讓您附加至您傳送電子郵件訊息標頭中的電子郵件的數位簽章。從您的網域接收電子郵件的電子郵件系統來決定其接收內送電子郵件是否合法使用此數位簽章。如需 DKIM 與 Office 365 的資訊，請參閱[使用 DKIM 驗證自 Office 365 中您網域傳送的輸出電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。

- **網域式訊息驗證、 報告和符合性 (DMARC)。** 接收的郵件系統的 DMARC 協助決定如何處理失敗 SPF 或 DKIM 檢查，並提供其他的信任層級的電子郵件協力廠商的郵件。如需設定 DMARC 資訊，請參閱[使用 DMARC 來驗證 Office 365 中的電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。

如果您擔心垃圾郵件、 網路釣魚和詐騙 Office 365 中，使用 SPF、 DKIM、 和 DMARC 一起以協助防止垃圾郵件和詐騙不想要。
  
 **使用者受管理的設定。** 如果您正在尋找使用者如何管理自己的垃圾郵件設定的相關資訊，查看[概觀垃圾郵件篩選工具](https://go.microsoft.com/fwlink/?LinkId=270065)（適用於 Microsoft Outlook 使用者） 或[解垃圾郵件和網路釣魚](https://go.microsoft.com/fwlink/?LinkId=270068)（適用於 web 使用者在 Outlook)。如果您使用 EOP 來保護內部部署信箱，請務必以確保這些設定會同步處理至服務使用目錄同步處理。如需設定目錄同步作業的詳細資訊，請參閱在[EOP 中的管理郵件使用者](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)的 「 使用目錄同步作業管理郵件使用者 」。
  
## <a name="for-more-information"></a>如需詳細資訊

[部落格： 為什麼沒有垃圾郵件和網路釣魚取得透過 Office 365？](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[反垃圾郵件保護常見問題集](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[使用安全清單或其他技術防止誤判電子郵件標示為垃圾郵件](prevent-email-from-being-marked-as-spam-0.md)
  
[如何設定 Office 365 垃圾郵件篩選可協助封鎖垃圾郵件](reduce-spam-email.md)
  
[什麼是垃圾郵件與大量電子郵件的差異？](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[反垃圾郵件訊息標頭](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[非法回應郵件與 EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a>其他資源

[從 Office 365 社群論壇獲得協助](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[管理員：登入及建立服務要求](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[管理員：連絡支援人員](https://go.microsoft.com/fwlink/p/?LinkID=518322)
