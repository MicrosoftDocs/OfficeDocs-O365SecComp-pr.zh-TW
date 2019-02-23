---
title: 進階垃圾郵件篩選選項
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
description: 進階垃圾郵件篩選選項可讓系統管理員將檢查的一則訊息的各種內容屬性。在郵件中的這些屬性的目前狀態會增加 （進而增加可能會為其識別為垃圾郵件） 郵件的垃圾郵件計分或標示為垃圾郵件訊息。ASF 選項目標特定郵件的內容，例如 HTML 標籤和 URL 重新導向位於垃圾郵件。
ms.openlocfilehash: d9333fd4f5c8937e440efb15e1a04db787b39b78
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218673"
---
# <a name="advanced-spam-filtering-options"></a>進階垃圾郵件篩選選項

進階垃圾郵件篩選選項可讓系統管理員將檢查的一則訊息的各種內容屬性。在郵件中的這些屬性的目前狀態會增加 （進而增加可能會為其識別為垃圾郵件） 郵件的垃圾郵件計分或標示為垃圾郵件訊息。ASF 選項目標特定郵件的內容，例如 HTML 標籤和 URL 重新導向位於垃圾郵件。
  
啟用 ASF 選項是一種很激進的垃圾郵件篩選方式，這些選項所篩選出來的任何郵件都無法回報為誤判。您可透過定期的使用者垃圾郵件通知來識別這些郵件，並從垃圾郵件隔離區將其救回。也可以透過 X-header 文字來識別這些郵件，此文字為各個 ASF 選項所特有，出現在已找到相符 ASF 選項的郵件的 Internet 標頭中。如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。
  
ASF 選項您可以將開啟、 關閉，或以測試模式時您編輯內容篩選原則。如需詳細資訊，請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)。測試模式不適用於**NDR 非法回應**， **SPF 記錄： 完全未通過**、**條件式寄件者識別碼篩選： 完全未通過**，與**大量電子郵件**選項。 
  
> > [!TIP]
> 選用資訊可協助使用者可更成功考量啟用在測試模式中的您 ASF 選項以最大化垃圾郵件封鎖根據您的環境。高的垃圾郵件百分比 （英文） 特定 ASF 選項的客戶，我們建議您測試先在實際執行環境之前實作它們這些選項。我們建議您擔心網路釣魚的組織開啟的 > **SPF 記錄： 完全未通過**] 選項。 
  
下表說明各個進階垃圾郵件篩選選項。
  
