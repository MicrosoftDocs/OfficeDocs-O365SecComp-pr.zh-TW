---
title: 保護內部部署信箱與 Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 即使您計劃主控部分或全部信箱內部，您仍然可以保護信箱與 Exchange Online Protection (EOP)。 若要設定連接器，您的帳戶必須是 Office 365 全域管理員或 Exchange 公司管理員 (組織管理角色群組)。 如需 Office 365 權限方式與 Exchange 權限相關資訊，請參閱在 21vianet 運作的 Office 365 中指派系統管理員角色。 如果您的 Exchange 信箱的所有內部部署，請遵循下列步驟來設定您的 EOP 服務。
ms.openlocfilehash: 20fa94a356823e624fcb42dc493d555cec3fe523
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156935"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>保護內部部署信箱與 Exchange Online Protection

> [!NOTE]
> 本文僅適用於由中國 21vianet 運作的 Office 365。 
  
即使您計劃主控部分或全部信箱內部，您仍然可以保護信箱與 Exchange Online Protection (EOP)。 若要設定連接器，您的帳戶必須是 Office 365 全域管理員或 Exchange 公司管理員 (組織管理角色群組)。 如需 Office 365 權限方式與 Exchange 權限相關資訊，請參閱[在 21vianet 運作的 Office 365 中指派系統管理員角色](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)。 如果您的 Exchange 信箱的所有內部部署，請遵循下列步驟來設定您的 EOP 服務。 
  
## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步驟 1： 使用 Microsoft 365 系統管理中心新增及確認您的網域

1. 在 Microsoft 365 系統管理中心中，瀏覽至安裝程式將您的網域新增至服務。
    
2.  遵循適用的 DNS 記錄新增至您的 DNS 主機服務提供者，以便驗證網域擁有權入口網站中的步驟。 
    
> [!TIP]
> [新增您的網域與使用者由 21Vianet 運作的 Office 365](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)和[Office 365 管理您的 DNS 記錄時建立 DNS 記錄](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)，是有用的資源來參照當您新增網域至此服務並設定 DNS。 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>步驟 2： 新增收件者和設定網域類型

在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](https://go.microsoft.com/fwlink/?LinkId=506782)＞。另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。如需 DBEB 的相關資訊，請參閱[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步驟 3：使用 EAC 來設定郵件流程

在 Exchange 系統管理中心 (EAC) 中建立連接器，以啟用 EOP 與您內部部署郵件伺服器之間的郵件流程。 如需詳細指示，請參閱 <<c0>建立所需的連接器，以設定基本的電子郵件流過 EOP。
  
 如何才能了解此工作是否正常運作？ 
  
 使用 Remote Connectivity Analyzer 執行用來檢查服務與您環境間之郵件流程的測試。 如需詳細資訊，請參閱 「 使用 Remote Connectivity Analyzer 來測試電子郵件傳遞 」 一節中[的測試郵件流程與 Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步驟 4：允許輸入連接埠 25 SMTP 存取

設定連接器之後，請等待 72 小時以允許傳播 DNS 記錄更新。 接著，限制在您的防火牆或郵件伺服器，以只接受來自 EOP 資料中心，特別是來自列在[Url 和 IP 位址範圍的由 21Vianet 運作的 Office 365](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)IP 位址的輸入連接埠 25 SMTP 流量。 這會限制您可接收的輸入郵件範圍，以保護內部部署環境的安全。 此外，若您在郵件伺服器上進行設定，以控制允許連線執行郵件轉送的 IP 位址，請一併更新這些設定。
  
> [!TIP]
> 將 SMTP 伺服器的連線時間設定設為超過 60 秒。此設定適用於大部分情況，例如在傳送具有大型附件的郵件時可稍許延遲。 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步驟 5：使用命令介面確定垃圾郵件路由傳送至每個使用者的垃圾電子郵件資料夾

為了確保垃圾電子郵件正確地路由傳送至每個使用者的 [垃圾郵件] 資料夾，您必須執行幾個設定步驟。 [確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](https://go.microsoft.com/fwlink/?LinkId=506804)中提供步驟。 如果不要將郵件移至每個使用者的 [垃圾郵件] 資料夾，您可以在 Exchange 系統管理中心編輯內容篩選原則，以選擇其他動作。 如需詳細資訊，請參閱＜[Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805)＞。 
  
## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步驟 6： 使用 Microsoft 365 系統管理中心將您的 MX 記錄指向 EOP

遵循 Office 365 網域組態步驟來更新網域的 MX 記錄，讓您的輸入電子郵件流過 EOP。 如需詳細資訊，您可以再次參照[建立 Office 365 管理您的 DNS 記錄時的 DNS 記錄](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)。
  
如何才能了解此工作是否正常運作？
  
 使用 Remote Connectivity Analyzer 執行用來驗證您 MX 記錄的測試。 如需詳細資訊，請參閱 「 使用 Remote Connectivity Analyzer 來測試 MX 記錄和輸出連接器 」 一節中[測試 Remote Connectivity Analyzer 中的郵件流程](https://go.microsoft.com/fwlink/?LinkId=506784)。 
  
到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：
  
- 在 Remote Connectivity Analyzer 中，按一下 **[Office 365]** 索引標籤，然後執行位於 **[網際網路電子郵件測試]** 底下的 **[輸入 SMTP 電子郵件]** 測試。
    
- 從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。
    
- 如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>較不普遍： 信箱內部部署與雲端混合式安裝程式

如果您有 Exchange 信箱的內部部署與一或多個信箱在雲端中 Exchange Online 中，您必須在*混合式*設定。 在混合式安裝程式功能，例如空閒/忙碌行事曆共用和郵件路由可以搭配使用，在您內部部署和雲端環境。 當您轉換至 Exchange Online 信箱時，您可能必須在混合式設定就地。 不同 EOP 獨立保護設定混合式環境。 
  
您可能會選擇若要利用雲端式電子郵件的員工大部分的混合式案例。 您可以這麼做時也主控有些信箱在內部;例如，針對您的法務部門。 
  
在混合式設定可能會很複雜，但它有許多優點。 若要深入了解設定與 Exchange 混合式案例，請參閱[設定 Exchange 混合式部署功能，使用由 21Vianet 運作的 Office 365](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)。
  

