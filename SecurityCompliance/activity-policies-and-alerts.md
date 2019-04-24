---
title: Office 365 雲端 App 安全性中的活動原則和警訊
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 定義活動原則與 Office 365 雲端 App 安全性設定提醒，以特定活動，即會發生，或發生次數太頻繁時觸發。 透過設定以觸發提醒的原則，您可以通知，並監視特定活動。
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242708"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性中的活動原則和警訊

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](anomaly-detection-policies-in-ocas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
使用 Office 365 雲端 App 安全性，進階的雲端管理原則會觸發警示所發生的事件，或發生次數太頻繁的特定活動。 例如，假設使用者嘗試登入 Office 365 和 70 時間中一分鐘失敗。 假設另一位使用者下載 7000 檔案，或看起來的身分登入從加拿大，當使用者應該要放在另一個位置。 或惡化，假設某個人的帳戶已遭洩露，而且攻擊者會使用該帳戶來存取貴組織的雲端應用程式和機密資料。
  
如果您是[全域系統管理員或安全性系統管理員](permissions-in-the-security-and-compliance-center.md)，活動警訊會通知您事件 like 這些時就會發生。 您接著可以採取特定的動作，例如擱置的使用者帳戶，直到您可以調查發生了什麼事。
  
> [!NOTE]
> Office 365 雲端 App 安全性原則會不同於[警示中 Office 365 安全性原則&amp;合規性中心](alert-policies.md)。 本文所述的原則定義在 Office 365 雲端 App 安全性入口網站中，並可協助您更好的活動管理貴組織的雲端環境。 
  
## <a name="before-you-begin"></a>開始之前

請確定：
  
- 您的組織有[Office 365 雲端 App 安全性](office-365-cas-overview.md)，並服務已[開啟](turn-on-office-365-cas.md)。
    
- [稽核記錄](turn-audit-log-search-on-or-off.md)已為您的 Office 365 環境。 
    
- 您是全域系統管理員或 Office 365 的安全性系統管理員。
    
## <a name="create-a-new-activity-policy"></a>建立新的活動原則

1. 以全域管理員或安全性管理員中，移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。 <br>這會帶您前往 Office 365 雲端 App 安全性原則] 頁面上。<br>![當您移至 Office 365 雲端 App 安全性入口網站時，您以啟動 [原則] 頁面](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
2. 按一下 [**建立原則**]，然後選取 [**活動原則**。<br>![當您建立原則 O365 CAS 中時，您可以選擇之間的活動原則和異常偵測原則。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
3. 在 [**建立活動原則**] 頁面上，指定**原則名稱**與**描述**。 若要依據您的原則的預設範本上，選擇其中一個的**原則範本**] 清單中，或建立您自己的原則，而不使用範本。<br>![您可以使用 Office 365 雲端 App 安全性建立活動原則。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
4. 選擇 [**原則嚴重性**（低、 中或高） 來測量如何嚴重是您如果此原則會觸發警示。 這可協助您篩選提醒，當您在稍後檢閱它們。 
    
5. 選擇**類別**，此原則。 這可協助您篩選和排序提醒已被觸發，或當您要檢閱這些變更的群組原則。 
    
6. 若要設定其他動作或就會觸發警示根據此原則的計量，請選擇 [**活動篩選**]。 
    
7. 在 [**活動符合參數**，指定是否將觸發原則違規情形，當單一活動符合篩選器，或指定的數目的重複的活動，都必須先警示的觸發程序。<br>如果您選取 [**重複活動**，指定的活動，在時間範圍，以及是否違規會計算特定應用程式內的使用者，或透過任何應用程式相同的使用者。
    
8. 或者，您可以選取**建立警示**來建立其他提醒給該原則 （透過電子郵件、 文字訊息，或兩者） 中會收到通知。<br>**請確定您的電子郵件提供者不會封鎖寄件者的電子郵件`no-reply@cloudappsecurity.com`**。 
  
9. 選擇 [擱置使用者或要求使用者再次登入 Office 365 應用程式就會觸發警示時應採取的**動作**。 
    
10. 選擇 [**建立**] 以完成建立您的原則。 
    
## <a name="next-steps"></a>後續步驟

- [異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [將 SIEM 伺服器整合](integrate-your-siem-server-with-office-365-cas.md)
    
- [檢閱並採取相應動作提醒](review-office-365-cas-alerts.md)
    
- [您的 IP 位址，以簡化管理群組](group-your-ip-addresses-in-ocas.md)
    

