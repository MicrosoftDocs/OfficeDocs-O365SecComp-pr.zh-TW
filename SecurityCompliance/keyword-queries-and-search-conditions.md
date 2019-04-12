---
title: 內容搜尋的關鍵字查詢和搜尋條件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: '您可以搜尋在 Exchange Online 信箱，並在 SharePoint 或 OneDrive for Business 網站使用內容搜尋工具安全性 & 合規性中心中了解電子郵件和文件屬性。  '
ms.openlocfilehash: bb8c8090f8439bbd08b9c153b332c30d78ced8c8
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31814164"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>內容搜尋的關鍵字查詢和搜尋條件

本主題說明您可以在 Exchange Online 和儲存在 SharePoint 和 OneDrive for Business 網站的安全性 & 合規性中心中使用 「 內容搜尋 」 功能的文件中的電子郵件項目中搜尋的電子郵件和文件屬性。 您也可以使用**\*-ComplianceSearch**安全性 & 來搜尋這些屬性的合規性中心 PowerShell 中的指令程式。 主題亦說明：   
  
- 使用布林搜尋運算子、 搜尋條件，以及其他搜尋查詢技術來縮小搜尋結果。
    
- 正在搜尋的敏感資料類型與 SharePoint 和商務用 OneDrive 中的自訂的敏感資料類型。
    
- 搜尋與組織外的使用者共用的網站內容
    
