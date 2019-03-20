---
title: 使用中的安全性威脅總管&amp;合規性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解 （也稱為威脅總管） 的瀏覽器安全性&amp;合規性中心。
ms.openlocfilehash: 0c86792d8ed84b43b28bde31004dc95d2fa2b547
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693612"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>使用中的安全性威脅總管&amp;合規性中心

如果您的組織有[Office 365 進階威脅防護計劃 2](office-365-ti.md)，而且您具有必要權限，您可以使用威脅總管來識別和分析潛在威脅。 例如，您可以識別並刪除惡意電子郵件已傳遞，或請參閱 Office 365 安全性功能所攔截惡意程式碼。 威脅總管 （也稱為 Explorer）] 是功能強大的接近即時的工具，以協助調查及回應安全性威脅的安全性作業小組&amp;合規性中心。
  
![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
若要使用檔案總管中，安全性&amp;合規性中心，移至**威脅管理** \> **總管**。

> [!IMPORTANT]
> Office 365 威脅情報現在是 Office 365 進階威脅防護計劃 2，以及其他威脅保護功能。 若要深入了解，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
      
## <a name="explorer-overview"></a>Explorer 概觀

檔案總管] 會顯示組織資訊可疑的惡意軟體和電子郵件中的釣魚程式和 Office 365 中的檔案，以及其他安全性威脅及風險。 當您首次開啟檔案總管時的預設檢視中顯示電子郵件惡意程式碼偵測在過去 7 天。 瀏覽器也可以顯示安全性保護功能在 Office 365 中，包括[安全連結](atp-safe-links.md)和[安全附件](atp-safe-attachments.md)，您可以修改顯示過去 30 天的資料。 如果您有 Office 365 進階威脅防護方案 2 或 Office 365 E5 試用訂閱，只會針對在過去 7 天看到偵測和電子郵件資料。
  
