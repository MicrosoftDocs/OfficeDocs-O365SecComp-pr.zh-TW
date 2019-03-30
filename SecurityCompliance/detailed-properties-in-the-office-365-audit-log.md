---
title: Office 365 稽核記錄中的詳細內容
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: 包含 Office 365 中的其他屬性的說明稽核記錄。
ms.openlocfilehash: f64b514b777c08048e0f904c17e21c235f8a6f23
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000326"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 稽核記錄中的詳細內容

當您從安全性 & 合規性中心匯出的稽核記錄搜尋結果時，您必須下載符合您的搜尋準則的所有結果的選項。 您執行這項操作藉由選取 [**將結果匯出**\>在**稽核記錄搜尋**] 頁面上的 [**下載所有結果**。 如需詳細資訊，請參閱 <<c0>的搜尋稽核記錄在 Office 365。
  
 當您所有的匯出稽核記錄搜尋結果時，從 Office 365 整合的稽核記錄檔複製到逗點的未經處理資料分隔值 (CSV) 檔案，這會下載到本機電腦。 此檔案包含的其他資訊從名為**詳細資料**] 欄中的稽核記錄項目。 此資料行包含多個屬性的稽核記錄檔記錄的多重值屬性。 此多重值屬性中的**屬性： 值**組的每個都以逗號分隔。 
  
