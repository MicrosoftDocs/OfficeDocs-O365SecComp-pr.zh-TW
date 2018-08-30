---
title: 內容搜尋的關鍵字查詢和搜尋條件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: '了解您可以使用 Office 365 安全性內容搜尋工具商務網站的搜尋在 Exchange Online 信箱及 SharePoint 或 OneDrive 的電子郵件和檔案屬性&amp;規範中心。  '
ms.openlocfilehash: c043b6667e6847ff944b05e6bbe91df8ed2f600c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526911"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>內容搜尋的關鍵字查詢和搜尋條件

本主題說明您可以在 Exchange Online 與儲存在 SharePoint 文件中的電子郵件項目中搜尋的電子郵件和文件屬性及使用 Office 365 安全性內容的搜尋功能的網站 OneDrive for Business&amp;規範置中。您也可以使用**\*-ComplianceSearch**中安全性的指令程式&amp;規範中心 PowerShell 搜尋這些屬性。同時說明主題： 
  
- 使用布林搜尋運算子、 搜尋條件及其他搜尋查詢技術 （英文） 調整您的搜尋結果。
    
- 搜尋機密資料類型與 SharePoint 和 OneDrive for Business 中的自訂敏感資料類型。
    
- 搜尋網站內容的共用與組織外的使用者
    
如需如何建立內容的搜尋的逐步指示，請參閱[Office 365 中的內容搜尋](content-search.md)。 |

  
> [!NOTE]
> 內容搜尋安全性&amp;規範中心及對應**\*-ComplianceSearch**中安全性的指令程式&amp;規範中心 PowerShell 使用關鍵字查詢語言 (KQL)。如需詳細資訊，請參閱[關鍵字查詢語言語法參考 （英文）](https://go.microsoft.com/fwlink/?LinkId=269603)。 
  
## <a name="searchable-email-properties"></a>可搜尋的電子郵件屬性

下表列出使用中的安全性內容搜尋功能可搜尋的電子郵件內容&amp;規範中心或使用**新 ComplianceSearch**或**組 ComplianceSearch**指令程式。表格包含每個屬性並由範例傳回的搜尋結果的描述_屬性： 值_語法範例。您可以輸入這些`property:value`成對的關鍵字] 方塊的內容搜尋。 
  
