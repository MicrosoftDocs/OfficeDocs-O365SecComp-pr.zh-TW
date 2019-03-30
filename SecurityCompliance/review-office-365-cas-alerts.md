---
title: 檢閱並對 Office 365 雲端 App 安全性中的警示採取動作
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用 Office 365 雲端 App 安全性中的 [提醒] 頁面上，檢視潛在的問題，並採取動作。 您可以關閉或解決的警示，並如有必要，擱置的使用者帳戶。
ms.openlocfilehash: ddef10293fca7b722a13babdca5c05bbe2398cb3
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000036"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>檢閱並對 Office 365 雲端 App 安全性中的警示採取動作
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
   
您可以使用 Office 365 雲端 App 安全性中的 [提醒] 頁面上，檢視潛在的問題，並如有需要採取動作。
  
> [!NOTE]
> 您必須是全域系統管理員或安全性系統管理員來執行本文中的工作。 請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="how-to-get-to-the-alerts-page"></a>如何取得 [提醒] 頁面上

1. 移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。
  
2. 在跨螢幕頂端導覽列中，選擇 [**提醒**]。<br/>![在 [提醒] 頁面中，您可以看到所觸發的警示和採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
 
> [!NOTE]
> 雲端 App 安全性提醒也會顯示在安全性 & 合規性中心 (前往**提醒** > **檢視警示**。 目前，不過，您必須先解決這些 Cloud App Security 入口網站和安全性 & 合規性中心中的警示。 若要深入了解，請參閱[檢視 Cloud App Security 警示](alert-policies.md#viewing-cloud-app-security-alerts)）。 
 
## <a name="review-and-handle-alerts"></a>檢閱及控點通知

警示可協助您找出您可能想要更進一步調查與 Office 365 雲端環境中的活動。 您也可能決定要建立新的原則或編輯現有的原則，根據您看到的通知。 例如，如果您看到從怪異位置登入系統管理員，您可能決定設定防止系統管理員登入 Office 365 從特定位置的原則。
  
> [!TIP]
> 讓您可以先管理最重要的您可以篩選依**類別**] 或 [依**嚴重性**的警示。 
  
在每個警示，查看項目會導致它讓您可以決定要採取什麼動作。 若要查看警示的更多詳細資料，要採取的動作，例如解決警示或擱置的使用者帳戶，選擇 [若要開啟 [詳細資料] 頁面上警示。 在 [詳細資料] 頁面中，您可以檢閱活動記錄檔、 帳戶及警示，相關的使用者，並採取動作如下所示：
  
- **關閉**如果警示誤判，關閉它。 您可以選擇新增註解解釋您關閉的原因。 
    
- **解決警示**如果警示所觸發的活動，您知道不威脅、 加以解決。 您可以選擇性地新增說明為什麼您解決的註解。 
    
- **暫停**如果您懷疑未經授權的正負號的帳戶，例如某人時您知道該人員從另一個國家/地區登入集實際位於本機 office，您可以[暫停帳戶](suspend-or-restore-an-account-in-ocas.md)時，要調查什麼事。 
    
## <a name="next-steps"></a>後續步驟

- [調查活動](investigate-an-activity-in-office-365-cas.md)
    
- [暫停或還原使用者帳戶](suspend-or-restore-an-account-in-ocas.md)
    
- 檢視支援的[網頁流量記錄及資料來源](web-traffic-logs-and-data-sources-for-ocas.md)的清單
    
- 檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)
    

