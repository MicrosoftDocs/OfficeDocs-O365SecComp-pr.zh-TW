---
title: 設定您的 Office 365 租用戶以提高安全性
ms.author: tracyp
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: 帶領您完成建議的租用戶整個設定會影響您的 Office 365 環境的安全性設定。安全性需求可能需要更多或更少的安全性。使用這些建議為起點。
ms.openlocfilehash: 95b00d2f5a5c77eff1fcef2450ffb20ce5c57617
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213923"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>設定您的 Office 365 租用戶以提高安全性

本主題會帶領您完成建議的租用戶整個設定會影響您的 Office 365 環境的安全性設定。安全性需求可能需要更多或更少的安全性。使用這些建議為起點。
  
## <a name="check-office-365-secure-score"></a>檢查 Office 365 安全分數

Office 365 安全分數分析根據規則活動和安全性設定的 Office 365 組織的安全性和指派分數。先利用您目前的分數的附註。調整某些整個租用戶的設定會增加您分數。目標是未達到最大的分數，但感知來保護環境不造成負面影響的使用者產能的機會。請參閱[簡介 （英文） 的 Office 365 安全分數](office-365-secure-score.md)。
  
## <a name="tune-threat-management-policies-in-the-office-365-security-amp-compliance-center"></a>調整 Office 365 安全性威脅管理原則&amp;規範中心

Office 365 安全性&amp;規範中心包括保護您的環境的功能。它也包括報表和儀表板可用來監視及採取動作。某些區域隨附的預設原則設定。某些方面未加上預設原則或規則。請造訪威脅管理調整 threat management 設定更安全的環境下這些原則。 
  