|**屬性**|**屬性描述**|**範例**|**範例所傳回的搜尋結果**|
|:-----|:-----|:-----|:-----|
|AttachmentNames  <br/> |附加到電子郵件的檔案名稱。  <br/> |`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual\*`  <br/> |郵件包含一個名為 annualreport.ppt 的附件檔案。在第二個範例中，使用萬用字元會傳回在附件的檔案名稱中包含「annual」字詞的訊息。  <br/> |
|密件副本  <br/> |電子郵件訊息的 [密件副本] 欄位。<sup>1</sup> <br/> |`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`  <br/> |所有的範例會傳回包含在密件副本欄位中具有 Pilar Pinilla 的郵件。  <br/> |
|類別  <br/> | 要搜尋的類別。使用者可以使用 Outlook 或 Outlook Web App 定義類別。可能的值為：  <br/><br/>  藍色  <br/>  綠色  <br/>  橙色  <br/>  紫色  <br/>  紅色  <br/>  黃色  <br/> |`category:"Red Category"`  <br/> |來源信箱中已指派紅色類別的郵件。   <br/> |
|副本  <br/> |電子郵件訊息的 [副本] 欄位。<sup>1</sup> <br/> |`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`  <br/> |在這兩個範例中，具有在 [副本] 欄位中指定 Pilar Pinilla 的郵件。  <br/> |
|Folderid  <br/> |識別碼 (GUID) 特定信箱資料夾的資料夾。如果您使用此屬性，請務必搜尋指定的資料夾位於的信箱。請注意只有在指定的資料夾拼寫須符合。將不會搜尋的資料夾中的任何子資料夾。若要搜尋的子資料夾，您需要使用 Folderid 屬性針對您想要搜尋的子資料夾。<br/> 如需搜尋 Folderid 屬性以及如何使用指令碼來取得特定信箱的識別碼資料夾的詳細資訊，請參閱[使用 Office 365 中的目標集合的內容搜尋](use-content-search-for-targeted-collections.md)。  <br/> |`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`  <br/> |第一個範例會傳回指定的信箱資料夾中的所有項目。第二個範例會傳回已傳送或接收 garthf@contoso.com 所指定的信箱資料夾中的所有項目。  <br/> |
|寄件者  <br/> |電子郵件訊息的寄件者。<sup>1</sup> <br/> |`from:pilarp@contoso.com`  <br/> `from:contoso.com`  <br/> |指定的使用者或從指定的網域傳送的郵件。  <br/> |
|HasAttachment  <br/> |會指出將郵件具有附件。使用的值則為**true**或**false**。<br/> |`from:pilar@contoso.com AND hasattachment:true`  <br/> |所傳送的郵件指定的使用者具有附件。  <br/> |
|Importance  <br/> |電子郵件寄件者可以在傳送郵件時指定的重要性。根據預設，郵件是傳送使用標準的重要性，除非寄件者設定為**高**或**低**重要性。<br/> |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`  <br/> |標示為高重要性、中重要性或低重要性的郵件。  <br/> |
|IsRead  <br/> |會指出已讀取的郵件。使用的值則為**true**或**false**。<br/> |`isread:true`  <br/> `isread:false`  <br/> |第一個範例會傳回郵件並將 IsRead 屬性設定為**True**。第二個範例會傳回郵件 IsRead 屬性設定為**False**。<br/> |
|ItemClass  <br/> |使用這個屬性來搜尋您的組織匯入至 Office 365 的協力廠商的特定資料類型。這個屬性使用下列語法：`itemclass:ipm.externaldata.<third-party data type>*` <br/> |`itemclass:ipm.externaldata.Facebook\* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter\* AND from:"Ann Beebe" AND "Northwind Traders"`  <br/> |第一個範例會傳回包含單字的 Facebook 項目 「 contoso 」 主旨屬性中。第二個範例會傳回的當天的 Ann Beebe 且包含關鍵字文句"Northwind Traders 」 的 Twitter 項目。<br/> 如要使用的協力廠商資料類型 ItemClass 屬性的值的完整清單，請參閱[使用搜尋的已匯入 Office 365 的協力廠商資料的內容搜尋](use-content-search-to-search-third-party-data-that-was-imported.md)。  <br/> |
|類型  <br/> | 若要搜尋的電子郵件訊息的類型。可能的值：  <br/>  連絡人  <br/>  文件  <br/>  電子郵件  <br/>  externaldata  <br/>  傳真  <br/>  IM  <br/>  日誌  <br/>  會議  <br/>  microsoftteams （從聊天室、 會議及電話的 Microsoft 小組中傳回的項目）  <br/>  附註  <br/>  張貼  <br/>  rssfeeds  <br/>  工作  <br/>  語音信箱  <br/> |`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`  <br/> |第一個範例會傳回符合搜尋準則的電子郵件訊息。第二個範例會傳回電子郵件、 立即訊息交談和語音訊息符合搜尋準則。第三個範例會傳回已匯入 Office 365 中的信箱與協力廠商資料來源，例如 Twitter、 Facebook，以及 Jabber Cisco、 符合搜尋準則的項目。如需詳細資訊，請參閱[Office 365 中的封存與協力廠商資料](https://go.microsoft.com/fwlink/p/?linkid=716918)。<br/> |
|參與者  <br/> |電子郵件中所有的人員欄位；這些欄位為 [寄件者]、[收件者]、[副本] 及 [密件副本]。<sup>1</sup> <br/> |`participants:garthf@contoso.com`  <br/> `participants:contoso.com`  <br/> |garthf@contoso.com 所傳送或接收的郵件。第二個範例會傳回 contoso.com 網域中的使用者所傳送或接收的所有郵件。  <br/> |
|已收到  <br/> |收件者收到電子郵件的日期。  <br/> |`received:04/15/2016`  <br/> `received\>=01/01/2016 AND received\<=03/31/2016`  <br/> |2016 年 4 月 15, 所接收的郵件。第二個範例會傳回所有 2016 年 1 月 1，與 2016 年 3 月 31 之間收到的訊息。  <br/> |
|收件者  <br/> |電子郵件中所有的收件者欄位；這些欄位為 [收件者]、[副本] 及 [密件副本]。<sup>1</sup> <br/> |`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`  <br/> |傳送至 garthf@contoso.com 的郵件。第二個範例會傳回傳送至 contoso.com 網域中任何使用者的郵件。  <br/> |
|寄件日期  <br/> |寄件者傳送電子郵件的日期。  <br/> |`sent:07/01/2016`  <br/> `sent\>=06/01/2016 AND sent\<=07/01/2016`  <br/> |在特定日期傳送或指定的日期範圍內所傳送的郵件。  <br/> |
|大小  <br/> |項目的大小 (以位元組為單位)。  <br/> |`size\>26214400`  <br/> `size:1..1048567`  <br/> |郵件大於 25??MB。第二個範例會傳回介於 1 到 1,048,567 位元組 (1 MB) 的大小的郵件。  <br/> |
|主旨  <br/> |電子郵件的主旨行中的文字。  <br/> **附註：** 當您在查詢中使用 Subject 屬性時，???the 搜尋會傳回所有在其中的主旨行包含您要搜尋的文字的郵件。換句話說，查詢不會傳回僅有完全相符的郵件。例如，如果您搜尋`subject:"Quarterly Financials"`、 結果將會包含 「 Quarterly Financials 2018"之主旨的郵件。<br/> |`subject:"Quarterly Financials"`  <br/> `subject:northwind`  <br/> |包含片語"Quarterly Financials"的主旨行文字中的任何位置的郵件。第二個範例會傳回包含 word northwind 主旨行中的所有郵件。  <br/> |
|收件者  <br/> |電子郵件的 [收件者] 欄位。<sup>1</sup> <br/> |`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`  <br/> |所有範例會傳回在 [收件者:] 行中指定 Ann Beebe 的郵件。  <br/> |
   
> [!NOTE]
> <sup>1</sup>個收件者屬性的值，您可以使用電子郵件地址 （也稱為的*使用者主體名稱*或 UPN）、 顯示名稱或別名為指定的使用者。例如，您可以使用 annb@contoso.com、 annb、 或"Ann Beebe"來指定 Ann Beebe 的使用者。<br/><br/>搜尋任何收件者屬性 （From、 To、 [副本]、 [密件副本、 參與者及收件者） 的 Office 365 嘗試展開每位使用者的身分識別所要尋找 Azure Active Directory 中向上它們。 如果在 Azure Active Directory 中找到使用者，就會包含使用者的電子郵件地址 （或 UPN）、 別名、 顯示名稱以及 LegacyExchangeDN 擴充查詢。<br/><br/>例如，例如查詢`participants:ronnie@contoso.com`就會展開成`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`。

## <a name="searchable-site-properties"></a>可搜尋的網站屬性

下表列出的一些 SharePoint 與 OneDrive 商務屬性可以使用內容的搜尋功能安全性搜尋&amp;規範中心或使用**新 ComplianceSearch**或**設定 ComplianceSearch**指令程式。表格包含每個屬性並由範例傳回的搜尋結果的描述_屬性： 值_語法範例。 
  
可搜尋的 SharePoint 內容的完整清單，請參閱[編目及 managed 屬性在 SharePoint 中的概觀](https://go.microsoft.com/fwlink/p/?LinkId=331599)。可以搜尋標示 [**是]** **設定為可查詢**] 欄中的屬性。 
  
|**屬性**|**屬性描述**|**範例**|**範例所傳回的搜尋結果**|
|:-----|:-----|:-----|:-----|
|Author  <br/> |[作者] 欄位從 Office 文件可保存如果複製文件。例如，如果使用者建立文件和電子郵件它給其他人，然後將其上傳至 SharePoint 文件將仍保留原始作者。請務必使用這個屬性的使用者的顯示名稱。  <br/> |`author:"Garth Fort"`  <br/> |Garth Fort 所編寫的所有文件。  <br/> |
|ContentType  <br/> |項目，例如項目、 文件或視訊 SharePoint 內容類型。  <br/> |`contenttype:document`  <br/> |會傳回所有文件。  <br/> |
|建立日期  <br/> |項目建立的日期。  <br/> |`created\>=06/01/2016`  <br/> |建立在或 2016 年 6 月 1 之後, 的所有項目。  <br/> |
|CreatedBy  <br/> |建立或已上傳項目的人員。請務必使用這個屬性的使用者的顯示名稱。  <br/> |`createdby:"Garth Fort"`  <br/> |Garth Fort 所建立或上傳的所有項目。  <br/> |
|DetectedLanguage  <br/> |項目的語言。  <br/> |`detectedlanguage:english`  <br/> |英文版的所有項目。  <br/> |
|FileExtension  <br/> |檔案 ； 的副檔名例如 docx、 一、 pptx、 或 xlsx。  <br/> |`fileextension:xlsx`  <br/> |所有的 Excel 檔案 (Excel 2007 與更新版本)  <br/> |
|FileName  <br/> |檔案的名稱。  <br/> |`filename:"marketing plan"`  <br/> `filename:estimate`  <br/> |第一個範例會傳回在標題中具有精準字詞「marketing plan」的檔案。第二個範例會傳回檔案名稱中具有「estimate」字詞的檔案。  <br/> |
|LastModifiedTime  <br/> |項目上次變更日期。  <br/> |`lastmodifiedtime\>=05/01/2016`  <br/> `lastmodifiedtime\>=05/10/2016 AND lastmodifiedtime\<=06/1/2016`  <br/> |第一個範例會傳回在或之後 2016 年 5 月 1，已變更的項目。第二個範例會傳回 2016 年 5 月 1，與 2016 年 6 月 1、 之間變更的項目。  <br/> |
|ModifiedBy  <br/> |上次變更項目的人員。請務必使用這個屬性的使用者的顯示名稱。  <br/> |`modifiedby:"Garth Fort"`  <br/> |上次由 Garth Fort 變更的所有項目。  <br/> |
|路徑  <br/> |在 SharePoint 或 OneDrive 商務網站的特定的資料夾路徑 (URL)。如果您使用此屬性，請務必在指定的資料夾位於網站中搜尋。<br/> 若要傳回在您為 path 屬性所指定資料夾的子資料夾中的項目，您必須新增 /\*至指定的資料夾的 URL例如， `path: https://contoso.sharepoint.com/Shared Documents/*`。  <br/> <br/> **附註：** 使用`Path`搜尋 OneDrive 位置屬性不會傳回搜尋結果中的媒體檔案，例如.png、.tiff、 或使用的.wav 檔。使用搜尋查詢中的不同網站屬性來搜尋 OneDrive 資料夾中的媒體檔案。<br/> <br/> 如需搜尋的 Path 屬性以及如何使用指令碼來取得特定站台上的資料夾路徑 Url 的詳細資訊，請參閱[使用 Office 365 中的目標集合的內容搜尋](use-content-search-for-targeted-collections.md)。  <br/> |`path:https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/\*" AND filename:confidential`  <br/> |第一個範例會傳回指定之 OneDrive for Business 資料夾中的所有項目。第二個範例會傳回指定的網站] 資料夾 （和所有子資料夾） 中含有單字"confidential"檔案名稱] 中的文件。  <br/> |
|SharedWithUsersOWSUser  <br/> |指定的使用者與共用及顯示在使用者的 OneDrive for Business 網站**與我共用**] 頁面上的文件。這些是已明確指定的使用者藉由與共用其他人您組織中的文件。當您匯出符合搜尋查詢使用 SharedWithUsersOWSUser 屬性的文件時、 文件都要匯出從指定的使用者與共用的文件的人員原始內容的位置。如需詳細資訊，請參閱[您的組織內的搜尋網站內容的共用](keyword-queries-and-search-conditions.md#internal)。<br/> |`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`  <br/> |這兩個範例會傳回所有內部文件的已與阮建輝明確共用和會出現在阮建輝**與我共用**] 頁面上 OneDrive for Business 帳戶。  <br/> |
|網站  <br/> |網站的 URL 或組織中的網站群組。  <br/> |`site:https://contoso-my.sharepoint.com`  <br/> `site:https://contoso.sharepoint.com/sites/teams`  <br/> |第一個範例會從 OneDrive for Business 網站的組織中的所有使用者傳回的項目。第二個範例會傳回所有小組網站的項目。  <br/> |
|大小  <br/> |項目的大小 (以位元組為單位)。  <br/> |`size\>=1`  <br/> `size:1..10000`  <br/> |第一個範例會傳回大於 1 個位元組的項目。第二個範例會傳回 1 到 10,000 個位元組大小的項目。  <br/> |
|標題  <br/> |文件的標題。Title 屬性是在 Microsoft Office 文件中所指定的中繼資料。它是不同的文件的檔案名稱。  <br/> |`title:"communication plan"`  <br/> |Office 文件的 [標題] 中繼資料屬性中包含「communication plan」一詞的任何文件。  <br/> |
   
## <a name="searchable-contact-properties"></a>可搜尋連絡人屬性

下表列出的連絡人的內容編製索引及您可搜尋的使用內容搜尋。這些是可供使用者 （也稱為個人連絡人） 位於使用者信箱的個人通訊錄中的連絡人設定的屬性。若要搜尋連絡人，您可以選取的信箱搜尋，並再使用關鍵字查詢中的一或多個連絡人的屬性。
  
> [!TIP]
> 若要搜尋的值包含空格，請使用包含詞語; 雙引號 ("??")例如， `businessaddress:"123 Main Street"`。 
  
|**屬性**|**屬性描述**|
|:-----|:-----|
|BusinessAddress  <br/> |**商務地址**屬性中的位址。此屬性也稱為**公司**地址連絡人內容] 頁面上。<br/> |
|BusinessPhone  <br/> |在任何**商務電話**的電話號碼字屬性。  <br/> |
|CompanyName  <br/> |在 [**公司**] 屬性名稱。  <br/> |
|部門  <br/> |在 [**部門**] 屬性名稱。  <br/> |
|DisplayName  <br/> |連絡人的顯示名稱。這是在連絡人的**全名**屬性的名稱。<br/> |
|EmailAddress  <br/> |之任何連絡人的電子郵件地址屬性的地址。請注意使用者可以新增多個電子郵件地址的連絡人。使用此屬性會傳回符合任何連絡人的電子郵件地址的連絡人。  <br/> |
|FileAs  <br/> |**檔案做為**屬性。此屬性用來指定如何連絡人會列於使用者的連絡人清單中。例如，連絡人無法列為*FirstName、 LastName*或*LastName、 FirstName* 。<br/> |
|GivenName  <br/> |**名字**屬性中的名稱。  <br/> |
|HomeAddress  <br/> |**住家**地址屬性的任何地址。  <br/> |
|住家電話  <br/> |在任何的**住家**電話的電話號碼字屬性。  <br/> |
|IMAddress  <br/> |IM 位址屬性，通常是用於立即訊息的電子郵件地址。  <br/> |
|MiddleName  <br/> |**中間**的 name 屬性中的名稱。  <br/> |
|MobilePhone  <br/> |在**行動**電話的電話號碼字屬性。  <br/> |
|Nickname  <br/> |**暱稱**屬性中的名稱。  <br/> |
|OfficeLocation  <br/> |在 [ **Office** ] 或 [**辦公室位置**屬性值。  <br/> |
|OtherAddress  <br/> |**其他**地址屬性的值。  <br/> |
|Surname  <br/> |中**最後**的 name 屬性的名稱。  <br/> |
|Title  <br/> |**職稱**屬性中的標題。  <br/> |
   

## <a name="searchable-sensitive-data-types"></a>可搜尋的敏感資料類型

您可以使用 「 內容搜尋功能安全性&amp;規範中心來搜尋的機密資料，如信用卡號或社會安全號碼儲存文件中 SharePoint 和 OneDrive for Business 的網站。您可以這麼做使用`SensitiveType`屬性和敏感資訊的名稱輸入關鍵字查詢中。例如，查詢`SensitiveType:"Credit Card Number"`會傳回含有信用卡號的文件。查詢`SensitiveType:"U.S. Social Security Number (SSN)"`傳回包含美國社會安全號碼的文件。若要查看可搜尋的機密資料類型的清單，請移至**分類**\>中安全性的**敏感資訊類型**&amp;規範中心。您也可以使用**Get DlpSensitiveInformationType** cmdlet 安全性&amp;規範中心 PowerShell 將顯示的敏感資訊類型清單。 
  
您也可以使用`SensitiveType`屬性來搜尋您 （或另一個系統管理員） 為組織建立自訂的敏感資訊類型的名稱。請注意您可以在安全性**敏感資訊類型**] 頁面上使用 [ **Publisher** ] 欄&amp;區分內建及自訂機密規範中心 （或 PowerShell 中的**Publisher**屬性）資訊類型。如需詳細資訊，請參閱[建立自訂的敏感資訊類型](create-a-custom-sensitive-information-type.md)。
  
