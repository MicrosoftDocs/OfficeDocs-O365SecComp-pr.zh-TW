---
title: 使用 Office 365 雲端 App 安全性建立 App 探索報表
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
description: 建立報表與 Office 365 雲端應用程式安全性可讓您了解如何在組織中的人員會使用 Office 365 和其他應用程式。
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220293"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>使用 Office 365 雲端 App 安全性建立 App 探索報表

|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |您在此處 ！  <br/> [後續步驟](#next-steps) <br/> |
   
Office 365 雲端應用程式安全性協助全域管理員、 安全性管理員及安全性讀者掌握人員在組織中的使用的雲端服務。例如，您可以看到其中使用者會儲存在文件上共同作業和資料量要上傳至應用程式或 Office 365 外部的服務。
  
若要產生的應用程式探索報表，您手動上傳您的網頁流量記錄檔案從防火牆及 proxy，並再 Office 365 雲端應用程式安全性會剖析分析報表這些檔案。
  
> [!NOTE]
> 您必須是執行本文所述的工作的全域管理員、 安全性管理員或安全性讀者。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="create-a-report-with-app-discovery"></a>應用程式探索與建立報告

若要建立的應用程式探索報表，您可以識別您想要有分析、 選取 [記錄檔，並請求報表的記錄檔的廠商資料來源。
  
> [!NOTE]
> 使用包含尖峰流量期間取得最佳的使用方式代表您組織中的網頁流量記錄檔案。 
  
1. 收集您的[網頁流量記錄檔與資料來源為 Office 365 雲端應用程式安全性](web-traffic-logs-and-data-sources-for-ocas.md)。
    
2. 移至雲端應用程式安全性入口網站 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 並登入。 
       
3. 選擇 [**搜索** \> **建立新的報表**。 <br>![在 Office 365 CAS 入口網站中選擇 [搜索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. 指定的名稱和描述您的報表，並在 [**資料來源**] 清單中選取 web 流量記錄檔的資料來源。 <br>![O365 CAS 中選擇 [搜索\>建立新的報表](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>如果未列出您想要使用的資料來源，您可以要求要新增。選取 [**其他****資料來源**，然後輸入 [您嘗試將上傳的資料來源的名稱。我們將檢閱記錄檔，並且可讓您知道是否我們將新增其產生的資料來源的支援。 
  
5. 瀏覽至您收集記錄檔的位置及選取的檔案。您選擇的報告的資料來源必須已產生記錄檔。
    
6. 按一下 [**建立**] 以啟動報表建立程序。 
    
7. 若要查看報告的狀態，請按一下 [**管理快照報告**]。準備報表時，您會看到 [**檢視報告**] 選項。 
    
## <a name="next-steps"></a>後續步驟

- [檢閱並採取行動提醒](review-office-365-cas-alerts.md)
    
- [檢閱 Office 365 雲端 App 安全性中的 App 探索結果](review-app-discovery-findings-in-ocas.md)
    
- 檢閱您[的 Office 365 雲端應用程式安全性使用率活動](utilization-activities-for-ocas.md)
    

