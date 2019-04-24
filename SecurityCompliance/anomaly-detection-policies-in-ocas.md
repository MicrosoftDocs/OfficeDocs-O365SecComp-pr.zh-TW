---
title: Office 365 雲端 App 安全性中的異常偵測原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/15/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'Office 365 雲端 App 安全性中的異常偵測原則會使用內建的演算法，來協助找出潛在的問題。 您應該有至少一個異常偵測原則，您可以使用篩選器來調整 （當您建立它）。 '
ms.openlocfilehash: 5308af139a46dad0793ed7eedacab0aee62dcc6c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242848"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性中的異常偵測原則

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](ocas-conditional-access-app-control.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
開始使用[Microsoft Cloud App Security 釋出 116](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116)，Office 365 雲端 App 安全性，包括數個預先定義的異常偵測原則 （「 現成可用 」），包括使用者和實體行為分析 (UEBA) 與機器學習 (ML)。
  
![若要檢視您的異常偵測原則，請選擇 [控制項\>原則。](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
這些異常偵測原則藉由提供即時偵測，您的使用者和機器和裝置連線到您網路的目標許多行為異常問題提供即時運算的結果。 此外，新的原則會公開 Cloud App Security 偵測引擎可協助您加速調查的程序，並包含持續威脅的詳細資料。
  
為 Office 365 全域系統管理員或安全性系統管理員，您可以檢閱，並如有必要，修改預設原則，可用來搭配 Office 365 雲端 App 安全性。
  
 > [!IMPORTANT]
> 沒有七 （7） 天期間異常行為提醒都不會觸發的初始學習週期。 異常偵測演算法已經過最佳化，以減少 false 正數的提醒數目。 
  
## <a name="before-you-begin"></a>開始之前

請確定：
  
- 您的組織有[Office 365 雲端 App 安全性](office-365-cas-overview.md)，並服務已[開啟](turn-on-office-365-cas.md)。
    
- [稽核記錄](turn-audit-log-search-on-or-off.md)已為您的 Office 365 環境。 
    
- 您是全域系統管理員或 Office 365 的安全性系統管理員。
    
## <a name="view-your-anomaly-detection-policies"></a>檢視您的異常偵測原則

1. 以全域管理員或安全性管理員中，移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。<br>這會帶您前往 Office 365 雲端 App 安全性原則] 頁面上。
    
2. 在 [**類型**] 清單中，選擇 [**異常偵測原則**。<br>貴組織的預設 （或現有） 的異常偵測原則會顯示。<br>![Office 365 雲端 App 安全性中的異常偵測原則](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
3. 選取要檢視或編輯其設定的原則。
    
4. 選擇 [**更新**] 以儲存變更。 
    
## <a name="learn-more-about-anomaly-detection-policies"></a>深入了解的異常偵測原則

異常偵測原則會自動啟用。不過，Office 365 雲端 App 安全性有七天期間哪些並非所有的異常偵測警示所提出的初始學習一段。 在那之後，每個工作階段是相較於活動，當使用者已作用中、 IP 位址、 裝置等偵測到在上個月及這些活動風險分數。 這些偵測屬於啟發式異常偵測引擎設定檔您的環境，會觸發警示相對於已在您的組織活動學到基準線。 這些偵測的資訊也會利用設計用來設定檔的使用者和登入模式，以降低誤判的機器學習演算法。
  
異常會偵測 crypto 掃描使用者活動。 風險評估查看超過 30 不同的風險指標，分成多個風險因素，例如有風險的 IP 位址、 登入失敗、 系統管理員活動、 非使用中帳戶、 位置、 無法旅行、 裝置及使用者代理程式和活動工資率。
  
根據原則結果，便會觸發安全性警告。 Office 365 雲端 App 安全性查看 Office 365 中的每個使用者工作階段，並且每當發生變化不同從貴組織的基準線，或從使用者的一般活動時提醒您。
  
下表說明預設的異常偵測原則、 使用者執行的動作，以及它們的運作方式。
  
|**異常偵測原則名稱**|**運作方式**|
|:-----|:-----|
|無法執行流通。  <br/> |識別兩個使用者的活動 （可為單一或多個工作階段） 源自遠距位置時間較短的期間內它可能需要花從第一個位置移動到第二，指出使用者不同使用者正在使用相同的認證。 此偵測會使用機器學習明顯 「 誤判 」 造成無法旅行條件，例如 Vpn 和定期在組織中其他使用者所使用的位置，會略過的演算法。 偵測有七天的期間它可學習新使用者的活動模式的初始學習一段。  <br/> |
|從非經常性國家/地區的活動  <br/> |若要判斷最新及非經常性位置會考慮過去的活動位置。 異常偵測引擎會儲存在組織中的使用者所使用的舊位置的相關資訊。 活動發生從不最近或永不造訪的次數，由使用者或組織中任何使用者的位置時，就會觸發警示。  <br/> |
|從匿名的 IP 位址的活動  <br/> |識別使用者已被識別為匿名 proxy IP 位址的 IP 位址從作用中。 想要隱藏他們的裝置 IP 位址，以及可能用於惡意意圖的人員會使用這些 proxy。 此偵測會使用機器學習減少 「 誤判 」，例如正確標記廣泛組織中的使用者所用的 IP 位址的演算法。  <br/> |
|從可疑的 IP 位址的活動  <br/> |識別使用者已被識別為風險由 Microsoft 威脅情報 IP 位址從作用中。 這些 IP 位址參與惡意活動，例如 Botnet C&amp;C，可能表示遭入侵的帳戶。 此偵測會使用機器學習減少 「 誤判 」，例如正確標記廣泛組織中的使用者所用的 IP 位址的演算法。  <br/> |
|異常的活動 （依使用者）  <br/> | 識別使用者執行不尋常的活動，例如：  <br/>  -多個檔案下載  <br/>  -檔案共用活動  <br/>  -檔案刪除活動  <br/>  -模擬活動  <br/>  -管理活動  <br/>  這些原則尋找活動相對於基線學會，在單一工作階段內這可能表示發生資料外洩嘗試。 這些偵測利用機器學習設定檔的使用者登入模式的演算法，並減少誤判。 這些偵測屬於啟發式異常偵測引擎設定檔您的環境，會觸發警示相對於已在您的組織活動學到基準線。  <br/> |
|多個失敗的登入  <br/> |識別失敗的單一工作階段中的多個登入的使用者有關學到基準線，這可能表示資料外洩嘗試。  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a>分級異常偵測警示

為提醒來自，您可以快速分級這些提醒，並判斷第一次處理哪些項目。 具有內容警示可讓您看到更大的圖片，並判斷是否有惡意確實情形。 使用下列程序，開始探索警示：
  
1. 以全域管理員或安全性管理員中，移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。 
    
2. 選擇 [**提醒**，以檢視您的通知。 
    
3. 若要取得警示內容，請遵循下列步驟：
    
4. 選擇 [ **Investigate** \> **活動記錄檔**。
    
5. 選取項目，例如使用者或 IP 位址。 如此會開啟相關的觀點抽屜。<br>![在活動記錄檔，您可以檢查 IP 位址。](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. 在相關的觀點抽屜中，按一下 [可用的命令，例如 [**顯示類似**] 區段中的圖示。<br> ![按一下以查看所選活動的 48 小時內執行活動的時鐘圖示](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
7. 深入了解選取的項目藉由繼續瀏覽該項目的詳細資料。
    
在多個失敗的登入警示可能的確是可疑，並可以指出潛在的暴力攻擊。 不過，這類警示也可以是應用程式設定錯誤，導致是無害的則為 true 正數警示。 如果您看到多-失敗的登入警示與其他的可疑活動，則較高的可能性帳戶遭到入侵。 例如，假設多失敗的登入警示從危害這兩個強式指標 TOR IP 位址和無法旅行活動，後面接著活動。 您甚至可能會看到相同的使用者執行大量下載活動，這通常是攻擊者執行 exfiltration 的資料指標。 它的工作，您可以檢視和分類您的通知，並採取動作 Office 365 雲端 App 安全性中探索在需要時。
  
## <a name="next-steps"></a>後續步驟

- [為 Office 365 應用程式部署條件式存取應用程式控制](ocas-deploy-conditional-access-app-control.md)

- [您的 IP 位址，以簡化管理群組](group-your-ip-addresses-in-ocas.md)

- [將 SIEM 伺服器整合](integrate-your-siem-server-with-office-365-cas.md)
    
- [檢閱並採取相應動作提醒](review-office-365-cas-alerts.md)
    
    