如需關於使用建立查詢`SensitiveType`屬性，請參閱[表單來尋找機密資料儲存在網站上的查詢](form-a-query-to-find-sensitive-data-stored-on-sites.md)。
  
## <a name="search-operators"></a>搜尋運算子

布林搜尋運算子，例如**AND** **OR**，且**不**會協助您包括或排除特定字詞的搜尋查詢中所定義更精確的搜尋。其他技術，例如使用屬性運算子 (例如\>= 或。。 {3})、 引號括號，且萬用字元，協助您調整搜尋查詢。下表列出您可以使用縮小或擴大搜尋結果的運算子。 
  
|**運算子**|**Usage**|**描述**|
|:-----|:-----|:-----|
|AND  <br/> |keyword1 AND keyword2  <br/> |會傳回內含指定的關鍵字的所有項目或`property:value`運算式。例如，`from:"Ann Beebe" AND subject:northwind`會傳回所有包含主旨行中的 word northwind Ann Beebe 所傳送的郵件。<sup>2</sup> <br/> |
|+  <br/> |keyword1??+ keyword2??+ keyword3  <br/> |會傳回包含*一個*項目，`keyword2`或`keyword3`*和*也包含`keyword1`。因此，此範例會相當於查詢`(keyword2 OR keyword3) AND keyword1`。  <br/> 請注意，查詢`keyword1 + keyword2`(之後空白**+** 符號) 不是使用相同 * * AND * * 運算子。此查詢就是相當於`"keyword1 + keyword2"`並傳回 「 實際 」 階段的項目`"keyword1 + keyword2"`。<br/> |
|OR  <br/> |keyword1 OR keyword2  <br/> |會傳回包含一或多個指定關鍵字的項目或`property:value`運算式。<sup>2</sup> <br/> |
|NOT  <br/> |keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> Im 不種類：  <br/> |排除關鍵字所指定的項目或`property:value`運算式。在第二個範例會排除 Ann Beebe 所傳送的郵件。第三個範例會排除任何立即訊息交談，例如 Skype 商務儲存至交談記錄的信箱資料夾的交談。<sup>2</sup> <br/> |
|-  <br/> |keyword1 -keyword2  <br/> |相同**不**運算子。因此這個查詢會傳回包含的項目`keyword1`會排除包含的項目和`keyword2`。<br/> |
|NEAR  <br/> |keyword1 NEAR(n) keyword2  <br/> |傳回與彼此、 相近的單字的項目其中 n 等於字數分開。例如，`best NEAR(5) worst`會傳回任何項目單字"百分比顯示"所在內的"最佳"的五個字。如果未不指定任何數字，則預設距離是八個單字。<sup>2</sup> <br/> |
|ONEAR  <br/> |keyword1 ONEAR(n) keyword2  <br/> |類似**附近**，但傳回的項目中指定的順序靠近彼此的單字。例如，`best ONEAR(5) worst`會傳回其中的字"適合使用 「 發生"最糟"字詞前面且兩個文字內的其他每五個字的任何項目。如果未不指定任何數字，則預設距離是八個單字。<sup>2</sup> <br/> > [!NOTE]> 搜尋信箱; 時不支援將**ONEAR**運算子僅適用於搜尋 SharePoint 和 OneDrive for Business 的網站時。如果您在相同的搜尋中搜尋信箱和網站及查詢包含**ONEAR**運算子，搜尋會傳回信箱項目如果當您使用**NEAR**運算子。換句話說，搜尋未傳回項目之指定的文字的彼此附近不論發生之文字的順序。           |
|:  <br/> |property:value  <br/> |冒號 （:） 中的`property:value`語法會指定要搜尋的屬性的值包含指定的值。例如，`recipients:garthf@contoso.com`傳回傳送至 garthf@contoso.com 任何訊息。<br/> |
|=  <br/> |property=value  <br/> |相同 **:** 運算子。  <br/> |
|\<  <br/> |屬性\<值  <br/> |代表所搜尋的屬性小於指定的值。 <sup>1</sup> <br/> |
|\>  <br/> |屬性\>值  <br/> |代表所搜尋的屬性大於指定的值。<sup>1</sup> <br/> |
|\<=  <br/> |屬性\<= 值  <br/> |代表所搜尋的屬性小於或等於指定的值。<sup>1</sup> <br/> |
|\>=  <br/> |屬性\>= 值  <br/> |代表所搜尋的屬性大於或等於指定的值。<sup>1</sup> <br/> |
|..  <br/> |屬性： value1.value2  <br/> |代表所搜尋的屬性大於或等於 value1 且小於或等於 value2。<sup>1</sup> <br/> |
|"  "  <br/> |"fair value"  <br/> 主旨:"Quarterly Financials"  <br/> |使用雙引號 ("") 搜尋精確對應字詞或字詞關鍵字和`property:value`搜尋查詢。  <br/> |
|\*  <br/> |cat\*  <br/> 主旨： 設定\*  <br/> |前置詞萬用字元搜尋 （星號放置一個字結尾處） 符合零或多個關鍵字中的字元或`property:value`查詢。例如，`title:set*`傳回含有字組、 設定和設定 （與其他 「 設定 」 的開頭的字） 的文件中的文件標題。<br/><br/> **附註：** 您可以使用僅限前置詞萬用字元搜尋 ；例如， **cat\*** 或**設定\***。尾碼搜尋 ( ** \*cat** )、 中置搜尋 ( **c\*t** )，以及子字串搜尋 ( ** \*cat\* ** ) 不受支援。           |
|(  )  <br/> | (fair OR free) AND (from:contoso.com)  <br/>  (IPO OR initial) AND (stock OR shares)  <br/>  (quarterly financials)  <br/> |括弧括住群組在一起布林片語`property:value`項目和關鍵字。例如，`(quarterly financials)`會傳回包含每季文字的項目及 financials。<br/> |
   
