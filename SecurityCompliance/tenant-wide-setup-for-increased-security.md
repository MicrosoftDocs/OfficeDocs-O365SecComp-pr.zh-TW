---
title: 設定 Office 365 租用戶以提高安全性
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: 逐步解說租用戶整體設定會影響您的 Office 365 環境的安全性建議的組態。 您的安全性需求可能需要更多或更少的安全性。 使用這些建議作為起點。
ms.openlocfilehash: bac2592fcfefaeb150497cddf134679f9429c656
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408248"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>設定 Office 365 租用戶以提高安全性

本主題引導您逐步完成會影響您的 Office 365 環境的安全性的全租用戶設定的建議組態。 您的安全性需求可能需要更多或更少的安全性。 使用這些建議作為起點。
  
## <a name="check-office-365-secure-score"></a>檢查 Office 365 安全分數

Office 365 安全分數分析根據您的日常活動和安全性設定的 Office 365 組織的安全性，並為其打分數。 開始 = 389917 記下您目前的分數。 調整某些租用戶整體設定會增加您的分數。 目標是未以達到最大的分數，但要注意的機會來保護您的環境，而不造成負面影響使用者產能。 請參閱 < <b0>Microsoft 安全分數</b0>。
  
## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>調整在 Microsoft 365 安全性中心中的威脅管理原則

