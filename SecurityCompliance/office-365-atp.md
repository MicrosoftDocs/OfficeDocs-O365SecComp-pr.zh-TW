---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/09/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 進階威脅保護包含詐騙智慧、 安全的連結、 安全附件及進階的反網路釣魚功能。進階的威脅保護也要延伸至檔案的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組。
ms.openlocfilehash: e3b282118b5fde0374bb9f052e7efe8a13e2fd70
ms.sourcegitcommit: ba2175e394d0cb9f8ede9206aabb44b5b677fa0a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496857"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 進階威脅防護

Office 365 進階威脅保護 (ATP) 有幫助保護您的組織從惡意的攻擊：
  
- 掃描惡意程式碼[ATP 安全](atp-safe-attachments.md)附件的電子郵件的附件
    
- 掃描的網頁位址 (Url) 中的電子郵件及 Office 文件的[ATP 安全連結](atp-safe-links.md)
    
- 識別和封鎖與[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)線上文件庫中的惡意檔案
    
- 檢查未經授權詐騙[詐騙智慧](learn-about-spoof-intelligence.md)與電子的郵件
    
- 偵測當某人嘗試模擬您的使用者與您的組織與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)的自訂網域
    
**透過 Office 365 ATP 保護會由貴組織的安全性小組的安全連結、 安全附件及反網路釣魚定義的原則**。請務必定期檢閱並修改原則來保留其最新及才會加到服務的新功能的優點。[提供報告所](view-reports-for-atp.md)要顯示 ATP 組織的運作方式。這些報告也可顯示您您可能需要重新檢閱並更新您的原則的區域。而且，如果您有都會標記為惡意程式碼的不應該是相同網域或檔案您想要檢查的 Microsoft 的檔案，您可以[提交給 Microsoft 進行分析的檔案](#submit-a-suspicious-file-to-microsoft-for-analysis)。
      
## <a name="get-office-365-atp"></a>取得 Office 365 ATP

> [!IMPORTANT]
> Office 365 ATP 隨附於訂閱，例如 Microsoft 365 企業版、 Office 365 企業版 E5、 Office 365 教育版 A5，以及[Microsoft 365 Business](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc)。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅 Protection 服務說明](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx)。 

1. 為通用或安全性管理員，請移至[https://portal.office.com](https://portal.office.com)和登入 Office 365 您工作或學校的帳戶。 
    
2. 選擇 [**管理** \> **帳務**查看您目前的訂閱所包含的內容。 <br/>![全域管理員身分登入在 portal.office.com 並移至 [系統管理\>計費](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. 如果您看到**Office 365 企業版 E5**、 **Office 365 教育版 A5**或**Microsoft 365 Business**，您的組織有 ATP。 <br/>如果您看到不同的訂閱，例如**Office 365 企業版 E3**或**Office 365 企業版 E1**，請考慮新增 ATP。若要這樣做，選擇 [ **+ 新增訂閱**。
    
您有 ATP 下, 一步是為您的安全性小組來定義原則。 
  
## <a name="define-policies-for-atp"></a>為 ATP 定義原則

- **[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)** 包括模擬型攻擊以防止傳送電子郵件訊息的攻擊者顯示可從信任的人員或網域 

- **[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)** 包括您的組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
- **[Office 365 中的原則設定 ATP 安全附件](set-up-atp-safe-attachments-policies.md)** 內含[動態傳遞和預覽](dynamic-delivery-and-previewing.md)
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>請參閱 ATP 檢視報告的運作方式

ATP 原則已備妥之後，就有一個報表可用來顯示服務運作的方式。

[![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 請確定您是 Office 365 全域管理員、 安全性管理員或安全性讀者。(請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。)
    
2. [進階威脅保護的檢視報告](view-reports-for-atp.md)。
    
3. 是否需要進行調整您的安全性原則。請參閱下列資源：

  - [Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)
    
  - [Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
    
  - [Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>提交給 Microsoft 進行分析可疑的檔案

- 如果您收到您懷疑可能是惡意程式碼檔案，您可以提交給 Microsoft 進行分析該檔案。請造訪[Windows 防禦者安全性智慧提交入口網站](https://go.microsoft.com/fwlink/?linkid=857185)。

- 如果您要取得您想要提交給 Microsoft 進行分析的電子郵件訊息 （使用或不含附件），請使用[報告郵件增益集](enable-the-report-message-add-in.md)。 
  
## <a name="related-topics"></a>相關主題

[進階威脅保護的檢視報告](view-reports-for-atp.md)
  
[管理 Office 365 安全性威脅&amp;規範中心](threat-management.md)
  