> [!NOTE]
> <sup>1</sup>??????Use 此運算子具有日期或數字值的屬性。> <sup>2</sup>??????Boolean 搜尋運算子必須為大寫;例如， **AND**。如果您使用小寫的運算子，例如**和**，它會視為在搜尋查詢關鍵字。 
  
## <a name="search-conditions"></a>新增條件

您可以新增條件，將搜尋縮小並傳回結果集更精簡的搜尋查詢。每個條件將子句新增至 KQL 搜尋查詢，建立及執行當您啟動搜尋。
  
[一般屬性的條件 ](#conditions-for-common-properties)

[郵件屬性的條件](#conditions-for-mail-properties)

[文件屬性的條件](#conditions-for-document-properties)

[與條件搭配使用的運算子](#operators-used-with-conditions)

[使用條件的指導方針](#guidelines-for-using-conditions)

[範例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>一般屬性的條件 

建立使用通用屬性相同的搜尋中搜尋信箱和網站時的條件。下表列出可用來新增條件時使用的屬性。
  
|**條件**|**描述**|
|:-----|:-----|
|日期  <br/> |電子郵件、 已接收到收件者或寄件者所傳送郵件的日期。文件、 文件的上次修改的日期。  <br/> |
|寄件者/撰寫者  <br/> |電子郵件傳送訊息的人員。文件的 Office 文件從 [作者] 欄位中所引用的人員。您可以輸入多個名稱，用逗號隔開。兩個或多個值以邏輯方式連線**或**接線生。<br/> |
|大小 （位元組）  <br/> |針對電子郵件和文件，為項目的大小 (以位元組計)。  <br/> |
|主旨/標題  <br/> |電子郵件之郵件的主旨行中的文字。文件、 文件的標題。如先前所述的標題屬性是 Microsoft Office 文件中所指定的中繼資料。您可以輸入多個主題/標題、 以逗號分隔的名稱。兩個或多個值以邏輯方式連線**或**接線生。<br/> |
|合規性標籤  <br/> |電子郵件和文件，且已指派給郵件和文件自動標籤原則或標籤的標籤已手動指派使用者。標籤可用來分類電子郵件和文件資料管理和強制執行保留標籤所定義的分類為基礎的規則。您可以輸入部分標籤名稱和使用萬用字元或輸入完整的標籤名稱。如需詳細資訊，請參閱 ＜ [Overview of Office 365 中的標籤](labels.md)。<br/> |
  
### <a name="conditions-for-mail-properties"></a>郵件屬性的條件

搜尋信箱或公用資料夾時使用電子郵件屬性來建立條件。下表列出您可以用於條件的電子郵件屬性。請注意，這些屬性是先前所說明的電子郵件屬性的子集；會重複這些說明以方便您使用。
  
|**條件**|**描述**|
|:-----|:-----|
|訊息類型  <br/> | 要搜尋的郵件類型。這是 Kind email 屬性為相同的屬性。可能的值：  <br/><br/>  連絡人  <br/>  文件  <br/>  電子郵件  <br/>  externaldata  <br/>  傳真  <br/>  IM  <br/>  日誌  <br/>  會議  <br/>  microsoftteams  <br/>  附註  <br/>  張貼  <br/>  rssfeeds  <br/>  工作  <br/>  語音信箱  <br/> |
|參與者  <br/> |電子郵件中所有的人員欄位；這些欄位為 [寄件者]、[收件者]、[副本] 及 [密件副本]。  <br/> |
|類型  <br/> |電子郵件項目的訊息類別屬性。這是 ItemClass email 屬性為相同的屬性。它也是多重值條件。因此，若要選取多個郵件類別，按住**CTRL**鍵並再按您想要新增至條件下拉式清單中的兩個或多個郵件類別。選取清單中每個郵件類別將會以邏輯方式連接所對應的搜尋查詢中的**OR**運算子。<br/> 如需 Exchange 及所使用的郵件類別 （和其對應的郵件類別識別） 清單您可以在**郵件類別**清單中選取，請參閱[項目類型和郵件類別](https://go.microsoft.com/fwlink/?linkid=848143)。  <br/> |
|已收到  <br/> |收件者收到電子郵件的日期。這是與 [收到日期] 電子郵件屬性相同的屬性。  <br/> |
|收件者  <br/> |若要傳送之人員的電子郵件。這是 To 電子郵件屬性為相同的屬性。  <br/> |
|寄件者  <br/> |電子郵件訊息的寄件者。  <br/> |
|寄件日期  <br/> |寄件者傳送的電子郵件的日期。這是傳送電子郵件屬性相同的屬性。  <br/> |
|主旨  <br/> |電子郵件的主旨行中的文字。  <br/> |
|收件者  <br/> |電子郵件收件者。  <br/> |
  
### <a name="conditions-for-document-properties"></a>文件屬性的條件

建立搜尋上 SharePoint 和 OneDrive for Business 的網站的文件時使用文件屬性的條件。下表列出您可以使用情況的文件屬性。請注意這些屬性的子集先前所述的 ； 網站屬性為方便您使用重複這些描述。
  
|**條件**|**描述**|
|:-----|:-----|
|Author  <br/> |[作者] 欄位從 Office 文件可保存如果複製文件。例如，如果使用者建立文件和電子郵件它給其他人，然後將其上傳至 SharePoint 文件將仍保留原始作者。  <br/> |
|Title  <br/> |文件的標題。Title 屬性是在 Office 文件中所指定的中繼資料。它會不同於文件的檔案名稱。  <br/> |
|建立日期  <br/> |建立文件的日期。  <br/> |
|上次修改日期  <br/> |上次變更文件的日期。  <br/> |
|檔案類型  <br/> |檔案 ； 的副檔名例如 docx、 一、 pptx、 或 xlsx。這是做為 FileExtension site 屬性為相同的屬性。  <br/> |
  
### <a name="operators-used-with-conditions"></a>與條件搭配使用的運算子

當您新增條件時，您可以選取與條件的屬性類型相關的運算子。下表會描述搭配條件使用的運算子，並列出搜尋查詢中所使用的對等用法。
  
|**運算子**|**查詢對等用法**|**描述**|
|:-----|:-----|:-----|
|之後  <br/> |`property\>date`  <br/> |與日期條件搭配使用。傳回指定日期之後所傳送、接收或修改的項目。   <br/> |
|之前  <br/> |`property\<date`  <br/> |與日期條件搭配使用。傳回指定日期之前所傳送、接收或修改的項目。  <br/> |
|介於  <br/> |`date..date`  <br/> |使用未含日期及大小的條件。日期條件搭配使用時，傳回的項目那里已傳送、 接收到，或修改指定的日期範圍內。大小條件搭配使用時，會傳回其大小是在指定範圍內的項目。  <br/> |
|包含任何  <br/> |`(property:value) OR (property:value)`  <br/> |搭配條件為指定的字串值的屬性。會傳回包含一或多個指定的字串任何的值部分的項目。  <br/> |
|不包含任何  <br/> |`-property:value`  <br/> `NOT property:value`  <br/> |與指定字串值的屬性條件搭配使用。傳回不包含一或多個指定字串值任何部分的項目。  <br/> |
|不等於任何
  <br/> |`-property=value`  <br/> `NOT property=value`  <br/> |與指定字串值的屬性條件搭配使用。傳回不包含指定字串的項目。  <br/> |
|等於  <br/> |`size=value`  <br/> |傳回與指定大小相等的項目。<sup>1</sup> <br/> |
|等於任何  <br/> |`(property=value) OR (property=value)`  <br/> |與指定字串值的屬性條件搭配使用。傳回與一或多個指定值完全相符的項目。  <br/> |
|大於  <br/> |`size>value`  <br/> |傳回指定屬性大於指定值的項目。<sup>1</sup> <br/> |
|大於或等於  <br/> |`size>=value`  <br/> |傳回指定屬性大於或等於指定值的項目。<sup>1</sup> <br/> |
|小於  <br/> |`size<value`  <br/> |傳回大於或等於特定值的項目。<sup>1</sup> <br/> |
|小於或等於  <br/> |`size<=value`  <br/> |傳回大於或等於特定值的項目。<sup>1</sup> <br/> |
|不等於  <br/> |`size<>value`  <br/> | 傳回與指定大小不相等的項目。<sup>1</sup> <br/> |
   
> [!NOTE]
> <sup>1</sup>此運算子是僅供使用 Size 屬性的條件。 
  
### <a name="guidelines-for-using-conditions"></a>使用條件的指導方針

使用搜尋條件時，請務必記住下列幾點。
  
- 條件是以邏輯方式連線到 （在 [關鍵字] 方塊中指定） 的關鍵字查詢**和**運算子。這表示項目必須滿足的關鍵字查詢與結果中包含的條件。這是條件，縮減結果協助的方式。 
    
- 如果您將兩個或多個唯一的條件新增至搜尋查詢 （指定不同的屬性的條件） 時，這些條件就必定連線所**AND**運算子。這表示會傳回只滿足 （除了任何關鍵字查詢） 的所有條件的項目。 
    
- 若您要新增多個條件的相同的屬性，這些條件就必定連線**或**接線生。這表示會傳回符合關鍵字查詢及任何一項條件的項目。如此，相同的條件群組給對方連接所連接的**OR**運算子，然後**和**接線生連線設定的唯一條件。 
    
- 如果您將多個值 （以逗號或分號分隔） 新增至單一條件時，這些值是透過**OR**運算子連接。這表示如果它們包含任何指定之條件中屬性的值會傳回的項目。 
    
- 使用關鍵字] 方塊與條件來建立搜尋查詢會顯示在 [**搜尋**] 頁面選取搜尋的詳細資料窗格中。在右邊的標記法的每個項目查詢`(c:c)`表示加入至查詢的條件。 
    
- 條件只能將屬性新增至搜尋查詢;不要為首行新增運算子。這就是為什麼詳細資料窗格中顯示的查詢不會顯示右邊的運算子`(c:c)`註解。KQL 新增邏輯運算子 （根據先前所述的規則） 時執行查詢。 
    
- 您可以使用拖曳並捨棄控制項重新排序條件的順序。只要按一下條件的控制項上並將它移向上或向下。
    
- 如先前所述的部分條件屬性可讓您輸入多個值。每個值以邏輯方式是透過**OR**運算子連接。這會產生相同的邏輯為具有多個執行個體的相同的條件，其中每一個都位於單一值。下圖顯示含有多個值的單一條件的範例和多個條件 （適用於相同的屬性） 的單一值的範例。這兩個範例會導致相同查詢：`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![具有多個值的一個條件](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![相同屬性的多重搜尋條件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 如果條件接受多個值，則我們建議您使用單一條件，並指定多個值 (以逗號或分號分隔)。這有助於確保所套用的查詢邏輯為您所想要的。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>範例

下列範例顯示 GUI 型版本與條件，會顯示所選的搜尋 （這也由**Get ComplianceSearch**指令程式所傳回） 的詳細資料窗格中的搜尋查詢語法的搜尋查詢和邏輯對應 KQL 查詢。 
  
#### <a name="example-1"></a>範例 1

本範例會傳回包含信用卡號且已上次修改日期早於 2016 年 1 月 1、 商務網站的 SharePoint 和 OneDrive 的文件。
  
 **GUI**
  
![搜尋條件的第一個範例](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **搜尋查詢語法**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **搜尋查詢邏輯**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>範例 2

本範例傳回包含關鍵字「report」的電子郵件項目或文件，這些項目或文件是在 2015 年 4 月1 日以前傳送或建立，且在電子郵件的主旨欄位或文件的標題屬性中包含「northwind」一字。查詢會排除符合其他搜尋準則的網頁。 
  
 **GUI**
  
![搜尋條件的第二個範例](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **搜尋查詢語法**
  
 `report???(c:c)??????(date<2016-04-01)??????(subjecttitle:"northwind")??????(-filetype="aspx")???`
  
 **搜尋查詢邏輯**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>範例 3
<a name="conditionexamples"> </a>

本範例會傳回電子郵件或行事曆會議的 12/1/2016年與 11/30/2016年之間傳送且包含"電話"或"smartphone"開頭的單字。
  
 **GUI**
  
![搜尋條件的第三個範例](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **搜尋查詢語法**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **搜尋查詢邏輯**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>搜尋與外部使用者共用的網站內容

您也可以使用 「 內容搜尋功能安全性&amp;規範中心來搜尋儲存在 SharePoint 和 OneDrive 已與組織外的人共用的商務網站的文件。這可協助您識別共用您組織外部的敏感或機密資訊。您可以這麼做使用`ViewableByExternalUsers`關鍵字查詢中的屬性。這個屬性會傳回已使用其中一種共用方法共用與外部使用者的網站或文件： 
  
- 需要使用者在登入經驗證使用者組織共用邀請。
    
- 可讓具有此連結無須來驗證存取資源的任何人匿名來賓連結。
    
以下為一些範例：
  
- 查詢`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`會傳回已與組織外部人員共用且包含信用卡號的所有項目。 
    
- 查詢`ViewableByExternalUsers:true AND ContentType:document AND Site:https://contoso.sharepoint.com/Sites/Teams`會傳回所有在組織中已與外部使用者共用的小組網站上的文件的清單。 
    
> [!TIP]
> 例如在搜尋查詢`ViewableByExternalUsers:true AND ContentType:document`可能會傳回許多.aspx 檔案的搜尋結果中。若要避免這些 （或其他類型的檔案），您可以使用`FileExtension`排除特定檔案類型的屬性例如`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`。 
  
什麼是被視為與組織外部人員共用的內容？在您的組織 SharePoint 和 OneDrive 文件的商務網站的共用的傳送共用邀請或在公用位置中的共用。例如，下列的使用者活動會導致外部使用者可檢視的內容：
  
- 使用者會與您組織外部的人員共用檔案或資料夾。

    
- 使用者會建立並將連結傳送給組織外部人員共用檔案。此連結可讓外部使用者可以檢視 （或編輯） 檔案。
    
- 使用者會傳送共用邀請或來賓連結給組織外部的人員以檢視 (或編輯) 共用的檔案。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>問題使用 ViewableByExternalUsers 屬性

雖然`ViewableByExternalUsers`屬性代表的狀態是否與外部使用者共用文件或網站、 有一些至這個屬性的沒有出現警告和 doesn???t 反映。在下列情況下的值`ViewableByExternalUsers`屬性將不會更新，並使用此屬性的內容的搜尋查詢的結果可能不正確。 
  
- 共用原則，例如關閉外部共用網站或組織的變更。屬性仍會顯示為要從外部存取即使外部存取已被撤銷先前的共用文件。
    
- 變更群組的成員資格，如新增或移除 Office 365 群組或 Office 365 安全性群組的外部使用者。屬性將不會自動進行更新群組有權存取的項目。
    
- 傳送的共用邀請外部使用者收件者所在尚未接受邀請中，與因此尚不具有內容的存取權。
    
在下列情況下，`ViewableByExternalUsers`屬性不會反映目前的共用狀態之前的網站或文件庫重新編目，且重新編製索引。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>搜尋共用您的組織內的網站內容

如先前所述，您可以使用`SharedWithUsersOWSUser`屬性讓搜尋的具備已在組織中的人員之間共用的文件。當人員與貴組織內的其他使用者共用的檔案 （或資料夾） 時、 共用檔案連結會出現在 OneDrive for Business 帳戶的檔案已與共用的人**與我共用**] 頁面上。例如，若要搜尋被 Sara Davis 與共用的文件，您可以使用查詢`SharedWithUsersOWSUser:"sarad@contoso.com"`。如果您匯出此搜尋結果時，將會下載 （位於與 Sara 共享文件的人員的內容位置） 的原始文件。
  
請注意必須與特定使用者使用時要在搜尋結果中傳回明確共用文件`SharedWithUsersOWSUser`屬性。例如時人員共用其 OneDrive 帳戶中的文件，擁有與任何人 （組織內外） 共用、 共用只能與組織內的人員或其與特定人員共用選項。以下是顯示的三個共用選項的 onedrive 的 [**共用**] 視窗的螢幕擷取畫面。 
  
![與特定的人共用的唯一檔案將會傳回由 searcj 查詢使用 SharedWithUsersOWSUser 屬性](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
僅使用 （與**特定的人**共用） 的第三個選項共用的文件會使用搜尋查詢所傳回`SharedWithUsersOWSUser`屬性。 

## <a name="search-tips-and-tricks"></a>搜尋秘訣與技巧

- 關鍵字搜尋不區分大小寫。例如，**cat** 和 **CAT** 得到的結果一樣。  
    
- 布林值運算元**AND**、**或**、**不**、 **NEAR**及**ONEAR**必須大寫。 
    
- 兩個關鍵字或兩個之間有空格`property:value`運算式會使用**與**相同。例如，`from:"Sara Davis" subject:reorganization`會傳回所有所傳送的郵件 Sara Davis 包含主旨行中的 word 重組。 
    
- 使用比對的語法`property:value`格式。值不區分大小寫，以及它們不能有空格之後運算子。如果有空格、 預定的值將只是全文檢索搜尋。例如`to: pilarp`搜尋的"pilarp"為關鍵字，而不是以 pilarp 所傳送的郵件。 
    
- 當您搜尋收件者屬性時 (例如 To、From、Cc 或 Recipients)，可以使用 SMTP 地址、別名或顯示名稱以代表收件者。例如，您可以使用 pilarp@contoso.com、pilarp 或「Pilar Pinilla」。
    
- 您可以使用僅限前置詞萬用字元搜尋 ；例如， **cat\*** 或**設定\***。尾碼搜尋 ( ** \*cat** )、 中置搜尋 ( **c\*t** )，以及子字串搜尋 ( ** \*cat\* ** ) 不受支援。 
    
- 搜尋屬性、 時使用雙引號 ("") 如果搜尋的值包含多個單字。例如`subject:budget Q1`會傳回包含**預算**中的郵件的主旨行且包含**Q1**無所不在郵件或中的任何郵件屬性。使用`subject:"budget Q1"`會傳回包含**預算 Q1**主旨行中的任何位置的所有郵件。 
    
- 若要排除標示為具有特定屬性值從搜尋結果的內容，放置減號 （-） 屬性的名稱之前。例如，`-from:"Sara Davis"`就會排除任何 Sara Davis 所傳送的郵件。 
