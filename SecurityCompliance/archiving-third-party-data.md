---
title: 在 Office 365 中封存協力廠商資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 系統管理員可以從匯入協力廠商資料社交媒體平台、 立即訊息平台及文件共同作業平台至 Office 365 組織中的信箱。這可讓您封存 Office 365 中的 Facebook、 Twitter 與資料來源的資料。然後您可以與協力廠商資料 appply Office 365 的符合性功能 （例如法務保存措施、 內容搜尋和保留原則）。
ms.openlocfilehash: f5590d170986b8ae69458e69cedeb8a0ef137ef4
ms.sourcegitcommit: 81c2fd5cd940c51bc43ac7858c7bdfa207ce401a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2018
ms.locfileid: "23809708"
---
# <a name="archiving-third-party-data-in-office-365"></a>在 Office 365 中封存協力廠商資料

Office 365 可讓系統管理員匯入及封存立即訊息平台和文件共同作業平台，至 Office 365 組織中信箱的社交媒體平台的協力廠商資料。您可以匯入至 Office 365 的協力廠商資料來源的範例包括： 
  
- **社交**-Twitter、 Facebook、 Yammer 及 LinkedIn 
    
- **立即訊息**-Yahoo Messenger、 GoogleTalk、 及 Cisco Jabber 
    
- **文件共同作業**-方塊和投寄箱 
    
- **垂直產業**-客戶關係管理 （例如 Salesforce 交談） 和 Financials （例如湯氏路透社和 Bloomberg） 
    
- **SMS/文字郵件**-BlackBerry 
    
在匯入協力廠商資料之後，您可以套用 Office 365 的符合性功能 — 例如訴訟暫止狀態、 內容搜尋、 就地封存、 稽核、 及 Office 365 的保留原則-此資料。例如，當信箱處於訴訟暫止狀態，則會保留與協力廠商資料。您可以使用內容搜尋來搜尋協力廠商資料。或您可以套用封存和保留原則就像您可以為 Microsoft 資料的第三方資料。在短封存 Office 365 中的第三方資料可協助組織保持在最符合政府和法規的原則。
  
以下是程序和步驟的概觀 （英文） 需要協力廠商將資料匯入 Office 365。

