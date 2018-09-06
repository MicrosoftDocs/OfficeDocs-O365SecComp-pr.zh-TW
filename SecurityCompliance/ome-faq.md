---
title: Office 365 郵件加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 已在 Office 365 中的新郵件保護功能的運作方式的相關問題嗎？檢查的答案。
ms.openlocfilehash: 8fc3fa2378dfc8dba6ed17c042269f726235bc58
ms.sourcegitcommit: a8884b9675559018e1fddec1c0cc2de0bc3bdde5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839953"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 郵件加密常見問題集

已在 Office 365 中的新郵件保護功能的運作方式的相關問題嗎？檢查的答案。此外，仔細[常見問題集關於 Azure 資訊保護中的資料保護](https://docs.microsoft.com/information-protection/get-started/faqs-rms)的資料保護服務、 Azure 版權管理] 的相關問題的答案在 Azure 資訊保護。 
  
## <a name="what-is-office-365-message-encryption-ome"></a>什麼是 Office 365 郵件加密 (OME)？

OME 合併電子郵件加密和權限管理功能。版權管理功能是由 Azure 資訊保護提供。
  
## <a name="who-can-use-ome"></a>誰可以使用 OME？

您可以在下列情況下使用 OME 的新功能：
  
- 如果您有永不 set up OME 或 IRM for Office 365 中的 Exchange Online。
    
- 如果您已設定好 OME 和 IRM，您可以使用下列步驟，如果您使用 Azure 資訊保護 Azure 版權管理服務。
    
- 如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS)，就無法立即啟用這些新功能。而您需要[移轉至 Azure 資訊保護 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)第一次。當您已經完成移轉時，您可以成功設定 OME。 
    
    如果您選擇繼續使用內部部署 AD RMS 與 Exchange Online 而不是移轉至 Azure 資訊保護，您將無法使用這些新功能。
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>我需要何種訂閱使用新的 OME 功能？

若要使用的新 OME 功能，您需要下列計劃其中一項：
  
- Office 365 郵件加密被提供 Office 365 E3 和 E5、 Microsoft E3 和 E5、 Office 365 A1、 A3 和 A5、 與 Office 365 G3 及 G5 的一部分。客戶不需要以接收新的保護功能由 Azure 資訊保護提供額外的授權。 
    
- 您也可以新增 Azure 資訊保護計劃 1 的下列計劃以接收新的 Office 365 郵件加密功能： Exchange Online 計劃 1、 Exchange Online 計劃 2、 Office 365 F1、 Office 365 商務 Essentials、 Office 365 企業進階版或Office 365 企業版 E1。
    
- 從 Office 365 郵件加密而且可以享有每位使用者必須被授權功能所涵蓋。
    
- 完整清單請參閱[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)Office 365 郵件加密。 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>我可以使用 Exchange Online 與整合 Azure 資訊保護您自己的金鑰 (BYOK) 吗？

是 ！Microsoft 建議您完成之前設定 OME BYOK 設定步驟。
  