|區域 * * *|包含預設原則 * * *|建議 * * *|
|:-----|:-----|:-----|
|**反網路釣魚** <br/> |是  <br/> | 如果您有自訂的網域，建立反網路釣魚原則來保護您最重要的使用者，例如 CEO、 電子郵件帳戶及保護您的網域。檢閱[設定反網路釣魚原則](set-up-anti-phishing-policies.md)並建立原則使用做為指南的範例："範例： 反網路釣魚保護使用者和網域的原則。"|
|**反惡意程式碼引擎** <br/> |是  <br/> | 編輯預設原則：  <br/> &ensp;&ensp;• 一般附件篩選類型 — 選取 [開啟]  <br/><br>  您也可以建立自訂惡意程式碼篩選原則與您組織中套用至指定的使用者、 群組或網域。  <br/> <br> 詳細資訊：  <br/> &ensp;&ensp;•[反惡意程式碼保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> &ensp;&ensp;•[設定反惡意程式碼原則](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**ATP 安全附件** <br/> |否  <br/> | 在 [主要] 頁面的安全附件保護檔案 SharePoint、 OneDrive 及 Microsoft 小組中的核取此方塊：  <br/>  &ensp;&ensp;SharePoint、 OneDrive 及 Microsoft 小組 ATP • 開啟  <br/> <br> 使用這些設定中新增新的安全附件原則：  <br/>  &ensp;&ensp;• [封鎖-封鎖目前和未來的電子郵件和附件的偵測到惡意程式碼 （選擇這個選項）  <br/>  &ensp;&ensp;• [啟用重新導向 — （核取此方塊並輸入電子郵件地址，例如管理或隔離區的帳戶）  <br/>  &ensp;&ensp;• [套用上述的選取範圍惡意程式碼掃描附件的逾時則會發生錯誤 （核取此方塊）  <br/>  &ensp;&ensp;• [套用至 — 收件者選取的網域是 （網域）  <br/>  <br>更多資訊：[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md) <br/> |
|**ATP 安全連結** <br/> |是  <br/> | 將此設定新增至整個組織的預設原則：  <br/> &ensp;&ensp;• [使用安全中的連結： Office 365 ProPlus、 iOS 適用於 Office 及 Android （選取這個選項）。  <br/> <br>建議的特定收件者原則：  <br/>  &ensp;&ensp;• Url 將會修正與使用者按下連結上時檢查已知惡意連結的清單 （選取這個選項）。  <br/>  &ensp;&ensp;• [使用安全附件要掃描的可下載內容 （核取此方塊）。  <br/>  &ensp;&ensp;• [套用至 — 收件者選取的網域是 （網域）。  <br/> <br> 更多資訊： [Office 365 ATP 安全的連結](atp-safe-links.md)。  <br/> |
|**反垃圾郵件 （郵件篩選）** <br/> |是  <br/> | 新留意：  <br/>  &ensp;&ensp;• 太多垃圾郵件 — 選擇的自訂設定及編輯預設垃圾郵件篩選器原則。  <br/>  &ensp;&ensp;• 詐騙智慧 — 檢閱所詐騙網域的寄件者。封鎖或允許這些寄件者。<br/>  <br>更多資訊： [Office 365 電子郵件反垃圾郵件保護](anti-spam-protection.md)。  <br/> |
|***電子郵件的驗證*** <br/> |是  <br/> |電子郵件驗證使用網域名稱系統 (DNS) 將可驗證資訊新增至相關的電子郵件寄件者的電子郵件訊息。Office 365 設定其預設網域 (onmicrosoft.com) 的電子郵件驗證但 Office 365 系統管理員也可以使用自訂網域的電子郵件的驗證。使用三種驗證方法：<br/> <br> &ensp;&ensp;• [寄件者原則架構 （或 SPF）。<br/>&ensp;&ensp;&ensp;&ensp;-進行安裝，請參閱[Set up SPF 避免詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 <br/> &ensp;&ensp;• DomainKeys 識別郵件 (DKIM)。 <br/> &ensp;&ensp;&ensp;&ensp;-請參閱[使用 DKIM 自訂網域在 Office 365 中的電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)。 <br>&ensp;&ensp;&ensp;&ensp;-您已設定 DKIM 後，會將它啟用安全性&amp;規範中心。<br/> &ensp;&ensp;• 網域式訊息驗證、 報告和符合性 (DMARC)。 </br> &ensp;&ensp;&ensp;&ensp;-針對 DMARC 的安裝程式[使用 DMARC 來驗證 Office 365 中的電子郵件](use-dmarc-to-validate-email.md)。<br/>  <br/>
|

> [!NOTE]
> 非標準部署的 SPF、 混合部署及疑難排解：[如何 Office 365 使用寄件者原則架構 (SPF) 若要防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-security-amp-compliance-center"></a>檢視儀表板和報表安全性&amp;規範中心

瀏覽這些報告及儀表板以深入了解您環境的狀況。這些報告中的資料會成為豐富為您的組織使用 Office 365 服務。現在請先熟悉您可以監視以及採取動作。如需詳細資訊，請參閱： [Reports in Office 365 安全性&amp;規範中心](reports-in-security-and-compliance.md)。
  
|儀表板 * * *|****Description****|
|:-----|:-----|
|威脅管理儀表板  <br/> |在威脅管理] 區段中的安全性&amp;規範中心，請使用此儀表板至已經已處理，請參閱威脅及方便使用的工具來保護報告上新威脅智慧有已完成的商務決策者適用您商務。  <br/> |
|威脅瀏覽器  <br/> |這也是在威脅管理] 區段中的安全性&amp;規範中心。如果您正在調查或針對您的 Office 365 租用戶可能遭受攻擊，可用於在 [檔案總管威脅分析威脅。威脅瀏覽器顯示您攻擊數量一段時間，並您可以分析的威脅系列、 攻擊者基礎結構及更多此資料。您也可以標示任何可疑的電子郵件的 [事件] 清單。  <br/> |
|報告 — 儀表板  <br/> |在 [報告] 區段中的安全性&amp;為您的 SharePoint Online 與 Exchange Online 組織的規範中心檢視稽核報告。您也可以存取 Azure Active Directory (AD) 使用者登入報告、 使用者活動報告，並 Azure AD 稽核記錄從 「 檢視報告 」 頁面。  <br/> |
   
![安全性&amp;規範中心儀表板](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>設定其他 Exchange Online 租用戶整體設定

安全性及保護 Exchange 系統管理中心中的控制項的許多也會包含安全性和規範中心 」。您不需要設定這些在這兩個位置。以下是一些其他建議的設定。 
  
|區域 * * *|包含預設原則 * * *|建議 * * *|
|:-----|:-----|:-----|
|**郵件流程**（傳輸規則）  <br/> |否  <br/> | 新增郵件流程規則可協助保護 ransomware。請參閱此部落格文章中的 「 如何使用 Exchange 傳輸規則來追蹤或封鎖的副檔名 ransomware 所使用的電子郵件":[如何處理 ransomware](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/)。<br><br/> 建立傳輸規則，以防止自動轉寄電子郵件至外部網域。如需詳細資訊，請參閱[減輕用戶端外部轉寄規則安全分數](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。<br/> <br>更多資訊： [Mail flow 規則 （傳輸規則） 在 [Exchange Online](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx) <br/> |
|**啟用摩登的驗證** <br/> |否  <br/> | Office 365 中的現代驗證是使用多重要素驗證 (MFA) 的必要條件。MFA 建議保護雲端資源，包括電子郵件的存取權。<br/>  <br>請參閱下列主題：  <br/> • [[啟用或停用現代驗證在 Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/> • [Skype 商務 online： 啟用經過驗證的租用戶](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/>  <br>預設會啟用經過驗證的 Office 2016 用戶端、 SharePoint Online 和 OneDrive for Business。  <br/>  <br>更多資訊：[使用 Office 365 現代 Office 用戶端驗證](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a) <br/> |
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>在 SharePoint 系統管理中心中設定全租用戶的共用原則

Microsoft 建議在增加的保護，開頭基準保護層級設定 SharePoint 小組網站。如需詳細資訊，請參閱[Secure SharePoint Online 網站及檔案](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)
  
SharePoint 小組網站層級的比較基準設定允許與外部使用者共用檔案使用匿名存取的連結。這個方法被建議電子郵件中傳送檔案。 
  
若要支援目標的比較基準保護，此處所建議來設定全租用戶的共用原則。共用設定個別的網站可以超過這個全租用戶的原則，但不是更寬鬆更嚴格。 
  
|區域 * * *|包含預設原則 * * *|建議 * * *|
|:-----|:-----|:-----|
|**共用**（SharePoint Online 和 OneDrive for Business）  <br/> |是  <br/> | 預設會啟用外部共用。建議使用下列設定：<br/>  • [允許驗證外部使用者共用及使用匿名存取連結 （預設值）。  <br/>  • [匿名存取連結在此幾天後到期。輸入一個數字，若有需要，例如 30 天。<br/>  • [預設的連結類型 — 選取 [內部] （僅限組織中的人員）。想要共用使用匿名連結的使用者必須在 [共用] 功能表中選擇此選項。<br/>  <br>更多資訊：[外部共用的概觀 （英文)](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85) <br/> |
   
SharePoint 系統管理中心和 OneDrive for Business admin center 包含相同的設定。在 [管理中心設定會套用至兩者。
  
## <a name="configure-settings-in-azure-active-directory"></a>在 Azure Active Directory 設定

請務必瀏覽這些 Azure Active Directory 完成整個租用戶的安裝程式更安全的環境中的兩個區域。
  
### <a name="configure-named-locations-under-conditional-access"></a>設定具名的位置 （在設定格式化的條件 access)

如果貴組織安全網路存取權的辦公室，將信任的 IP 位址範圍新增至 Azure Active Directory 做為具名的位置。此功能可協助減少報告誤判登入風險事件的數目。 
  
請參閱： [Azure Active Directory 中的具名位置](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>不支援經過驗證的封鎖應用程式

多重要素驗證需要支援經過驗證的應用程式。不支援經過驗證的應用程式無法使用設定格式化的條件存取規則封鎖。
  
安全的環境中，務必停用不支援經過驗證的應用程式的驗證。您可以這麼 Azure Active Directory 中具有即將推出的控制項。
  
同時，使用下列方法之一來完成的 SharePoint Online 和 OneDrive for Business:
  
- 使用 PowerShell，請參閱[封鎖，請勿使用經過驗證的相關應用程式](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)。
    
- 在 SharePoint 系統管理中心中設定此"裝置存取] 頁面上 —"控制從應用程式不使用經過驗證的存取 」。選擇 [封鎖]。 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>開始使用雲端應用程式安全性或 Office 365 雲端應用程式安全性

使用 Office 365 雲端應用程式安全性評估可疑活動上的提醒的風險，並自動採取動作。需要 Office 365 E5 計劃。
  
或者，使用 Microsoft 雲端應用程式安全性以取得更深入的可見度偶數之後授與存取、 全方位控制項及改善的保護所有的雲端應用程式，包括 Office 365。 
  
由於此解決方案建議 EMS E5 計劃，因此建議您開始使用雲端應用程式安全性讓您可以這與其他 saas 和應用程式環境中使用。開始使用預設原則和設定。
  
詳細資訊：
  
- [部署 Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Microsoft Cloud App Security 的詳細資訊](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Office 365 雲端 App 安全性概觀](office-365-cas-overview.md)
    
![Cloud App Security 儀表板](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>其他資源

這些文章和輔助線提供保護您的 Office 365 環境的其他規定資訊：
  
- [Microsoft 安全性指導政治活動、 非營利機構，以及其他靈活的組織](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)（您可以在任何環境中，特別是僅限雲端環境使用這些建議） 
    
- [建議使用安全性原則和設定身分識別和裝置](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations)（這些建議包含 AD FS 環境的說明） 
    

