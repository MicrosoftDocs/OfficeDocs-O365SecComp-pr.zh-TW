---
title: 開啟 Office 365 雲端 App 安全性
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
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: 閱讀本篇文章以了解如何在 Office 365 雲端 App 安全性，提供雲端 App 安全性，在 Microsoft Azure 中開啟。
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264125"
---
# <a name="turn-on-office-365-cloud-app-security"></a>開啟 Office 365 雲端 App 安全性
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |您在此處 ！  <br/> [下一步](activity-policies-and-alerts.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a>開啟 Office 365 雲端 App 安全性

> [!IMPORTANT]
> 您必須是全域系統管理員或安全性系統管理員可執行下列工作。 若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 為了讓 Office 365 雲端 App 安全性運作正確，**必須開啟稽核記錄功能**適用於 Office 365 環境。 如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。 
  
1. 以全域管理員或安全性管理員中，移至[https://protection.office.com](https://security.microsoft.com)和 Office 365 使用公司或學校帳戶登入。 (這會帶您前往安全性&amp;合規性中心。) 
    
2. 前往 [**提醒** \> **管理進階提醒**。
    
3. 選取 [**開啟 Office 365 雲端 App 安全性**]。
    
4. 選擇 [**移至 Office 365 雲端 App 安全性**。<br/>![安全性&amp;合規性中心，選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>這將帶您至 Office 365 雲端 App 安全性入口網站，您可以在其中檢視報表和建立或編輯您的原則。

您已開啟 Office 365 雲端 App 安全性後，您可以造訪移至 Cloud App Security 入口網站[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)與登入。
    
> [!NOTE]
> 當您開啟 Office 365 雲端 App 安全性時，您的 Office 365 使用者帳戶和使用者活動的稽核資訊會被轉接至[Microsoft Cloud App Security](https://aka.ms/whatiscas)。 這可讓 Office 365 來提供進階的提醒、 篩選和其他功能，因此您可以取得資訊並採取動作的相關可疑活動。 
  
## <a name="next-steps"></a>後續步驟

- [活動原則](activity-policies-and-alerts.md)
    
- [異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [將 SIEM 伺服器整合](integrate-your-siem-server-with-office-365-cas.md)
    
- [您的 IP 位址，以簡化管理群組](group-your-ip-addresses-in-ocas.md)
    

