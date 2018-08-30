---
title: Office 365 稽核記錄中的詳細內容
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/8/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: 包含 Office 365 中的其他屬性的說明稽核記錄。
ms.openlocfilehash: 69c5565ac71715ba2cb22d93d80f7e5dd12c6440
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526799"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 稽核記錄中的詳細內容

當您將稽核記錄搜尋結果匯出的 Office 365 安全性&amp;規範中心已下載符合搜尋準則的所有結果的選項。您這麼做選取 [**匯出結果**\>安全性**稽核記錄搜尋**] 頁面上的 [**下載所有結果**&amp;規範中心。如需詳細資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。
  
 當您匯出所有產生的稽核記錄搜尋時、 整合的稽核記錄檔複製到逗點到 Office 365 中的原始資料區隔這會下載至您的本機電腦的值 (CSV) 檔案。這個檔案包含名為**詳細資料**] 欄中的稽核記錄項目中的其他資訊。此資料行包含多個屬性的稽核記錄的記錄從多重值屬性。每個成對此多重值屬性中的**屬性： 值**是以逗號分隔。 
  
下表說明所包含的屬性--根據 Office 365 服務中發生的事件 — 多屬性的**詳細資料**] 欄中。**具有此屬性的 Office 365 服務**] 欄會指出服務及活動 （使用者或系統管理員） 包含屬性的類型。有關這些屬性或屬性的可能不會列在本主題的詳細資訊，請參閱[Office 365 管理活動 API 結構描述](https://go.microsoft.com/fwlink/p/?LinkId=717993)。
  
> [!TIP]
> 您可以使用 Excel 中的 Power 查詢此資料行分割成多個資料欄，，讓每個屬性將有其專屬資料行。這可讓您排序及篩選一或多個這些屬性。了解如何執行這項作業，請參閱"分割資料行來分隔字元"一節中[分割資料行的文字 （進階查詢）](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)。 
  
|**屬性**|**描述**|**此屬性的 office 365 服務**|
|:-----|:-----|:-----|
|動作項目  <br/> |執行巨集指令的使用者或服務帳戶。 |Azure Active Directory  <br/> |
|AddOnName  <br/> |已新增、 移除或更新小組中附加元件的名稱。附加元件中的 Microsoft 小組的類型為 bot、 連接器或] 索引標籤。  <br/> |Microsoft Teams  <br/> |
|AddOnType  <br/> |已新增、 移除、 或小組中更新的附加元件的類型。下列的值會指出附加元件的類型。<br/> **1** -會指出 bot。<br/> **2** -會指出連接器。<br/> **3** -會指出索引標籤。 |Microsoft Teams  <br/> |
|AzureActiveDirectoryEventType  <br/> |Azure Active Directory 事件的類型。下列的值表示事件的類型。<br/> **0** -會指出帳戶登入事件。<br/> **1** -會指出 Azure 應用程式安全性事件。 |Azure Active Directory  <br/> |
|ChannelGuid  <br/> |Microsoft 小組通道的識別碼。通道位於 「 小組**TeamName**及**TeamGuid**屬性來識別。<br/> |Microsoft Teams  <br/> |
|ChannelName  <br/> |Microsoft 小組通道的名稱。通道位於 「 小組**TeamName**及**TeamGuid**屬性來識別。<br/> |Microsoft Teams  <br/> |
|用戶端  <br/> |用戶端裝置、 裝置 OS 及用於登入事件 (例如 Nokia Lumia 920 ； 裝置瀏覽器Windows Phone 8;IE Mobile 11)。  <br/> |Azure Active Directory  <br/> |
|ClientInfoString  <br/> |電子郵件用戶端用來執行此作業，例如瀏覽器版本、 Outlook 版本和行動裝置資訊的相關資訊  <br/> |Exchange （信箱活動）  <br/> |
|ClientIP  <br/> |活動已記錄時使用的裝置 IP 位址。IP 位址是 IPv4 或 IPv6 地址格式顯示。  <br/> |Exchange 和 Azure Active Directory  <br/> |
|ClientIPAddress  <br/> |ClientIP 相同。  <br/> |SharePoint  <br/> |
|CreationTime  <br/> |日期及時間的國際標準時間 (UTC) 使用者執行活動時。  <br/> |全部  <br/> |
|DestinationFileExtension  <br/> |檔案複製或移動的副檔名。此屬性僅適用於 FileCopied 和 FileMoved 使用者活動的顯示。  <br/> |SharePoint  <br/> |
|DestinationFileName  <br/> |複製或移動的檔案名稱。此屬性僅適用於 FileCopied 和 FileMoved 動作的顯示。  <br/> |SharePoint  <br/> |
|DestinationRelativeUrl  <br/> |其中檔案複製或移動的目的地資料夾的 URL。**SiteURL**、 **DestinationRelativeURL**，與**DestinationFileName**屬性值的組合是**ObjectID**屬性，亦即已複製的檔案完整路徑名稱的值相同。此屬性僅適用於 FileCopied 和 FileMoved 使用者活動的顯示。<br/> |SharePoint  <br/> |
|EventSource  <br/> |會識別事件發生在 SharePoint 中。可能的值為**SharePoint**和**ObjectModel**。<br/> |SharePoint  <br/> |
|ExternalAccess  <br/> |Exchange admin 活動，會指定是否在您的組織，由 Microsoft 資料中心人員或資料中心服務帳戶的使用者或委派的管理員執行此 cmdlet。**False**的值會指出此 cmdlet 所執行的組織中的某個人。**則為 True**的值會指出此 cmdlet 所執行的資料中心人員、 資料中心服務帳戶或委派的管理員。<br/> Exchange 信箱活動，會指定是否由組織外部使用者存取信箱。  <br/> |Exchange  <br/> |
|ExtendedProperties  <br/> |擴充的屬性如 Azure Active Directory 事件。  <br/> |Azure Active Directory  <br/> |
|ID  <br/> |報告項目的識別碼。識別碼可唯一識別報告項目。  <br/> |全部  <br/> |
|InternalLogonType  <br/> |保留供內部使用。  <br/> |Exchange （信箱活動）  <br/> |
|ItemType  <br/> |已存取或修改物件的類型。可能的值包括**檔案**、**資料夾**、**網頁**伺服器、**網站**、**租用戶**，與**DocumentLibrary**。<br/> |SharePoint  <br/> |
|LoginStatus  <br/> |識別可能發生的登入失敗。  <br/> |Azure Active Directory  <br/> |
|LogonType  <br/> |信箱存取類型。下列的值表示使用者存取之信箱的類型。<br/><br/> **0** -會指出信箱擁有者。<br/> **1** -表示以系統管理員。<br/> **2** -會指出代理人。 <br/>**3** -會指出 Microsoft 資料中心中的傳輸服務。<br/> **4** -ndicates Microsoft 資料中心的服務帳戶。 <br/>**6** -會指出委派的管理員。 |Exchange （信箱活動）  <br/> |
|MailboxGuid  <br/> |存取信箱之 Exchange GUID。  <br/> |Exchange （信箱活動）  <br/> |
|MailboxOwnerUPN  <br/> |擁有者存取信箱的之人員的電子郵件地址。  <br/> |Exchange （信箱活動）  <br/> |
|成員  <br/> |列出已新增或移除的小組的使用者。下列的值表示已指派給使用者的角色類型。<br/><br/> **1** -會指出擁有者 」 角色。<br/> **2** -會指出成員角色。<br/> **3** -會指出來賓角色。 <br/><br/>Members 屬性也會包含您的組織和成員的電子郵件地址的名稱。  <br/> |Microsoft Teams  <br/> |
|ModifiedProperties (名稱、 NewValue、 OldValue)  <br/> |屬性是供系統事件，例如將使用者新增為網站或網站集合管理員群組的成員。屬性包含 （例如 [網站管理] 群組） 已修改的屬性名稱新值已修改的屬性 （這類的使用者新增為網站管理員以及修改物件的先前值。  <br/> |所有 （admin 活動）  <br/> |
|ObjectID  <br/> |針對 Exchange 管理員稽核記錄功能，由 cmdlet 修改物件的名稱。  <br/> SharePoint 活動、 檔案或資料夾供使用者存取的完整 URL 路徑名稱。  <br/> 為 Azure AD 活動，如有修改的使用者帳戶的名稱。  <br/> |全部  <br/> |
|作業  <br/> |使用者或系統管理員活動的名稱。此屬性的值會對應至在**活動**中選定的值] 下拉式清單中。如果**顯示所有的活動的結果**所選取報表會包含所有服務的所有使用者和系統活動的項目。Office 365 稽核記錄檔中作業/活動的說明，請參閱**Audited 活動**] 索引標籤中的[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。<br/> Exchange admin 活動，這個屬性會識別上次執行此指令程式的名稱。  <br/> |全部  <br/> |
|OrganizationID  <br/> |Office 365 組織的 GUID。  <br/> |全部  <br/> |
|路徑  <br/> |存取訊息所在的信箱資料夾的名稱。此屬性也會識別位置的資料夾中建立或複製/移至郵件。  <br/> |Exchange （信箱活動）  <br/> |
|參數  <br/> |Exchange admin 活動、 名稱與使用中的 Operation 屬性識別指令程式所使用的所有參數的值。  <br/> |Exchange （admin 活動）  <br/> |
|RecordType  <br/> |指定記錄的作業類型。下列的值表示記錄類型。<br/><br/> **1** -會指出從 Exchange 管理員稽核記錄的記錄。 <br/>**2** -會指出來自挑信箱項目上執行作業的 Exchange 信箱稽核記錄的記錄。 <br/>**3** -還會指出從 Exchange 信箱稽核記錄的記錄。此記錄類型表示 （例如將多個項目移至 [刪除的郵件] 資料夾或是永久刪除多個項目） 的來源信箱中的多個項目上執行作業。<br/>**4** -會指出網站管理作業 sharepoint，例如系統管理員或使用者指派至網站的權限。 <br/>**6** -會指出檔案或資料夾相關的作業 sharepoint，例如使用者檢視或修改檔案。 <br/>**8** -會指出在 Azure Active Directory 中執行的系統作業。 <br/>**9** -會指出 OrgId Azure Active Directory 中的登入事件。是要取代這個記錄類型。<br/>**10** -會指出由 Microsoft 資料中心中的人員所執行的安全性指令程式事件。 <br/>第**11**位在 SharePoint 中指出的資料遺失防護 (DLP) 事件。<br/> **12** -會指出 Sway 事件。 <br/>**14** -會指出在 SharePoint 中的共用事件。<br/> **15** -Azure Active Directory 中的指示 Secure Token Service (STS) 登入事件。 <br/>**18** -會指出安全性&amp;規範中心事件。 <br/>**20** -會指出 Power BI 事件。 <br/>第**22** -會指出 Yammer 事件。 <br/>**24** -會指出 eDiscovery 事件。這個記錄類型會指出由執行內容的搜尋及管理安全性的 eDiscovery 案例所執行的活動&amp;規範中心。如需詳細資訊，請參閱 Search Office 365 中的 eDiscovery 活動的稽核記錄。<br/>**25、 26、 或 27** -會指出 Microsoft 小組事件。 |全部  <br/> |
|ResultStatus  <br/> |會指出動作 （**作業**屬性中所指定） 是否已成功。  <br/> Exchange admin 活動的值為**True** （成功） 或**False** （失敗）。  <br/> |全部  <br/> |
|SecurityComplianceCenterEventType  <br/> |會指出活動已安全性&amp;規範中心事件。所有安全性&amp;規範中心活動會有**0**這個屬性的值。<br/> |Office 365 安全性&amp;規範中心  <br/> |
|SharingType  <br/> |已指派給與已共用的資源之使用者的共用權限類型。**UserSharedWith**屬性中所識別此使用者。<br/> |SharePoint  <br/> |
|網站  <br/> |為檔案或資料夾存取使用者所在的網站 GUID。  <br/> |SharePoint  <br/> |
|SiteUrl  <br/> |為檔案或資料夾存取使用者所在的網站 URL。  <br/> |SharePoint  <br/> |
|SourceFileExtension  <br/> |使用者存取的檔案副檔名。此屬性是空白的存取物件時的資料夾。  <br/> |SharePoint  <br/> |
|SourceFileName  <br/> |為檔案或使用者存取的資料夾名稱。  <br/> |SharePoint  <br/> |
|SourceRelativeUrl  <br/> |包含使用者存取的檔案的資料夾的 URL。**SiteURL**、 **SourceRelativeURL**，與**SourceFileName**屬性值的組合是**ObjectID**屬性，亦即使用者存取的檔案完整路徑名稱的值相同。<br/> |SharePoint  <br/> |
|主旨  <br/> |存取郵件的主旨行。  <br/> |Exchange （信箱活動）  <br/> |
|TabType  <br/> | 新增、 移除或小組中更新] 索引標籤的類型。此屬性的可能值是：<br/><br/> **Excelpin** -Excel] 索引標籤。  <br/> **副檔名**所有的第一個廠商或協力廠商應用程式;例如規劃、 VSTS，與表單。  <br/> **備忘稿**-OneNote] 索引標籤。  <br/> **Pdfpin** -PDF] 索引標籤。  <br/> **Powerbi** -PowerBI] 索引標籤。  <br/> **Powerpointpin** -PowerPoint] 索引標籤。  <br/> **Sharepointfiles** -SharePoint] 索引標籤。  <br/> **Webpage** -pinned 的網站] 索引標籤。  <br/> **Wiki] 索引標籤**-wiki] 索引標籤。  <br/> **Wordpin** -Word 索引標籤。  <br/> |Microsoft Teams  <br/> |
|目標  <br/> |使用者上執行的巨集指令 （[**作業**] 屬性中所識別）。例如如果來賓使用者已新增到 SharePoint 或 Microsoft 小組，該使用者會列在此屬性。<br/> |Azure Active Directory  <br/> |
|TeamGuid  <br/> |小組中的 Microsoft 小組的識別碼。  <br/> |Microsoft Teams  <br/> |
|TeamName  <br/> |小組中的 Microsoft 小組名稱。  <br/> |Microsoft Teams  <br/> |
|UserAgent  <br/> |使用者的瀏覽器相關資訊。瀏覽器所提供的此資訊。  <br/> |SharePoint  <br/> |
|UserDomain  <br/> |用戶組織的使用者 （動作項目） 的身分識別資訊誰執行動作。  <br/> |Azure Active Directory  <br/> |
|UserID  <br/> |執行該詞彙所產生正在記錄一筆記錄的動作 （**作業**屬性中所指定） 之使用者。請注意系統帳戶 （例如 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM） 所執行的活動的記錄也會包含在稽核記錄檔。<br/> |全部  <br/> |
|UserKey  <br/> |**UserID**屬性中所識別之使用者的替代 ID。例如，這個屬性會填入事件執行在 SharePoint 中的使用者所擁有的 passport 唯一識別碼 (PUID)。此屬性也可能相同值指定為其他服務] 與 [系統帳戶所執行的事件中發生事件的**UserID**屬性。<br/> |全部  <br/> |
|UserSharedWith  <br/> |與已共用資源的使用者。如果此屬性為包含**作業**屬性的值是**SharingSet**。這位使用者也會列在報表中的 [**共用對象**] 欄中。<br/> |SharePoint  <br/> |
|UserType  <br/> |使用者執行作業的類型。下列的值會指出使用者類型。<br/> <br/> **0** -一般使用者。 <br/>**2** -Office 365 組織中系統管理員。 <br/>**3** -Microsoft 資料中心系統管理員或資料中心系統帳戶。 <br/>**4** -系統帳戶。 <br/>**5** -應用程式。 <br/>**6** -服務主要名稱。 |全部  <br/> |
|版本  <br/> |會指出活動 （**作業**屬性識別） 已登入的版本號碼。  <br/> |全部  <br/> |
|工作量  <br/> |Office 365 服務發生活動。此屬性的可能值是：<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>規範<br/>Sway<br/>SecurityComplianceCenter<br/>PowerBI<br/>MicrosoftTeams<br/>ThreatIntelligence**|全部  <br/> |
   
請注意，上述屬性也會顯示當您按一下檢視特定事件的詳細資料時的**詳細資訊**。 
  
![按一下 [檢視稽核記錄的事件記錄的詳細的屬性的詳細資訊](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

