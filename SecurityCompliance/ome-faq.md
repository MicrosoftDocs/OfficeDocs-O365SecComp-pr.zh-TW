---
title: Office 365 郵件加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 有關於 Office 365 中新的郵件保護功能的運作方式的問題嗎？ 檢查的答案。
ms.openlocfilehash: 2c140ef476b5fe19ef3655b062a3f197d36222e7
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936783"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 郵件加密常見問題集

有關於 Office 365 中新的郵件保護功能的運作方式的問題嗎？ 檢查的答案。 此外，看看[常見問題集有關 Azure 資訊保護中的資料保護](https://docs.microsoft.com/information-protection/get-started/faqs-rms)資料保護服務、 Azure Rights Management 的相關問題的答案的 Azure 資訊保護。

||
|:-----|
|本文屬於較大的一連串的 Office 365 郵件加密的相關文章。 本文適用於系統管理員和 ITPros。 如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。 |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>什麼是 Office 365 郵件加密 (OME)？

OME 合併的電子郵件加密和權限管理功能。 版權管理功能是由 Azure 資訊保護提供。
  
## <a name="who-can-use-ome"></a>誰可以使用 OME？

您可以在下列情況下，使用 OME 的新功能：
  
- 如果您有永遠不會設定 OME 或 IRM for Office 365 中的 Exchange Online。
    
- 如果您已設定好 OME 和 IRM，您可以使用下列步驟，如果您使用 Azure 資訊保護 Azure 版權管理服務。
    
- 如果您使用 Exchange Online 與 Active Directory Rights Management 服務 (AD RMS)，則無法立即啟用這些新功能。 相反地，您需要[移轉至 Azure 資訊保護的 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)第一次。 完成移轉之後，您可以成功設定 OME。 
    
    如果您選擇繼續使用內部部署 AD RMS 搭配 Exchange Online 而不是移轉至 Azure 資訊保護，您將無法使用這些新功能。
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>若要使用全新的 OME 功能是否需要何種訂閱？

若要使用全新的 OME 功能，您需要下列其中一個下列方案：
  
- Office 365 郵件加密被提供 Office 365 企業版 E3 和 E5，Microsoft 企業版 E3 和 E5、 Microsoft 365 商務版、 Office 365 A1、 A3 和 A5，和 Office 365 政府版 G3 和 G5 的一部分。 客戶不需要額外的授權，以接收由 Azure 資訊保護提供的新保護功能。 
    
- 您也可以新增 Azure 資訊保護方案 1 於下列計劃以接收新的 Office 365 郵件加密功能： Exchange Online Plan 1 Exchange Online Plan 2、 Office 365 F1、 Office 365 商務基本版、 Office 365 商務進階版，或Office 365 企業版 E1。
    
- 從 Office 365 郵件加密優點每位使用者需要功能線所涵蓋的授權。
    
- 完整清單請參閱[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)Office 365 郵件加密。 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>我是否可以使用 Exchange Online 與攜帶您自己的金鑰 (BYOK) 在 [Azure 資訊保護？

Yes ！ Microsoft 建議您完成設定 BYOK，才能設定 OME 的步驟。
  
如需 BYOK 的詳細資訊，請參閱[規劃及實作您的 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>不要 OME 並使用 Azure 資訊保護 BYOK 變更 Microsoft 方法協力廠商資料要求，例如 subpoenas 嗎？

否。 OME 與] 選項，以提供並控制您自己的加密金鑰，從 Azure 資訊保護呼叫 BYOK，已並非特別設計用來回應法律強制執行 subpoenas。 OME，與 Azure 資訊保護，BYOK 專為符合性為主的客戶。 Microsoft 會非常重視採用客戶資料的第三方的要求。 為雲端服務提供者，我們一直主張針對客戶資料的隱私權。 事件中我們取得傳票，我們一直嘗試將協力廠商重新導向至客戶取得的資訊。 (請參閱將 Smith 部落格: [ Protecting 客戶資料從政府側錄](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我們會定期發佈我們收到的要求的詳細的資訊。 如需更多關於協力廠商資料要求的詳細資訊，請參閱 Microsoft 信任中心的[政府，以及存取客戶資料 law 強制執行要求的回應](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)。 此外，請參閱 「 外洩的客戶資料 」 的[線上服務條款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>這項功能如何與舊版的 Office 365 郵件加密 (OME) 」 和 「 資訊版權管理 (IRM) 功能？

Office 365 郵件加密的新功能是舊版 OME 解決方案與現有的 IRM 演變。 下表提供更多詳細資料。
  
**舊版 OME、 IRM、 與全新的 OME 功能的比較**

|**功能**|**舊版的 OME**|**IRM**|**全新的 OME 功能**|
|:-----|:-----|:-----|:-----|
|**傳送加密的電子郵件**|只能透過 Exchange 郵件流程規則|從 Outlook 中的 PC、 Mac 版 Outlook 或 Outlook 網頁; 起始的使用者或透過 Exchange 郵件流程規則|從 Outlook 中的 PC、 Mac 版 Outlook 或 Outlook 網頁; 起始的使用者或透過郵件流程規則|
|**版權管理**|-|不要轉寄] 選項，自訂範本|不要轉寄] 選項、 僅加密選項、 預設及自訂範本|
|**支援的收件者類型**|僅外部收件者|僅限內部收件者|內部和外部收件者|
|**收件者的經驗**|外部收件者接收到 HTML 郵件他們下載和瀏覽器中開啟或下載行動應用程式。|內部收件者只會收到電腦版 Outlook、 Outlook for Mac 和 outlook 網頁版中的加密的電子郵件。|內部和外部收件者電子郵件中接收電腦版 Outlook、 Mac 版 Outlook、 outlook 網頁版、 Android 版 Outlook 和 Outlook for iOS、 或透過入口網站，不論是否都在相同的 Office 365 組織中或任何 Office 365組織。 OME 入口網站需要沒有個別下載。|
|**攜帶您自己的金鑰支援**|無|無| BYOK 支援|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何在我的組織啟用全新的 OME 功能？

請參閱 <<c0>設定新的 Office 365 郵件加密功能。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>將會取代舊版 OME 嗎？

您仍然可以使用 OME 的前一個版本，它不會取代這一次。 不過，我們強烈鼓勵組織使用的新增和改善 OME 解決方案。 不已部署 OME 的客戶無法設定舊版的 OME 的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>我的組織使用 Active Directory Rights Management，我可以使用這項功能嗎？

否。 如果您使用 Exchange Online 與 Active Directory Rights Management 服務 (AD RMS)，則無法立即啟用這些新功能。 相反地，您需要[移轉至 Azure 資訊保護的 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)第一次。 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的組織具有 Exchange 混合式部署。 可以使用這項功能嗎？

內部部署使用者可以傳送加密的郵件使用 Exchange Online 的郵件流程規則。 若要這麼做，您必須透過 Exchange Online 路由電子郵件。 如需詳細資訊，請參閱[第 2 部分： 將郵件設定為從您的電子郵件伺服器流向 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>若要使用，以便建立 OME 加密的郵件是否需要何種電子郵件用戶端？ 支援哪些應用程式傳送受保護的訊息嗎？

從 Outlook 2016、 和 PC 和 Mac 的 Outlook 2013 和 outlook 網頁版，您可以建立受保護的郵件。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>查看電子郵件用戶端支援閱讀和回覆受保護的電子郵件？

您可以讀取和回應從 Outlook PC 和 Mac （2013年和 2016年）、 在網頁型 Outlook 和 Outlook 行動裝置 （Android 和 iOS），如果您是 Office 365 使用者。 如果貴組織可讓它，您也可以使用 iOS 的原生的郵件用戶端。 如果您是在非 Office 365 使用者，您可以閱讀和回覆加密的郵件，在 web 上透過網頁瀏覽器。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>以受保護的電子郵件的附件所支援檔案類型？ 附件繼承受保護的電子郵件相關聯的保護原則嗎？

不過，保護原則只套用至檔案格式所述在[這裡](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)，您可以以受保護的郵件，附加任何檔案類型。 
  
如果支援的檔案格式，例如 Word、 Excel 或 PowerPoint 檔案，檔案會一律受到保護，即使收件者已下載附件。 例如，如果附件受保護的 [不要轉寄，且原始的收件者下載，並轉寄給新的收件者的附件，新的收件者將無法開啟受保護的檔案。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF 檔案附件支援？

如果您將 PDF 檔案附加到受保護的郵件時，在郵件本身會受到保護，但沒有額外的保護會套用至 PDF 檔案之後收件者已收到它。 這表示收件者可以另存新檔、 轉寄、 複製及列印的 PDF 檔案。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>支援的商務附件是 OneDrive？

Not yet. OneDrive 商務的附件不受支援，使用者無法加密包含雲端 OneDrive for Business 附件的郵件。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>可以藉由設定原則會自動加密郵件？

可以。 使用郵件流程規則 Exchange Online 中自動加密根據特定條件的郵件。 例如，您可以建立原則，根據收件者識別碼，收件者的網域，或內文或主旨郵件的內容。 請參閱[定義郵件流規則以加密 Office 365 中的電子郵件。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>可以我會自動加密郵件所設定的原則中的資料外洩防護 (DLP) 透過安全性&amp;合規性中心？

Yes ！ 您可以設定郵件流程規則在 Exchange Online 或安全性使用 DLP&amp;合規性中心。
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>可開啟加密的郵件傳送至共用信箱？

共用信箱不支援目前加密的郵件。

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>可以與我公司商標自訂加密的郵件嗎？

Yes ！ 如需自訂電子郵件訊息和 OME 入口網站，請參閱 < 將貴組織的商標新增至您的加密郵件。 請參閱[將貴組織的商標新增至您的加密郵件。](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>是否有任何報表功能或加密的電子郵件的深入資訊？

不是在這段時間，但即將推出。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>可以使用郵件加密與符合性功能，例如 eDiscovery？

可以。 所有加密的電子郵件是由 Office 365 合規性功能，可供搜尋。
  

