---
title: 設定 EOP 服務
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 本主題說明如何設定 Microsoft Exchange Online Protection (EOP)。如果您從 Office 365 網域精靈進入這裡，而您不希望使用 Exchange Online Protection 的話，請回到 Office 365 網域精靈。如果您正在尋找如何設定連接器的詳細資訊，請參閱Configure mail flow using connectors in Office 365。
ms.openlocfilehash: f1c65164adcaa17c58ae9c4b4b957c477b9e02f3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027110"
---
# <a name="set-up-your-eop-service"></a>設定 EOP 服務

本主題說明如何設定 Microsoft Exchange Online Protection (EOP)。如果您從 Office 365 網域精靈進入這裡，而您不希望使用 Exchange Online Protection 的話，請回到 Office 365 網域精靈。如果您正在尋找如何設定連接器的詳細資訊，請參閱[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)。
  
> [!NOTE]
> 本主題假設您擁有內部部署信箱，且您想要使用 EOP 來保護這些信箱 (稱為獨立案例)。如果您想要使用 Exchange Online 在雲端中裝載所有的信箱，並不需要完成本主題中所有的步驟。請移至 [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) 來註冊及購買雲端信箱。如果您想要將一部分信箱裝載在內部部署、一部分信箱裝載在雲端中，這稱為 混合案例。這需要更進階的郵件流程設定。[Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)會說明混合郵件流程，並提供一些說明相關設定方式的連結。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 完成此工作的預估時間：1 小時
    
- 若要設定連接器，您的帳戶必須是 Office 365 全域管理員或 Exchange 公司管理員 (組織管理角色群組)。如需 Office 365 權限與 Exchange 權限之關係的相關資訊，請參閱 [Office 365 中的權限](https://go.microsoft.com/fwlink/p/?LinkID=335814)。
    
- 如果您尚未註冊 EOP，請造訪 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660)，並選擇購買或試用服務。 
    
- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 **Keyboard shortcuts in Exchange 2013**。
    
> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="how-do-you-do-this"></a>該怎麼做？

### <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>步驟 1：使用 Office 365 系統管理中心 新增及確認您的網域

1. 在 Office 365 系統管理中心中，瀏覽至您的網域新增至服務的**安裝程式**。 
    
    不確定要前往何處尋找 Office 365 系統管理中心？請參閱[關於 Office 365 系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=521888)以深入了解。
    
2. 請遵循這些步驟，將適用的 DNS 記錄新增到 DNS 主機提供者，以便驗證網域擁有權。
    
> [!TIP]
> 當您新增網域至此服務並設定 DNS 時，[新增網域至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=282303) 和 [建立 Office 365 的 DNS 記錄](https://go.microsoft.com/fwlink/p/?LinkId=304219)，是有用的參考資源。 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>步驟 2：新增收件者並選擇性地啟用 DBEB

在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)＞。另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。如需 DBEB 的相關資訊，請參閱[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步驟 3：使用 EAC 來設定郵件流程

在 Exchange 系統管理中心 (EAC) 中建立連接器，以啟用 EOP 與您內部部署郵件伺服器之間的郵件流程。如需詳細指示，請參閱 [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx)。
  
#### <a name="how-do-you-know-this-task-worked"></a>如何才能了解此工作是否正常運作？

使用 Remote Connectivity Analyzer 執行用來檢查服務與您環境間之郵件流程的測試。如需詳細資訊，請參閱[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)中的「使用 Remote Connectivity Analyzer 來測試電子郵件傳遞」一節。
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a>步驟 4：允許輸入連接埠 25 SMTP 存取

設定連接器之後，請等待 72 小時以允許傳播 DNS 記錄更新。接著限制防火牆或郵件伺服器上的通訊埠 25 SMTP 流量，以僅接受來自 EOP 資料中心的郵件 (尤其是來自 [Exchange Online Protection IP 位址](exchange-online-protection-ip-addresses.md) 所列 IP 位址的郵件)。這會限制您可接收的輸入郵件範圍，以保護內部部署環境的安全。此外，若您在郵件伺服器上進行設定，以控制允許連線執行郵件轉送的 IP 位址，請一併更新這些設定。
  
> [!TIP]
> 將 SMTP 伺服器的連線時間設定設為超過 60 秒。此設定適用於大部分情況，例如在傳送具有大型附件的郵件時可稍許延遲。 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步驟 5：使用命令介面確定垃圾郵件路由傳送至每個使用者的垃圾電子郵件資料夾

若要確保垃圾郵件 （垃圾郵件） 郵件正確地傳送至每位使用者的垃圾郵件資料夾，您必須執行一些設定步驟。[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)中提供的步驟。
  
如果您不想將郵件移至每位使用者的垃圾郵件] 資料夾，您可以選擇另一個巨集指令來編輯您在 Exchange 系統管理中心中的內容篩選原則。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](../configure-your-spam-filter-policies.md)。
  
### <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>步驟 6：使用 Office 365 系統管理中心 將您的 MX 記錄指向 EOP

遵循 Office 365 網域組態步驟來更新網域的 MX 記錄，讓您的輸入電子郵件流過 EOP。請務必直接將 MX 記錄指向 EOP 而非讓協力廠商篩選服務將郵件轉送至 EOP。如需詳細資訊，請再次參照[建立 Office 365 的 DNS 記錄](https://go.microsoft.com/fwlink/p/?LinkId=304219)。
  
#### <a name="how-do-you-know-this-task-worked"></a>如何才能了解此工作是否正常運作？

使用 Remote Connectivity Analyzer 執行用來驗證您 MX 記錄的測試。如需詳細資訊，請參閱[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)中的「使用 Remote Connectivity Analyzer 來測試 MX 記錄和輸出連接器」一節。 
  
到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：
  
- 在 Remote Connectivity Analyzer 中，按一下 **[Office 365]** 索引標籤，然後執行位於 **[網際網路電子郵件測試]** 底下的 **[輸入 SMTP 電子郵件]** 測試。 
    
- 從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。
    
- 如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。
    
> [!TIP]
> 當您完成設定時，不需要執行額外步驟即可讓 EOP 移除垃圾郵件和惡意軟體。EOP 會自動移除垃圾郵件和惡意軟體。不過，您可以根據本身的商務需求來微調 EAC 中的設定。如需詳細資訊，請參閱 [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)。 > 現在您的服務在執行中，建議您閱讀[設定 EOP 的最佳作法](best-practices-for-configuring-eop.md)，其中會說明設定好 EOP 後的建議設定和注意事項。 
  

