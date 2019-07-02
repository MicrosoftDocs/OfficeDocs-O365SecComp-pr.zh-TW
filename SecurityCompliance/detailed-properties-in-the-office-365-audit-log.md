---
title: Office 365 稽核記錄中的詳細內容
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
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
description: Office 365 audit log 記錄中所包含的其他屬性說明。
ms.openlocfilehash: 8ce85ea452389b0d8239de88730acd6039cc02be
ms.sourcegitcommit: a6968df6e47ab5733a995f1efdc6e3676c5b5d7b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2019
ms.locfileid: "35253932"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 稽核記錄中的詳細內容

當您從安全性 & 合規性中心匯出審核記錄搜尋的結果時, 您可以選擇下載符合搜尋準則的所有結果。 若要執行此動作, 請選取 [**匯出結果** \> ] [**審核記錄搜尋**] 頁面上的 [**下載所有結果**]。 如需詳細資訊, 請參閱[Search the audit log in The Office 365](search-the-audit-log-in-security-and-compliance.md)。
  
 當您匯出審核記錄搜尋的所有結果時, Office 365 統一的審核記錄中的原始資料會複製到逗號分隔值 (CSV) 檔案, 此檔案會下載到您的本機電腦上。 此檔案包含名為**AuditData**之資料行中每個審計記錄的其他資訊。 此資料行包含來自 audit log 記錄的多個屬性的多重值屬性。 此多重值屬性中的每個**屬性: 值**對都是以逗號分隔。 
  
