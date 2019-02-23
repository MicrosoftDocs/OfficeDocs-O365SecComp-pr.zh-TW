---
title: Threat management in the Office 365 Security &amp; Compliance Center
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98
description: 協助控制及管理行動裝置存取您的組織資料、 從資料遺失保護您的組織使用 Threat management 以及從惡意軟體和垃圾郵件保護輸入及輸出郵件。您也可以使用 threat management 來保護您的網域信譽並決定要惡意詐騙的寄件者從您的網域帳戶。
ms.openlocfilehash: 30083c1e030921598d950afbedc78acab2a24910
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221163"
---
# <a name="threat-management-in-the-office-365-security-amp-compliance-center"></a>Threat management in the Office 365 Security &amp; Compliance Center

協助控制及管理行動裝置存取您的組織資料、 從資料遺失保護您的組織使用 Threat management 以及從惡意軟體和垃圾郵件保護輸入及輸出郵件。您也可以使用 threat management 來保護您的網域信譽並決定要惡意詐騙的寄件者從您的網域帳戶。
  
## <a name="how-to-view-and-use-threat-management-in-the-security-amp-compliance-center"></a>如何檢視及使用安全性威脅管理&amp;規範中心

Office 365 中使用安全性&amp;規範中心來管理在組織中的威脅。
  
 **若要直接移至 [安全性]&amp;規範中心：**
  