如需 BYOK 的詳細資訊，請參閱[規劃及實作您 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>不要 OME 和 Azure 資訊保護 BYOK 變更 Microsoft 的方法如 subpoenas 協力廠商資料要求吗？

[否]。OME 和選項提供並控制您自己的加密金鑰，從 Azure 資訊保護呼叫 BYOK，不是以回應 law 強制執行 subpoenas 而設計。OME，與 BYOK Azure 資訊保護，旨在規範為主的客戶。Microsoft 非常嚴重採用客戶資料的第三方的要求。做為雲端服務提供者，我們一律主張的客戶資料的隱私。我們要取得傳票、 可行我們永遠嘗試將第三方重新導向至客戶資訊。(請參閱此 Smith 的部落格： [＜ Protecting 政府側錄的客戶資料](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我們會定期發行我們會收到的要求的詳細的資訊。如需有關協力廠商資料要求，請參閱 Microsoft 信任中心上的[政府及存取客戶資料 law 強制執行要求的回應](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)。請參閱 「 洩漏的客戶資料 」 在[線上服務合約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>這項功能如何與舊版的 Office 365 郵件加密 (OME) 」 和 「 資訊版權管理 (IRM) 功能？

Office 365 郵件加密的新功能的現有 IRM 和舊版 OME 解決方案的發展。下表提供更多詳細資料。
  
**舊版 OME、 IRM、 與 OME 的新功能的比較**

|**功能**|**舊版的 OME**|**IRM**|**OME 的新功能**|
|:-----|:-----|:-----|:-----|
|**傳送加密的電子郵件**|只能透過 Exchange 郵件流程規則|從 Outlook PC、 Outlook for Mac，或 Outlook web; 上的起始的使用者或透過 Exchange 郵件流程規則|從 Outlook PC、 Outlook for Mac，或 Outlook web; 上的起始的使用者或透過郵件流程規則|
|**版權管理**|-|不要轉寄選項和自訂範本|不要轉寄] 選項、 僅加密的選項、 預設和自訂範本|
|**支援的收件者類型**|僅外部收件者|僅限內部收件者|內部和外部收件者|
|**收件者經驗**|外部收件者接收到的 HTML 郵件他們下載和瀏覽器中開啟或下載行動裝置應用程式。|內部收件者只在收到的 PC Outlook、 Outlook for Mac 及 web 上的 Outlook 中加密的電子郵件。|內部和外部收件者電子郵件中接收的 PC Outlook、 Outlook for Mac、 網路上的 Outlook、 Outlook for android （英文)、 和 Outlook iOS，或透過入口網站，不論都在相同的 Office 365 組織或任何 Office 365組織。OME 入口網站需要沒有個別下載。|
|**將您自己的金鑰支援**|無|無| BYOK 支援|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何在 「 我的組織啟用新 OME 功能？

請參閱 ＜ [Set up Office 365 郵件加密的新功能](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>將會過時 OME 的舊版本吗？

您仍然可以使用舊版 OME，它不會在此階段過時。不過，我們強烈鼓勵使用新增及改良的 OME 解決方案的組織。您尚未部署 OME 的客戶無法設定 OME 的前一版的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>「 我的組織使用 Active Directory Rights Management，可以使用這項功能嗎？

[否]。如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS)，就無法立即啟用這些新功能。而您需要[移轉至 Azure 資訊保護 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)第一次。 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的組織具有 Exchange 混合部署。可以使用這項功能吗？

內部使用者可以傳送加密的郵件使用 Exchange Online 郵件流程規則。為達成此目的，您需要透過 Exchange Online 電子郵件路由。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>我需要哪些電子郵件用戶端使用，以建立 OME 加密的郵件？支援哪些應用程式傳送受保護的郵件？

您可以在從 Outlook 2016 和 Outlook 2013 的 PC 或 Mac，然後從 Outlook web 上建立受保護的郵件。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>讀取和對受保護的電子郵件回覆支援何種電子郵件用戶端？

您可以閱讀和回應從 Outlook PC 和 Mac （2013年和 2016年）、 在 web 上的 Outlook 和 Outlook 行動裝置 （Android 和 iOS） 如果您是 Office 365 使用者。您也可以使用 iOS 原生的郵件用戶端如果貴組織可讓它。如果您是非 Office 365 使用者，您可以閱讀和回覆加密郵件在 web 上透過網頁瀏覽器中。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>做為受保護的電子郵件中的附件支援何種檔案類型？不要附件繼承受保護的電子郵件相關聯的保護原則吗？

不過，保護原則會套用只在檔案格式提及之[以下](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)可以受保護的郵件，附加任何檔案類型。 
  
如果支援的檔案格式，例如 Word、 Excel、 或 PowerPoint 檔案檔案會永遠受到保護，即使收件者已下載附件。例如如果附件受到保護的 [不要轉寄、 和原始收件者下載並將新的收件者的附件轉寄、 新的收件者將無法開啟受保護的檔案。
  
## <a name="are-pdf-file-attachments-supported"></a>所支援的 PDF 檔案附件

如果您以受保護的郵件附加的 PDF 檔案本身的郵件將會受到保護，但沒有其他保護會套用至 PDF 檔案後收件者已收到它。這表示的收件者可以另存新檔、 轉接、 複製及列印的 PDF 檔案。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>支援的商務附件是否 OneDrive 吗？

尚未。OneDrive for Business 附件不受支援與使用者無法加密雲端 OneDrive for Business 附件的郵件。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>可以藉由設定原則會自動加密郵件吗？

[是]。郵件流程規則在 Exchange Online 使用自動加密根據特定條件的郵件。例如，您可以建立原則為基礎的收件者的識別碼，收件者的網域，或在本文或主旨郵件的內容。請參閱[定義加密 Office 365 中的電子郵件的郵件流程規則。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>可以使用自動加密郵件所設定的原則中的資料遺失防護 (DLP) 透過安全性&amp;規範中心吗？

目前您可以僅設定郵件流程規則在 Exchange Online。透過安全性 DLP 目前不支援加密&amp;規範中心。
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>可自訂加密的郵件具有我的公司品牌吗？

是 ！如需自訂電子郵件及 OME 入口網站，請參閱 ＜ 將您的組織的商標新增至加密的郵件。請參閱[將您的組織的商標新增至加密的郵件。](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>是否有任何報表功能或前瞻加密的電子郵件吗？

不在此時間但即將推出。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>可以使用郵件加密與符合性功能，例如 eDiscovery 吗？

[是]。所有加密的電子郵件訊息是由 Office 365 的符合性功能可供搜尋。
  

