---
title: Office 365 郵件加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 對於 Office 365 中新郵件保護功能的運作方式有疑問嗎？ 請在此處查看答案。
ms.openlocfilehash: 1625ecd3f2c7991e2726539bcfa0c772d1ffea59
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222257"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 郵件加密常見問題集

對於 Office 365 中新郵件保護功能的運作方式有疑問嗎？ 請在此處查看答案。 此外, 請參閱[Azure 資訊保護中資料](https://docs.microsoft.com/information-protection/get-started/faqs-rms)保護的常見問題, 以取得 Azure 資訊保護中有關資料保護服務 (Azure 版權管理) 問題的答案。

||
|:-----|
|本文是更多有關 Office 365 郵件加密的文章系列的一部分。 本文適用于系統管理員和 ITPros。 如果您只是尋找傳送或接收加密郵件的相關資訊, 請參閱[Office 365 訊息加密 (OME)](ome.md)中的文章清單, 並找出最符合您需求的文章。 |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>何謂 Office 365 郵件加密 (OME)？

OME 合併電子郵件加密和版權管理功能。 Rights management 功能是由 Azure 資訊保護供電的。
  
## <a name="who-can-use-ome"></a>誰可以使用 OME？

在下列情況下, 您可以使用 OME 的新功能:
  
- 如果您從未在 Office 365 中設定 Exchange Online 的 OME 或 IRM。

- 如果您已設定 OME 和 IRM, 您可以使用下列步驟, 如果您使用的是 azure 資訊保護的 Azure 版權管理服務。

- 如果您使用的是 Active Directory Rights Management service (AD RMS) 的 Exchange Online, 您就無法立即啟用這些新功能。 相反地, 您必須先將[AD RMS 遷移至 Azure 資訊保護](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。 當您完成遷移時, 您可以成功地設定 OME。

    如果您選擇繼續將內部部署 AD RMS 與 Exchange Online 搭配使用, 而不是遷移至 Azure 資訊保護, 您將無法使用這些新功能。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>我需要使用新 OME 功能的訂閱為何？

若要使用新的 OME 功能, 您需要下列其中一個計畫:
  
- Office 365 郵件加密是作為 Office 365 企業版 E3 和 E5、Microsoft Enterprise E3 和 E5、Microsoft 365 商務版、Office 365 A1、A3 和 A5, 以及 Office 365 政府版 G3 和 G5 的一部分提供。 客戶不需要額外的授權, 即可接收 Azure 資訊保護所支援的新保護功能。

- 您也可以將 Azure 資訊保護方案1新增至下列計畫, 以接收新的 Office 365 郵件加密功能: Exchange Online Plan 1、Exchange Online Plan 2、Office 365 F1、Office 365 商務基本版、Office 365 商務特優或Office 365 企業版 E1。

- Office 365 郵件加密的每個使用者都必須經過授權, 才能享受該功能。

- 如需完整清單, 請參閱 Office 365 郵件加密的[Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>我可以使用 Exchange Online, 搭配在 Azure 資訊保護中攜帶您自己的金鑰 (BYOK) 嗎？

是的！ Microsoft 建議您先完成設定 BYOK 的步驟, 再設定 OME。
  
如需 BYOK 的詳細資訊, 請參閱[規劃及執行您的 Azure 資訊保護租使用者金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>使用 Azure 資訊保護進行 OME 和 BYOK 變更 Microsoft 對協力廠商資料要求的方法, 例如 subpoenas？

否。 OME 以及提供和控制您自己的加密金鑰 (稱為 BYOK) 的選項, 來自 Azure 資訊保護, 而不是設計用來回應執法機關 subpoenas。 OME (含 BYOK for Azure 資訊保護) 是專為符合規範的客戶而設計。 Microsoft 對客戶資料所進行的協力廠商要求非常嚴重。 做為雲端服務提供者, 我們永遠提倡使用客戶資料的隱私權。 在這種情況下, 我們會收到傳票, 我們總是嘗試將協力廠商重新導向給客戶以取得資訊。 (請閱讀 Brad Smith 的博客:[防止政府窺探的客戶資料](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我們會定期發佈所收到之要求的詳細資訊。 如需協力廠商資料要求的詳細資訊, 請參閱[回應政府和法律強制要求, 以](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)在 Microsoft 信任中心存取客戶資料。 此外, 請參閱[線上服務條款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中的「客戶資料洩漏」。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>這項功能與舊版 Office 365 郵件加密 (OME) 和資訊版權管理 (IRM) 功能有何關係？

Office 365 郵件加密的新功能是現有 IRM 和舊版 OME 解決方案的演變。 下表提供更多詳細資料。
  
**舊版 OME、IRM 及新的 OME 功能的比較**

|**功能**|**舊版本的 OME**|**IRM**|**新的 OME 功能**|
|:-----|:-----|:-----|:-----|
|**傳送加密的電子郵件**|只能透過 Exchange 郵件流程規則|使用者從 Outlook 針對電腦、Mac 版 Outlook 或 Outlook 網頁版啟動;或透過 Exchange 郵件流程規則|使用者從 Outlook 針對電腦、Mac 版 Outlook 或 Outlook 網頁版啟動;或透過郵件流程規則|
|**版權管理**|-|[不要轉寄] 選項和自訂範本|[不要轉寄] 選項、[僅加密] 選項、[預設] 和 [自訂範本]|
|**支援的收件者類型**|僅限外部收件者|僅限內部收件者|內部和外部收件者|
|**收件者的經驗**|外部收件者在瀏覽器或下載的行動裝置應用程式中收到他們下載和開啟的 HTML 郵件。|內部收件者只會在 Outlook 中收到加密的電子郵件、Outlook for Mac, 以及網頁上的 Outlook。|內部和外部收件者會在 Outlook 中收到電子郵件、outlook for Mac、outlook for Android、outlook for Android、outlook for iOS, 或透過 web 入口網站, 不論他們是否在相同的 Office 365 組織或任何 Office 365 中公司. OME 入口網站不需要個別下載。|
|**攜帶您自己的主要支援**|無|無| BYOK 支援|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何為組織啟用新的 OME 功能？

請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>舊版本的 OME 是否已被取代？

您仍然可以使用舊版的 OME, 這次將不會被取代。 不過, 我們強烈建議組織使用新的和改進的 OME 解決方案。 尚未部署 OME 的客戶無法設定舊版本 OME 的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>我的組織使用 Active Directory Rights Management, 我可以使用此功能嗎？

否。 如果您使用的是 Active Directory Rights Management service (AD RMS) 的 Exchange Online, 您就無法立即啟用這些新功能。 相反地, 您必須先將[AD RMS 遷移至 Azure 資訊保護](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的組織有 Exchange 混合式部署。 我可以使用這項功能嗎？

內部部署使用者可以使用 Exchange Online 郵件流程規則傳送加密的郵件。 若要這麼做, 您必須透過 Exchange Online 路由傳送電子郵件。 如需詳細資訊, 請參閱[第2部分: 將郵件設定為從您的電子郵件伺服器流向 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>我需要使用什麼電子郵件客戶程式, 才能建立 OME 加密的郵件？ 哪些應用程式支援傳送受保護的郵件？

您可以從 Outlook 2016, 以及 Outlook 2013 for PC 和 Mac, 以及從網路上的 outlook 來建立受保護的郵件。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>支援哪些電子郵件客戶程式以讀取和回復受保護的電子郵件？

如果您是 Office 365 使用者, 您可以從 Outlook 的電腦和 Mac (2013 和 2016)、Outlook 網頁版, 以及 Outlook mobile (Android 和 iOS) 讀取和回應。 您也可以使用 iOS 原生郵件用戶端 (如果您的組織允許的話)。 如果您是非 Office 365 使用者, 您可以透過網頁瀏覽器讀取和回復網頁上的加密郵件。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>受保護的電子郵件中的附件支援哪些檔案類型？ 附件是否繼承與受保護的電子郵件相關的保護原則？

您可以將任何檔案類型附加至受保護的郵件, 但只會在[此處](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)提及的檔案格式套用保護原則。 
  
如果支援某種檔案格式 (例如 Word、Excel 或 PowerPoint 檔案), 即使收件者已下載附件, 也會永遠保護該檔案。 例如, 如果附件受到 [不轉寄] 的保護, 且原始收件者下載並轉寄附件至新的收件者, 則新的收件者將無法開啟受保護的檔案。
  
## <a name="are-pdf-file-attachments-supported"></a>是否支援 PDF 檔案附件？

如果您將 PDF 檔案附加到受保護的郵件, 郵件本身就會受到保護, 但收件者收到後, 將不會對 PDF 檔案套用額外的保護。 這表示收件者可以儲存為、轉寄、複製和列印 PDF 檔案。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>是否支援商務用 OneDrive 附件？

Not yet. 商務用 OneDrive 附件不受支援, 使用者無法加密包含雲端商務用 OneDrive 附件的郵件。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>是否可以透過設定原則來自動加密郵件？

是。 使用 Exchange Online 中的郵件流程規則, 根據特定條件自動加密郵件。 例如, 您可以建立以收件者識別碼、收件者網域或郵件內文或主旨內容為基礎的原則。 請參閱[定義郵件流程規則以加密 Office 365 中的電子郵件。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>是否可以透過安全性&amp;合規性中心來設定資料遺失防護 (DLP) 中的原則, 自動加密郵件？

是的！ 您可以在 Exchange Online 中設定郵件流程規則, 或在安全性&amp;與規範中心使用 DLP。
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>我可以開啟傳送至共用信箱的加密郵件嗎？

共用信箱不支援目前加密的郵件。

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>我可以使用公司的品牌來自訂加密的郵件嗎？

是的！ 如需自訂電子郵件和 OME 入口網站的詳細資訊, 請參閱將貴組織的品牌新增至加密的郵件。 請參閱[將貴組織的品牌新增至加密的郵件。](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>是否有任何報告功能或加密電子郵件的深入資訊？

在安全性與合規性中心有一個加密報告。 請參閱[在安全性 & 規範中心中查看電子郵件安全性報告。](view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>我可以使用郵件加密與相容性功能 (例如 eDiscovery) 嗎？

是。 所有加密的電子郵件都可透過 Office 365 符合性功能來探索。
