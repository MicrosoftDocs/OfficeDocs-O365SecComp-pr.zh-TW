---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 進階威脅保護包含詐騙智慧、 安全的連結、 安全附件及進階的反網路釣魚功能。進階的威脅保護也要延伸至檔案的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組。
ms.openlocfilehash: 6cdbdde2c91f8a9a77eb688ae27d509163da42a1
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769797"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 進階威脅防護

## <a name="overview"></a>概觀

Office 365 進階威脅保護 (ATP) 有幫助保護您的組織從惡意的攻擊：
  
- 掃描惡意程式碼[ATP 安全](atp-safe-attachments.md)附件的電子郵件的附件
    
- 掃描的網頁位址 (Url) 中的電子郵件及 Office 文件的[ATP 安全連結](atp-safe-links.md)
    
- 識別和封鎖與[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)線上文件庫中的惡意檔案
    
- 檢查未經授權詐騙[詐騙智慧](learn-about-spoof-intelligence.md)與電子的郵件
    
- 偵測當某人嘗試模擬您的使用者與您的組織與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)的自訂網域
    
**透過 Office 365 ATP 保護會由貴組織的安全性小組的安全連結、 安全附件及反網路釣魚定義的原則**。請務必定期檢閱並修改原則來保留其最新及才會加到服務的新功能的優點。 

[提供報告所](view-reports-for-atp.md)要顯示 ATP 組織的運作方式。這些報告也可顯示您您可能需要重新檢閱並更新您的原則的區域。而且，如果您有都會標記為惡意程式碼的不應該是相同網域或檔案您想要檢查的 Microsoft 的檔案，您可以[提交給 Microsoft 進行分析的檔案](#submit-a-suspicious-file-to-microsoft-for-analysis)。

## <a name="new-features-are-continually-being-added-to-atp"></a>ATP 持續所加入的新功能

我們會繼續新增至 Office 365 的新功能並包含 ATP。以下是一些新功能，其中有些呼叫在檢閱和更新 ATP 原則的清單。若要深入了解傳入 ATP （或在一般的 Microsoft 365） 的新功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。


|功能更新  |動作項目  |
|---------|---------|
|開始在年 10 月 2018年及後續的幾個月內啟用，當使用者使用 Outlook Web 應用程式 (OWA) 或 Outlook、 ATP 安全連結轉譯原始 Url 不會修正 Url。（我們呼叫此原生連結可見性）。|無         |
|開始在 9 月 2018年、 [Office 365 ATP 警告頁面](atp-safe-links-warning-pages.md)] 功能的新的色彩配置、 詳細資訊及能夠繼續而不管網站授與警告和建議。 |無         |
|從開始 2018年第二個半，ATP 安全連結保護會延伸至套用至 Office Online （線上 Word、 Excel Online、 PowerPoint Online 和 OneNote Online） 和 Office 365 ProPlus mac 上的 Url   |[檢閱並編輯 ATP 安全連結原則](set-up-atp-safe-links-policies.md)  |
|開始在落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能&amp;規範中心會被擴充至[ATP 的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組](atp-for-spo-odb-and-teams.md)。 |[檢閱並編輯 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md) |
|從開始年 3 月 2018年，ATP 安全連結保護會延伸至套用至組織內的人員之間所寄送的電子郵件。 |[檢閱並編輯 ATP 安全連結原則](set-up-atp-safe-links-policies.md) |
|從開始落後年 10 月 2017年，ATP 安全連結保護會延伸至 Url 中電子郵件時的 Url 是以套用至 Office 365 ProPlus 的文件，例如 Word、 Excel、 PowerPoint 及 Visio 在 Windows，以及 Office iOS 及 Android 裝置上的應用程式。  |請確定您使用[Office 的現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |

      
## <a name="get-office-365-atp"></a>取得 Office 365 ATP

Office 365 ATP 隨附於訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5，以及 Office 365 教育版 A5。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

## <a name="define-policies-for-atp"></a>為 ATP 定義原則

- **[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)** 包括模擬型攻擊以防止傳送電子郵件訊息的攻擊者顯示可從信任的人員或網域 

- **[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)** 包括您的組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
- **[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)** 選擇 [從數個選項 [[動態傳遞和預覽](dynamic-delivery-and-previewing.md)
  
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
  

