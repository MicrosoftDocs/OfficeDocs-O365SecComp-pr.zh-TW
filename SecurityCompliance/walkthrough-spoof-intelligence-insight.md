---
title: 逐步解說詐騙智慧洞察力
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: 請參閱新詐騙智慧洞察力的運作方式。
ms.openlocfilehash: ca9c4ae6f2d65ef2700a2e02acd5b4f1dfbfe903
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22596092"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>逐步解說： 詐騙智慧洞察力

藉由使用詐騙智慧洞察力，您可以快速地決定哪些寄件者的合法傳送未經驗證電子郵件。藉由 documents 它們傳送詐騙的郵件，您可以減少任何誤判移至您的使用者的風險。
  
此外，您也可以使用詐騙智慧監視及管理提供多一層的安全性及防止不安全的郵件抵達您組織中的允許的網域配對。
  
您可以使用詐騙智慧洞察力安全性&amp;規範中心如果工作或學校帳戶具有已授與 Office 365 全域管理員、 安全性管理員或安全性讀取權限。如需詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。
  
如果您是新[報告與 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)，它可能會說明若要查看如何您可以輕鬆地瀏覽儀表板至洞察力及建議的動作。
  
您可以檢視多個儀表板詐騙智慧洞察力安全性&amp;規範中心。不論您正在查看哪些儀表板、 洞察力提供相同的詳細資訊與可讓您快速地執行的相同工作。
  
這是一個安全性的數個逐步解說&amp;規範中心。若要瀏覽提供及報告，請參閱 [相關的主題] 區段中的逐步解說。
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>易於存取安全性詐騙智慧洞察力&amp;規範中心

1. 若要開始，您將需要[移至 [安全性&amp;規範中心](go-to-the-securitycompliance-center.md)。
    
2. 安全性&amp;規範管理中心，移至**Threat Management** \> **儀表板。**
    
3. 在 [**前瞻**] 列中，尋找詐騙智慧洞察力。如果您已啟用詐騙智慧則洞察力即資格**Spoofed 網域的失敗的過去 30 天的驗證**。如果尚未啟用詐騙保護，然後據會提示您可以使用標題**啟用詐騙保護**來進行。 
    
## <a name="about-the-insight-on-the-dashboard"></a>關於儀表板上洞察力

在儀表板上的洞察力會顯示類似的資訊。
  
![詐騙智慧洞察力的螢幕擷取畫面](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
此洞察力有兩種模式：
  
 **洞察力模式**。如果您有啟用任何詐騙原則，然後據顯示我們詐騙智慧功能所影響多少信箱過去 30 天。 
  
 **怎麼辦模式**。如果您沒有任何已啟用的詐騙原則，然後據顯示多少信箱*會*有已受到我們詐騙智慧功能過去 30 天。 
  
無論如何，顯示在洞察力詐騙的網域分成兩個類別 ；可疑網域配對和非可疑網域組。這些類別會進一步細分為三個不同的 bucket 您檢閱。 
  
*網域配對*是組合"從:"地址及傳送基礎結構。 
  
- "From"地址是由您的郵件應用程式顯示 From 地址的地址。這個位址會識別作者的電子郵件。也就是人員或系統負責撰寫郵件的信箱。這有時稱為 5322.From 地址。
    
- 傳送基礎結構、 或寄件者為組織網域的傳送端 IP 位址的 PTR 記錄。如果傳送的 IP 位址已無的 PTR 記錄，則寄件者與 255.255.255.0 識別所傳送的 IP 子網路遮罩中 CIDR 註解 （/ 24）。例如，如果的 IP 位址為 192.168.100.100 寄件者的完整 IP 位址則 192.168.100.100/24。
    
 **可疑網域配對**包括： 
  
- **高信賴詐騙**。Office 365 接收強式信號這些網域所可疑，根據歷程記錄傳送模式和網域信譽分數。Office 365 是高度有信心網域詐騙及這些網域傳送的訊息是較不可能是合法。 
    
- **中等信賴詐騙**。Office 365 接收中等信號這些網域所可疑，根據歷程記錄傳送模式和網域信譽分數。Office 365 是溫和有信心網域詐騙及這些網域傳送的訊息是合法。此 bucket 有更大的包含誤判 (FPs) 較高信賴詐騙 bucket 機會。 
    
 **非可疑網域配對**包括**人詐騙**。救回的詐騙都無法明確驗證檢查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) 但傳遞我們延伸的驗證檢查的網域。因為這、 Office 365 人代替您撥打電話郵件和反詐騙採取任何動作已的郵件。 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>檢視來自詐騙智慧洞察力可疑網域成對的詳細的資訊

1. 在詐騙智慧洞察力中，按一下 [任何網域配對 （高、 中級或救回）。
  
**詐騙智慧洞察力**] 頁面上會出現顯示的已傳送至您的組織未經過驗證的郵件的寄件者清單。在此頁面上的資訊可協助您判斷是否詐騙的郵件已獲得授權，或未或如果您需要進一步採取動作。您可以排序資訊的郵件計數上次偵測到詐騙、 日期及其他。（按一下欄標題，例如**訊息計數**或**上次呈現**，例如）。 
    
2. 若要開啟 [詳細資料] 窗格包含網域一組豐富的資訊表格中選取項目，包括為什麼我們攔截這，您需要做些什麼，網域摘要、 WhoIs 資料相關的寄件者和類似我們討論過在您的租用戶從相同的寄件者的電子郵件。從這裡，您也可以選擇新增或移除**AllowedToSpoof**安全寄件者清單中的網域組的名稱。 
  
![詐騙智慧洞察力詳細資料窗格中的網域的螢幕擷取畫面](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>新增或移除 AllowedToSpoof 安全寄件者清單中的網域

您新增或移除 AllowedToSpoof 安全寄件者清單中的網域，時檢閱詐騙智慧洞察力網域組詳細資料窗格中。只是據此設定切換。
  
這會修改詐騙的網域和傳送基礎結構的唯一的網域配對組合，而不提供涵蓋範圍的整個詐騙的網域] 或 [隔離傳送基礎結構。例如，如果 'AllowedToSpoof' 寄件者新增下列網域對允許清單：*詐騙網域*"gmail.com"和*傳送基礎結構*"tms *。 mx.com"，* 則只能從該網域配對的郵件仍可詐騙。其他的寄件者嘗試詐騙"gmail.com"和"tms.mx.com"嘗試詐騙會繼續詐騙智慧會受到其他網域。 
  
## <a name="related-topics"></a>相關主題

[深入了解詐騙情報](learn-about-spoof-intelligence.md)
  
[Office 365 的反詐騙保護](anti-spoofing-protection.md)
  
[逐步解說 - 從儀表板到深入解析](from-a-dashboard-to-an-insight.md)
  
[逐步解說 - 從詳細報告到深入解析](from-a-detailed-report-to-an-insight.md)
  
[逐步解說 - 從深入解析到詳細報告](from-an-insight-to-a-detailed-report.md)
  

