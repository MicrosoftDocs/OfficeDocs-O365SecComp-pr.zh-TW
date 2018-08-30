---
title: 使用瀏覽器安全性&amp;規範中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: 了解安全性 （也稱為威脅瀏覽器） 的瀏覽器&amp;規範中心。
ms.openlocfilehash: 51228101ba75eb2d51b2594db50f679ff107ed46
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527333"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a>使用瀏覽器安全性&amp;規範中心

如果您的組織具有[Office 365 威脅智慧](office-365-ti.md)，且您所需的[權限中的 Office 365 安全性和規範中心](permissions-in-the-security-and-compliance-center.md)，您可以使用瀏覽器來識別和分析威脅。例如，您可以識別和刪除惡意的電子郵件已傳遞或請參閱 Office 365 的安全性功能所攔截的惡意程式碼。Explorer （也稱為威脅 Explorer） 是功能強大的即時報告安全性附近&amp;規範中心。
  
![移至 [Threat management\>瀏覽器](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
若要使用總管]、 [安全性&amp;規範管理中心，移至**威脅管理** \> **瀏覽器**。
      
## <a name="explorer-overview"></a>Explorer 概觀 （英文)

瀏覽器顯示您的組織有關電子郵件中的可疑惡意程式碼與 Office 365 中的檔案，以及其他安全性威脅及風險的資訊。當您首次開啟瀏覽器時，將預設檢視會顯示從防毒惡意程式碼偵測。瀏覽器也可以顯示安全性保護功能在 Office 365 中，包括[安全的連結](atp-safe-links.md)及[安全的附件](atp-safe-attachments.md)。
  
![瀏覽器顯示上方的惡意程式碼和目標的使用者的資訊](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
若要變更哪些資訊會顯示使用 [檢視] 功能表。
  
![瀏覽器的 [檢視] 功能表](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
Explorer 有數種篩選和查詢功能可讓您切入的詳細資訊，例如頂端目標使用者、 上方的惡意程式碼系列等等。每一種報表提供各種方式檢視和瀏覽資料，如下表所述。
  
|**選擇此選項**|**若要檢視此資料**|
|:-----|:-----|
|**電子郵件**\> **惡意程式碼** <br/> |電子郵件會被識別為包含惡意程式碼。  <br/> 檢視資訊中的惡意程式碼系列、 寄件者的網域、 寄件者 IP、 保護狀態 （所採取的動作威脅保護功能與 Office 365 中的原則），並偵測技術 （如何惡意程式碼偵測到） 圖表。  <br/> ![檢視有關偵測到惡意程式碼](media/d11dc568-b091-4159-b261-df13d76b520b.png)           <br/> 圖表、 檢視上的惡意程式碼系列的詳細資料下方頂端目標使用者，而關於特定郵件的詳細資訊。  <br/> |
|**電子郵件**\> **Phish** <br/> |電子郵件訊息識別為網路釣魚嘗試次數。  <br/> 檢視由寄件者的網域、 寄件者 IP 及保護狀態 （threat 保護功能與 Office 365 中的原則所採取的動作） 的資訊。  <br/> ![關於電子郵件會被識別為網路釣魚嘗試檢視資料](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png)           <br/> 圖表下方檢視關於特定郵件的詳細資訊。  <br/> |
|**電子郵件**\> **使用者報告** <br/> |使用者會回報為垃圾郵件、 未垃圾郵件或網路釣魚電子郵件的電子郵件。  <br/> 檢視資訊報告類型 （使用者決定電子郵件是垃圾郵件、 未垃圾郵件或 phish、） 以及傳遞原因 （原因電子郵件至特定位置，例如垃圾郵件篩選器原則、 郵件流程規則、 封鎖的寄件者清單、 安全寄件者] 清單中，發生的原因等）。  <br/> ![檢視資料相關的電子郵件使用者回報為垃圾郵件、 未垃圾郵件或網路釣魚](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)           <br/> 圖表下方檢視特定的電子郵件訊息，例如主旨行、 寄件者的 IP 位址、 回報為垃圾郵件、 不垃圾郵件，或 phish、 及更多的郵件使用者相關的詳細資訊。  <br/> |
|**電子郵件**\> **所有郵件** <br/> |電子郵件活動，包括做為識別為因網路釣魚或惡意程式碼、 惡意的電子郵件的所有延展檢視以及 （一般的電子郵件、 垃圾郵件、 部署與大量郵件） 的所有非惡意郵件。  <br/> > [!NOTE]> 如果您收到錯誤，可讀取**太多資料顯示**、 新增篩選及必要的話，縮小您要檢視的日期範圍。若要套用篩選器，並選擇 [**寄件者**、 選取項目在清單中，然後按一下 [重新整理] 按鈕。在我們的範例中，我們會使用**偵測技術**為篩選 （還有數個選項可）。          檢視依寄件者、 寄件者的網域、 收件者、 主旨、 附件檔案名稱、 惡意程式碼系列、 保護狀態 （threat 保護功能與 Office 365 中的原則所採取的動作）、 偵測技術 （如何惡意程式碼偵測到）、 資訊及更多。<br/> ![關於偵測到的電子郵件偵測技術來檢視資料](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)           <br/> 圖表、 下方檢視特定的電子郵件訊息，例如主旨行、 收件者、 寄件者、 狀態] 等的更多詳細資料。  <br/> |
|**內容**\> **惡意程式碼** <br/> |已識別為惡意的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組的檔案。  <br/> 惡意程式碼 （如何惡意程式碼偵測到）、 系列，偵測技術來檢視資訊和工作負載 （OneDrive、 SharePoint、 或小組）。  <br/> ![檢視有關偵測到惡意程式碼](media/d11dc568-b091-4159-b261-df13d76b520b.png)           <br/> 圖表下方檢視特定的檔案，例如附件檔案名稱、 工作量、 檔案大小、 上次修改者檔案和更多有關的詳細資訊。  <br/> |
  
## <a name="new-click-to-filter-capabilities"></a>（新增 ！）按一下 [以篩選功能

新瀏覽器為按一下 [篩選的能力。開始在落後 5 2018，當您按一下圖例中的項目，該項目會成為報表的篩選器。例如，假設我們要尋找在檔案總管中的惡意程式碼檢視：
  
![移至 [Threat management\>瀏覽器](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
這個圖表會導致類似的檢視中按一下**ATP Detonation** ： 
  
![顯示只 ATO Detonation 結果篩選過的檔案總管](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
在此檢視中，我們會立即查看資料已 detonated 由[Office 365 ATP 安全附件](atp-safe-attachments.md)的檔案。圖表下方我們可以看到關於有已偵測到的 ATP 安全附件的附件的特定電子郵件的詳細資訊。
  
![關於偵測到的附件的電子郵件的特定詳細資料](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
選取一或多個項目會啟動 [**動作**] 功能表，提供數個選項可供選擇為選取的項目。 
  
![選取項目會啟動 [動作] 功能表](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
能夠在按一下篩選及瀏覽至特定的詳細資料可以儲存您很多時間調查威脅。
  
## <a name="how-do-i-get-explorer"></a>如何取得 Explorer？

[Office 365 威脅智慧](office-365-ti.md)隨附檔案總管]。您必須具備適當[權限指派在 Office 365 安全性及規範中心 」](permissions-in-the-security-and-compliance-center.md)，例如安全性管理員或安全性讀者才能檢視及使用檔案總管]。
  
## <a name="related-topics"></a>相關主題

[報告與 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)
  
[尋找與調查惡意的電子郵件已傳遞 （Office 365 威脅智慧）](investigate-malicious-email-that-was-delivered.md)
  
[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)
  

