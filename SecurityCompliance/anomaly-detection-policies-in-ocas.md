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
description: 'Office 365 雲端應用程式安全性異常偵測原則使用內建的演算法可協助從抽出潛在的問題。您應該會有至少一個異常偵測原則] 中，您可以使用篩選器來調整 （當您建立它）。 '
ms.openlocfilehash: 5308af139a46dad0793ed7eedacab0aee62dcc6c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220673"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性中的異常偵測原則

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](ocas-conditional-access-app-control.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
Office 365 雲端應用程式安全性開頭[版本 116 Microsoft 雲端應用程式安全性](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116)，包括數個預先定義的異常偵測原則原則 （"現成可用"），包括使用者和實體行為上有無分析 (UEBA) 和學習 （毫升） 的電腦。
  
![若要檢視您異常偵測原則，請選擇 [控制\>原則。](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
這些異常偵測原則提供立即偵測、 目標許多行為上有無異常為您的使用者在機器和裝置連線到您的網路之間提供立即的結果。此外，新的原則會公開可協助您加速調查程序，包含持續威脅的雲端應用程式安全性偵測引擎的詳細資料。
  
為 Office 365 全域管理員或安全性管理員，您可以檢閱及必要時修改可用來搭配 Office 365 雲端應用程式安全性的預設原則。
  
 > [!IMPORTANT]
> 有七 （7） 天的期間異常行為提醒不會觸發初始學習期間。異常偵測演算法已最佳化來減少 false 正數的提醒數目。 
  
## <a name="before-you-begin"></a>開始之前

請確定：
  
- 您的組織具有[Office 365 雲端應用程式安全性](office-365-cas-overview.md)] 和服務已[開啟](turn-on-office-365-cas.md)。
    
- [稽核記錄](turn-audit-log-search-on-or-off.md)已開啟的 Office 365 環境。 
    
- 您已為全域管理員或 Office 365 的安全性管理員。
    
## <a name="view-your-anomaly-detection-policies"></a>檢視您異常偵測原則

1. 以全域管理員或安全性管理員中，移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。<br>這會帶您至 [Office 365 雲端應用程式的安全性原則] 頁面上。
    
2. 在 [**類型**] 清單中選擇 [**異常偵測原則**]。<br>貴組織的預設值 （或現有） 顯示異常偵測原則。<br>![Office 365 雲端 App 安全性中的異常偵測原則](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
3. 選取要檢視或編輯其設定的原則。
    
4. 選擇 [**更新**] 以儲存變更。 
    
## <a name="learn-more-about-anomaly-detection-policies"></a>深入了解異常偵測原則

異常偵測原則會自動啟用;不過，Office 365 雲端應用程式安全性有哪些不是所有異常期間偵測警示所引發的七天的初始學習期間。之後，每個工作階段會比較當使用者已作用中的活動、 IP 位址、 裝置、 等偵測的過去月及這些活動風險分數。這些偵測屬於探索異常偵測引擎的設定檔環境及觸發提醒表示已在您的組織活動學到的基準。這些偵測也運用機器學習演算法設計用來設定檔的使用者和登入模式來減少誤判。
  
異常偵測到掃描使用者活動。透過查看超過 30 不同風險指標，分為多個風險因素，risky IP 位址、 登入失敗、 系統活動、 非使用中帳戶、 位置、 無法運用旅行、 裝置和使用者代理程式及活動率等評估風險。
  
根據原則結果，安全性提醒會觸發。Office 365 雲端應用程式安全性尋找在 Office 365 中每個使用者工作階段，並在提醒您每當發生變化不同從您的組織的基準或從使用者的一般活動。
  
下表說明預設異常偵測原則、 所執行的動作，以及它們的運作方式。
  
|**異常偵測原則名稱**|**運作方式**|
|:-----|:-----|
|無法運用旅行  <br/> |會識別兩個使用者活動 （為單一或多個工作階段） 源自遠距位置小於時間期間內它可能需要花旅行社從第一個位置的第二個，指出使用者不同使用者正在使用的相同認證。此偵測如何運用學習明顯"誤判"貢獻無法運用旅行條件，例如 Vpn 和定期組織中的其他使用者所使用的位置會略過的演算法機器。偵測有七天的期間它可學習新使用者的活動模式的初始學習期間。  <br/> |
|從非經常性國家/地區的活動  <br/> |若要判斷最新及非經常性位置會考慮過去的活動位置。異常偵測引擎會儲存在組織中使用者所使用的上一個位置相關資訊。從已不最近或永不造訪由使用者或組織中任何使用者的位置活動時發生觸發提醒。  <br/> |
|從匿名的 IP 位址的活動  <br/> |識別使用者已被識別為匿名的 proxy IP 位址的 IP 位址從作用中。想要隱藏使用者的裝置 IP 位址，以及可能會使用惡意的人使用這些 proxy。此偵測如何運用學習減少"誤判 」，例如正確標記廣泛組織中的使用者所使用的 IP 位址的演算法機器。  <br/> |
|從可疑的 IP 位址的活動  <br/> |識別使用者已被識別為 risky 由 Microsoft Threat 智慧 IP 位址從作用中。這些 IP 位址參與惡意活動的 Botnet C&amp;C，而且可能會指出入侵的帳戶。此偵測如何運用學習減少"誤判 」，例如正確標記廣泛組織中的使用者所使用的 IP 位址的演算法機器。  <br/> |
|不尋常活動 （由使用者）  <br/> | 識別使用者執行不尋常的活動，例如：  <br/>  -多個檔案下載  <br/>  -檔案共用的活動  <br/>  -檔案刪除活動  <br/>  -模擬活動  <br/>  -管理活動  <br/>  這些原則尋找活動內單一工作階段相對於基線學會，這可能表示上破壞嘗試。這些偵測運用學習設定檔的使用者登入模式的演算法機器並減少誤判。這些偵測屬於探索異常偵測引擎的設定檔環境及觸發提醒表示已在您的組織活動學到的基準。  <br/> |
|多個失敗的登入嘗試次數  <br/> |失敗的單一工作階段中的多個登入嘗試的使用者會識別相對於學到的基準，這可能表示上破壞嘗試。  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a>分辨異常偵測警示

當提醒甚至，您可以快速分辨這些提醒並決定哪些先處理。具有內容的通知可讓您查看更大的圖片，並決定是否遭到惡意的某個項目確實正在進行的活動。使用下列程序開始探索提醒：
  
1. 以全域管理員或安全性管理員中，移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。 
    
2. 選擇 [以檢視您提醒的**提醒**。 
    
3. 若要取得快顯通知，請遵循下列步驟：
    
4. 選擇**調查** \> **活動記錄檔**。
    
5. 選取項目，例如使用者或 IP 位址。如此會開啟相關的見解抽屜。<br>![您可以在活動記錄檔調查 IP 位址。](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. 在相關的見解抽屜中，按一下 [可用的命令，例如**顯示如下**一節中的圖示。<br> ![按一下 [時鐘] 圖示以查看所選活動的 48 小時內執行的活動](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
7. 深入了解選取的項目來繼續探索表示項目詳細資料。
    
在多個登入失敗通知可能確實可疑，因此可以表示潛在的暴力破解攻擊。但是，這類通知也可以是應用程式設定錯誤，導致設為良性 true 誤判提醒。如果您看到其他可疑活動與多重失敗 logins 提醒，就會危害帳戶的較高機率。例如，假設為多個失敗登通知後面接活動從 TOR IP 位址和無法運用旅行活動危害這兩個強式指標。您甚至可能會看到相同的使用者執行大量下載 （英文） 活動，這通常是執行 exfiltration 資料的攻擊者的指標。它的之類的可探索 Office 365 雲端應用程式安全性檢視和分辨您提醒，並採取動作在需要時。
  
## <a name="next-steps"></a>後續步驟

- [為 Office 365 應用程式部署條件式存取應用程式控制](ocas-deploy-conditional-access-app-control.md)

- [群組簡化管理 IP 位址](group-your-ip-addresses-in-ocas.md)

- [整合 SIEM server](integrate-your-siem-server-with-office-365-cas.md)
    
- [檢閱並採取行動提醒](review-office-365-cas-alerts.md)
    
    

