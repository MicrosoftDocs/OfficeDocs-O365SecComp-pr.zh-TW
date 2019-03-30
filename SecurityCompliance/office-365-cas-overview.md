---
title: Overview of Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 雲端 App 安全性可讓您深入了解可疑的活動在 Office 365 中，您可以調查可能有問題且，如有需要採取動作來解決安全性問題的情況。 '
ms.openlocfilehash: 960e4c75a4da13e1a0365f75d290cd18587abd58
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001206"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Overview of Office 365 Cloud App Security
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|您在此處 ！  <br/> [下一步](get-ready-for-office-365-cas.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Office 365 雲端 App 安全性是在 Office 365 企業版 E5。 如果您的組織要使用另一個 Office 365 企業版訂閱，能以附加元件形式購買 Office 365 雲端 App 安全性。 (以全域管理員，在 Microsoft 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)並[購買或編輯商務用 Office 365 的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。 
  
Office 365 雲端 App 安全性能讓您洞悉可疑活動在 Office 365 中，您可以調查可能有問題且，如有需要採取動作來解決安全性問題的情況。 與 Office 365 雲端 App 安全性，您可以接收的典型或可疑活動的觸發警示的通知，請參閱 < 如何在 Office 365 中的貴組織的資料存取和使用，暫停一直發生可疑活動的使用者帳戶，且需要當使用者在登入 Office 365 應用程式之後觸發警示。 閱讀本篇文章以取得 Office 365 雲端 App 安全性功能的概觀。
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>如何尋找 Office 365 雲端 App 安全性入口網站

> [!NOTE]
> 若要存取 Office 365 雲端 App 安全性入口網站，您必須是 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取者。 若要深入了解，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。 
  
您可以透過 Office 365 雲端 App 安全性入口網站以移至[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)與登入。 

您也可以取得那里從 Office 365 安全性&amp;合規性中心。 以下是一個很好的方法：
  
1. 移至 [[https://protection.office.com](https://protection.office.com)和 Office 365 使用公司或學校帳戶登入。 (這會帶您前往安全性&amp;合規性中心。)
    
2. 安全性&amp;合規性中心，選擇 [**提醒** \> **管理進階提醒**。 <br/>![選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>（如果尚未啟用 Office 365 雲端 App 安全性，而您是全域系統管理員，[開啟 [Office 365 雲端 App 安全性](turn-on-office-365-cas.md)）。
    
3. 選擇 [**移至 Office 365 雲端 App 安全性**。 
    
## <a name="policies"></a>原則

Office 365 雲端 App 安全性適用於為組織定義的原則。 與 Office 365 雲端 App 安全性，您的組織會取得許多預先定義的異常偵測原則及數個活動原則範本。 這些原則被設計用於偵測一般異常行為，找出使用者登入風險的 IP 位址從、 偵測勒索軟體活動，偵測從非公司的 IP 位址和更多的系統管理員活動。
  
![在 CAS 入口網站中，選擇 [控制項]\>若要檢視或建立原則範本的範本](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
檢視/使用原則範本，在 Office 365 雲端 App 安全性入口網站，移至**控制項** \> **範本**。 
  
![在 O365 CAS 入口網站中，選擇控制項](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
若要深入了解關於原則的詳細資訊，請參閱下列資源：
  
- [Office 365 雲端 App 安全性中的活動原則和警訊](activity-policies-and-alerts.md)
    
- [Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>警示

當已定義原則時，提醒通知您所偵測到可疑或典型活動。 若要檢視您組織的提醒，請選擇**提醒**在導覽列中跨螢幕頂端。 
  
![在 [提醒] 頁面中，您可以看到所觸發的警示和採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
為會觸發警訊您可以檢閱若要深入了解什麼事。 然後，如果仍然可疑活動，您可以採取動作。 例如，您可以通知使用者有關的問題，暫停從登入 Office 365 使用者或要求使用者在登入 Office 365 應用程式。
  
若要深入了解提醒，請參閱下列資源：
  
- [Office 365 雲端 App 安全性中的活動原則和警訊](activity-policies-and-alerts.md)
    
- [Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [檢閱並對 Office 365 雲端 App 安全性警示採取動作](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>活動記錄檔

在活動記錄檔] 頁面上，Office 365 雲端 App 安全性中檢視使用者活動的相關資訊。
  
![在 O365 CAS 入口網站中，選擇 [Investigate\>活動記錄檔](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
若要前往此頁面上，在 Office 365 雲端 App 安全性入口網站中，前往 [**調查** \> **活動記錄檔**。 
  
![在 O365 CAS 入口網站中，選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
您可以使用 Office 365 雲端 App 安全性，太使用您網站的流量記錄。 更多詳細資料中所包含的記錄檔，您將有較佳的可見性使用者活動。 您可以使用從 Barracuda、 藍色外覆、 檢查點、 Cisco、 Clavister、 Dell SonicWALL、 Fortinet、 杜、 McAfee、 Microsoft、 Palo 琴奧圖、 Sophos、 Squid、 Websence、 Zscaler，和更多的記錄檔。
  
[了解網頁流量記錄檔與資料來源的 Office 365 雲端 App 安全性](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>OAuth 應用程式

與 Office 365 雲端 App 安全性，您可以允許或防止您的組織使用協力廠商應用程式存取 Office 365 中的資料中的人員。
  
![O365 CAS 中您可以從調查] 功能表存取 [管理 OAuth 應用程式] 頁面。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
若要前往此頁面上，移至**Investigate** \> **OAuth 應用程式**。 
  
![在 O365 CAS 入口網站中，選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[使用 Office 365 雲端 App 安全性管理 OAuth 應用程式](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>雲端探索儀表板

**雲端探索儀表板**，也稱為**產能應用程式探索**，顯示組織內的雲端應用程式使用狀況的相關資訊。 您可以檢視應用程式、 使用者、 流量、 交易，並請使用此儀表板的相關資訊。 在雲端探索儀表板的格式類似於下列影像： 
  
![在 Office 365 CAS 入口網站中，選擇 [探索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要取得此儀表板，在 Office 365 雲端 App 安全性入口網站中，前往 [**探索** \> **雲端探索儀表板**。 
  
![在 Office 365 CAS 入口網站中，選擇 [探索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[檢閱 Office 365 雲端 App 安全性中的 App 探索結果](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>後續步驟

- 取得[Office 365 雲端 App 安全性使用情況和使用狀況指南](https://aka.ms/O365CASGuide)
    
- [準備好使用 Office 365 雲端 App 安全性](get-ready-for-office-365-cas.md)
    