||||
|:-----|:-----|:-----|
|**進階垃圾郵件篩選選項** <br/> |**描述** <br/> |**X-header 文字** <br/> |
|**[增加垃圾郵件計分] 區段** <br/> |啟用時，這些選項會將符合之郵件的垃圾郵件信賴等級 (SCL) 設為 5 或 6 (視為可疑的垃圾郵件)。對郵件執行的動作將符合內容篩選原則中的 **[垃圾郵件]** 設定。<br/> ||
|影像連結到遠端站台  <br/> |啟用此設定時，郵件只要含有具有遠端 （例如，使用 http） 連結 IMG 標記的 HTML 內容會得到較高的垃圾郵件計分。  <br/> |X-CustomSpam：遠端站台的影像連結  <br/> |
|URL 中的數值 IP 位址  <br/> |啟用此設定時，郵件只要含有數值式 Url (通常是 IP 位址的格式） 會得到較高的垃圾郵件計分。  <br/> |X-CustomSpam：URL 中的數值 IP  <br/> |
|URL 重新導向到其他連接埠  <br/> |啟用此設定時，任何包含以外將使用者重新導向至連接埠的超連結的訊息連接埠 80 （一般 HTTP 通訊協定連接埠）、 8080 （HTTP 替代的連接埠、） 或 443 （HTTPS 連接埠） 會得到較高的垃圾郵件計分。  <br/> |X-CustomSpam：URL 重新導向到其他連接埠  <br/> |
|.biz 或 .info 網站的 URL  <br/> |啟用此設定時，任何含有.biz 或.info 副檔名為一則訊息本文中的郵件會得到較高的垃圾郵件計分。  <br/> |X-CustomSpam：.biz 或 .info 網站的 URL  <br/> |
|**[標記為垃圾郵件] 區段** <br/> |啟用時，這些選項會將符合之郵件的垃圾郵件信賴等級 (SCL) 設為 9 (確信為垃圾郵件)。對郵件執行的動作將符合內容篩選原則中的 **[高信賴度的垃圾郵件]** 設定。<br/> ||
|空白訊息  <br/> |啟用此設定時，郵件只要任何內文與主旨行皆空白，且不含附件，就會被標記為垃圾郵件。  <br/> |X-CustomSpam：空白郵件  <br/> |
|HTML 中有 JavaScript 或 VBScript  <br/> |啟用此設定時，郵件只要在 HTML 中使用 JavaScript 或 Visual Basic Script Edition，就會被標記為垃圾郵件。這兩種指令碼語言用在 HTML 郵件中，都是為了要讓特定動作自動執行。瀏覽器會剖析及處理指令碼以及文件的其餘部分。  <br/> |X-CustomSpam：HTML 中有 Javascript 或 VBscript 標記  <br/> |
|HTML 中有 Frame 或 IFrame 標籤  <br/> |啟用此設定時，包含任何訊息\<圖文框\>或\<IFrame\> HTML 標籤將會標示為垃圾郵件。這些標記用以在網站上或在 HTML 郵件格式顯示的文字或圖形的頁面。  <br/> |X-CustomSpam：HTML 中有 IFRAME 或 FRAME  <br/> |
|HTML 中有 Object 標籤  <br/> |啟用此設定時，包含任何訊息\<物件\>HTML 標籤將會標示為垃圾郵件。外掛程式或的 HTML 視窗中執行的應用程式可讓此 HTML 標籤。  <br/> |X-CustomSpam：HTML 中有 Object 標記  <br/> |
|HTML 中有 Embed 標籤  <br/> |啟用此設定時，包含任何訊息\<Embed\> HTML 標籤將會標示為垃圾郵件。此 HTML 標籤可讓不同種類的文件的 varying 內嵌到 HTML 文件的資料類型。範例包括聲音、 影片、 或圖片。  <br/> |X-CustomSpam：HTML 中有 Embed 標記  <br/> |
|HTML 中有 Form 標籤  <br/> |啟用此設定時，包含任何訊息\<表單\>HTML 標籤將會標示為垃圾郵件。此 HTML 標籤用來建立網站表單。電子郵件廣告通常包含此標籤加入請求收件者的資訊。  <br/> |X-CustomSpam：HTML 中有 Form 標記  <br/> |
|HTML 中有錯誤網頁  <br/> |啟用此設定時，郵件只要含有 Web Bug，就會被標記為垃圾郵件。Web Bug 是一個圖形，用來判斷某個網頁或電子郵件是否已被讀取。收件者通常看不見 Web Bug，因為加在郵件中的 Web Bug 通常是一個很小的圖形，最小只有一個像素的見方。合法的電子報也會使用此技術，但有許多人將此視為侵犯隱私權。  <br/> |X-CustomSpam：Web Bug  <br/> |
|套用敏感字詞清單  <br/> |啟用此設定時，郵件只要含有敏感字詞清單中的文字，就會被標記為垃圾郵件。使用敏感字詞清單，可讓您輕易封鎖可能與冒犯性的郵件相關聯的文字。其中有些文字區分大小寫。您無法以系統管理員的身分編輯此清單。敏感字詞清單篩選功能會同時套用至郵件的主旨與內文。  <br/> |X-CustomSpam：主旨/本文中有敏感字詞  <br/> |
|SPF 記錄：完全未通過  <br/> |啟用此設定時，未通過 SPF 檢查的郵件 (表示從 SPF 記錄中未指定的 IP 位址寄來) 會標示為垃圾郵件。對於擔心網路釣魚郵件的組織，建議開啟此設定。<br/> <br/>> [!NOTE]
無法使用此選項 > 測試模式。  <br/> |X-CustomSpam：SPF 記錄失敗  <br/> |
|條件式寄件者識別碼篩選：完全未通過  <br/> |啟用此設定時，郵件只要完全未通過條件式寄件者識別碼檢查，就會被標記為垃圾郵件。此選項結合了 SPF 檢查與寄件者識別碼檢查，以防範含有偽造寄件者的郵件標頭。<br/> <br/>> [!NOTE]
無法使用此選項 > 測試模式。  <br/> |X-CustomSpam：SPF 寄件者記錄失敗  <br/> |
|NDR 非法回應  <br/> |如果您使用 EOP 來保護在內部部署信箱啟用此設定時，所有合法的未傳遞回報 (NDR) 會傳遞至原始寄件者和非法回應 (非法 NDR) 的所有訊息將都標記為垃圾郵件。如果您不要啟用此設定，然後所有 Ndr 仍都移到垃圾郵件篩選。在此例中最合法的郵件會取得已傳遞給原始寄件者時一些，但不是所有、 非法回應郵件會取得標示為垃圾郵件。不過，非法回應郵件的未標示為垃圾郵件將不會移至原始寄件者，因為它會前往詐騙的寄件者。<br/> <br/> 如果您使用服務來保護 Exchange Online 的雲端託管信箱，您不需要進行此設定。  <br/><br/> > [!NOTE]
> （內部部署和雲端託管信箱） 這兩種情況很也不需要啟用此設定外寄郵件傳送到服務] 的合法彈跳訊息將會自動偵測到並傳遞給原始寄件者的 Ndr.無法使用此選項 > 測試模式。<br/><br/>> [!TIP]
> 秘訣： 如需非法回應郵件與 EOP 的詳細資訊，請參閱[非法回應郵件與 EOP](backscatter-messages-and-eop.md)。          |X-customspam： 非法回應 NDR<br/> | |大宗郵件  <br/> |進階垃圾郵件篩選大量電子郵件的已撤銷並之後取代大量和電子郵件臨界值設定。取出[垃圾郵件與大量電子郵件之間的差異為何？](what-s-the-difference-between-junk-email-and-bulk-email.md)及[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)的詳細資訊以及如何設定是家生機械 」。<br/> ||
   

