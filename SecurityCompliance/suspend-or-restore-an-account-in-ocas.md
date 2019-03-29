---
title: 暫停或還原 Office 365 雲端 App 安全性中的使用者帳戶
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Office 365 雲端 App 安全性，您可以採取的控管動作有擱置或 unsuspend 的使用者帳戶。 '
ms.openlocfilehash: 10da1385f850fadf077b4e3f9e3a00e9e4629fdd
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862445"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>暫停或還原 Office 365 雲端 App 安全性中的使用者帳戶

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps)<br/> |
   
假設您收到警示的 Office 365 組織的使用者帳戶的其中一個已遭洩露。 或者，假設您收到警示，指出有問題的使用者帳戶。 與 Office 365 雲端 App 安全性，您可以暫停的使用者帳戶，並稍後再將它還原後已經調查您收到的警示。
  
> [!NOTE]
> Office 365 雲端 App 安全性是在 Office 365 企業版 E5。 如果您的組織要使用另一個 Office 365 企業版訂閱，能以附加元件形式購買 Office 365 雲端 App 安全性。 (以全域管理員，在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;合規性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)並[購買或編輯商務用 Office 365 的附加元件](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>若要擱置 Office 365 雲端 App 安全性中的使用者帳戶

當您暫停的使用者帳戶時，您會防止使用者再次登入。 它是與編輯直接在若要將登入狀態設為**登入已封鎖**的 Office 365 中的使用者帳戶相同。
  
> [!NOTE]
> 如果您封鎖使用者登入 Office 365，以暫停它們或編輯其登入狀態，請注意，可能需要一小時或動作才能生效的所有使用者的裝置和用戶端 （[編輯或變更 Office 365 中的使用者](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)） 上。 如果使用者登入 Office 365 時，封鎖就會生效，每當 Office 365 需要再次登入。 
  
1. 以[全域管理員或安全性系統管理員](permissions-in-the-security-and-compliance-center.md)，請移至[https://protection.office.com](https://protection.office.com)並使用您的公司或學校帳戶登入。 (這會帶您前往安全性&amp;合規性中心。) 
    
2. 安全性&amp;合規性中心，選擇 [**提醒** \> **管理進階提醒**。
    
3. 選擇 [**移至 Office 365 雲端 App 安全性**。<br>![安全性&amp;合規性中心，選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>
  
4. 在跨螢幕頂端導覽列中，選擇 [**提醒**]。
    
5. 在 [**提醒**] 欄中，連按兩下 [適用於特定的使用者帳戶的警示。 
    
6. **帳戶**] 下的 [在 [**狀態**] 欄中，選擇 [設定![設定] 圖示](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **暫停使用者**。
    
## <a name="to-restore-a-user-account"></a>若要還原的使用者帳戶

請參閱[還原 Office 365 中的使用者](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)
  
## <a name="next-steps"></a>後續步驟

- [檢閱並對 Office 365 雲端 App 安全性中的警示採取動作](review-office-365-cas-alerts.md)
    
- [使用 Office 365 雲端 App 安全性管理 OAuth 應用程式](manage-app-permissions-in-ocas.md)
    
- 檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)
    

