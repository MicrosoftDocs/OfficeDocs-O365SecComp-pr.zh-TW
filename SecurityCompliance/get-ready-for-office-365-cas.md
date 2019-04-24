---
title: 準備好使用 Office 365 雲端 App 安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 開始使用 Office 365 雲端 App 安全性
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254010"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>準備好使用 Office 365 雲端 App 安全性
  
|評估 * *\>**|規劃 * *\>**|部署 * *\>**|使用率 * * *|
|:-----|:-----|:-----|:-----|
|[啟動評估](office-365-cas-overview.md) <br/> |您在此處 ！  <br/> [下一步](turn-on-office-365-cas.md) <br/> |[開始部署](turn-on-office-365-cas.md) <br/> |[開始使用](utilization-activities-for-ocas.md) <br/> |
   
當您準備來開啟，並為您的組織實作 Office 365 雲端 App 安全性，有一些事項需要考量。 使用本文做為指南，規劃 Office 365 雲端 App 安全性。
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>步驟 1： 識別和保護您的全域和安全性系統管理員帳戶

全域系統管理員、 安全性管理員和安全性讀取者可以存取檢視原則、 檢閱提醒，並使用報告在 Office 365 雲端 App 安全性入口網站。 全域系統管理員和安全性系統管理員可以定義原則，並採取其他動作，以保護您的組織。 (如需詳細資訊，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。)檢閱您的組織為了預防萬一，有更高權限的使用者帳戶。 
  
 **[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>步驟 2： 開啟稽核記錄為您的組織

為了讓 Office 365 雲端 App 安全性運作正確，必須先開啟稽核記錄。 這通常是由 Exchange Online 的系統管理員或全域系統管理員。
  
 **[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)**。 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>步驟 3： 移至 Office 365 雲端 App 安全性入口網站

您可以透過 Office 365 雲端 App 安全性入口網站以移至[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)與登入。 

您也可以取得那里從 Office 365 安全性&amp;合規性中心。 以下是一個很好的方法：

1. 移至 [[https://protection.office.com](https://protection.office.com)並登入。 (這會帶您前往安全性&amp;合規性中心。)
    
2. 前往 [**提醒** \> **管理進階提醒**。
    
3. 選擇 [移至 Office 365 雲端 App 安全性入口網站的 [**移至 Office 365 雲端 App 安全性**。<br> ![選擇 [管理進階提醒移至 Office 365 雲端 App 安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>當您移至 Office 365 雲端 App 安全性入口網站時，您會看到的第一頁會是下列影像的格式類似於 [原則] 頁面上：<br>![當您移至 Office 365 雲端 App 安全性入口網站時，您以啟動 [原則] 頁面](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>步驟 4： 定義原則並設定提醒&amp;動作

全域系統管理員和安全性系統管理員定義原則在 Office 365 雲端 App 安全性中。 在定義原則的過程中，警告與動作也會設定。 警示是標準為基礎的通知出現在檢視中或透過電子郵件傳送。 
  
有兩種類型的 Office 365 雲端 App 安全性中的警示： 偵測到可疑活動的異常偵測警示和活動警訊，所定義的可能是典型組織的活動。 Office 365 環境中，是為您的組織不尋常的活動時，警示通知全域系統管理員和安全性系統管理員。
  
請參閱若要了解更多的下列資源：
  
- [Office 365 雲端 App 安全性中的活動原則和警訊](activity-policies-and-alerts.md)
    
- [Office 365 雲端 App 安全性中的異常偵測原則](anomaly-detection-policies-in-ocas.md)
    
- [檢閱並對 Office 365 雲端 App 安全性警示採取動作](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a>步驟 5： 設定條件式存取應用程式控制

設定和強制執行組織的應用程式，根據特定條件，例如哪些使用者可以使用哪些應用程式上的控制項和位置。 定義使用者應用程式存取及工作階段原則，以判斷是否機密文件可以下載及加密，封鎖特定應用程式的存取，設定為唯讀模式的特定應用程式]，並將使用者工作階段限制從非公司網路。

請參閱若要了解更多的下列資源：

- [使用 Office 365 雲端 App 安全性條件式存取應用程式控制來保護應用程式](ocas-conditional-access-app-control.md)

- [為 Office 365 應用程式部署條件式存取應用程式控制](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a>步驟 6︰ 了解貴組織雲端使用方式

為全域系統管理員、 安全性系統管理員或安全性讀取者，您可以了解貴組織的雲端流量透過報告和雲端探索儀表板 （也稱為產能應用程式探索）。 這個儀表板會顯示使用者、 應用程式、 web 流量及風險層級的相關資訊。
  
![在 Office 365 CAS 入口網站中，選擇 [探索\>雲端探索儀表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要移至產能應用程式探索儀表板中的 Office 365 雲端 App 安全性入口網站中，選擇 [**探索** \> **雲端探索儀表板**。
  
![在 Office 365 CAS 入口網站中，選擇 [探索](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
若要填入報告與所需的資訊上, 傳您的記錄檔，從貴組織的防火牆和 proxy。 若要深入了解，請參閱下列資源：
  
- [在 Office 365 雲端 App 安全性建立 app 探索報表](create-app-discovery-reports-in-ocas.md)
    
- [檢閱 Office 365 雲端 App 安全性中的 App 探索結果](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a>步驟 7： 管理您的組織用來存取 Office 365 的應用程式

以全域管理員或安全性系統管理員，您可以管理應用程式，例如自訂應用程式或協力廠商應用程式，其與 Office 365 的裝置上使用您組織中的人員。 例如，假設有人已下載他們想要使用與 Office 365 的自訂應用程式。 您可以檢閱人員使用的應用程式、 禁止使用不受信任的應用程式，或將應用程式標示為核准您追蹤的目的。 [使用 Office 365 雲端 App 安全性管理 OAuth 應用程式](manage-app-permissions-in-ocas.md)。
  
## <a name="step-8-create-a-maintenance-plan"></a>步驟 8： 建立維護計劃

您已安裝並設定為 Office 365 雲端 App 安全性之後，您會想要做為 Office 365 全域系統管理員或組織的安全性管理員執行特定使用率工作。
藉由執行這些工作，您將會協助確定已正確設定 Office 365 雲端 App 安全性、 您的原則是最新狀態，且您的組織實現從 Office 365 的值。 使用本文做為指南，以協助您規劃這些工作。 [推出 Office 365 雲端 App 安全性後的使用率活動](utilization-activities-for-ocas.md)，請參閱。

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a>（選用）步驟 9： 使用 SIEM 伺服器與 Office 365 雲端 App 安全性

您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器？ Office 365 雲端 App 安全性，現在可以整合與 SIEM 伺服器啟用集中式監視的提醒。 整合與 SIEM 服務可讓您更妥善地維護您的一般安全性工作流程、 自動化安全性程序及助益之間雲端時保護您的雲端應用程式，以及內部事件。 SIEM 代理程式會在您的伺服器上執行、 提取提醒從 Office 365 雲端 App 安全性，並會那些警示串流傳送至 SIEM 伺服器。 請參閱[Office 365 雲端 App 安全性與 SIEM 整合](integrate-your-siem-server-with-office-365-cas.md)。
  
## <a name="next-steps"></a>後續步驟

- [開啟 Office 365 雲端 App 安全性](turn-on-office-365-cas.md)
    
- 請試著您可以在此示範 Office 365 雲端 App 安全性的強大功能，並建立的概念證明的實踐經驗我們[測試實驗室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)。 
    