1. 移至 [https://protection.office.com](https://protection.office.com)。

2. 使用公司或學校帳戶登入 Office 365。

3. 在左窗格中，選取 [ **Threat management**。

    ![Office 365 安全性&amp;規範中心 Threat management 功能表](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **若要移至 [安全性]&amp;使用 Office 365 應用程式啟動器規範中心：**
  
1. 使用公司或學校帳戶登入 Office 365。

2. 選取 [應用程式啟動器![Office 365 中的應用程式啟動器圖示](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)在左上方角落、，，然後選取**安全性&amp;規範**並排顯示。 

3. 在左窗格中，選取 [ **Threat management**。

## <a name="about-threat-management-in-office-365"></a>關於 Office 365 中的潛在威脅管理

這些選項可用安全性**威脅管理**下&amp;規範中心。
  
我們仍推出的安全性威脅管理&amp;規範中心，您可能不看到所有這些尚未，或您可能會讓多個選項此處所列。期間導入，其中有些，例如反惡意程式碼、 Dkim，與其他人，會繼續可透過 Exchange 系統管理中心 (EAC) 有限的時間。

在某些情況下，有 EAC 與安全性的次要差異&amp;規範中心實作。例如，垃圾郵件篩選器支援的字元都不同之間的兩個平台。文章都提供可授與特定的差異的詳細資訊時所發生。
  
|**工具**|**描述**|
|:-----|:-----|
|**儀表板、 威脅 explorer 與事件** <br/> |一旦啟用，這些窗格可讓您管理 Office 365 分析和威脅智慧。如需詳細資訊，請參閱[Office 365 威脅智慧概觀 （英文）](office-365-ti.md)。<br/> |
|**郵件篩選** <br/> |微調及監視協助防止 Office 365 中的垃圾郵件的設定。建立允許與封鎖清單，請決定誰詐騙網域與原因，並設定並檢視垃圾郵件篩選器原則。如需詳細資訊，請參閱[Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)。<br/> 您也可以檢查您的使用者不傳送垃圾郵件設定的原則。這可以發生，例如，如果使用者的電腦會取得感染所設計用來傳送電子郵件訊息的惡意程式碼。若要了解您可以防止輸出垃圾郵件的方式，請參閱[設定輸出垃圾郵件原則](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)。<br/> 如果您目前遇到垃圾郵件問題，您可以使用[垃圾郵件和惡意程式碼的疑難排解員](https://configure.office.com/Scenario.aspx?sid=73)。           |
|**反惡意程式碼** <br/> |提供保護免受病毒及間諜軟體進出您組織中 Office 365。病毒的惡意軟體程式、 執行、 自我複製及修改其他程式和資料的電腦上。病毒散播整個電腦尋找程式感染的和也會從一部電腦共用至另一個通常是透過電子郵件。間諜軟體收集您的個人資訊，例如登入資訊，並傳送回其作者。若要開始設定反惡意程式碼原則，請參閱 ＜ [Configure 反惡意程式碼原則](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx)。<br/> 如果您目前遭遇到惡意程式碼有問題，您可以使用[垃圾郵件和惡意程式碼的疑難排解員](https://configure.office.com/Scenario.aspx?sid=73)。           |
|**DKIM** <br/> |適用對象的更進階的 Office 365 系統管理員，但提供給所有的 Office 365 客戶、 DomainKeys 識別郵件 (DKIM) 可協助確保其他電子郵件系統信任您從 Office 365 傳送的郵件。DKIM 執行方法是將唯一的數位簽章新增至您從您的組織傳送的電子郵件訊息。接收電子郵件從您的電子郵件系統可以使用此數位簽章可協助判斷是否合法電子郵件。<br/> 如果擔心的運作方式的詳細資料似乎複雜，因為您設定 Office 365 中的預設應該用於大多數的組織。如果您不需要設定 DKIM 自行、 Office 365 使用其預設原則 」 和 「 讓 DKIM 網域建立的機碼。此外，如果您停用之後進行一段時間，DKIM 簽署 Office 365 會自動啟用您網域的 Office 365 預設原則。<br/> 如果您想，您可以檢視此頁面安全性&amp;規範中心並且看見是否 DKIM 簽章目前已啟用您的網域，且您可以檢視 Office 365 所使用的加密金鑰已旋轉最後一次。您也手動可以自行旋轉機碼。<br/> **重要 ！** DKIM 是 Office 365 所使用的只有一個電子郵件驗證技巧。若要最有效地，DKIM 會使用搭配其他支援的技術等寄件者原則架構 (SPF) 和網域式訊息驗證，Reporting，and Conformance (DMARC)。在一起，這些網域型驗證技術協助防止垃圾郵件和詐騙不想要。<br/>  使用安全性 DKIM 以進行變更前&amp;規範中心，成為自信能達成技術和其運作方式。若要開始使用，請參閱[超過基本概念： 更多的方式來防止在 Office 365 中的垃圾郵件](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)。           |
|**安全附件**<br/>|[安全的附件](atp-safe-attachments.md)是進階威脅保護的一部分。啟用時，他們就會傳送給收件者的收件匣之前會與 Office 365 分開的特殊、 隔離環境中所開啟的電子郵件附件。安全的附件專門設計來協助即使之前防毒簽章可用偵測惡意的附件。若要深入了解，請參閱[Office 365 中的安全附件](atp-safe-attachments.md)。<br/> |
|**安全連結** <br/> |[安全的連結](atp-safe-links.md)是進階威脅保護的一部分。安全的連結可協助防止使用者在電子郵件或指向已辨識為惡意的網站的 Office 文件中的下列 Url。若要深入了解，請參閱[Office 365 中的安全連結](atp-safe-links.md)。<br/> |
|**隔離區**<br/>|設定[隔離區](http://go.microsoft.com/fwlink/p/?LinkID=809005)的 Office 365 其中已為垃圾郵件篩選的郵件大量、 網路釣魚、 中的內送電子郵件和惡意程式碼郵件可以保留供日後檢閱。使用者與系統管理員可以使用隔離的郵件。使用者可以使用剛才自己經過篩選的郵件隔離區中。系統管理員可以搜尋並管理隔離的郵件的所有使用者。<br/> |
|**進階的威脅** <br/> |檢視[威脅保護狀態報表](https://support.office.com/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats)以找到與封鎖的 Exchange Online Protection 和進階威脅保護惡意內容的相關資訊。  <br/> |