在 Microsoft 365 安全性中心包含保護您的環境的能力。 它還包含報表和儀表板可用於監視，並採取動作。 某些區域隨附的預設原則設定。 某些區域未加上預設原則或規則。 請造訪 [調整更安全的環境威脅管理設定的威脅管理這些原則。 
  
|區域 * * *|包含預設原則 * * *|建議 * * *|
|:-----|:-----|:-----|
|**反網路釣魚** <br/> |是  <br/> | 如果您有自訂網域，請建立反網路釣魚原則來保護您最有價值的使用者，例如 CEO、 電子郵件帳戶，以及保護您的網域。 檢閱[設定防網路釣魚原則](set-up-anti-phishing-policies.md)，並建立原則，此範例使用做為指南: 「 範例： 反網路釣魚原則來保護使用者和網域。 」|
|**反惡意程式碼引擎** <br/> |是  <br/> | 編輯預設原則：  <br/> &ensp;&ensp;• 一般附件篩選類型-選取 [開啟]  <br/><br>  您也可以建立自訂惡意程式碼篩選原則，並將它們套用至指定的使用者、 群組或網域中，您組織中。  <br/> <br> 詳細資訊：  <br/> &ensp;&ensp;•[反惡意程式碼保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> &ensp;&ensp;•[設定反惡意程式碼原則](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**ATP 安全附件** <br/> |否  <br/> | 在 [安全附件的 [主要] 頁面中，檢查此方塊保護 SharePoint、 OneDrive 及 Microsoft Teams 中的檔案：  <br/>  &ensp;&ensp;• 開啟 atp SharePoint、 OneDrive 及 Microsoft Teams  <br/> <br> 使用這些設定新增新的安全附件原則：  <br/>  &ensp;&ensp;• 封鎖-封鎖目前和未來的電子郵件和附件的偵測到惡意程式碼 （請選擇這個選項）  <br/>  &ensp;&ensp;• 啟用重新導向 — （] 核取此方塊並輸入電子郵件地址，例如系統管理員或隔離區的帳戶）  <br/>  &ensp;&ensp;• 將上述選擇套用惡意程式碼掃描附件的逾時或就會發生錯誤 （核取此方塊）  <br/>  &ensp;&ensp;• 套用至 — 收件者選取的網域是 （網域）  <br/>  <br>更多資訊：[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md) <br/> |
|**ATP 安全連結** <br/> |是  <br/> | 將此設定加入至整個組織的預設原則：  <br/> &ensp;&ensp;• 使用中的安全連結： Office 365 專業增強版、 Office for iOS 和 Android （選取這個選項）。  <br/> <br>建議的特定收件者原則：  <br/>  &ensp;&ensp;• Url 將會修正並檢查針對已知惡意連結的清單，當使用者按一下連結時 （選取這個選項）。  <br/>  &ensp;&ensp;• 使用安全附件以掃描可下載內容 （核取此方塊）。  <br/>  &ensp;&ensp;• 套用至 — 收件者選取的網域是 （網域）。  <br/> <br> 更多資訊： [Office 365 ATP 安全連結](atp-safe-links.md)。  <br/> |
|**反垃圾郵件 （郵件篩選）** <br/> |是  <br/> | 該怎麼辦監看的：  <br/>  &ensp;&ensp;• 太多垃圾郵件-選擇 [自訂設定及編輯預設垃圾郵件篩選原則。  <br/>  &ensp;&ensp;• 詐騙智慧-檢閱詐騙網域的寄件者。 封鎖或允許這些寄件者。  <br/>  <br>更多資訊： [Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)。  <br/> |
|***電子郵件驗證*** <br/> |是  <br/> |電子郵件驗證會使用網域名稱系統 (DNS)，將可驗證資訊新增至相關的電子郵件寄件者的電子郵件訊息。 Office 365 設定為其預設網域 (onmicrosoft.com) 的電子郵件驗證，但 Office 365 系統管理員也可以使用的自訂網域的電子郵件驗證。 使用三種驗證方法： <br/> <br> &ensp;&ensp;• 寄件者原則架構 （或 SPF）。<br/>&ensp;&ensp;&ensp;&ensp;-如安裝程式，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 <br/> &ensp;&ensp;• DomainKeys 識別 Mail (DKIM)。 <br/> &ensp;&ensp;&ensp;&ensp;-請參閱[在 Office 365 中的自訂網域中的電子郵件使用 DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)。 <br>&ensp;&ensp;&ensp;&ensp;-您已設定 DKIM 之後，請在資訊安全中心啟用。<br/> &ensp;&ensp;• 網域型郵件驗證、 報告和執行符合性聲明 (DMARC)。 <br/> &ensp;&ensp;&ensp;&ensp;-如 DMARC 的安裝程式[使用 DMARC 來驗證 Office 365 中的電子郵件](use-dmarc-to-validate-email.md)。<br/>  <br/>
|

> [!NOTE]
> 針對 SPF 的非標準部署、 混合式部署，以及進行疑難排解： [Office 365 如何使用寄件者原則架構 (SPF)，來防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>檢視安全性與合規性中心中的儀表板和報告

請造訪這些報表和儀表板到深入了解您的環境的狀況。 這些報告中的資料將會變成為您的組織使用 Office 365 服務更豐富的。 現在，請先熟悉什麼您可以監視並採取相應動作。 如需詳細資訊，請參閱：[報告中的 Microsoft 365 安全性與合規性中心](reports-in-security-and-compliance.md)。
  
|儀表板 * * *|****描述****|
|:-----|:-----|
|[威脅管理儀表板](security-dashboard.md)  <br/> |資訊安全中心的**威脅管理**] 區段中，使用此儀表板來查看有已處理的威脅，並做為報告哪些威脅商務決策者的便利工具調查及回應功能已經有為了保護您的業務。  <br/> |
|[威脅總管 （或即時偵測的資訊）](threat-explorer.md)  <br/> |這也是**威脅管理**] 區段中的資訊安全中心。 如果您正在調查，或針對您的 Office 365 租用戶可能遭受攻擊，使用檔案總管] （或即時偵測） 來分析威脅。 Explorer （並即時偵測] 報告） 顯示您的攻擊的磁碟區一段時間，，您可以分析威脅系列、 攻擊者基礎結構，以及其他此資料。 您也可以標示任何可疑的電子郵件事件清單。  <br/> |
|報告 — 儀表板  <br/> |在 [安全性中心] 的 [**報告**] 區段中，檢視稽核報告的 SharePoint Online 和 Exchange Online 組織。 您也可以存取 Azure Active Directory (Azure AD) 使用者登入報告，使用者活動報告，並從 [**檢視報告**] 頁面上的 Azure AD 稽核記錄。  <br/> |
   
![資訊安全中心儀表板](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>設定 Exchange Online 的其他全租用戶設定

許多安全性和保護在 Exchange 系統管理中心中的控制項也會包含資訊安全中心。 您不需要設定這些這兩個位置中。 以下是幾個建議的其他設定。 
  
|區域 * * *|包含預設原則 * * *|建議 * * *|
|:-----|:-----|:-----|
|**郵件流程**（郵件流程規則，也稱為傳輸規則）|否|新增郵件流程規則，以協助防範勒索軟體。 請參閱此部落格文章中的 < 如何使用 Exchange 傳輸規則來追蹤或封鎖電子郵件與勒索軟體所使用的檔案副檔名 >:<b0>如何處理勒索軟體</b0>。 <br><br/> 請參閱下列主題： <br/>•[針對勒索軟體保護](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide#ransomware)<br/>•[惡意程式碼和勒索軟體防護，Office 365 中](office-365-malware-and-ransomware-protection.md)<br/><br/>  建立郵件流程規則，以防止自動轉寄電子郵件至外部網域。 如需詳細資訊，請參閱[減輕用戶端外部轉寄規則與安全分數](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。 <br/><br/> 更多資訊：[郵件流程規則 （傳輸規則） 在 [Exchange Online](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx)|
|**啟用新式驗證**|否|Office 365 中的新式驗證是使用多重要素驗證 (MFA) 的必要條件。 MFA 被建議用於保護雲端資源，包括電子郵件的存取權。 <br/><br/> 請參閱下列主題：  <br/>•[啟用或停用新式驗證在 Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/>• [Skype for Business Online： 啟用新式驗證在租用戶](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> 預設會啟用新式驗證的 Office 2016 用戶端、 SharePoint Online 和商務用 OneDrive。 <br/><br/> 更多資訊：[使用 Office 365 新式驗證搭配 Office 用戶端](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)|
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>在 SharePoint 系統管理中心中設定全租用戶共用原則

Microsoft 建議在增加保護，開頭基準保護層級設定 SharePoint 小組網站。 如需詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)
  
SharePoint 小組網站的基準層級設定允許利用匿名存取連結與外部使用者共用檔案。 而非傳送電子郵件中的檔案，建議您使用此方法。 
  
若要支援基準保護目標，請設定全租用戶共用原則，以下建議的方式。 共用設定個別的網站可以比這個全租用戶原則，但不是更寬鬆限制更多。 
  
|區域 * * *|包含預設原則 * * *|建議 * * *|
|:-----|:-----|:-----|
|**共用**（SharePoint Online 和商務用 OneDrive）|是|預設會啟用外部共用。 建議使用下列設定： <br/>• 允許與經過驗證外部使用者共用，以及使用匿名存取連結 （預設值）。 <br/>  • 匿名存取連結在這幾天內到期。 若有需要，例如 30 天，請輸入數字。 <br/>• 預設連結類型-選取 [內部] （僅限組織裡的人員）。 想要共用使用匿名連結的使用者必須從 [共用] 功能表選擇此選項。 <br/><br/> 更多資訊：[外部共用概觀](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85)|
   
SharePoint 系統管理中心和 OneDrive for 商務版系統管理中心包含相同的設定。 在 [系統管理中心中的設定套用至兩者。
  
## <a name="configure-settings-in-azure-active-directory"></a>設定 Azure Active Directory 中的設定

請務必瀏覽至完成更安全的環境的全租用戶設定 Azure Active Directory 中這兩個區域。
  
### <a name="configure-named-locations-under-conditional-access"></a>設定具名的位置 （在 [條件式存取）

如果貴組織有辦公室具有安全的網路存取權，將信任的 IP 位址範圍新增至 Azure Active Directory 做為具名位置。 這項功能可協助減少登入風險事件報告誤判的數目。 
  
請參閱： [Azure Active Directory 中的具名位置](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>封鎖應用程式不支援新式驗證

多重要素驗證需要支援新式驗證的應用程式。 不支援新式驗證的應用程式不能使用條件式存取規則被封鎖。
  
安全的環境中，務必停用不支援新式驗證的應用程式的驗證。 您可以運用這 Azure Active Directory 中即將推出的控制項。
  
同時，使用下列方法之一來完成這項作業的 SharePoint Online 和商務用 OneDrive:
  
- 使用 PowerShell，請參閱[封鎖應用程式，請勿使用新式驗證](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)。
    
- 在 SharePoint 系統管理中心中設定此 「 裝置存取] 頁面上 — 」 控制從不使用新式驗證的應用程式的存取 」。 選擇 [封鎖]。 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>開始使用 Cloud App Security 或 Office 365 雲端 App 安全性

若要評估上可疑的活動警訊的風險，並自動採取動作，請使用 Office 365 雲端 App 安全性。 需要 Office 365 E5 方案。
  
或者，使用 Microsoft Cloud App Security，以取得更深入的可見度偶數之後授與存取權、 完整的控制項和所有雲端應用程式，包括 Office 365 改良的保護。 
  
因為此解決方案建議 EMS E5 方案，我們建議您從開始 Cloud App Security，您可以與其他 SaaS 應用程式中使用這個，在您的環境中。 啟動與預設原則和設定。
  
詳細資訊：
  
- [部署 Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Microsoft Cloud App Security 的詳細資訊](https://www.microsoft.com/cloud-platform/cloud-app-security)
    
- [雲端 App 安全性是什麼？](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
    
![Cloud App Security 儀表板](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>其他資源

這些文章及輔助線提供其他規定資訊保護您的 Office 365 環境：
  
- [適用於政治活動、 非營利組織和其他彈性組織的 Microsoft 安全性指南](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)（您可以在任何的環境，尤其是僅限雲端環境中使用這些建議） 
    
- [建議的安全性原則和設定身分識別與裝置](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations)（這些建議包含 AD FS 環境的說明） 
    