下表說明所包含的屬性, 取決於發生事件的 Office 365 服務 (在 [多重屬性**AuditData** ] 欄中)。 **具有此屬性欄的 Office 365 服務會**指出包含屬性的服務和活動類型 (使用者或系統管理員)。 如需這些屬性的詳細資訊, 或是本主題中可能未列出的屬性, 請參閱[Office 365 管理活動 API 架構](https://go.microsoft.com/fwlink/p/?LinkId=717993)。
  
> [!TIP]
> 您可以使用 Excel 中的 Power Query 將此欄分割成多個欄, 讓每個屬性都有自己的資料行。 這可讓您排序及篩選其中一個或多個屬性。 若要瞭解如何執行這項操作, 請參閱[分割一欄文字 (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)中的「依分隔符號分割資料行」一節。 
  
|**屬性**|**描述**|**具有此屬性的 Office 365 服務**|
|:-----|:-----|:-----|
|參與者|執行動作的使用者或服務帳戶。|Azure Active Directory|
|AddOnName|在小組中新增、移除或更新之附加元件的名稱。 Microsoft 小組中的附加元件類型為 bot、連接器或索引標籤。|Microsoft Teams|
|AddOnType|在小組中新增、移除或更新的附加元件類型。 下列值會指出附加元件的類型。  <br/> **1** -表示 bot。<br/> **2** -表示連接器。<br/> **3** -表示索引標籤。|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory 事件的類型。 下列值會指出事件的類型。  <br/> **0** -表示帳戶登入事件。<br/> **1** -表示 Azure 應用程式安全性事件。|Azure Active Directory|
|ChannelGuid|Microsoft 小組通道的識別碼。 通道所在的小組是由**TeamName**和**TeamGuid**屬性來識別。|Microsoft Teams|
|ChannelName|Microsoft 小組通道的名稱。 通道所在的小組是由**TeamName**和**TeamGuid**屬性來識別。|Microsoft Teams|
|用戶端|用於登入事件的用戶端裝置、裝置 OS 和裝置瀏覽器 (例如 Nokia Lumia 920;Windows Phone 8;IE Mobile 11)。|Azure Active Directory|
|ClientInfoString|用來執行作業之電子郵件客戶程式的相關資訊, 例如瀏覽器版本、Outlook 版本, 以及行動裝置資訊|Exchange (信箱活動)|
|ClientIP|記錄活動時所使用之裝置的 IP 位址。 IP 位址會以 IPv4 或 IPv6 位址格式顯示。|Exchange 和 Azure Active Directory|
|ClientIPAddress|與 ClientIP 相同。|SharePoint|
|CreationTime|使用者執行活動時的日期和時間 (國際標準時間 (UTC))。|全部|
|DestinationFileExtension|複製或移動之檔案的副檔名。 只有 FileCopied 和 FileMoved 使用者活動才會顯示此屬性。|SharePoint|
|Destinationfilename 檔案|將複製或移動的檔案名。 此屬性只會針對 FileCopied 和 FileMoved 動作顯示。|SharePoint|
|DestinationRelativeUrl|將檔案複製或移動至其中的目的地資料夾的 URL。 **SiteURL**、 **DestinationRelativeURL**及**destinationfilename 檔案**屬性值的組合與**ObjectID**屬性的值相同, 後者是已複製檔案的完整路徑名稱的值。 只有 FileCopied 和 FileMoved 使用者活動才會顯示此屬性。|SharePoint|
|EventSource|識別 SharePoint 中發生的事件。 可能的值為**SharePoint**和**ObjectModel**。|SharePoint|
|ExternalAccess|針對 Exchange 系統管理員活動, 指定由組織中的使用者、Microsoft 資料中心人員或資料中心服務帳戶, 或委派的管理員是否執行 Cmdlet。 值**False**表示您組織中的某個人已執行 Cmdlet。 值**True**表示 Cmdlet 由資料中心人員、資料中心服務帳戶或委派的管理員執行。  <br/> 在 [Exchange 信箱活動] 中, 指定是否由組織外部的使用者存取信箱。|Exchange|
|ExtendedProperties|Azure Active Directory 事件的延伸屬性。|Azure Active Directory|
|ID|報表專案的識別碼。 識別碼可唯一識別報表專案。|全部|
|InternalLogonType|保留給內部使用。|Exchange (信箱活動)|
|ItemType|已存取或修改的物件類型。 可能的值**** 包括檔案、**資料夾**、 **Web**、**網站**、**租**使用者和**DocumentLibrary**。|SharePoint|
|LoginStatus|識別可能發生的登入失敗。|Azure Active Directory|
|LogonType|信箱存取的類型。 下列值表示存取信箱的使用者類型。  <br/><br/> **0** -表示信箱擁有者。<br/> **1** -表示系統管理員。<br/> **2** -表示代理人。 <br/>**3** -指出 Microsoft 資料中心內的傳輸服務。<br/> **4** -表示 Microsoft 資料中心的服務帳戶。 <br/>**6** -表示委派的系統管理員。|Exchange (信箱活動)|
|MailboxGuid|所存取之信箱的 Exchange GUID。|Exchange (信箱活動)|
|MailboxOwnerUPN|擁有所存取信箱之人員的電子郵件地址。|Exchange (信箱活動)|
|成員|列出已從小組中新增或移除的使用者。 下列值會指出指派給使用者的角色類型。  <br/><br/> **1** -指出擁有者角色。<br/> **2** -指出成員角色。<br/> **3** -表示來賓角色。 <br/><br/>Members 屬性也包括您的組織名稱, 以及成員的電子郵件地址。|Microsoft Teams|
|ModifiedProperties (Name、NewValue、OldValue)|此屬性包含在系統管理事件中, 例如將使用者新增為網站成員或網站集合管理員群組。 此屬性包含已修改的屬性名稱 (例如, 網站管理員群組) 修改過的屬性的新值 (例如, 新增為網站管理員的使用者, 以及已修改物件的先前值)。|全部 (系統管理活動)|
|ObjectID|對於 Exchange 系統管理員審核記錄, 此 Cmdlet 所修改的物件名稱。  <br/> 針對 SharePoint 活動, 使用者所存取之檔案或資料夾的完整 URL 路徑名稱。  <br/> 針對 Azure AD 活動, 已修改的使用者帳戶名稱。|全部|
|作業|使用者或系統管理員活動的名稱。 此屬性的值會對應至在 [**活動**] 下拉式清單中選取的值。 如果已選取 [**顯示所有活動的結果**], 則報告將包含所有服務的所有使用者和系統管理員活動的專案。 如需在 Office 365 audit 記錄檔中記錄之作業/活動的描述, 請參閱在[office 365 中搜尋 audit log](search-the-audit-log-in-security-and-compliance.md)中的 [已**審核的活動**] 索引標籤。  <br/> 對於 Exchange 系統管理員活動, 此屬性會識別所執行的指令程式名稱。|全部|
|OrganizationID|Office 365 組織的 GUID。|全部|
|路徑|所存取郵件所在之信箱資料夾的名稱。 此屬性也會識別在其中建立郵件或複製/移動至其中的資料夾。|Exchange (信箱活動)|
|參數|針對 Exchange 系統管理活動, 所有參數的名稱和值, 都是與 Operation 屬性中所識別的 Cmdlet 搭配使用。|Exchange (系統管理活動)|
|RecordType|記錄所指定的作業類型。 下列值會指出記錄類型。  <br/><br/> **1** -指出 Exchange 系統管理員 audit log 中的記錄。 <br/>**2** -表示 Exchange 信箱 audit 記錄檔中對 singled 信箱專案執行的作業的記錄。 <br/>**3** -也指出 Exchange 信箱 audit log 中的記錄。 此記錄類型表示已對來源信箱中的多個專案執行作業 (例如, 將多個專案移至 [刪除的郵件] 資料夾, 或永久刪除多個專案)。 <br/>**4** -表示 SharePoint 中的網站管理員作業, 例如系統管理員或使用者指派許可權給網站。 <br/>**6** -表示 SharePoint 中的檔案或資料夾相關作業, 例如使用者查看或修改檔案。 <br/>**8** -指出在 Azure Active Directory 中執行的系統管理作業。 <br/>**9** -表示 Azure Active Directory 中的 OrgId 登入事件。 此記錄類型已被取代。 <br/>**10** -指出由 Microsoft 人員在資料中心執行的安全性 Cmdlet 事件。 <br/>**11** -指出 SharePoint 中的資料遺失保護 (DLP) 事件。<br/> **12** -表示 Sway 事件。 <br/>**13** -當使用統一的 DLP 原則設定時, 會指出 Exchange 中的 DLP 事件。 不支援以 Exchange 郵件流程規則 (也稱為傳輸規則) 為基礎的 DLP 事件。<br>**14** -表示 SharePoint 中的共用事件。<br/> **15** -表示 Azure Active Directory 中的安全權杖服務 (STS) 登入事件。 <br/>**18** -指出安全性 & 規範中心事件。 <br/>**20** -表示 Power BI 事件。 <br/>**21**-表示 Dynamics 365 事件。<br/>**22** -表示 Yammer 事件。 <br/>**23** -表示商務用 Skype 事件。 <br/>**24** -表示 eDiscovery 事件。 此記錄類型會指出在安全性與合規性中心執行內容搜尋及管理 eDiscovery 案例所執行的活動。 如需詳細資訊, 請參閱[在 Office 365 audit 記錄檔中搜尋 eDiscovery 活動](search-for-ediscovery-activities-in-the-audit-log.md)。<br/>**25、26或 27** -表示 Microsoft 小組事件。 <br/>**28** -指出來自 Exchange Online Protection 和 Office 365 Advanced 威脅防護事件的網路釣魚和惡意程式碼事件。<br/> **30** -表示 Microsoft 流程事件。<br/> **31** -表示高級 eDiscovery 事件。<br/> **32** -表示 Microsoft Stream 事件。<br/> **35** -表示 Microsoft Project 事件。 <br/> **36** -指出 SharePoint 清單事件。<br/> **38** -指出與安全性與合規性中心中的保留原則和保留標籤相關的事件。  <br/>**40** -指出安全性和合規性警示信號所產生的事件。<br/> **41** -指出 Office 365 Advanced 威脅防護中的安全連結封鎖時間和封鎖覆寫事件。<br/>**44** -表示工作場所分析事件。 <br/>**45** -表示 PowerApps 應用程式事件。 <br/> **47** -表示 SharePoint、OneDrive 及 Microsoft 小組檔案的 Office 365 高級威脅防護的網路釣魚和惡意程式碼事件。 <br/> **52** -指出與資料洞察力 REST API 相關的事件。<br/>**54** -指出 SharePoint 清單專案事件。<br/>**55** -指出 SharePoint 內容類型事件。
|ResultStatus|會指出動作 (在**Operation**屬性中指定) 是否成功。  <br/> 對於 Exchange 系統管理員活動, 此值為**True** (成功) 或**False** (失敗)。|全部  <br/>|
|SecurityComplianceCenterEventType|表示活動是 & 規範中心事件的安全性。 所有安全性 & 規範中心活動的值都是**0**的屬性。|安全規範中心|
|SharingType|指派給與資源分享之使用者的共用許可權類型。 此使用者是在**UserSharedWith**屬性中識別的。|SharePoint|
|網站|使用者所存取的檔案或資料夾所在之網站的 GUID。|SharePoint|
|SiteUrl|使用者所存取的檔案或資料夾所在之網站的 URL。|SharePoint|
|SourceFileExtension|使用者所存取之檔案的副檔名。 如果所存取的物件是資料夾, 則此屬性為空白。|SharePoint|
|SourceFileName|使用者所存取的檔案或資料夾名稱。|SharePoint|
|SourceRelativeUrl|資料夾的 URL, 該資料夾包含使用者所存取的檔案。 **SiteURL**、 **SourceRelativeURL**及**SourceFileName**屬性值的組合與**ObjectID**屬性的值相同, 後者是使用者存取之檔案的完整路徑名稱。.。|SharePoint|
|主旨|所存取之郵件的主旨行。|Exchange (信箱活動)|
|TabType| 在小組中新增、移除或更新的索引標籤類型。 此屬性可能的值為:  <br/><br/> **Excelpin** -Excel 索引標籤。  <br/> **分機**-所有第一方和協力廠商應用程式;例如 Planner、VSTS 和表單。  <br/> [**附注**-OneNote] 索引標籤。  <br/> **Pdfpin** -PDF 索引標籤。  <br/> **Powerbi** -powerbi 索引標籤。  <br/> **Powerpointpin** -PowerPoint 索引標籤。  <br/> **Sharepointfiles** -A SharePoint 索引標籤。  <br/> [**網頁**]-[固定的網站] 索引標籤。  <br/> **Wiki-** 索引標籤-[wiki] 索引標籤。  <br/> **WorDPIn** -[Word] 索引標籤。|Microsoft Teams|
|Target|執行動作 (在**Operation**屬性中識別) 的使用者。 例如, 如果將來賓使用者新增至 SharePoint 或 Microsoft 小組, 則該使用者將會列在此屬性中。|Azure Active Directory|
|TeamGuid|Microsoft 小組中的小組識別碼。|Microsoft Teams|
|TeamName|Microsoft 小組中的小組名稱。|Microsoft Teams|
|UserAgent|使用者瀏覽器的相關資訊。 此資訊是由瀏覽器所提供。|SharePoint|
|UserDomain|執行動作之使用者 (主角) 之租使用者組織的身分識別資訊。|Azure Active Directory|
|UserID|執行動作的使用者 (在**Operation**屬性中指定), 導致記錄正在記錄中。 請注意, 系統帳戶 (例如 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM) 所執行之活動的記錄也會包含在 audit 記錄檔中。|全部|
|UserKey|在**UserID**屬性中所識別之使用者的替代識別碼。 例如, 此屬性會填入使用者在 SharePoint 中執行之事件的 passport 唯一識別碼 (PUID)。 此屬性也可能會指定與其他服務中**** 發生的事件相同的值, 以及系統帳戶執行的事件。|全部|
|UserSharedWith|與資源分享的使用者。 如果**Operation**屬性的值為**SharingSet**, 則會包含此屬性。 此使用者也會列在報告中的 [**共用**欄位] 欄中。|SharePoint|
|UserType|執行作業的使用者類型。 下列值表示使用者類型。 <br/> <br/> **0** -一般使用者。 <br/>**2** -您的 Office 365 組織中的系統管理員。 <sup>一級</sup> <br/>**3** -Microsoft 資料中心管理員或資料中心系統帳戶。 <br/>**4** -系統帳戶。 <br/>**5** -應用程式。 <br/>**6** -A 服務主體。<br/>**7** -自訂原則。<br/>**8** -系統原則。|全部|
|版本|會指出已記錄之活動的版本號碼 (由**Operation**屬性識別)。|全部|
|工作量|發生活動的 Office 365 服務。 此屬性可能的值為:  <br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>合規<br/>性<br/>Sway 商務<br/>用 Skype<br/>SecurityComplianceCenter<br/>PowerBI CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>專案<br/>PowerApps<br/>工作區分析**|全部|
||||

> [!NOTE]
> <sup>1</sup>對於 Azure Active Directory 相關事件, 系統管理員的值不會用於審計記錄。 由系統管理員所執行之活動的審計記錄會指出一般使用者 (例如, **UserType: 0**) 會執行活動。 **UserID**屬性會識別執行活動的人員 (一般使用者或系統管理員)。

當您在查看特定事件的詳細資料時, 當您按一下 [**詳細資訊**] 時, 也會顯示上面所述的屬性。 
  
![按一下 [詳細資訊] 以查看 audit log 事件記錄的詳細屬性](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  