如需如何建立內容搜尋的逐步指示，請參閱 <<c0>在 Office 365 中的內容搜尋。

  
> [!NOTE]
> 內容搜尋中安全性 & 規範中心和對應的**\*-ComplianceSearch**安全性 & 合規性中心 PowerShell 中的指令程式使用關鍵字查詢語言 (KQL)。 如需詳細資訊，請參閱[關鍵字查詢語言語法參照](https://go.microsoft.com/fwlink/?LinkId=269603)。 
  
## <a name="searchable-email-properties"></a>可搜尋的電子郵件屬性

下表列出使用中的安全性 & 合規性中心的內容搜尋功能，或使用**New-compliancesearch**或**Set-compliancesearch** cmdlet 可搜尋的電子郵件內容。 該表格包含的每個屬性，以及說明範例所傳回的搜尋結果的_屬性： value_語法範例。 您可以輸入這些`property:value`內容搜尋方塊中的關鍵字組。 
  
|**Property**|**屬性描述**|**範例**|**在範例中所傳回的搜尋結果**|
|:-----|:-----|:-----|:-----|
|AttachmentNames|附加到電子郵件訊息的檔案名稱。|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*`|具有的附加的檔案的郵件名為 annualreport.ppt。 在第二個範例中，使用萬用字元會傳回郵件的字 「 年 」 中的附件檔案名稱。|
|密件副本|電子郵件的密件副本] 欄位。<sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|所有範例會都傳回具有 [密件副本] 欄位中包含的 Pilar Pinilla 的郵件。|
|類別| 若要搜尋類別。 類別可以由使用者所定義，使用 Outlook 或網頁 （原先稱為 Outlook Web App）。 可能的值如下：  <br/><br/>  藍  <br/>  綠色  <br/>  橙色  <br/>  紫色  <br/>  紅色  <br/>  黃色|`category:"Red Category"`|已指派紅色類別之來源信箱中的郵件。|
|副本|電子郵件 [副本] 欄位。<sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|在這兩個範例中，[副本] 欄位中指定 Pilar Pinilla 的郵件。|
|Folderid|資料夾識別碼 (GUID) 的特定信箱資料夾中。 如果您使用此屬性，請務必搜尋指定的資料夾位於信箱。 請注意，只有指定的資料夾可供搜尋。 無法搜尋的資料夾中的任何子資料夾。 若要搜尋的子資料夾，您需要針對您想要搜尋的子資料夾使用 Folderid 屬性。  <br/> 如需搜尋 Folderid 屬性以及如何使用指令碼來取得特定信箱的資料夾識別碼的詳細資訊，請參閱 <<c0>對目標集合的 Office 365 中使用內容搜尋。|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|第一個範例會傳回指定的信箱資料夾中的所有項目。 第二個範例傳回所有項目中的指定的信箱資料夾，已傳送或接收的garthf@contoso.com。|
|寄件者|電子郵件的寄件者。<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|郵件寄件者指定的使用者，或寄件者指定的網域。|
|HasAttachment|會指出郵件具有附件。 使用值 **，則為 true**或**false**。|`from:pilar@contoso.com AND hasattachment:true`|寄件者指定的使用者有附件的郵件。|
|Importance|電子郵件，這會傳送郵件時，可以指定寄件者的重要性。 根據預設，郵件會傳送與普通重要性，除非寄件者設定為**高重要性**或**低**重要性。|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|標示為高重要性、 中重要性或低重要性的郵件。|
|IsRead|會指出已讀取郵件。 使用值 **，則為 true**或**false**。|`isread:true`  <br/> `isread:false`|第一個範例會傳回郵件 IsRead 屬性設定為**True**。 第二個範例會傳回郵件與 IsRead 屬性設定為**False**。|
|ItemClass|使用這個屬性可搜尋您的組織匯入至 Office 365 的特定協力廠商資料類型。 此屬性使用下列語法：  `itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|第一個範例會傳回包含單字的 Facebook 項目 「 contoso 」 Subject 屬性。 第二個範例會傳回所 Ann Beebe 已張貼的且包含關鍵字片語 「 Northwind Traders 」 的 Twitter 項目。  <br/> 若要使用的協力廠商資料類型的 ItemClass 屬性的值的完整清單，請參閱[使用內容搜尋 」 來搜尋協力廠商資料匯入的 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)。|
|類型| 若要搜尋的電子郵件訊息的類型。 可能的值：  <br/>  連絡人  <br/>  文件  <br/>  email  <br/>  externaldata  <br/>  傳真  <br/>  im  <br/>  日誌  <br/>  會議  <br/>  microsoftteams （從聊天、 會議及 Microsoft Teams 中的呼叫會傳回的項目）  <br/>  備忘稿  <br/>  文章  <br/>  rssfeeds  <br/>  工作  <br/>  語音信箱|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|第一個範例會傳回符合搜尋準則的電子郵件訊息。 第二個範例會傳回電子郵件、 立即訊息交談 （包括 Skype 商務交談和 Microsoft Teams 中的聊天室） 和語音訊息符合搜尋準則。 第三個範例會傳回已匯入 Office 365 中的信箱從協力廠商資料來源，例如 Twitter、 Facebook 和 Cisco Jabber，符合搜尋準則的項目。 如需詳細資訊，請參閱[Office 365 中的封存協力廠商資料](https://go.microsoft.com/fwlink/p/?linkid=716918)。|
|參與者|電子郵件; 中的所有人員欄位這些欄位為、 To、 [副本] 及 [密件副本]。<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|郵件所傳送或是傳送至garthf@contoso.com。 第二個範例會傳回所有郵件所傳送或傳送給 contoso.com 網域中的使用者。|
|Received|收件者收到電子郵件的日期。|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|2016 年 4 月 15 日所收到的郵件。 第二個範例會傳回 2016 年 1 月 1 日和 2016 年 3 月 31 日之間接收到的所有郵件。|
|收件者|電子郵件; 中的所有收件者欄位這些欄位是以 [副本] 及 [密件副本]。<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|若要傳送的郵件garthf@contoso.com。 第二個範例會傳回傳送給 contoso.com 網域中任何收件者的郵件。|
|寄件日期|寄件者傳送電子郵件的日期。|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|已在指定日期傳送或指定的日期範圍內所傳送的郵件。|
|大小|項目，以位元組為單位的大小。|`size>26214400`  <br/> `size:1..1048567`|大於 25 的郵件？MB。 第二個範例會傳回介於 1 到 1,048,567 位元組 (1 MB) 的大小的郵件。|
|主旨|電子郵件訊息的主旨行中的文字。  <br/> **附註：** 當您在查詢中使用 Subject 屬性時，???the 搜尋會傳回所有郵件的主旨行中包含您要搜尋的文字。 換句話說，查詢不會傳回已完全符合這些郵件。 例如，如果您搜尋`subject:"Quarterly Financials"`，您的結果會包含郵件主旨為 「 Quarterly Financials 2018 」。|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|包含字詞"Quarterly Financials"的主旨行文字中的任何位置的郵件。 第二個範例會傳回包含 word northwind 主旨行中的所有郵件。|
|收件者|電子郵件訊息的 [到] 欄位。<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|所有範例會都傳回郵件中指定 Ann Beebe 的地方： 線條。|
   
> [!NOTE]
> <sup>1</sup>的收件者屬性的值，您可以使用電子郵件地址 （也稱為的*使用者主體名稱*或 UPN）、 顯示名稱或若要指定使用者的別名。 例如，您可以使用annb@contoso.com，annb，或若要指定使用者 Ann Beebe 的"Ann Beebe"。<br/><br/>搜尋任何時 （From、 To、 [副本]、 [密件副本、 參與者及收件者） 的收件者屬性，Office 365 會嘗試展開每位使用者的身分識別所要尋找 Azure Active Directory 中設定它們。  如果使用者在 Azure Active Directory 中找到，查詢就會展開成包含使用者的電子郵件地址 （或 UPN）、 別名、 顯示名稱，以及 LegacyExchangeDN。<br/><br/>例如，例如查詢`participants:ronnie@contoso.com`就會展開成`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`。

## <a name="searchable-site-properties"></a>可搜尋的網站屬性

下表列出部分 SharePoint 和 OneDrive 使用安全性 & 合規性中心中的內容搜尋功能，或使用**New-compliancesearch**或**Set-compliancesearch 可搜尋的商務屬性**指令程式。 該表格包含的每個屬性，以及說明範例所傳回的搜尋結果的_屬性： value_語法範例。 
  
可搜尋的 SharePoint 內容的完整清單，請參閱[Overview of 編目及 managed properties in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599)。 可搜尋的屬性**是****設定為可查詢**] 欄中標示。 
  
|**Property**|**屬性描述**|**範例**|**在範例中所傳回的搜尋結果**|
|:-----|:-----|:-----|:-----|
|作者|[作者] 欄位從 Office 文件，可保存如果複製文件。 例如，如果使用者建立文件和電子郵件至其他人然後將它上傳至 SharePoint 文件仍會保留原始作者。 請務必使用這個屬性的使用者的顯示名稱。|`author:"Garth Fort"`|Garth Fort 所編寫的所有文件。|
|ContentType|項目，例如項目、 文件或視訊 SharePoint 內容類型。|`contenttype:document`|會傳回所有文件。|
|建立時間|建立項目的日期。|`created\>=06/01/2016`|建立或 2016 年 6 月 1 日之後的所有項目。|
|CreatedBy|建立或上傳項目的人員。 請務必使用這個屬性的使用者的顯示名稱。|`createdby:"Garth Fort"`|建立或 Garth Fort 所上傳的所有項目。|
|DetectedLanguage|項目的語言。|`detectedlanguage:english`|英文版的所有項目。|
|DocumentLink|在 SharePoint 或 OneDrive for Business 網站特定的資料夾路徑 (URL)。 如果您使用此屬性，請務必搜尋指定的資料夾位於站台。  <br/> 若要傳回位於您為 documentlink 屬性指定的資料夾的子資料夾中的項目，您必須新增 /\*在指定的資料夾; 的 url例如，  `documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>如需搜尋 documentlink 屬性以及如何使用指令碼來取得特定站台上的資料夾的 documentlink Url 的詳細資訊，請參閱 <<c0>對目標集合的 Office 365 中使用內容搜尋。|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|第一個範例會傳回所有項目中指定之商務用 OneDrive 資料夾。 第二個範例會傳回指定的站台資料夾 （和所有子資料夾） 中含有單字"confidential"的檔案名稱中的文件。|
|FileExtension|檔案; 的副檔名例如，docx、 一個、 pptx 或 xlsx。|`fileextension:xlsx`|所有的 Excel 檔案 (Excel 2007 及更新版本)|
|FileName|檔案的名稱。|`filename:"marketing plan"`  <br/> `filename:estimate`|第一個範例會傳回與精準字詞 「 行銷計劃 」 的檔案，標題中。 第二個範例會傳回與 word 檔案 「 評估 」 中的檔案名稱。|
|LastModifiedTime|上次變更項目的日期。|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|第一個範例會傳回已變更或 2016 5 月 1 日之後的項目。 第二個範例傳回 2016 5 月 1 日和 2016 年 6 月 1 日之間變更的項目。|
|ModifiedBy|上次變更項目的人員。 請務必使用這個屬性的使用者的顯示名稱。|`modifiedby:"Garth Fort"`|上次由 Garth Fort 變更的所有項目。|
|路徑|在 SharePoint 或 OneDrive for Business 網站特定的網站路徑 (URL)。  <br/> 若要傳回位於指定路徑屬性站台中的資料夾中的項目，您必須新增 /\*以指定的網站; 的 URL例如，  `path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **附註：** 使用`Path`來搜尋 OneDrive 位置的屬性不會傳回媒體檔案，例如.png、.tiff 或.wav 檔案，在搜尋結果中。 不同的站台屬性用於搜尋查詢中搜尋的 OneDrive 資料夾中的媒體檔案。 <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|第一個範例會傳回所有項目中指定的 OneDrive for Business 網站。 第二個範例會傳回指定的網站 （和網站中的資料夾） 中含有單字"confidential"的檔案名稱中的文件。|
|SharedWithUsersOWSUser|以指定的使用者共用並顯示在使用者的 OneDrive for Business 網站的 **「 與我共用 」** 頁面上的文件。 這些是已明確與共用所指定的使用者由其他人在組織中的文件。 當您匯出符合搜尋查詢使用 SharedWithUsersOWSUser 屬性的文件時，會匯出文件內容的原始位置，以指定的使用者共用文件的人員。 如需詳細資訊，請參閱[組織內共用的網站內容的搜尋](#searching-for-site-content-shared-within-your-organization)。|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|這兩個範例會傳回所有內部文件，必須與 Garth Fort 明確地共用且 Garth Fort [**與我共用**] 頁面上顯示商務用 OneDrive 帳戶。|
|網站|站台或群組的組織中的網站的 URL。|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|第一個範例會從 OneDrive for Business 網站的所有使用者在組織中傳回項目。 第二個範例會從所有小組網站中傳回項目。|
|大小|項目，以位元組為單位的大小。|`size>=1`  <br/> `size:1..10000`|第一個範例會傳回大於 1 個位元組的項目。 第二個範例會傳回介於 1 到 10000 位元組大小的項目。|
|Title|文件的標題。 Title 屬性是 Microsoft Office 文件中所指定的中繼資料。 它是不同的文件的檔案名稱。|`title:"communication plan"`|在 Office 文件的標題的中繼資料屬性中含有片語 「 communication plan 」 任何文件。|
   
## <a name="searchable-contact-properties"></a>可搜尋的連絡人內容

下表列出連絡人的內容編製索引，您可以使用內容搜尋的搜尋。 這些是信箱的可供使用者個人通訊錄的使用者都位於連絡人 （也稱為個人連絡人） 設定的屬性。 若要搜尋的連絡人，您可以選取的信箱搜尋，然後使用關鍵字查詢中的 [一或多個連絡人的內容。
  
> [!TIP]
> 若要搜尋的值包含空格或特殊字元，請使用雙引號 ("") 包含片語;例如， `businessaddress:"123 Main Street"`。 
  
|**Property**|**屬性描述**|
|:-----|:-----|
|BusinessAddress|**商務地址**屬性中的地址。 **公司**地址也被呼叫屬性連絡人的內容] 頁面上。|
|BusinessPhone|在任何**商務電話**的電話號碼的數字的屬性。|
|CompanyName|[**公司**] 內容中的名稱。|
|部門|[**部門**] 內容中的名稱。|
|DisplayName|連絡人的顯示名稱。 這是該連絡人的**完整名稱**屬性中的名稱。|
|EmailAddress|連絡人的任何電子郵件地址屬性的地址。 請注意，使用者可以新增多個電子郵件地址的連絡人。 使用此屬性會傳回符合任何連絡人的電子郵件地址的連絡人。|
|FileAs|[**歸檔為**] 屬性。 此屬性用來指定如何將該連絡人列出在使用者的連絡人清單中。 例如，連絡人可以列為*名字、 姓氏*或*LastName、 FirstName* 。|
|GivenName|[**名字**] 屬性中的名稱。|
|HomeAddress|**住家**地址屬性的任何地址。|
|住家電話|在任何的**住家**電話的電話號碼的數字屬性。|
|IMAddress|IM 位址屬性，通常是用於立即訊息的電子郵件地址。|
|MiddleName|**中間**的 name 屬性中的名稱。|
|MobilePhone|在 [**行動**電話的電話號碼的數字屬性。|
|暱稱|**Nickname**屬性中的名稱。|
|OfficeLocation|在 [ **Office** ] 或 [**辦公室地點**] 屬性值。|
|OtherAddress|**其他**地址屬性的值。|
|姓氏|**Last** name 屬性中的名稱。|
|Title|[**職稱**] 屬性中的標題。|
   

## <a name="searchable-sensitive-data-types"></a>可搜尋的敏感資料類型

若要搜尋的敏感資料，例如信用卡號碼或身分證號碼，會儲存在 SharePoint 和 OneDrive for Business 網站的文件中，您可以使用安全性與合規性中心中的內容搜尋功能。 您可以使用`SensitiveType`關鍵字查詢中輸入的屬性和敏感資訊的名稱。 例如，查詢`SensitiveType:"Credit Card Number"`會傳回包含信用卡卡號的文件。 查詢`SensitiveType:"U.S. Social Security Number (SSN)"`會傳回包含美國社會安全號碼的文件。 若要查看您可以搜尋的敏感資料類型的清單，請移至 **[分類]** \>安全性 & 合規性中心中的**敏感資訊類型**。 或者，您可以在安全性 & 合規性中心 PowerShell 中使用**Get-dlpsensitiveinformationtype 來**cmdlet，來顯示清單中的敏感資訊類型。 
  
您也可以使用`SensitiveType`屬性來搜尋您 （或另一個系統管理員） 為組織建立自訂機密資訊類型的名稱。 請注意，您可以使用以區別安全 & 合規性中心 （或 PowerShell 中的 [ **Publisher** ] 屬性） 中的**敏感資訊類型**] 頁面上的 [ **Publisher** ] 欄之間內建及自訂的敏感資訊類型。 如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)。
  
如需有關使用建立查詢`SensitiveType`屬性，請參閱[形成查詢以搜尋儲存在網站上的敏感資料](form-a-query-to-find-sensitive-data-stored-on-sites.md)。

> [!NOTE]
> 您不能使用的敏感資料類型和`SensitiveType`搜尋來搜尋的敏感資料待用 Exchange Online 信箱中的屬性。 不過，您可以使用資料外洩防護 (DLP) 原則來保護傳輸中的機密 emaill 資料。 如需詳細資訊，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)及[搜尋及尋找個人資料](search-for-and-find-personal-data.md)。
  
## <a name="search-operators"></a>搜尋運算子

布林搜尋運算子，例如**AND**、 **OR**和**不**，幫助您藉由包括或排除特定字詞的搜尋查詢定義更精確的搜尋。 其他技術，例如使用屬性運算子 (例如： \>= 或..)、 引號、 括號和萬用字元，協助您縮小搜尋查詢。 下表列出您可以使用逐漸變窄，或以擴大搜尋結果的運算子。 
  
|**運算子**|**Usage**|**描述**|
|:-----|:-----|:-----|
|AND|keyword1 AND keyword2|會傳回內含指定的關鍵字的所有項目或`property:value`運算式。 例如，`from:"Ann Beebe" AND subject:northwind`會傳回包含主旨行中的 word northwind Ann Beebe 所傳送的所有郵件。 <sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|會傳回包含 *[* 項目`keyword2`或`keyword3`*和*也包含`keyword1`。   因此，本範例會相當於查詢`(keyword2 OR keyword3) AND keyword1`。  <br/> 請注意，查詢`keyword1 + keyword2`(與後面的間距**+** 符號) 不是使用相同 * * 及 * * 運算子。 此查詢就會相當於`"keyword1 + keyword2"`，並傳回的確切階段的項目`"keyword1 + keyword2"`。|
|或|keyword1 OR keyword2|會傳回包含一或多個指定關鍵字的項目或`property:value`運算式。 <sup>2</sup>|
|NOT|keyword1 不 keyword2  <br/> 而不是由:"Ann Beebe"  <br/> 不類型： im|排除關鍵字所指定的項目或`property:value`運算式。 在 [第二個範例會排除 Ann Beebe 所傳送的郵件。 第三個範例會排除任何立即訊息對話，例如 Skype for Business 交談儲存在 [交談歷程記錄的信箱資料夾。 <sup>2</sup>|
|-|keyword1-keyword2|**不**運算子相同。 讓此查詢會傳回包含的項目`keyword1`及會排除項目包含`keyword2`。|
|NEAR|keyword1 NEAR(n) keyword2|傳回項目與彼此，相近的字其中 n = 字數遠。 例如，`best NEAR(5) worst`會傳回任何項目 」 最壞打算 」 這個字所在內的五個字的 「 最佳 」。 如果不指定任何數字，則預設距離為八個字。 <sup>2</sup>|
|ONEAR|keyword1 ONEAR(n) keyword2|類似於**附近**，但傳回與指定的順序是靠近彼此的字詞的項目。 例如，`best ONEAR(5) worst`會傳回其中 word 「 最佳 」，就會發生 「 最糟 」 一詞以前和兩個字都在彼此的五個文字範圍內的任何項目。 如果不指定任何數字，則預設距離為八個字。 <sup>2</sup> <br/> > [!NOTE]搜尋信箱; 時，不支援 > **ONEAR**運算子它只適用於搜尋 SharePoint 和 OneDrive for Business 網站時。 如果您在相同的搜尋中搜尋信箱和站台及查詢包含**ONEAR**運算子，搜尋會傳回信箱項目，因為如果您已使用**NEAR**運算子。 換句話說，搜尋作業沒有傳回項目中指定的文字是靠近彼此不論字發生的順序。|
|:|屬性值：|冒號 （:）在 [`property:value`語法會指定要搜尋的屬性的值包含指定的值。 例如，`recipients:garthf@contoso.com`會傳回任何訊息傳送到garthf@contoso.com。|
|=|屬性 = 值|: **:** 運算子相同。|
|\<|屬性\<值|代表所搜尋的屬性小於指定值。 <sup>1</sup>|
|\>|屬性\>值|代表所搜尋的屬性大於指定的值。<sup>1</sup>|
|\<=|屬性\<= 值|代表所搜尋的屬性小於或等於特定值。<sup>1</sup>|
|\>=|屬性\>= 值|代表所搜尋的屬性大於或等於特定值。<sup>1</sup>|
|..|屬性： value1..value2|代表所搜尋的屬性大於或等於 value1 且小於或等於 value2。<sup>1</sup>|
|"  "|「 普通值 」  <br/> subject:"Quarterly Financials"|使用雙引號 ("」) 若要搜尋的精準字詞或關鍵字中的字詞和`property:value`搜尋查詢。|
|\*|cat\*  <br/> 主旨： 設定\*|（星號放在文字的結尾） 的前置詞萬用字元搜尋符合關鍵字中的零個或多個字元或`property:value`查詢。 例如，`title:set*`會傳回包含 word 組、 設定和設定 （和其他與 「 設定 」 開頭的字） 的文件中的文件標題。  <br/><br/> **附註：** 您可以使用僅限前置詞萬用字元搜尋;例如， **cat\*** 或**設定\***。 尾碼搜尋 ( ** \*cat** ) 中, 置搜尋 ( **c\*t** )，以及子字串搜尋 ( ** \*cat\* ** ) 不支援。|
|(  )|（普通即表示可用）與 (from:contoso.com)  <br/> (初始 IPO OR)與 （股票或共用）  <br/> (quarterly financials)|括號群組在一起，則為 True 的片語，`property:value`項目，以及關鍵字。 例如，`(quarterly financials)`會傳回包含每季字詞的項目及 financials。|
   
> [!NOTE]
> <sup>1</sup>會使用此運算子具有日期或數值的屬性。<br/> <sup>2</sup> ，則為 True 的搜尋運算子必須大寫;例如， **AND**。 如果您使用小寫字母的運算子，例如**和**，它會視為搜尋查詢中的關鍵字。 
  
## <a name="search-conditions"></a>搜尋條件

您可以將條件新增至搜尋查詢以縮小搜尋範圍，並傳回更精細的結果集。 每個條件會將一個子句新增至 KQL 搜尋查詢，當您啟動搜尋時便會建立並執行。
  
[一般屬性的條件](#conditions-for-common-properties)

[郵件屬性的條件](#conditions-for-mail-properties)

[文件屬性的條件](#conditions-for-document-properties)

[與條件搭配使用的運算子](#operators-used-with-conditions)

[使用條件的指導方針](#guidelines-for-using-conditions)

[在搜尋查詢中使用條件的範例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>一般屬性的條件

建立在相同的搜尋中搜尋信箱和站台時，使用通用屬性的條件。 下表列出使用新增條件時可用的屬性。
  
|**條件**|**描述**|
|:-----|:-----|
|日期|電子郵件的日期已接收到收件者或寄件者所傳送。 對於文件，上次修改文件的日期。|
|寄件者/作者|寄送郵件人員的電子郵件。 對於文件，在 Office 文件中的 [作者] 欄位中所引用的人員。 您可以輸入多個名稱，以逗號隔開。 **OR**運算子會以邏輯方式連線兩個或多個值。|
|大小 （以位元組為單位）|電子郵件與文件的大小 （以位元組為單位） 的項目。|
|主旨/標題|電子郵件訊息的主旨行中的文字。 對於文件，文件的標題。 如先前所述，Title 屬性是 Microsoft Office 文件中指定的中繼資料。 您可以輸入多個主體/標題，以逗號隔開的名稱。 **OR**運算子會以邏輯方式連線兩個或多個值。|
|合規性標籤|電子郵件和文件的標籤已指派給郵件和文件會自動由標籤原則或標籤，已手動指派的使用者。 標籤用來分類電子郵件和文件的資料控管和強制執行的標籤所定義的分類為基礎的保留規則。 您可以輸入部分標籤名稱並使用萬用字元，或輸入完整標籤名稱。 如需詳細資訊，請參閱 < <b0>Overview of Office 365 中的標籤</b0>。|
  
### <a name="conditions-for-mail-properties"></a>郵件屬性的條件

建立搜尋信箱或公用資料夾時，使用電子郵件屬性的條件。 下表列出您可以使用條件的電子郵件屬性。 請注意，這些屬性先前所述; 電子郵件屬性的子集這些描述就會重複進行，方便您使用。
  
|**條件**|**描述**|
|:-----|:-----|
|訊息類型| 要搜尋的郵件類型。 這是做為類型的電子郵件屬性相同的屬性。 可能的值：  <br/><br/>  連絡人  <br/>  文件  <br/>  email  <br/>  externaldata  <br/>  傳真  <br/>  im  <br/>  日誌  <br/>  會議  <br/>  microsoftteams  <br/>  備忘稿  <br/>  文章  <br/>  rssfeeds  <br/>  工作  <br/>  語音信箱|
|參與者|電子郵件; 中的所有人員欄位這些欄位為、 To、 [副本] 及 [密件副本]。|
|Type|電子郵件項目的郵件類別屬性。 這是一樣的 ItemClass 電子郵件屬性的屬性。 它也是多重值條件。 因此，若要選取多個郵件類別，按住**CTRL**鍵，然後按一下 [您想要新增到條件的下拉式清單中的兩個或多個郵件類別。 在清單中選取每個郵件類別將會以邏輯方式連接所對應的搜尋查詢中的**OR**運算子。  <br/> 如需郵件類別 （和其對應的郵件類別識別碼） 的清單所使用的 Exchange，您可以選取**郵件類別**] 清單中，請參閱[項目類型和郵件類別](https://go.microsoft.com/fwlink/?linkid=848143)。|
|Received|收件者收到電子郵件的日期。 這是做為接收電子郵件屬性相同的屬性。|
|收件者|該人員的電子郵件已傳送至。 這是做為目的地電子郵件屬性相同的屬性。|
|寄件者|電子郵件的寄件者。|
|寄件日期|寄件者傳送電子郵件的日期。 這是做為已傳送電子郵件屬性相同的屬性。|
|主旨|電子郵件訊息的主旨行中的文字。|
|收件者|電子郵件的收件者。|
  
### <a name="conditions-for-document-properties"></a>文件屬性的條件

建立搜尋 SharePoint 和 OneDrive for Business 網站的文件時使用的文件屬性的條件。 下表列出您可以使用條件的文件屬性。 請注意，這些屬性先前所述，網站屬性的子集這些描述就會重複進行，方便您使用。
  
|**條件**|**描述**|
|:-----|:-----|
|作者|[作者] 欄位從 Office 文件，可保存如果複製文件。 例如，如果使用者建立文件和電子郵件至其他人然後將它上傳至 SharePoint 文件仍會保留原始作者。|
|Title|文件的標題。 Title 屬性是在 Office 文件中指定的中繼資料。 它是不同於文件的檔案名稱。|
|建立時間|建立文件的日期。|
|上次修改日期|上次變更文件的日期。|
|檔案類型|檔案; 的副檔名例如，docx、 一個、 pptx 或 xlsx。 這是做為 FileExtension 站台屬性相同的屬性。|
  
### <a name="operators-used-with-conditions"></a>與條件搭配使用的運算子

當您新增條件時，您可以選取運算子時相關的屬性的條件類型。 下表說明與條件搭配使用的運算子，並列出搜尋查詢中使用的對等。
  
|**運算子**|**查詢對等用法**|**描述**|
|:-----|:-----|:-----|
|之後|`property>date`|日期條件搭配使用。 傳回已傳送、 接收或修改所指定日期之後的項目。|
|之前|`property<date`|日期條件搭配使用。 傳回已傳送、 接收或所指定日期之前修改的項目。|
|之間|`date..date`|使用日期與大小條件。 日期條件搭配使用時，傳回的項目那里已傳送、 接收或修改指定的日期範圍內。 大小條件搭配使用時，傳回其大小是在指定範圍內的項目。|
|包含任何|`(property:value) OR (property:value)`|與指定的字串值的屬性的條件搭配使用。 會傳回包含一或多個指定的字串任何的值部分的項目。|
|不包含任何|`-property:value`  <br/> `NOT property:value`|與指定的字串值的屬性的條件搭配使用。 會傳回不含任何部分指定的字串值的項目。|
|不等於任何|`-property=value`  <br/> `NOT property=value`|與指定的字串值的屬性的條件搭配使用。 會傳回不含特定字串的項目。|
|等於|`size=value`|會傳回與指定大小相等的項目。<sup>1</sup>|
|等於任何|`(property=value) OR (property=value)`|與指定的字串值的屬性的條件搭配使用。 會傳回一或多個指定的字串值完全相符的項目。|
|大於|`size>value`|傳回指定的屬性大於指定值的項目。<sup>1</sup>|
|大於或等於|`size>=value`|傳回的項目指定的屬性大於或等於指定值。<sup>1</sup>|
|較少|`size<value`|會傳回大於或等於特定值的項目。<sup>1</sup>|
|小於或等於|`size<=value`|會傳回大於或等於特定值的項目。<sup>1</sup>|
|不等於|`size<>value`|會傳回不等於指定的大小的項目。<sup>1</sup>|
   
> [!NOTE]
> <sup>1</sup>此運算子是僅適用於使用 Size 屬性的條件。 
  
### <a name="guidelines-for-using-conditions"></a>使用條件的指導方針

使用搜尋條件時，請謹記下列。
  
- 條件會以 **AND** 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與條件。 這就是條件如何協助您縮小搜尋結果。 
    
- 如果您將兩個或多個唯一的條件新增至搜尋查詢 （指定不同的屬性的條件） 時，這些條件會以邏輯方式連線**AND**運算子。 這表示會傳回滿足 （除了之外的任何關鍵字查詢） 的所有條件的項目。 
    
- 如果您新增之相同屬性的多個條件，這些條件會以邏輯方式連線**OR**運算子。 這表示會傳回符合關鍵字查詢和任何一項條件的項目。 因此，群組相同條件的相互連接所連接的**OR**運算子，然後**AND**運算子來連線的唯一的條件。 
    
- 如果您將多個值 （以逗點或分號分隔） 新增至一個單一條件時，這些值**OR**運算子來連線。 這表示如果它們包含任何條件中屬性的指定值，會傳回項目。 
    
- 使用關鍵字] 方塊中，條件建立搜尋查詢會顯示在 [**搜尋**] 頁面上，選取搜尋詳細資料窗格中。 在查詢中，每個項目右邊的標記法`(c:c)`表示加入至查詢的條件。 
    
- 條件只能將屬性新增至搜尋查詢;不要加上運算子。 這就是為什麼詳細資料窗格中顯示查詢不會顯示右邊的運算子`(c:c)`表示法。 KQL 時新增邏輯運算子 （根據先前所述的規則） 執行查詢。 
    
- 您可以使用拖曳控制項拖重新排序條件的順序。 只要按一下之控制項的條件，並向上或向下移動它。
    
- 如先前所述，某些條件屬性可讓您可以輸入多個值。 每個值以邏輯方式是透過**OR**運算子連接。 這會導致相同的邏輯為具有多個執行個體的相同的條件，其中每個都有單一值。 下圖顯示單一條件與多個值的範例，以及 （適用於相同的屬性） 的多個條件與單一值的範例。 這兩個範例會導致相同的查詢：  `(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![郵件必須符合規則中的所有條件。如果您需要符合一個條件或另一個條件，請對每一個條件使用不同的規則。例如，如果要對附件和內容符合特定模式的郵件加入相同的免責聲明，請為每一個條件建立一個規則。您可以輕易地複製規則。](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![相同屬性的多重搜尋條件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 如果條件接受多個值，我們建議您使用單一條件，並指定多個值 （以逗點或分號分隔）。 這有助於確保套用的查詢邏輯是什麼打算。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>在搜尋查詢中使用條件的範例

下列範例會示範 GUI 型版本與條件，會顯示選取的搜尋 （這也會傳回**Get-compliancesearch** cmdlet） 的詳細資料窗格中的搜尋查詢語法的搜尋查詢和邏輯對應的 KQL 查詢。 
  
#### <a name="example-1"></a>範例 1

本範例會傳回文件上 SharePoint 和 OneDrive for Business 網站包含信用卡卡號且上次修改時間為 2016 年 1 月 1 日。
  
 **GUI**
  
![搜尋條件的第一個範例](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **搜尋查詢語法**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **搜尋查詢邏輯**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>範例 2

此範例會傳回電子郵件項目或文件包含關鍵字 「 報表 」 中，找出已傳送或建立之前 2105、 April 1，且包含 「 northwind"title 內容的文件或電子郵件的主旨欄位中的字。 查詢會排除符合其他搜尋準則的網頁。
  
 **GUI**
  
![搜尋條件的第二個範例](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **搜尋查詢語法**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **搜尋查詢邏輯**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>範例 3
<a name="conditionexamples"> </a>

此範例會傳回電子郵件或行事曆會議，2016 年 12 月 1 日和 2016 年 11 月 30 日之間所傳送且包含以 「 phone 」 或 「 smartphone 」 開頭的單字。
  
 **GUI**
  
![搜尋條件的第三個範例](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **搜尋查詢語法**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **搜尋查詢邏輯**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>搜尋與外部使用者共用的網站內容

您也可以使用安全性 & 合規性中心中的 「 內容搜尋 」 功能來搜尋儲存在 SharePoint 和 OneDrive for Business 網站已與組織外部人員共用的文件。 這可協助您識別共用組織外部的敏感或機密資訊。 您可以使用`ViewableByExternalUsers`關鍵字查詢中的屬性。 此屬性會傳回文件或已是使用下列其中一個下列共用方法與外部使用者共用的網站： 
  
- 需要使用者登入您的組織，以驗證的使用者共用邀請。
    
- 匿名來賓連結，可讓任何人使用此連結可以存取資源，而不必經過驗證。
    
以下為一些範例：
  
- 查詢`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`會傳回指與組織外部人員共用且含有信用卡號碼的所有項目。 
    
- 查詢`ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"`將會傳回所有組織中有已與外部使用者共用的小組網站上的文件清單。 
    
> [!TIP]
> 在搜尋查詢，例如`ViewableByExternalUsers:true AND ContentType:document`可能會在搜尋結果中傳回大量.aspx 檔案。 若要避免這些 （或其他類型的檔案），您可以使用`FileExtension`以排除特定的檔案類型; 屬性例如`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`。 
  
何謂與組織外部人員共用的內容？ 文件貴組織的 SharePoint 和 OneDrive for Business 網站的共用的傳送共用邀請或的在公用的位置中共用。 例如，下列的使用者活動會導致外部使用者可檢視的內容：
  
- 使用者與組織外部人員共用檔案或資料夾。
    
- 使用者會建立，並將連結傳送給組織外部人員共用檔案。 此連結可讓外部使用者檢視 （或編輯） 檔案。
    
- 使用者會傳送共用邀請或來賓連結給組織外部人員檢視 （或編輯） 共用的檔案。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>問題使用 ViewableByExternalUsers 屬性

雖然`ViewableByExternalUsers`屬性代表的狀態與外部使用者共用的是文件或網站，有一些警告到什麼這個屬性會以及不會反映。 在下列案例中，值`ViewableByExternalUsers`屬性不會更新，並使用此屬性的內容搜尋查詢的結果可能不正確。 
  
- 共用原則，例如關閉外部共用網站或組織的變更。 屬性仍會顯示為要從外部存取，即使外部存取已遭撤銷先前的共用文件。
    
- 群組成員資格，例如新增或移除 Office 365 群組或 Office 365 安全性群組的外部使用者的變更。 群組有權存取的項目時，不會自動更新屬性。
    
- 外部使用者收件者所在尚未接受邀請，並因此不會尚未傳送共用邀請可存取內容。
    
在這些案例中，`ViewableByExternalUsers`屬性不會反映目前的共用狀態，直到網站或文件庫重新編目和重新編製索引。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>搜尋共用組織內的網站內容

如先前所述，您可以使用`SharedWithUsersOWSUser`屬性讓搜尋的已是您組織中的人員之間共用的文件。 當某人與您的組織內的另一位使用者共用檔案 （或資料夾） 時，共用檔案連結會出現在商務用 OneDrive 帳戶的檔案共用的人員的 **「 與我共用 」** 頁面上。 例如，若要搜尋已與 Sara Davis 共用的文件，您可以使用查詢`SharedWithUsersOWSUser:"sarad@contoso.com"`。 如果您匯出的搜尋結果時，不會下載 （位於 Sara 與共用文件的人員的內容位置） 的原始文件。
  
請注意，必須與特定使用者使用時，搜尋結果中傳回明確地共用文件`SharedWithUsersOWSUser`屬性。 例如，當人員共用其 OneDrive 帳戶中的文件，它們會有任何人 （組織內部或外部） 與共用、 只與組織內的人員共用或與特定人員共用的選項。 以下是 OneDrive，會顯示三個共用選項中的 [**共用**] 視窗的螢幕擷取畫面。 
  
![搜尋查詢使用 SharedWithUsersOWSUser 屬性會傳回與特定人員共用的唯一檔案](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
會使用搜尋查詢所傳回只會使用第三個選項 （與**特定人員**共用） 共用的文件`SharedWithUsersOWSUser`屬性。 

## <a name="searching-for-skype-for-business-conversations"></a>Skype 商務交談的搜尋

您可以使用下列的關鍵字查詢特別搜尋中 Skype for Business 交談的內容：

```
kind:im
```

請注意舊的搜尋查詢也會傳回從 Microsoft Teams 的聊天室。 若要避免這種情況，您可以將縮小搜尋結果，以使用下列的關鍵字查詢包含 Skype 商務交談：

```
kind:im AND subject:conversation
```

先前的關鍵字查詢排除在 Microsoft Teams 中的聊天室，因為 Skype for Business 交談儲存為開頭的字 「 交談 」 [主旨] 行的電子郵件。

若要搜尋 skype 發生在特定日期範圍內的商務交談，請使用下列的關鍵字查詢：

```
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>搜尋秘訣與技巧

- 關鍵字搜尋不區分大小寫。 例如， **cat**和**CAT**會傳回相同的結果。 
    
- 布林運算子**AND**、**或**、**不**、 **NEAR**及**ONEAR**必須大寫。 
    
- 兩個關鍵字或兩者之間的空間`property:value`運算式是使用**與**相同。 例如，`from:"Sara Davis" subject:reorganization`會傳回所有所傳送的郵件 Sara Davis 包含主旨行中的 word 重組。 
    
- 使用比對的語法`property:value`格式。 值不區分大小寫，且他們不能有空格之後運算子。 如果沒有空間，您預定的值只會全文檢索搜尋。 例如`to: pilarp`搜尋的 「 pilarp"為關鍵字，而不是對郵件已傳送至 pilarp。 
    
- 當您搜尋收件者屬性，例如，從 [副本] 或 [收件者，您可以使用的 SMTP 地址別名，或顯示以註解收件者的名稱。 例如，您可以使用pilarp@contoso.com，pilarp，或 「 Pilar Pinilla 」。
    
- 您可以使用僅限前置詞萬用字元搜尋;例如， **cat\*** 或**設定\***。 尾碼搜尋 ( ** \*cat** ) 中, 置搜尋 ( **c\*t** )，以及子字串搜尋 ( ** \*cat\* ** ) 不支援。 
    
- 時搜尋的屬性，請使用雙引號 ("") 如果搜尋的值包含多個單字。 例如`subject:budget Q1`會傳回包含**預算**中的郵件在 [主旨] 行，包含**Q1**無所不在在郵件或任何訊息內容。 使用`subject:"budget Q1"`會傳回包含**預算 Q1**無所不在主旨行中的所有郵件。 
    
- 若要排除內容標示與您的搜尋結果中的特定屬性值，加上負號 （-） 之前屬性的名稱。 例如，`-from:"Sara Davis"`會排除任何 Sara Davis 所傳送的郵件。

- 某些特殊字元不包含在搜尋索引，因此不是可搜尋，包括搜尋運算子 （+-=:)和下列字元，或是取代由 $null 或導致錯誤，如果搜尋 ！ @ # %^ &;_ / ?

- 您可以匯出郵件類型為基礎的項目。 例如，若要匯出用 Skype 交談和 Microsoft Teams 中的聊天室，請使用語法`kind:im`。 若要傳回僅電子郵件，您可以使用`kind:email`。 若要傳回在 Microsoft Teams 中的聊天、 會議及電話，使用`kind:microsoftteams`。
