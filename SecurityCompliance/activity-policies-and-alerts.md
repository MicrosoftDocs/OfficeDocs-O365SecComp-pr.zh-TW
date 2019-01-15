---
title: Office 365 雲端 App 安全性中的活動原則和警訊
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 定義活動原則與 Office 365 雲端應用程式的安全性設定以特定活動發生或太常發生時觸發提醒。藉由設定原則以觸發提醒，您可通知及監視特定的活動。
ms.openlocfilehash: 6f5039d09dea98de970ab4bd28e95a6cfad73db4
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015005"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性中的活動原則和警訊

Office 365 進階安全性管理現在是 Office 365 雲端應用程式安全性。
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](anomaly-detection-policies-in-ocas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
與 Office 365 雲端應用程式安全性] 進階的雲端管理的原則會觸發發生或太常發生特定活動的提醒。例如，假設使用者嘗試登入 Office 365 和一分鐘內 70 時間會失敗。假設另一位使用者下載 7000 檔案，或出現在進行登入加拿大，當使用者應該要放在另一個位置。或糟的是，假設已遭洩露某個人的帳戶，而且攻擊者使用該帳戶存取您的組織的雲端應用程式和機密資料。
  
如果您是在[全域管理員或安全性管理員](permissions-in-the-security-and-compliance-center.md)、 活動提醒通知您時事件 like 這些發生。您可以採取例如直到調查有何擱置的使用者帳戶的特定動作。
  
> [!NOTE]
> Office 365 雲端應用程式安全性原則是不同[警示 Office 365 安全性原則&amp;規範中心](alert-policies.md)。活動本文所述的原則在 Office 365 雲端應用程式安全性入口網站中所定義及可協助您更有效管理組織的雲端環境。 
  
## <a name="before-you-begin"></a>開始之前

請確定：
  
- 您的組織具有[Office 365 雲端應用程式安全性](office-365-cas-overview.md)] 和服務已[開啟](turn-on-office-365-cas.md)。
    
- [稽核記錄](turn-audit-log-search-on-or-off.md)已開啟的 Office 365 環境。 
    
- 您已為全域管理員或 Office 365 的安全性管理員。
    
## <a name="create-a-new-activity-policy"></a>建立新的活動原則

1. 以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)並使用您工作或學校的帳戶登入。 
    
2. 安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。
    
3. 選擇 [**移至 Office 365 的雲端應用程式安全性**]。
    
    這會帶您至 [Office 365 雲端應用程式的安全性原則] 頁面上。
    
    ![當您移至 Office 365 雲端應用程式安全性入口網站時，啟動 [原則] 頁面上](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
4. 按一下 [**建立原則**]，然後選取 [**活動原則**。
    
    ![當您建立原則 O365 CAS 中時，您可以選擇活動原則與異常偵測原則之間。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
5. 在 [**建立活動原則**] 頁面上指定**原則名稱**和**描述**。若要根據預設範本您的原則，選擇 [**原則範本**] 清單中的其中一種或不使用範本建立您自己的原則。 
    
    ![您可以建立活動原則與 Office 365 雲端應用程式安全性。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
6. 選擇 [**原則嚴重性**（Low、 Medium 或 High） 的措施如何嚴重很您如果此原則會觸發提醒。這可協助您篩選提醒時要檢閱其更新版本。 
    
7. 選擇此原則的**類別**。這可協助您篩選和排序已觸發提醒或群組原則您要檢閱其進行變更時。 
    
8. 若要設定其他動作或會觸發此原則為基礎的提醒的評量選擇**活動篩選器**。 
    
9. 在 [**活動符合參數**，指定是否原則違規會在單一活動符合篩選器] 時才會觸發或指定的數目的重複活動才之前警示的觸發程序。
    
    如果您選取 [**重複活動**，指定的時間圖文框的活動和是否違規會計算的特定應用程式內的使用者或任何應用程式的同一個使用者。
    
10. （選用） 您可以選取**建立通知**以建立其他的提醒從 （透過電子郵件、 文字訊息或兩者） 此原則會收到通知。 
    
    > [!IMPORTANT]
    > 請確定您的電子郵件供應商不會封鎖從 no-reply@cloudappsecurity.com 傳送的電子郵件。 
  
11. 選擇 [暫停使用者或需要一次登入 Office 365 應用程式的使用者就會觸發提醒時應採取的**動作**。 
    
12. 選擇 [**建立**] 完成建立您的原則。 
    
## <a name="next-steps"></a>後續步驟

- [異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [整合 SIEM server](integrate-your-siem-server-with-office-365-cas.md)
    
- [檢閱並採取行動提醒](review-office-365-cas-alerts.md)
    
- [群組簡化管理 IP 位址](group-your-ip-addresses-in-ocas.md)
    

