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
description: 使用 Office 365 雲端應用程式安全性提醒] 頁面上檢視潛在的問題，採取的動作。您可以關閉或解析提醒，並如有必要，擱置的使用者帳戶。
ms.openlocfilehash: 6c2f9788cb238e86abc347a3a118eb08fa84e971
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213163"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>檢閱並對 Office 365 雲端 App 安全性中的警示採取動作
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
   
您可以使用 Office 365 雲端應用程式安全性的提醒] 頁面上檢視潛在的問題和必要時，採取動作。
  
> [!NOTE]
> 您必須是讓全域管理員或安全性管理員執行本文中的工作。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="how-to-get-to-the-alerts-page"></a>如何取得提醒] 頁面上

1. 移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。
  
2. 在不同螢幕頂端導覽列中，選擇 [**提醒**]。<br/>![在 [提醒] 頁面中，您可以看到所觸發的警告與採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a>檢閱及控點提醒

提醒可協助您識別您要進一步調查的 Office 365 雲端環境中的活動。您也可以決定建立新的原則或編輯現有的原則根據您會看到提醒。例如，如果您看到從怪異位置登入系統管理員，您可能會決定防止從特定位置登入 Office 365 系統管理員的原則設定。
  
> [!TIP]
> 您可以篩選提醒依**類別**] 或 [依**嚴重性**讓您可以先管理最重要的。 
  
針對每個通知中，尋找到項目會造成它讓您可以決定要採取的動作。若要查看通知的更多詳細資料，並採取動作，例如解決警示或暫止的使用者帳戶，選擇 [開啟詳細資料] 頁面上的提醒。在詳細資料] 頁面上，您可以檢閱活動記錄檔、 帳戶及使用者的相關警示中，並採取下列動作：
  
- **關閉**如果警示誤判，關閉它。您可以選擇性地新增註解解釋解除為何。 
    
- **解決通知**如果所觸發提醒您知道活動不是威脅、 加以解決。您可以選擇性地新增註解解釋解析為何。 
    
- **暫停**如果您認為未經授權的登入帳戶，例如某人時您知道該名人員從另一個國家 （地區） 登入集實際位於本機 office 時，您還可以[暫停帳戶](suspend-or-restore-an-account-in-ocas.md)時您調查什麼下來的動作。 
    
## <a name="next-steps"></a>後續步驟

- [調查活動](investigate-an-activity-in-office-365-cas.md)
    
- [擱置或還原使用者帳戶](suspend-or-restore-an-account-in-ocas.md)
    
- 檢視支援的[網頁流量記錄檔與資料來源](web-traffic-logs-and-data-sources-for-ocas.md)的清單
    
- 檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)
    

