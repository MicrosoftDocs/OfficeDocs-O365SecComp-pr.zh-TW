---
title: Office 365 雲端 App 安全性概觀
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 雲端應用程式安全性可讓您算可疑活動在 Office 365 中讓您可以調查可能有問題且，如果需要採取動作可解決安全性問題的情況。 '
ms.openlocfilehash: edce16edca822bed30c78f34cf141b23f2b2fb8c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2019
ms.locfileid: "29382546"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Office 365 雲端 App 安全性概觀
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|您在此處 ！  <br/> [下一步](get-ready-for-office-365-cas.md) <br/> |[開始規劃](get-ready-for-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> 在 Office 365 企業版 E5 中使用 office 365 雲端應用程式安全性。如果貴組織要使用另一個 Office 365 企業版訂閱，可做為附加元件購買 Office 365 雲端應用程式安全性。(全域管理員在 Office 365 系統管理中心中，選擇 [**計費** \> **新增訂閱**。)如需詳細資訊，請參閱[Office 365 平台服務說明： Office 365 安全性&amp;規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[購買或編輯企業版的 Office 365 的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。 
  
Office 365 雲端應用程式安全性可讓您深入了解可疑活動在 Office 365 中讓您可以調查可能有問題且，如果需要採取動作可解決安全性問題的情況。與 Office 365 雲端應用程式安全性] 您可以接收通知的公休或可疑活動的觸發提醒，請參閱如何在 Office 365 組織的資料是存取和使用擱置呈現可疑活動的使用者帳戶，且需要若要重新登入 Office 365 應用程式之後觸發通知使用者。請閱讀本篇文章以取得 Office 365 雲端應用程式安全性特性與功能的概觀。
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>如何尋找 Office 365 雲端應用程式安全性入口網站

> [!NOTE]
> 若要存取 Office 365 雲端應用程式安全性入口網站，您必須是 Office 365 全域管理員、 安全性管理員或安全性讀者。若要深入了解，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
您可以取得 Office 365 雲端應用程式安全性入口網站移至[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)及登入。 

您也可以取得那里從 Office 365 安全性&amp;規範中心。以下是執行它的其中一個好方法：
  
1. 移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。)
    
2. 安全性&amp;規範中心選擇**提醒** \> **管理進階提醒**。 <br/>![選擇 [管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>（如果尚未未啟用 Office 365 雲端應用程式安全性，而且會[開啟 [Office 365 雲端應用程式安全性](turn-on-office-365-cas.md)全域系統管理員）。
    
3. 選擇 [**移至 Office 365 的雲端應用程式安全性**]。 
    
## <a name="policies"></a>Policies

Office 365 雲端應用程式安全性適用於您組織所定義的原則。與 Office 365 雲端應用程式安全性]，您的組織會取得許多預先定義的異常偵測原則與數個活動的原則範本。這些原則的設計被用來偵測一般異常、 識別 risky 的 IP 位址從登入的使用者、 偵測 ransomware 活動、 偵測來自非公司的 IP 位址和更多的系統管理員活動。
  
![CAS 入口網站中選擇 [控制\>來檢視或建立原則範本的範本](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
檢視/使用中的 Office 365 雲端應用程式安全性入口網站原則範本，請移至**控制項** \> **範本**。 
  
![在 O365 CAS 入口網站中選擇控制項](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
若要深入了解原則，請參閱下列資源：
  
- [Office 365 雲端 App 安全性中的活動原則和警訊](activity-policies-and-alerts.md)
    
- [Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>警報

時所定義的原則，提醒通知您需可疑或公休所偵測到的活動。若要檢視您組織的提醒，請選擇**提醒**導覽列中不同螢幕頂端。 
  
![在 [提醒] 頁面中，您可以看到所觸發的警告與採取任何動作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
當觸發提醒您可以檢閱若要深入了解的項目將要。然後，若仍可疑活動，您可以採取動作。例如，您可以通知使用者有關問題，暫停登入 Office 365 中的使用者或需要使用者再次登入 Office 365 應用程式。
  
若要深入了解提醒，請參閱下列資源：
  
- [Office 365 雲端 App 安全性中的活動原則和警訊](activity-policies-and-alerts.md)
    
- [Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [檢閱並在 Office 365 雲端應用程式安全性警訊採取動作](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>活動記錄檔

在 Office 365 雲端應用程式安全性您活動記錄檔] 頁面上檢視使用者活動的相關資訊。
  
![在 O365 CAS 入口網站中選擇 [調查\>活動記錄檔](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
若要取得這個] 頁面上，在 Office 365 雲端應用程式安全性入口網站中移至**調查** \> **活動記錄檔**。 
  
![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
您可以使用 web 流量記錄檔太與 Office 365 雲端應用程式安全性]。更多詳細資料中所包含的記錄檔，必須將使用者活動的較佳的可見性。您可以使用 Barracuda、 藍色外覆、 檢查點、 Cisco、 Clavister、 Dell SonicWALL、 Fortinet、 Juniper、 McAfee、 Microsoft、 Palo Alto、 Sophos、 Squid、 Websence、 Zscaler、 及更多的記錄檔案。
  
[了解網頁流量記錄檔與資料來源的 Office 365 雲端應用程式安全性](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>OAuth 應用程式

與 Office 365 雲端應用程式安全性]，您可以允許或防止使用協力廠商應用程式存取 Office 365 中的資料在組織中的人員。
  
![O365 CAS 中您可以從調查] 功能表存取 [管理 OAuth 應用程式] 頁面。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
若要取得這個] 頁面上，移至**調查** \> **OAuth 應用程式**。 
  
![在 O365 CAS 入口網站中選擇 [調查]。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[使用 Office 365 雲端 App 安全性管理 OAuth 應用程式](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>雲端探索儀表板

**雲端探索儀表板**，又稱為**產能應用程式探索**，顯示組織內的雲端應用程式使用方式的相關資訊。您可以檢視應用程式、 使用者、 流量、 交易，以及其他使用此儀表板的相關資訊。雲端探索儀表板的格式類似於下列影像： 
  
![在 Office 365 CAS 入口網站中選擇 [搜索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要取得此儀表板，在 Office 365 雲端應用程式安全性入口網站中移至 [**搜索** \> **雲端探索儀表板**。 
  
![在 Office 365 CAS 入口網站中選擇 [搜索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[檢閱 Office 365 雲端 App 安全性中的 App 探索結果](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>後續步驟

- 取得[Office 365 雲端應用程式安全性使用案例] 和 [使用狀況指南](https://aka.ms/O365CASGuide)
    
- [準備好使用 Office 365 雲端 App 安全性](get-ready-for-office-365-cas.md)
    

