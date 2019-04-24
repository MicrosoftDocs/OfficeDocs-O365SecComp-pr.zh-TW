---
title: 使用 Office 365 雲端 App 安全性建立 App 探索報告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 使用 Office 365 雲端 App 安全性，可讓您了解您組織中的人員如何使用 Office 365 和其他應用程式來建立報告。
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259634"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>使用 Office 365 雲端 App 安全性建立 App 探索報告

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
   
Office 365 雲端 App 安全性，有助於全域系統管理員、 安全性系統管理員，並深入了解到組織中的人員所使用的雲端服務安全性讀取者。 例如，您可以看到其中使用者會儲存在文件上共同作業並多少資料上傳至應用程式或外部 Office 365 的服務。
  
若要產生應用程式探索報表，您手動上傳您的網頁流量記錄檔案，從您的防火牆和 proxy，然後並 Office 365 雲端 App 安全性剖析分析您的報表那些檔案。
  
> [!NOTE]
> 您必須是全域系統管理員、 安全性系統管理員或安全性讀取者若要執行本文所述的工作。 若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="create-a-report-with-app-discovery"></a>建立 app 探索報表

若要建立 app 探索報表，您可以識別您想要有分析，請選取記錄檔，然後再要求報告的記錄檔的廠商資料來源。
  
> [!NOTE]
> 使用包含尖峰流量期間，若要使用的最佳表示法取得貴組織中的 web 流量記錄檔。 
  
1. 收集[web 流量記錄檔和 Office 365 雲端 App 安全性的資料來源](web-traffic-logs-and-data-sources-for-ocas.md)。
    
2. 移至 Cloud App Security 入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com))，並登入。 
       
3. 選擇 [**探索** \> **建立新的報表**。 <br>![在 Office 365 CAS 入口網站中，選擇 [探索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. 指定的名稱和描述您的報表，，然後選取 [**資料來源**] 清單中的 [web 流量記錄檔的資料來源。 <br>![O365 CAS 中選擇 [探索\>建立新的報表](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>如果未列出您想要使用的資料來源，您可以要求，將它加入。 選取 [**其他****資料來源**，，，然後輸入您想要上傳的資料來源的名稱。 我們將檢閱記錄檔，並可讓您知道是否我們新增它產生的資料來源的支援。 
  
5. 瀏覽至您收集記錄檔的位置，並選取的檔案。 您所選擇的報告的資料來源必須已產生的記錄檔。
    
6. 按一下 [**建立**] 以啟動報表建立程序]。 
    
7. 若要查看報告的狀態，請按一下 [**管理快照報告**。 準備報表時，您會看到 [**檢視報告**] 選項。 
    
## <a name="next-steps"></a>後續步驟

- [檢閱並採取相應動作提醒](review-office-365-cas-alerts.md)
    
- [檢閱 Office 365 雲端 App 安全性中的 App 探索結果](review-app-discovery-findings-in-ocas.md)
    
- 檢閱您[的 Office 365 雲端 App 安全性的使用率活動](utilization-activities-for-ocas.md)
    

