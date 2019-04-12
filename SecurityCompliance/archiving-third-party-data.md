---
title: 在 Office 365 中封存協力廠商資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 系統管理員可以從匯入協力廠商資料社交媒體平台、 立即訊息平台，以及文件共同作業平台到 Office 365 組織中的信箱。 這可讓您封存在 Office 365 中的 Facebook、 Twitter 和資料來源中的資料。 然後您可以將 Office 365 符合性功能 （例如合法持有、 內容搜尋和保留原則） 套用至協力廠商資料。
ms.openlocfilehash: 06ac436b1583187e89cb7f1beb26411ba02becec
ms.sourcegitcommit: 86ff2eba1d57b9d5288840788529e69ad9d836b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31818610"
---
# <a name="archiving-third-party-data-in-office-365"></a>在 Office 365 中封存協力廠商資料

Office 365 可讓系統管理員匯入及封存立即訊息平台，與文件共同作業平台，您的 Office 365 組織中的信箱從社交媒體平台的協力廠商資料。 您可以匯入至 Office 365 的協力廠商資料來源的範例包括下列： 
  
- **社交**-Twitter、 Facebook、 Yammer 和 LinkedIn 
    
- **立即訊息**-Yahoo Messenger、 GoogleTalk 和 Cisco Jabber 
    
- **文件共同作業**-方塊和 DropBox 
    
- **垂直產業**-客戶關係管理 （例如 Salesforce Chatter) 和金融服務 （例如 Thomson Reuters 及 Bloomberg） 
    
- **SMS/簡訊**-BlackBerry 
    
協力廠商資料匯入之後，您可以套用 Office 365 合規性功能，例如訴訟暫止狀態、 內容搜尋、 就地封存、 稽核、 及 Office 365 保留原則 — 此資料。 例如，當信箱置於訴訟暫止狀態時，協力廠商資料將會保留。 您可以使用內容搜尋來搜尋協力廠商資料。 或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以對 Microsoft 資料進行的動作一樣。 總之，封存在 Office 365 中的協力廠商資料可協助組織符合規範與政府法規的原則。
  
Xxxx'x 協力廠商資料匯入至 Office 365 所需的程序和步驟的概觀。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Step 2: Create and configure a third-party data mailbox in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[步驟 4：提供資訊給合作夥伴](#step-4-provide-your-partner-with-information)

