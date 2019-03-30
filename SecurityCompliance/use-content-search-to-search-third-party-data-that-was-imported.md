---
title: 使用內容搜尋來搜尋協力廠商資料匯入至 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用內容搜尋電子文件探索工具來搜尋的項目都已從協力廠商資料來源匯入至 Office 365 中的信箱。 您可以建立查詢以搜尋所有匯入的項目，或是建立查詢以搜尋特定的協力廠商資料類型。 本文列出您可以使用關鍵字查詢來搜尋可匯入至 Office 365 的協力廠商資料類型的值。
ms.openlocfilehash: 361ead435d397464452c5b58ecf251a7322ced05
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999706"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>使用內容搜尋來搜尋協力廠商資料匯入至 Office 365

您可以使用安全性 & 合規性中心中的 「[內容搜尋電子文件探索工具](content-search.md)來搜尋協力廠商資料來源匯入至 Office 365 中的信箱項目。 您可以建立查詢以搜尋所有匯入的協力廠商資料的項目，或者您可以建立將查詢傳送至只搜尋特定的協力廠商資料的項目。 此外，您也可以建立查詢式保留原則，或查詢為基礎的 eDiscovery 保留來保留在 Office 365 中的協力廠商資料。 
  
如需有關匯入協力廠商資料與可匯入至 Office 365 的協力廠商資料類型清單的詳細資訊，請參閱[Office 365 中的封存協力廠商資料](archiving-third-party-data.md)。 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>建立查詢以搜尋所有協力廠商資料

搜尋 （或就地保留狀態） 的任何協力廠商資料類型，當您匯入至 Office 365，您可以可以使用`kind:externaldata`郵件 [關鍵字] 方塊中的屬性值配對的內容搜尋，或建立查詢式保留時。 例如，若要搜尋的項目都已匯入任何協力廠商資料來源，並匯入的項目之主旨屬性中包含 「 contoso 」 字樣，您會使用下列查詢： 
  
```
kind:externaldata AND subject:contoso
```

先前的關鍵字查詢範例包含 subject 屬性。 如需協力廠商資料的其他屬性的清單項目，可以包含關鍵字查詢中，請參閱[Office 365 中的封存協力廠商資料](archiving-third-party-data.md#more-information)」 的詳細資訊 」 一節。
  
建立查詢以搜尋並保留協力廠商資料時，您也可以使用條件縮小搜尋結果的範圍。 如需建立內容搜尋查詢的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>建立查詢以搜尋特定類型的協力廠商資料

而不是搜尋所有類型的協力廠商資料，您可以建立查詢指定類型的協力廠商資料只搜尋使用內容搜尋關鍵字] 方塊中的下列郵件屬性值組：
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

例如，若要只搜尋包含主旨屬性中的 「 contoso 」 字樣的 Facebook 資料，您會使用下列查詢：
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

下表列出您可以搜尋，協力廠商資料類型和值用於`itemclass:`message 特別搜尋協力廠商資料類型的屬性。 請注意，查詢語法不區分大小寫。 
  
|**協力廠商資料類型**|**值`itemclass:`屬性**|
|:-----|:-----|
|目標  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|含樞紐分析用戶端的 AOL  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|阿瑞斯  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs 版面配置區  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry Call Logs  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry pin 碼  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg 郵件  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg 郵件  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google +  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|冰聊天室  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|注意對齊  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|分享空間  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|樞紐  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|商務用 Skype  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|號交響曲  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|在 twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo ！  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