[步驟 1：尋找協力廠商資料合作夥伴](#step-1-find-a-third-party-data-partner)

[步驟 2：在 Office 365 中建立及設定協力廠商資料信箱](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[步驟 3：設定協力廠商資料的使用者信箱](#step-3-configure-user-mailboxes-for-third-party-data)

[步驟 4：提供資訊給合作夥伴](#step-4-provide-your-partner-with-information)

[步驟 5： 在 Azure Active Directory 中登錄的協力廠商資料連接器](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>如何將第三方的資料匯入程序的運作方式 >

下圖和描述會說明協力廠商資料匯入程序的運作方式。
  
![協力廠商資料匯入程序的運作方式](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. 客戶適用於設定連接器將從協力廠商資料來源擷取項目並再匯入 Office 365 的 [項目選擇的其合作夥伴。
    
2. 協力廠商連接器會連接到 （根據排程或做為設定） 的協力廠商 API 透過協力廠商資料來源，並從資料來源擷取項目。協力廠商連接器將電子郵件訊息格式轉換項目的內容。請參閱[的詳細資訊](#more-information)] 區段中的郵件格式結構描述的說明。 
    
3. 協力廠商連接器會使用 Exchange Web 服務 (EWS) 透過已知的終點連線到 Office 365 中的 Azure 服務。
    
4. 項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：
    
    a.**項目所擁有的對應至 Office 365 使用者帳戶的使用者識別碼**-如果協力廠商連接器可以對應至特定使用者在 Office 365 中，此項目 ID 複製到 [**清除**] 資料夾中的使用者的使用者識別碼的協力廠商資料來源中的項目可復原項目] 資料夾。使用者無法存取 [清除] 資料夾中的項目。不過，您可以使用 Office 365 eDiscovery 工具來搜尋 [清除] 資料夾中的項目。
    
    b.**所沒有的對應至 Office 365 使用者帳戶的使用者識別碼的項目**-如果協力廠商連接器無法將項目的使用者識別碼對應至特定使用者在 Office 365 中，此項目 ID 複製到的協力廠商資料信箱的 [**收件匣**] 資料夾。將項目匯入至收件匣可讓您或有人登入與協力廠商信箱來檢視和管理這些項目，並查看任何調整是否需要進行的協力廠商連接器設定在組織中。
 
## <a name="step-1-find-a-third-party-data-partner"></a>步驟 1：尋找協力廠商資料合作夥伴

封存 Office 365 中的第三方資料的重要元件會尋找並使用擷取協力廠商資料來源的資料及將其匯入 Office 365 中專門是 Microsoft 合作夥伴。它將資料匯入之後，可以封存和保留與您組織的其他 Microsoft 資料，例如電子郵件從 Exchange 和 SharePoint 和 OneDrive for Business 文件。合作夥伴會建立的資料擷取您組織的協力廠商資料來源 （例如 BlackBerry、 Facebook、 Google +、 湯氏路透社、 Twitter 及 YouTube） 並將該資料傳遞給將項目匯入至 Exchange 信箱作為 Office 365 API 的連接器電子郵件訊息。 
  
下列各節將列出 Microsoft 合作夥伴 — 以及它們所支援之協力廠商資料來源 — 可參與計劃封存 Office 365 中的第三方資料。

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
    
- 
MessageLabs 資料流

    
- OpenText
    
- Oracle/ATG 'click-to-call' 即時說明

    
- 樞紐分析 IMTRADER

    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 
商務用 Skype (Lync/OCS)
    
- 
商務用 Skype Online (Lync Online)

    
- SQL 資料庫
    
- 
Squawker

    
- Thomson Reuters Eikon Messenger

  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com)支援下列協力廠商資料來源： 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- 
含樞紐分析用戶端的 AOL

    
- Ares
    
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

    
- Cisco IM&amp;平台服務伺服器 (v9.0.1、 v9.1、 v9.1.1 SU1、 v10、 v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)

    
- Collaboration Import

    
- Collaboration Real Time Logging

    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+

    
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

    
- ICE/YellowJacket
    
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
    
- 
Microsoft Lync (2010、2013)

    
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
    
- Pivot
    
- QQ
    
- 商務用 Skype 2015
    
- SoftEther
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Tor
    
- TTT
    
- Twitter
    
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
    
- Twitter
    
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
    
- Cisco IM&amp;平台服務伺服器 (v10、 v10.5.1 SU1 v11.0、 v11.5 SU2)

- Cisco Webex 小組

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- 自訂分隔符號文字檔

    
- 自訂 XML 檔案

    
- Facebook （頁面）
    
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
    
- Pivot
    
- Salesforce Chatter

- 商務用 Skype Online
    
- 商務用 Skype 2007 版 R2 - 2016 (內部部署)

    
- Slack Enterprise Grid
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Thomson Reuters Dealings 3000 / FX Trading

    
- Twitter
    
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

    
- Cisco UCCX/UCCE 影片
    
- Cisco UCCX/UCCE 語音
    
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

以下是建立及設定將資料匯入 Office 365 的協力廠商資料信箱的步驟。為舊清楚、 項目將會匯入此信箱是否協力廠商連接器無法對應至 Office 365 使用者帳戶的使用者識別碼的項目。
  
 **完成這些工作在 Office 365 系統管理中心**
  
1. Office 365 中建立新的使用者帳戶並將其指派 Exchange Online 計劃 2 的授權;請參閱[新增使用者至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。計劃 2 授權，才能信箱置於訴訟暫止狀態或啟用封存信箱已無限制的儲存配額。
    
2. 將協力廠商資料信箱的使用者帳戶新增至 Office 365; 中的**Exchange 系統管理員**系統管理角色請參閱[指派 Office 365 中的系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。
    
    > [!TIP]
    > 請寫下此使用者帳戶的認證。您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。 
  
 **完成這些工作在 Exchange 系統管理中心**
  
1. 隱藏從通訊錄與您的組織 ； 在其他通訊清單的第三方資料信箱請參閱[Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058)。或者，您可以執行下列 PowerShell 命令：
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 指派協力廠商資料信箱的**FullAccess**權限，讓系統管理員或法務人員可以在 Outlook 桌面用戶端; 中開啟與協力廠商資料信箱請參閱[收件者的管理權限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。
    
3. 啟用下列規範相關 Office 365 的功能與協力廠商資料信箱：
    
    - 啟用封存信箱 ；請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)並[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。這可讓您藉由設定會與協力廠商資料的項目移至封存信箱的封存原則主要信箱中釋放儲存空間。這會提供給您不受限制的存放區的第三方資料。
    
    - 協力廠商資料信箱可以置於訴訟暫止狀態。您也可以套用 Office 365 安全性 Office 365 保留原則&amp;規範中心。將這個信箱設定保留會保留與協力廠商資料的項目 （無限期或指定的持續期間） 並防止從信箱清除。請參閱下列主題的其中一個：
    
      - [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Office 365 中的保留原則的概觀](retention-policies.md)
    
       
    
    - 啟用信箱稽核記錄的擁有者、 委派、 和系統信箱的存取權與協力廠商資料 ；請參閱[啟用信箱稽核 Office 365 中](enable-mailbox-auditing.md)。這可讓您以稽核在任何具有存取權的協力廠商資料信箱的使用者所執行的所有活動。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步驟 3：設定協力廠商資料的使用者信箱

下一步是設定為支援與協力廠商資料的使用者信箱。使用 Exchange 系統管理中心或使用相對應的 Windows PowerShell cmdlet 來完成這些工作。
  
1. 啟用封存信箱的每位使用者;請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)並[啟用 Office 365 中沒有限制之封存](enable-unlimited-archiving.md)。
    
2. 置於使用者信箱訴訟暫止狀態或適用於 Office 365 保留原則請參閱下列主題的其中一個： 
    
    - [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Office 365 中的保留原則的概觀](retention-policies.md)
    
    如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。

## <a name="step-4-provide-your-partner-with-information"></a>步驟 4：提供資訊給合作夥伴

最後一個步驟是讓您的合作夥伴具有下列資訊，讓他們可以設定連接器以連接到您的 Office 365 組織，將資料匯入至使用者信箱和協力廠商資料信箱。 
  
- 用來連線至 Office 365 的 Azure 服務端點：

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 登入您在步驟 2 中建立的協力廠商資料信箱認證 （Office 365 使用者識別碼和密碼）。這些認證是必要的協力廠商連接器可以存取和使用者信箱與協力廠商資料信箱匯入項目。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步驟 5： 在 Azure Active Directory 中登錄的協力廠商資料連接器

啟動 2018 September 30、 Office 365 的 Azure 服務會開始使用經過驗證在 Exchange Online 進行驗證嘗試連線至 Office 365 組織匯入資料的第三方資料連接器。這項變更的原因是經過驗證提供更多安全性比目前的方法來連線至 Azure 服務使用先前所述的端點的家協力廠商連接器的基礎。

若要啟用協力廠商資料連接線連線到 Office 365 使用新的現代的驗證方法，在 Office 365 組織中的系統管理員必須同意登錄為 Azure Active Directory 中的受信任的服務應用程式的連接器。做法是接受權限要求允許存取您的組織資料 Azure Active Directory 中的連接器。接受此要求之後，與協力廠商資料新增為 Azure Active directory 企業應用程式及連接器表示為服務主要名稱。如同意程序的詳細資訊，請參閱[租用戶系統同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

存取及接受登錄連接器要求的步驟如下：

1. 前往[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)及使用的 Office 365 全域管理員認證登入。<br/><br/>會顯示下列對話方塊。您可以展開檢閱會指派給連接器的權限插入號。<br/><br/>![顯示 [權限要求] 對話方塊](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. 按一下 [**接受**]。

接受邀請之後，會顯示[Azure 入口網站的儀表板](https://portal.azure.com)。若要檢視您組織的應用程式清單，請按一下 [ **Azure Active Directory** > **企業應用程式**。**企業應用程式**blade 會列出 Office 365 協力廠商資料連接器。

> [!IMPORTANT]
> 之後 2018 September 30、 協力廠商將不會再將資料匯入您組織中信箱如果您不在 Azure Active Directory 登錄協力廠商資料連接器。也必須遵循下列步驟 5 中的程序在 Azure Active Directory 中登錄現有的協力廠商資料連接器 （與其 2018 September 30、 之前建立） 的附註。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Grant 同意的協力廠商資料連接器

您的組織 consents 權限要求在 Azure Active Directory 中登錄的協力廠商資料連接器之後，您的組織可以撤銷隨時該同意。不過，撤銷連接器同意表示可與協力廠商資料來源的資料將不會再匯入 Office 365。

若要撤銷的協力廠商資料連接器的同意，您可以刪除應用程式 （刪除的對應的服務主要名稱） 從 Azure 入口網站，或使用[使用**企業應用程式**blade 部署 Azure Active Directory移除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) Office 365 PowerShell 中。您也可以使用 Azure Active Directory PowerShell 中的[移除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)指令程式。
  
## <a name="more-information"></a>其他資訊

- 為舊清楚，從協力廠商資料來源匯入至做為電子郵件的 Exchange 信箱的項目。協力廠商連接器匯入使用 Office 365 API 所需的結構描述的項目。下表說明郵件項目的屬性與協力廠商的資料來源之後匯入至 Exchange 信箱以電子郵件訊息。表也會指出是否 message 屬性是必要項目。必須填入必要屬性。如果項目缺少一個必要的屬性，將不會匯入至 Office 365。匯入程序將會傳回錯誤訊息說明為何項目未匯入和遺漏的屬性。
    
    |**郵件屬性**|**必要？**|**描述**|**範例值**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |是  <br/> |最初建立或傳送項目之協力廠商資料來源中的使用者。協力廠商連接器會嘗試將對應所有參與者 （FROM 和 TO 欄位中的使用者） 的 Office 365 使用者帳戶從來源項目 （例如 Twitter 控點） 的使用者識別碼。郵件的複本會匯入至每個參與者的信箱。如果任何項目從參與者可以對應至 Office 365 使用者帳戶，此項目將會匯入至 Office 365 中的第三方封存信箱。<br/> <br/> 項目的寄件者身分識別的參與者必須具備的項目以匯入 Office 365 組織中使用中信箱。如果寄件者沒有作用中的信箱，會傳回下列錯誤：<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |是  <br/> |接收項目的使用者，如果適用於資料來源中的項目。  <br/> | `bob@contoso.com` <br/> |
    |**SUBJECT** <br/> |否  <br/> |來源項目的主旨。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**日期** <br/> |是  <br/> |項目最初建立或張貼在客戶資料來源的日期。例如，Twitter 訊息推文的日期。  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |否  <br/> |郵件或張貼內容。某些資料來源而言，此屬性的內容可能是**SUBJECT**屬性的內容相同。匯入程序期間的協力廠商連接器會嘗試將維護儘可能將內容來源的完整不失真。請盡可能檔案、 圖形或其他內容從來源項目的本文隨附於此屬性。否則請內容從來源項目包含在**附件**屬性。此屬性的內容取決來源平台功能及協力廠商連接器上。<br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |否  <br/> |如果資料來源 （例如 Twitter 或立即訊息交談中叫） 中的項目具有附加的檔案或包含圖像、 協力廠商連線將第一次嘗試將附件納入**BODY**屬性。如果不是可行的則會新增到 * * 附件 * * 屬性。附件的其他範例 Facebook、 中繼資料與內容來源及回覆郵件或張貼中包含 「 讚 」。<br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |是  <br/> | 這是多重值屬性，會建立及填入的協力廠商連接器。此屬性的格式是`IPM.NOTE.Source.Event`。(此屬性必須以開頭`IPM.NOTE`； 此格式會類似的`IPM.NOTE.X`郵件類別。)此屬性包含下列資訊：<br/><br/>`Source`-會指出與協力廠商資料來源 ；例如，Twitter、 Facebook 或 BlackBerry。  <br/> <br/>  `Event`-會指出已執行所產生的項目 ； 協力廠商資料來源中的活動類型例如，Twitter 或 Facebook 中的張貼叫。事件屬於特定資料來源。<br/> <br/>  此屬性的目的之一是事件的篩選出或項目源自類型為基礎的資料來源為基礎的特定項目。例如，在 eDiscovery 搜尋無法建立搜尋查詢以尋找當天的特定使用者的所有 tweets。<br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- 當項目已成功匯入至 Office 365 中的信箱時的唯一識別碼會傳回回到來電者的 HTTP 回應的一部分。此識別碼 — 呼叫`x-IngestionCorrelationID`— 可用於後續的疑難排解用途協力廠商的端對端追蹤項目。建議合作夥伴擷取此資訊與據此記錄其結尾。以下是範例顯示此識別碼 HTTP 回應：

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- 您可以使用 「 內容搜尋工具在 Office 365 安全性&amp;規範中心來搜尋的項目已匯入 Office 365 中的信箱與協力廠商的資料來源。若要搜尋特別針對這些匯入的項目，您可以使用成對的下列郵件屬性值在 [關鍵字] 方塊中的內容搜尋。. 
    
  - **`kind:externaldata`**-使用此屬性值配對搜尋所有的協力廠商的資料類型。例如，若要搜尋的項目都已匯入協力廠商的資料來源及匯入的項目之主旨屬性中包含單字"contoso"，您會使用關鍵字查詢`kind:externaldata AND subject:contoso`。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-使用此屬性值組搜尋指定類型的協力廠商資料。例如，若要只搜尋 Facebook 資料包含單字"contoso"主旨屬性中，您會使用關鍵字查詢`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。 

  如要使用的協力廠商資料類型值的完整清單`itemclass`屬性，請參閱[使用搜尋的已匯入 Office 365 的協力廠商資料的內容搜尋](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰
    
  - [Office 365 中的內容搜尋](content-search.md)
    
  - [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
 
