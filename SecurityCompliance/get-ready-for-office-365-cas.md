---
title: 準備好使用 Office 365 雲端 App 安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 開始使用 Office 365 雲端應用程式安全性
ms.openlocfilehash: 906570c6607c70b63fa9d2059d56b50f7807124a
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229985"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>準備好使用 Office 365 雲端 App 安全性
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |您在此處 ！  <br/> [下一步](turn-on-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
若要開啟並實作您的組織的 Office 365 雲端應用程式安全性 （前身為進階安全性管理） 準備時，有幾點事項。使用本文做指南以規劃 Office 365 雲端應用程式安全性。
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>步驟 1： 識別及保護您的通用和安全性管理員帳戶

全域管理員、 安全性管理員及安全性讀取者可以存取 Office 365 雲端應用程式安全性入口網站來檢視原則、 檢閱提醒，並使用報告。全域管理員與安全性管理員可以定義原則並採取其他動作來保護您的組織。(如需詳細資訊，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。)檢閱您的組織擁有萬一提高權限的使用者帳戶。 
  
 **[保護您的 Office 365 全域管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>步驟 2： 開啟稽核記錄您的組織

Office 365 雲端應用程式安全性運作正確的順序，必須先開啟稽核記錄功能。這通常是由 Exchange Online 管理員或全域管理員。
  
 **[開啟 Office 365 稽核記錄搜尋開啟或關閉](turn-audit-log-search-on-or-off.md)**。 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>步驟 3： 移至 Office 365 雲端應用程式安全性入口網站

1. 移至 [[https://protection.office.com](https://protection.office.com)及使用 Office 365 工作或學校帳戶登入。(這會引導您安全性&amp;規範中心。) 
    
2. 移至 [**提醒** \> **管理進階提醒**。
    
3. 選擇 [移至 Office 365 雲端應用程式安全性入口網站的 [**移至 Office 365 雲端應用程式安全性**]。 
    
    ![安全性&amp;規範中心選擇管理進階警告移至 Office 365 雲端應用程式安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    當您移至 Office 365 雲端應用程式安全性入口網站時，您會看到的第一頁為下列影像的格式類似於 [原則] 頁面上：
    
    ![當您移至 Office 365 雲端應用程式安全性入口網站時，啟動 [原則] 頁面上](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>步驟 4： 定義原則和設定提醒&amp;動作

全域管理員與安全性管理員定義原則 Office 365 雲端應用程式安全性。在定義原則的過程中，提醒及動作也都會設。提醒是條件式或的通知出現在檢視中透過電子郵件傳送。 
  
有兩種類型的 Office 365 雲端應用程式安全性的警示： 偵測可疑活動的異常偵測警示和活動通知，因為這可能是您的組織公休活動定義。提醒通知全域管理員與安全性管理員在您為您的組織不尋常的 Office 365 環境中有活動時。
  
請參閱下列資源以深入了解：
  
- [Office 365 雲端 App 安全性中的活動原則和警訊](activity-policies-and-alerts.md)
    
- [Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [檢閱並在 Office 365 雲端應用程式安全性警訊採取動作](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a>步驟 5︰ 了解您組織的雲端流量

以全域管理員、 安全性管理員或安全性讀者，您可以了解您組織的雲端用法透過報告和雲端探索儀表板 （也稱為產能應用程式探索）。此儀表板顯示使用者、 應用程式、 網頁流量及風險層級的相關資訊。
  
![在 Office 365 CAS 入口網站中選擇 [搜索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要移至 [產能應用程式探索儀表板的 Office 365 雲端應用程式安全性入口網站中選擇 [**搜索** \> **雲端探索儀表板**。
  
![在 Office 365 CAS 入口網站中選擇 [搜索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
若要填入您所需的資訊的報表上, 傳記錄檔從您的組織防火牆及 proxy。若要深入了解，請參閱下列資源：
  
- [在 Office 365 雲端應用程式安全性中建立應用程式探索報告](create-app-discovery-reports-in-ocas.md)
    
- [檢閱 Office 365 雲端 App 安全性中的 App 探索結果](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a>步驟 6： 管理您的組織用來存取 Office 365 的應用程式

以全域管理員或安全性管理員，您可以管理應用程式，例如自訂應用程式或協力廠商應用程式] 與 Office 365 其裝置上使用您的組織中的人員。例如，假設某人已下載他們想要搭配 Office 365 使用的自訂應用程式。您可以檢閱人員所使用的應用程式、 禁止不受信任的應用程式]，或將應用程式標示為已核准追蹤用途。[管理應用程式使用 Office 365 雲端應用程式安全性的權限](manage-app-permissions-in-ocas.md)。
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a>步驟 7： 使用 SIEM 伺服器與 Office 365 雲端應用程式安全性

您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器吗？Office 365 雲端應用程式安全性現在可以整合與 SIEM 伺服器若要啟用集中式監控的提醒。整合和 SIEM 服務可讓您更妥善地保護您的雲端應用程式時維護您的一般安全性工作流程、 自動化安全性程序及相互關聯有所助益之間雲端和內部事件。SIEM 代理程式會在您的伺服器上執行、 從 Office 365 雲端應用程式安全性] 提取提醒及入 SIEM 伺服器串流傳送這些通知。請參閱[Office 365 雲端應用程式安全性 SIEM 整合](integrate-your-siem-server-with-office-365-cas.md)。
  
## <a name="next-steps"></a>後續步驟

- [開啟 Office 365 雲端 App 安全性](turn-on-office-365-cas.md)
    
- 嘗試實機操作的體驗您可以在此示範強大功能的 Office 365 雲端應用程式安全性及建立概念證明我們[測試實驗室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)。 
    