下表說明中所包含的內容-根據 Office 365 服務中發生事件 — 在多重屬性的**詳細資料**] 欄中。 **具有此屬性的 Office 365 服務**] 欄中指出之服務與活動 （使用者或系統管理員），其中包含屬性的類型。 有關這些屬性，或可能不會列示在本主題的內容的詳細資訊，請參閱[Office 365 管理活動 API 結構描述](https://go.microsoft.com/fwlink/p/?LinkId=717993)。
  
> [!TIP]
> 您可以使用 Excel 中的 Power Query 此資料行分割成多個資料行，使每個屬性將有它自己的資料行。 這可讓您排序及篩選一或多個這些屬性。 若要了解如何執行這項操作，請參閱[分割資料行的文字 (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)的 「 分割資料行分隔符號 」 一節。 
  
|**屬性**|**描述**|**具有此屬性的 office 365 服務**|
|:-----|:-----|:-----|
|動作項目|執行巨集指令的使用者或服務帳戶。|Azure Active Directory|
|AddOnName|已新增、 移除或小組中更新附加元件的名稱。 在 [Microsoft Teams 附加元件的型別是 bot、 連接器或] 索引標籤。|Microsoft Teams|
|AddOnType|已新增、 移除或小組中更新的附加元件的類型。 下列的值可指出附加元件的類型。  <br/> **1** -會指出 bot。<br/> **2** -會指出連接器。<br/> **3** -會指出索引標籤。|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory 事件的類型。 下列的值可指出事件的類型。  <br/> **0** -會指出帳戶登入事件。<br/> **1** -會指出 Azure 應用程式的安全性事件。|Azure Active Directory|
|ChannelGuid|Microsoft Teams 通道的識別碼。 通道位於小組識別由**TeamName**和**TeamGuid**屬性。|Microsoft Teams|
|ChannelName|Microsoft Teams 通道的名稱。 通道位於小組識別由**TeamName**和**TeamGuid**屬性。|Microsoft Teams|
|用戶端|用戶端裝置，裝置作業系統，用來登入事件 (例如，Nokia Lumia 920; 裝置瀏覽器Windows Phone 8;IE 行動 11）。|Azure Active Directory|
|ClientInfoString|電子郵件用戶端用來執行此作業，例如瀏覽器版本、 Outlook 版本，以及行動裝置資訊的相關資訊|Exchange （信箱活動）|
|ClientIP|活動已記錄時使用的裝置 IP 位址。 IP 位址會顯示在 IPv4 或 IPv6 地址格式。|Exchange 和 Azure Active Directory|
|ClientIPAddress|ClientIP 相同。|SharePoint|
|CreationTime|日期和時間以 Coordinated Universal Time (UTC) 使用者執行活動時。|全部|
|DestinationFileExtension|檔案副檔名的檔案，複製或移動。 此屬性僅適用於 FileCopied 和 FileMoved 使用者活動的顯示。|SharePoint|
|DestinationFileName|複製或移動的檔案名稱。 此屬性會顯示僅適用於 FileCopied 和 FileMoved 動作。|SharePoint|
|DestinationRelativeUrl|其中檔案複製或移動的目的地資料夾的 URL。 **SiteURL**、 **DestinationRelativeURL**，和**DestinationFileName**屬性值的組合為**ObjectID**屬性，亦即已複製之檔案的完整路徑名稱的值相同。 此屬性僅適用於 FileCopied 和 FileMoved 使用者活動的顯示。|SharePoint|
|EventSource|識別事件發生在 SharePoint 中。 可能值是**SharePoint**及**ObjectModel**。|SharePoint|
|ExternalAccess|對於 Exchange 系統管理員活動，指定是否在使用者在您的組織，由 Microsoft 資料中心的人員或資料中心服務帳戶，或委派的系統管理員執行指令程式。 **為 False**的值會指出此 cmdlet 所執行的組織中的人員。 **則為 True**的值會指出此 cmdlet 所執行的資料中心人員、 資料中心服務帳戶或將委派的管理員。  <br/> Exchange 信箱活動，會指定是否由組織外部使用者存取信箱。|Exchange|
|ExtendedProperties|擴充的屬性如 Azure Active Directory 事件。|Azure Active Directory|
|ID|報告項目的識別碼。 識別碼可唯一識別的報告項目。|全部|
|InternalLogonType|保留給內部使用。|Exchange （信箱活動）|
|ItemType|已存取或修改物件的類型。 可能值包括**檔案**、**資料夾**、 **Web**、**網站**、**租用戶**及**DocumentLibrary**。|SharePoint|
|LoginStatus|識別可能發生的登入失敗。|Azure Active Directory|
|LogonType|信箱存取的類型。 下列的值表示存取信箱的使用者類型。  <br/><br/> **0** -會指出信箱擁有者。<br/> **1** -會指出系統管理員。<br/> **2** -表示代理人。 <br/>**3** -會指出在 Microsoft 資料中心中的傳輸服務。<br/> **4** -會指出在 Microsoft 資料中心中的服務帳戶。 <br/>**6** -會指出委派的管理員。|Exchange （信箱活動）|
|MailboxGuid|Exchange 的上次存取信箱的 GUID。|Exchange （信箱活動）|
|MailboxOwnerUPN|擁有存取信箱之人員的電子郵件地址。|Exchange （信箱活動）|
|成員|列出已新增或移除的小組的使用者。 下列的值表示指派給使用者的角色類型。  <br/><br/> **1** -表示擁有者 」 角色。<br/> **2** -會指出 「 成員 」 角色。<br/> **3** -會指出 「 來賓 」 角色。 <br/><br/>Members 屬性也會包含您的組織和成員的電子郵件地址的名稱。|Microsoft Teams|
|ModifiedProperties (名稱、 NewValue，OldValue)|包含的系統管理事件，例如將使用者新增網站或網站集合系統管理員群組成員身分的屬性。 屬性包含 （例如，[網站管理] 群組） 已修改的屬性名稱的新值已修改的屬性 （這類使用者已新增為網站系統管理員，並修改物件的先前值。|所有 （系統管理員活動）|
|ObjectID|針對 Exchange 系統管理員稽核記錄，由指令程式修改物件的名稱。  <br/> SharePoint 活動、 檔案或資料夾的使用者存取的完整 URL 路徑名稱。  <br/> 針對 Azure AD 的活動，已修改的使用者帳戶的名稱。|全部|
|作業|使用者或系統管理員活動的名稱。 此屬性的值會對應至**活動**中，選取值下拉式清單。 如果已選取 [**顯示結果的所有活動**，報表將包含所有服務的所有使用者和系統管理員活動的項目。 描述登入 Office 365 的作業/活動的稽核記錄，請參閱[的搜尋稽核記錄在 Office 365](search-the-audit-log-in-security-and-compliance.md)中的 [**稽核活動**] 索引標籤。  <br/> Exchange 系統管理員活動，此屬性會識別所執行的指令程式的名稱。|全部|
|OrganizationID|Office 365 組織的 GUID。|全部|
|路徑|存取郵件所在的信箱資料夾的名稱。 此屬性也找出該資料夾的位置中建立或複製/移至郵件時。|Exchange （信箱活動）|
|參數|Exchange 系統管理員活動、 名稱和值的 Operation 屬性中所識別的指令程式搭配使用的所有參數。|Exchange （系統管理員活動）|
|RecordType|指定記錄的作業類型。 下列的值可指出的記錄類型。  <br/><br/> **1** -會指出來自 Exchange 系統管理員稽核記錄的記錄。 <br/>**2** -會指出來自挑信箱項目上執行作業的 Exchange 信箱稽核記錄檔的記錄。 <br/>**3** -也會指出來自 Exchange 信箱稽核記錄的記錄。 此記錄類型表示作業的來源信箱 （如將多個項目移至 [刪除的項目] 資料夾或是永久刪除多個項目） 中的多個項目上執行。 <br/>**4** -會指出在 SharePoint 中，網站系統作業，例如系統管理員或使用者權限指派至網站。 <br/>**6** -會指出檔案或資料夾相關的作業在 SharePoint 中，例如使用者檢視或修改檔案。 <br/>**8** -會指出在 Azure Active Directory 中執行系統管理作業。 <br/>**9** -在 Azure Active Directory 中表示 OrgId 登入事件。 這個記錄類型已被取代。 <br/>**10** -會指出在資料中心的 Microsoft 人員所執行的安全性指令程式事件。 <br/>**11** -會指出資料遺失防護 (DLP) 事件，在 SharePoint 中。<br/> **12** -會指出 Sway 事件。 <br/>**13** -Exchange，當設有一種整合的 DLP 原則中的指示 DLP 事件。 Exchange 郵件流程規則 （也稱為傳輸規則） 為基礎的 DLP 事件不受支援。<br>**14** -會指出在 SharePoint 中的共用事件。<br/> **15** -Azure Active Directory 中表示 Secure Token Service (STS) 登入事件。 <br/>**18** -會指出安全性 & 合規性中心事件。 <br/>**20** -會指出 Power BI 事件。 <br/>**21**-會指出 Dynamics 365 事件。<br/>**22** -會指出 Yammer 事件。 <br/>**23** -會指出 Skype for Business 事件。 <br/>**24** -會指出 eDiscovery 事件。 這個記錄類型會指出由執行內容搜尋及管理安全性與合規性中心中的 eDiscovery 案例所執行的活動。 如需詳細資訊，請參閱[搜尋 eDiscovery 活動在 Office 365 稽核記錄](search-for-ediscovery-activities-in-the-audit-log.md)。<br/>**25、 26 日或 27** -會指出 Microsoft Teams 事件。 <br/>**28** -會指出網路釣魚和惡意程式碼事件從 Exchange Online Protection 和 Office 365 進階威脅防護的事件。<br/> **30** -會指出 Microsoft Flow 事件。<br/> **32**位指示 Microsoft Stream 事件。<br/> **35** -會指出 Microsoft Project 事件。 <br/> **36** -會指出 SharePoint 清單事件。<br/> **38** -會指出與保留原則和安全性與合規性中心中的保留標籤相關的事件。  <br/>**40** -會指出從安全性與合規性警示訊號結果的事件。<br/> **41** -會指出在 Office 365 進階威脅防護中的安全連結時間的區塊] 與 [封鎖覆寫事件。<br/>**44** -會指出工作場所分析事件。 <br/>**45** -會指出 PowerApps 應用程式事件。 <br/> **47** -會指出網路釣魚和惡意程式碼事件從 Office 365 進階威脅防護 SharePoint、 OneDrive 及 Microsoft Teams 中的檔案。|全部|
|ResultStatus|會指出 （在 [**作業**] 屬性中指定） 的動作是否成功與否。  <br/> Exchange 系統管理員活動，此值為 **，則為 True** （成功） 或**False** （失敗）。|全部  <br/>|
|SecurityComplianceCenterEventType|表示活動是安全性 & 合規性中心事件。 所有安全性 & 合規性中心活動會都有此屬性為**0**的值。|安全規範中心|
|SharingType|已指派給資源共用的使用者的共用權限類型。 此使用者識別**UserSharedWith**屬性中。|SharePoint|
|網站|檔案或資料夾的使用者存取所在的網站 GUID。|SharePoint|
|SiteUrl|檔案或資料夾的使用者存取所在的網站 URL。|SharePoint|
|SourceFileExtension|由使用者所存取的檔案副檔名。 此屬性是空白的上次存取的物件時的資料夾。|SharePoint|
|SourceFileName|檔案或資料夾之使用者所存取的名稱。|SharePoint|
|SourceRelativeUrl|包含使用者所存取的檔案的資料夾的 URL。 **SiteURL**、 **SourceRelativeURL**，和**SourceFileName**屬性值的組合為**ObjectID**屬性，亦即使用者所存取的檔案的完整路徑名稱的值相同。|SharePoint|
|主旨|存取郵件的主旨行。|Exchange （信箱活動）|
|TabType| ] 索引標籤的類型新增、 移除或小組中更新。 此屬性的可能值包括：  <br/><br/> **Excelpin** -Excel] 索引標籤。  <br/> **分機**所有的第一方和協力廠商應用程式;例如 Planner、 VSTS、 和表單。  <br/> **附註**的 OneNote] 索引標籤。  <br/> **Pdfpin** -PDF] 索引標籤。  <br/> **Powerbi** -PowerBI] 索引標籤。  <br/> **Powerpointpin** -PowerPoint] 索引標籤。  <br/> **Sharepointfiles** -SharePoint] 索引標籤。  <br/> **網頁**-釘選的網站] 索引標籤。  <br/> **Wiki] 索引標籤**-wiki] 索引標籤。  <br/> **Wordpin** -Word 索引標籤。|Microsoft Teams|
|Target (目標)|使用者上所執行的巨集指令 （[**作業**] 屬性中所識別）。 例如，如果來賓使用者新增至 SharePoint 或 Microsoft 小組，則該使用者就會被列在此屬性。|Azure Active Directory|
|TeamGuid|在 [Microsoft Teams 小組的識別碼。|Microsoft Teams|
|TeamName|在 [Microsoft Teams 小組的名稱。|Microsoft Teams|
|UserAgent|使用者的瀏覽器的相關資訊。 在瀏覽器提供此資訊。|SharePoint|
|UserDomain|使用者 （動作項目） 的用戶組織的身分識別資訊誰執行巨集指令。|Azure Active Directory|
|使用者識別碼|執行的巨集指令 （在 [**作業**] 屬性中指定），造成正在記錄之記錄中的使用者。 請注意系統帳戶 （例如 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM） 所執行的活動的記錄也會包含在稽核記錄檔。|全部|
|UserKey|**UserID**屬性中所識別之使用者的替代識別碼。 例如，這個屬性會填入 passport 唯一識別碼 (PUID) 在 SharePoint 中的使用者所執行的事件。 此屬性也可能相同值指定為其他服務] 與 [系統帳戶所執行的事件中發生事件的**UserID**屬性。|全部|
|UserSharedWith|資源共用的使用者。 如果**作業**屬性的值是**SharingSet**包含此屬性。 此使用者也會列在報告中的**共用與**資料行。|SharePoint|
|UserType|執行此作業的使用者類型。 下列的值可指出使用者類型。 <br/> <br/> **0** -一般使用者。 <br/>**2** -Office 365 組織中系統管理員。 <br/>**3** -Microsoft 資料中心系統管理員或資料中心系統帳戶。 <br/>**4** -系統帳戶。 <br/>**5** -應用程式。 <br/>**6** -服務主要名稱。<br/>**7** -自訂原則。<br/>**8** -系統原則。|全部|
|版本|會指出記錄活動 （由**Operation**屬性識別） 的版本號碼。|全部|
|工作量|Office 365 服務發生的活動。 此屬性的可能值包括：  <br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>規範<br/>Sway<br/>商務用 Skype<br/>SecurityComplianceCenter<br/>PowerBI<br/>CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>專案<br/>PowerApps<br/>工作場所分析**|全部|
||||
   
當您按一下 [**詳細資訊**，檢視特定事件的詳細資料時，也會顯示內容上述的附註。 
  
![按一下 [檢視稽核記錄的事件記錄的詳細的內容的詳細資訊](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