[步驟 5： 在 Azure Active Directory 中註冊的協力廠商資料連接器](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>協力廠商資料匯入程序的運作方式

下圖和描述會說明協力廠商資料匯入程序的運作方式。
  
![協力廠商資料匯入程序的運作方式](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. 客戶的運作方式與設定連接器，從協力廠商資料來源擷取項目，並再匯入 Office 365 的 [這些項目所選擇的其合作夥伴。
    
2. 協力廠商連接器會連接到 （根據排程或做為設定） 的協力廠商 API 透過協力廠商資料來源，並從資料來源擷取項目。 協力廠商連接器會將項目的內容轉換為電子郵件訊息格式。 請參閱 [More information](#more-information) 一節以取得訊息格式結構描述的說明。 
    
3. 協力廠商連接器會連接至 Office 365 中的 Azure 服務透過已知端點使用 Exchange Web 服務 (EWS)。
    
4. 項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：
    
    a. **具有，會對應至 Office 365 使用者帳戶的使用者識別碼的項目**-如果協力廠商連接器可以將協力廠商資料來源中的項目的使用者識別碼對應至特定使用者在 Office 365 中，項目識別碼會複製到使用者的記錄中的 [**清除**] 資料夾overable 項目] 資料夾。 使用者無法存取 [清除] 資料夾中的項目。 不過，您可以使用 Office 365 電子文件探索工具來搜尋 [清除] 資料夾中的項目。
    
    b. **項目，不需要會對應至 Office 365 使用者帳戶的使用者識別碼**-如果協力廠商連接器無法將項目的使用者識別碼對應至特定使用者在 Office 365 中，項目識別碼會複製到的協力廠商資料信箱的 [**收件匣**] 資料夾。 將項目匯入至收件匣可讓您或組織中的某個人登入協力廠商信箱來檢視和管理這些項目，並查看是否需要在協力廠商連接器組態中進行任何調整。
 
## <a name="step-1-find-a-third-party-data-partner"></a>步驟 1：尋找協力廠商資料合作夥伴

封存 Office 365 中的協力廠商資料的主要元件是尋找並使用 Microsoft 合作夥伴，專門負責擷取協力廠商資料來源的資料，並將它匯入至 Office 365 中。 它在匯入資料之後，可以封存和保留沿著與您組織的其他 Microsoft 資料，例如來自 Exchange 電子郵件和文件中的 SharePoint 和商務用 OneDrive。 協力廠商建立連接器，從貴組織的協力廠商資料來源 （如 BlackBerry、 Facebook、 Google +、 Thomson Reuters、 Twitter 和 YouTube） 擷取資料，並將該資料傳遞給將項目匯入至 Exchange 信箱做為 Office 365 API電子郵件訊息。 
  
下列各節列出的 Microsoft 合作夥伴 — 以及它們所支援的協力廠商資料來源 —，參與程式來封存 Office 365 中的協力廠商資料。

[17a-4 LLC](#17a-4-llc)
  
[Actiance](#actiance)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

17a-4 LLC 支援下列協力廠商資料來源：
  
- BlackBerry
    
- Bloomberg 資料流
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs 資料流
    
- OpenText
    
- Oracle/ATG 'click-to-call' 即時說明
    
- 樞紐分析 IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 商務用 Skype (Lync/OCS)
    
- 商務用 Skype Online (Lync Online)
    
- SQL 資料庫
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com)支援下列協力廠商資料來源： 
  
- 目標
    
- American Idol
    
- Apple Juice
    
- 含樞紐分析用戶端的 AOL
    
- 阿瑞斯
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry Call Logs (v5、v10、v12)
    
- BlackBerry Messenger (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg 郵件
    
- CellTrust
    
- Chat Import
    
- Chat Real Time Logging and Policy
    
- Chatter
    
- Cisco IM &amp; Presence Server (v9.0.1、 v9.1、 v9.1.1 SU1、 v10、 v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
    
- Collaboration Import
    
- Collaboration Real Time Logging
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- 冰/YellowJacket
    
- IM Import
    
- IM Real Time Logging and Policy
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6、v7)
    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010、2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010、2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- Pinterest
    
- 樞紐
    
- QQ
    
- 商務用 Skype 2015
    
- SoftEther
    
- 號交響曲
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- 在 twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    
  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com)支援下列協力廠商資料來源： 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- 在 twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com)支援下列協力廠商資料來源： 
  
- 含樞紐分析用戶端的 AOL 
    
- BlackBerry Call Logs (v5、v10、v12)
    
- BlackBerry Messenger (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg Chat
    
- Bloomberg 郵件
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp; Presence Server (v10、 v10.5.1 SU1、 v11.0、 v11.5 SU2)

- Cisco Webex 小組

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- 自訂分隔符號文字檔
    
- 自訂 XML 檔案
    
- Facebook （網頁）
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- 樞紐
    
- Salesforce Chatter

- 商務用 Skype Online
    
- 商務用 Skype 2007 版 R2 - 2016 (內部部署)
    
- Slack Enterprise Grid
    
- 號交響曲
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- 在 twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支援下列協力廠商資料來源： 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com)支援下列協力廠商資料來源： 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber IM
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Cisco UCCX/UCCE Video
    
- Cisco UCCX/UCCE Voice
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle / Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- 商務用 Skype/Lync IM
    
- 商務用 Skype/Lync Video
    
- 商務用 Skype/Lync Voice
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Windows Desktop Computer Screen
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>步驟 2：在 Office 365 中建立及設定協力廠商資料信箱

以下是建立和設定將資料匯入 Office 365 的協力廠商資料信箱的步驟。 如同先前的說明，項目匯入到此信箱是否協力廠商連接器無法將項目的使用者識別碼對應至 Office 365 使用者帳戶。
  
 **在 Microsoft 365 系統管理中心完成這些工作**
  
1. 在 Office 365 中建立新的使用者帳戶，並將它指派 Exchange Online Plan 2 授權。請參閱[新增使用者至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。 若要讓信箱處於訴訟暫止狀態或啟用封存信箱時不受限制的儲存配額，需要計劃 2 授權。
    
2. 將協力廠商資料信箱的使用者帳戶新增至 Office 365; 中的**Exchange 系統管理員**系統管理角色請參閱[指派 Office 365 中的系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。
    
    > [!TIP]
    > 請寫下此使用者帳戶的認證。 您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。 
  
 **在 Exchange 系統管理中心完成這些工作**
  
1. 隱藏通訊錄及其他通訊清單中您的組織; 從協力廠商資料信箱請參閱[Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058)。 或者，您可以執行下列 PowerShell 命令：
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 指派給協力廠商資料信箱的**FullAccess**權限，讓系統管理員或法務人員可以在 Outlook 桌面用戶端; 中開啟的協力廠商資料信箱請參閱[管理收件者的權限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。
    
3. 啟用下列符合性相關 Office 365 功能的協力廠商資料信箱：
    
    - 啟用封存信箱;請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限制封存](enable-unlimited-archiving.md)。 這可讓您藉由將協力廠商資料的項目移至封存信箱的封存原則設定的主要信箱中釋放儲存空間。 這會提供您協力廠商資料的無限儲存容量。
    
    - 將協力廠商資料信箱處於 [訴訟暫止] 狀態。 您也可以套用在安全性與合規性中心的 Office 365 保留原則。 將此信箱置於保留狀態會保留協力廠商資料項目 （無限期或於指定期間內），並防止從信箱清除郵件。 請參閱下列主題：
    
      - [將信箱設為訴訟暫止](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [在 Office 365 中的保留原則概觀](retention-policies.md)
    
       
    
    - 啟用信箱稽核記錄的擁有者、 代理人及系統管理存取權的協力廠商資料信箱;請參閱 <<c0>啟用 Office 365 中的稽核的信箱。 這樣可讓您以稽核在所具有的存取權的協力廠商資料信箱的任何使用者執行的所有活動。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步驟 3：設定協力廠商資料的使用者信箱

下一步是設定使用者信箱以支援協力廠商資料。 使用 Exchange 系統管理中心或使用對應的 Windows PowerShell cmdlet，以完成這些工作。
  
1. 啟用封存信箱的每位使用者。請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限制封存](enable-unlimited-archiving.md)。
    
2. 將使用者信箱置於訴訟暫止狀態或適用於 Office 365 保留原則;請參閱下列主題： 
    
    - [將信箱設為訴訟暫止](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [在 Office 365 中的保留原則概觀](retention-policies.md)
    
    如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。

## <a name="step-4-provide-your-partner-with-information"></a>步驟 4：提供資訊給合作夥伴

最後一個步驟是讓您的合作夥伴具有下列資訊，讓他們可以設定連接器以連接到您的 Office 365 組織，將資料匯入至使用者信箱和協力廠商資料信箱。 
  
- 用來連線至 Office 365 中的 Azure 服務的端點：

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 登入您在步驟 2 中建立的協力廠商資料信箱的認證 （Office 365 使用者識別碼和密碼）。 協力廠商連接器需要這些認證才能存取項目以及將其匯入至使用者信箱和協力廠商資料信箱。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步驟 5： 在 Azure Active Directory 中註冊的協力廠商資料連接器

啟動 2018 年 9 月 30 日，Office 365 中的 Azure 服務將開始使用新式驗證在 Exchange Online 來驗證嘗試連線至 Office 365 組織，以匯入資料的協力廠商資料連接器。 這項變更的原因是新式驗證提供比目前的方法根據核准清單第三方連接器用來連線到 Azure 服務先前所述的端點更高的安全性。

若要啟用協力廠商資料連接器，以連線至 Office 365 中，使用新的新式驗證方法，在您的 Office 365 組織中系統管理員必須同意註冊為 Azure Active Directory 中的受信任的服務應用程式的連接器。 這是接受以允許存取貴組織的資料在 Azure Active Directory 連接器的權限要求。 接受此邀請之後，協力廠商資料連接器會新增為企業應用程式至 Azure Active Directory，並代表服務主要名稱。 如需詳細資訊的同意程序，請參閱[租用戶系統管理員同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

以下是步驟來存取，並接受邀請来登錄連接器：

1. 前往[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，並使用 Office 365 全域系統管理員認證登入。<br/><br/>下列對話方塊會顯示。 您可以展開檢閱會指派給連接器的權限插入號。<br/><br/>![權限要求] 對話方塊隨即顯示](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. 按一下 [接受]****。

接受邀請之後，會顯示[Azure 入口網站](https://portal.azure.com)。 若要檢視您組織的應用程式的清單，請按一下 [ **Azure Active Directory** > **企業應用程式**。 Office 365 協力廠商資料連接器會列在 [**企業應用程式**] 刀鋒視窗上。

> [!IMPORTANT]
> 2018 年 9 月 30 日之後, 協力廠商資料將無法再匯入您的組織中的信箱如果您不在 Azure Active Directory 中註冊的協力廠商資料連接器。 也必須依照下列步驟 5 中的程序在 Azure Active Directory 中註冊現有的協力廠商資料連接器 （那些 2018 年 9 月 30 日之前所建立） 的附註。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>撤銷同意的協力廠商資料連接器

您的組織 consents 要在 Azure Active Directory 中註冊的協力廠商資料連接器的權限要求之後，您的組織可以撤銷隨時該同意。 但是，撤銷同意的連接器會代表從協力廠商資料來源的資料將無法再匯入 Office 365。

若要撤銷同意的協力廠商資料連接器，您可以刪除應用程式 （藉由刪除對應的服務主要） 從 Azure 入口網站中，或使用[使用**企業應用程式**] 刀鋒視窗上的 Azure Active Directory移除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)在 Office 365 PowerShell。 您也可以在 Azure Active Directory PowerShell 中使用[移除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)指令程式。
  
## <a name="more-information"></a>詳細資訊

- 如先前所述，協力廠商資料來源的項目是匯入至 Exchange 信箱做為電子郵件訊息。 協力廠商連接器會匯入使用 Office 365 API 所需的結構描述的項目。 下表說明協力廠商資料來源的項目在匯入至 Exchange 信箱當做為電子郵件之後的郵件屬性。 表格也會指出郵件屬性是否為必要的。 必須填入必要屬性。 如果項目遺漏必要的屬性，它不會匯入至 Office 365。 匯入程序將傳回錯誤訊息，說明為什麼未匯入項目以及遺失哪些屬性。
    
    |**郵件屬性**|**強制嗎？**|**描述**|**範例值**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |是  <br/> |最初在協力廠商資料來源中建立或傳送項目的使用者。 協力廠商連接器會嘗試將從來源項目 （例如 Twitter 控點） 至 Office 365 使用者帳戶的使用者識別碼對應的所有參與者 （的 FROM 和 TO 欄位中的使用者）。 郵件副本會匯入至每個參與者的信箱。 如果沒有任何一個項目從參與者可以對應至 Office 365 使用者帳戶，Office 365 中的第三方封存信箱會被匯入項目。  <br/> <br/> 識別為項目的寄件者的參與者必須有 Office 365 組織中的項目匯入至作用中信箱。 如果寄件者沒有作用中的信箱，則會傳回下列錯誤︰<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |是  <br/> |接收項目的使用者，如果適用於資料來源中的項目。  <br/> | `bob@contoso.com` <br/> |
    |**主旨** <br/> |否  <br/> |來源項目的主旨。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**日期** <br/> |是  <br/> |項目最初建立或張貼在客戶資料來源的日期。例如，Twitter 訊息推文的日期。  <br/> | `01 NOV 2015` <br/> |
    |**本文** <br/> |否  <br/> |訊息或文章的內容。 對於某些資料來源，這個屬性的內容可能與 **SUBJECT** 屬性的內容相同。 在匯入程序期間，協力廠商連接器會盡可能嘗試維護內容來源不失真。 如果可能的話，來源項目的內文中的檔案、圖形或其他內容會包含在此屬性中。 否則，來源項目的內容會包含在 **ATTACHMENT** 屬性。 此屬性的內容取決於來源平台功能和協力廠商連接器上。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**附件** <br/> |否  <br/> |如果資料來源 （例如 Twitter 或立即訊息交談中叫） 中的項目已經附加的檔案，或包含圖像，合作夥伴連線將第一次嘗試在**BODY**屬性中包含附件。 如果不可行的則它會新增至 * * 附件 * * 屬性。 其他附件範例包括 Facebook 的「讚」、內容來源的中繼資料和訊息或文章的回應。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |是  <br/> | 這是多重值屬性，由合作夥伴連接器建立並填入。 此屬性的格式是`IPM.NOTE.Source.Event`。 (此屬性的開頭必須`IPM.NOTE`; 這種格式是類似的`IPM.NOTE.X`郵件類別。)此屬性包含下列資訊：  <br/><br/>`Source` -會指出的協力廠商資料來源;例如，Twitter、 Facebook 或 BlackBerry。  <br/> <br/>  `Event` -會指出已執行所產生的項目; 協力廠商資料來源中的活動類型例如，Twitter 或 Facebook 中的張貼叫。 事件只適用於資料來源。  <br/> <br/>  此屬性的其中一個用途是要根據項目產生來源位置的資料來源或根據事件類型，篩選特定項目。 例如，在 eDiscovery 搜尋中，您可以建立搜尋查詢來尋找特定使用者所張貼的所有推文。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- 當項目已成功匯入至 Office 365 中的信箱時的唯一識別碼會傳回回到一部分的 HTTP 回應來電者。 此識別碼 — 呼叫`x-IngestionCorrelationID`— 可用於由協力廠商的項目數的端對端追蹤後續疑難排解用途。 建議夥伴擷取這項資訊並加以記錄。 以下是顯示此識別碼之 HTTP 回應的範例：

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- 您可以使用安全性與合規性中心中的內容搜尋工具來搜尋協力廠商資料來源匯入至 Office 365 中的信箱項目。 若要搜尋特別針對這些匯入的項目，您可以使用下列郵件屬性值配對關鍵字] 方塊中的內容搜尋。
    
  - **`kind:externaldata`**-使用此屬性值組來搜尋所有協力廠商資料類型。 例如，若要搜尋的項目都已匯入與協力廠商資料來源，並匯入的項目之主旨屬性中包含 「 contoso 」 字樣，您會使用關鍵字查詢`kind:externaldata AND subject:contoso`。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-使用此屬性值組會只搜尋指定資料類型的協力廠商。 例如，若要只搜尋包含主旨屬性中的 「 contoso 」 字樣的 Facebook 資料，您會使用關鍵字查詢`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。 

  如需完整清單，要使用的協力廠商資料類型的值`itemclass`屬性，請參閱[使用內容搜尋 」 來搜尋協力廠商資料匯入的 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰
    
  - [Office 365 中的內容搜尋](content-search.md)
    
  - [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)
 