![瀏覽器顯示上方的惡意程式碼和目標的使用者的相關資訊](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
使用 [檢視] 功能表變更顯示的資訊。
  
![瀏覽器的 [檢視] 功能表](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
Explorer 有數個篩選和查詢功能可讓您切入詳細資訊，例如頂端的目標使用者、 上方的惡意程式碼系列、 偵測技術等等。 每一種報表提供了許多方式可檢視和瀏覽資料。

> [!IMPORTANT]
> 請勿使用萬用字元，例如星號 （*） 或問號 （？） 與檔案總管。 當您搜尋電子郵件的主旨欄位時，Explorer 便會執行部分符合及收益結果類似萬用字元搜尋。

## <a name="email--malware"></a>電子郵件\>惡意程式碼

這個檢視顯示電子郵件被識別為包含惡意程式碼。  

檢視惡意程式碼系列、 寄件者網域、 寄件者 IP、 保護狀態 （所採取的動作威脅保護功能和 Office 365 中的原則），並偵測技術 （如何惡意程式碼偵測到） 圖表中的資訊。  

![檢視有關偵測到惡意程式碼](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

下方圖表中，檢視上方的惡意程式碼系列的詳細資料的使用者，以及特定郵件的詳細，目標對象頂端。 

## <a name="email--phish"></a>電子郵件\>Phish

這個檢視顯示電子郵件識別為網路釣魚嘗試次數。  

檢視由寄件者網域、 寄件者 IP 和保護狀態 （威脅保護功能和 Office 365 中的原則所採取的動作） 的資訊。 

![關於電子郵件被識別為網路釣魚嘗試檢視資料](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

下方圖表，檢視特定郵件的相關詳細資料。 

## <a name="email--user-reported"></a>電子郵件\>使用者報告

這個檢視顯示電子郵件使用者會回報為垃圾郵件、 非垃圾郵件或網路釣魚電子郵件。  

檢視資訊報告類型 （使用者的決定電子郵件是垃圾郵件、 非垃圾郵件或釣魚程式，） 以與傳遞原因 （原因電子郵件至特定位置，例如垃圾郵件篩選原則、 郵件流程規則、 封鎖的寄件者清單、 安全的寄件者] 清單中，發生的原因等）。  

![檢視關於回報為垃圾郵件、 非垃圾郵件或網路釣魚電子郵件使用者的資料](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

下方圖表，檢視關於特定電子郵件，如主旨、 寄件者的 IP 位址、 回報郵件為垃圾郵件、 非垃圾郵件，或釣魚程式，等等的使用者詳細資料。 

## <a name="email--all-mail"></a>電子郵件\>所有郵件

此檢視全面檢視顯示的電子郵件活動，包括電子郵件識別為惡意由於網路釣魚或惡意程式碼，以及所有非惡意的郵件 （一般的電子郵件、 垃圾郵件，以及大量郵件）。 

> [!NOTE]
> 如果您收到錯誤，可讀取**太多要顯示的資料**、 新增篩選器，如有必要，縮小您要檢視的日期範圍。 

若要套用篩選器，選擇 [**寄件者**、 在清單中，選取項目，然後按一下 [重新整理] 按鈕。 在我們的範例中，我們使用**偵測技術**作為篩選器 （有幾個選項可以使用）。 檢視依寄件者、 寄件者的網域、 收件者、 主旨、 附件檔名、 惡意程式碼系列、 保護狀態 （威脅保護功能和 Office 365 中的原則所採取的動作）、 （如何惡意程式碼偵測到），偵測技術的資訊和更多。 

![關於偵測技術所偵測到電子郵件的檢視資料](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

下方圖表，檢視更多詳細資料特定的電子郵件，例如主旨行、 收件者、 寄件者、 狀態、 等等。 

## <a name="content--malware"></a>內容\>惡意程式碼

這個檢視顯示已由 Office 365 進階威脅防護中 SharePoint Online、 OneDrive for Business 和 Microsoft Teams 識別為惡意的檔案。

檢視惡意程式碼 （如何惡意程式碼偵測到），家長監護，偵測技術的資訊和工作負載 （OneDrive、 SharePoint 或小組）。 

![檢視有關偵測到惡意程式碼](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

下方圖表中，檢視需有關特定的檔案，例如附件檔名，工作負載，檔案大小，最後修改的檔案，以及更多詳細資訊。 
  
## <a name="new-click-to-filter-capabilities"></a>（新 ！）按一下 [以篩選功能

新瀏覽器是按一下 [以篩選的能力。 當您按一下圖例中的項目時，該項目會成為報表的篩選器。 例如，假設我們要尋找在檔案總管中的惡意程式碼檢視：
  
![移至威脅管理，\>總管](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
在此圖表中的結果就像這樣的檢視中，按一下 [ **ATP 爆炸**： 
  
![篩選只 ATO 爆炸結果顯示的瀏覽器](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
在此檢視中，我們現在要尋找在[Office 365 ATP Safe Attachments](atp-safe-attachments.md)已引爆的檔案的資料。 下方圖表中，我們可以看到關於有已偵測到由 ATP 安全附件的附件的特定電子郵件的詳細資訊。
  
![關於偵測到的附件的電子郵件的特定詳細資料](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
選取一或多個項目會啟動 [**動作**] 功能表，它提供了數個選項可供選擇為選取的項目。 
  
![選取項目會啟動 [動作] 功能表](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
在按一下篩選及瀏覽至特定的詳細資訊的能力可讓您節省大量時間中調查潛在威脅。
  
## <a name="how-do-i-get-explorer"></a>如何取得總管？

Explorer 隨附於[Office 365 進階威脅防護計劃 2](office-365-ti.md)。 

您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者，才能檢視及使用檔案總管。 若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="related-topics"></a>相關主題

[報告和 Office 365 安全性的深入解析&amp;合規性中心](reports-and-insights-in-security-and-compliance.md)
  
[尋找並調查惡意電子郵件已傳遞 （Office 365 威脅 Invesitgation 和回應）](investigate-malicious-email-that-was-delivered.md)
  
[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)
  

