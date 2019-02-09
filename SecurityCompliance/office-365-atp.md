---
title: Office 365 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 進階威脅保護包含詐騙智慧、 安全的連結、 安全的附件、 進階的反網路釣魚功能及威脅智慧。
ms.openlocfilehash: 213b262b0ecc821b8f139b1b63568b2b03e635c5
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792248"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 進階威脅防護

## <a name="overview-of-office-365-advanced-threat-protection"></a>Overview of Office 365 的進階的威脅保護

Office 365 進階威脅保護 (ATP) 有幫助保護您的組織從惡意的攻擊：
  
- 掃描惡意程式碼[ATP 安全](atp-safe-attachments.md)附件的電子郵件的附件
    
- 掃描的網頁位址 (Url) 中的電子郵件及 Office 文件的[ATP 安全連結](atp-safe-links.md)
    
- 識別和封鎖與[SharePoint、 OneDrive 及 Microsoft 小組 ATP](atp-for-spo-odb-and-teams.md)線上文件庫中的惡意檔案
    
- 檢查未經授權詐騙[詐騙智慧](learn-about-spoof-intelligence.md)與電子的郵件
    
- 偵測當某人嘗試模擬您的使用者與您的組織與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)的自訂網域
    
**透過 Office 365 ATP 保護會由貴組織的安全性小組的安全連結、 安全附件及反網路釣魚定義的原則**。務必可以定義原則，並定期檢閱並修改這些原則保持其最新並採取加到服務的新功能的優點。 

[提供報告所](view-reports-for-atp.md)要顯示 ATP 組織的運作方式。這些報告也可顯示您您可能需要重新檢閱並更新您的原則的區域。而且，如果您有都會標記為惡意程式碼的不應該是相同網域或檔案您想要檢查的 Microsoft 的檔案，您可以[提交給 Microsoft 進行分析的檔案](#submit-a-suspicious-file-to-microsoft-for-analysis)。

## <a name="new-features-are-continually-being-added-to-atp"></a>ATP 持續所加入的新功能

我們會繼續新增至 Office 365 的新功能並包含 ATP。以下是一些新功能，其中有些呼叫在檢閱和更新 ATP 原則的清單。若要深入了解傳入 ATP （或在一般的 Microsoft 365） 的新功能，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。


|功能更新  |動作項目  |
|---------|---------|
|開始在年 2 月 2019年和後續的幾個月內啟用、 威脅智慧功能會被新增至 ATP。此外，如果您的組織目前沒有 ATP，您必須考量，新的選項包括 ATP 計劃 1 和 ATP 計劃 2。若要深入了解，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)與[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 |檢閱您的組織訂閱及如果需要[購買或編輯的附加元件](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。  |
|開始在年 10 月 2018年及後續的幾個月內啟用，當使用者使用 Outlook 或 Outlook Web 應用程式 (OWA)、 ATP 安全連結轉譯原始 Url 不會修正 Url。（我們呼叫此原生連結轉譯）。<br>當原生連結轉譯為可供您的組織時，這項功能將 Outlook 365 （按一下 [隨選） 和 OWA 中運作。|無         |
|開始在 9 月 2018年、 [Office 365 ATP 警告頁面](atp-safe-links-warning-pages.md)] 功能的新的色彩配置、 詳細資訊及能夠繼續而不管網站授與警告和建議。 |無         |
|從開始 2018年第二個半，ATP 安全連結保護會延伸至套用至 Office Online （線上 Word、 Excel Online、 PowerPoint Online 和 OneNote Online） 和 Office 365 ProPlus mac 上的 Url   |[檢閱並編輯 ATP 安全連結原則](set-up-atp-safe-links-policies.md)  |
|開始在落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能&amp;規範中心會被擴充至[ATP 的 SharePoint Online、 OneDrive for Business 和 Microsoft 小組](atp-for-spo-odb-and-teams.md)。 |[檢閱並編輯 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md) |
|從開始年 3 月 2018年，ATP 安全連結保護會延伸至套用至組織內的人員之間所寄送的電子郵件。 |[檢閱並編輯 ATP 安全連結原則](set-up-atp-safe-links-policies.md) |
|從開始落後年 10 月 2017年，ATP 安全連結保護會延伸至 Url 中電子郵件時的 Url 是以套用至 Office 365 ProPlus 的文件，例如 Word、 Excel、 PowerPoint 及 Visio 在 Windows，以及 Office iOS 及 Android 裝置上的應用程式。  |請確定您使用[Office 的現代驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |


      
## <a name="get-office-365-atp"></a>取得 Office 365 ATP

Office 365 ATP 隨附於訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5，以及 Office 365 教育版 A5。如果您的組織有不包含 Office 365 ATP Office 365 訂閱，可能可以做為附加元件購買 ATP。如需詳細資訊，請參閱[Office 365 進階威脅保護計劃和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅 Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

## <a name="define-policies-for-atp"></a>為 ATP 定義原則

若要定義 （或編輯） ATP 原則，您必須具有角色如下表所示的其中一個：

|角色  |Where/如何指派  |
|---------|---------|
|Office 365 全域管理員 |若要購買 Office 365 設定簽署者為預設的全域系統管理員。（請參閱若要深入了[解 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。         |
|安全性管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要深入了解角色和權限，請參閱[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。

有數種 ATP 原則來定義並定期檢閱。

1. **[設定 Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)** 包括模擬型攻擊以防止攻擊者傳送電子郵件訊息的顯示可從信任的人員或網域。 

2. **[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)** 包括您的組織[自訂封鎖的 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自訂 「 未修正"Url 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
3. **[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)** 選擇 [從[動態傳遞和預覽](dynamic-delivery-and-previewing.md)數個選項。
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>請參閱 ATP 檢視報告的運作方式

ATP 原則已備妥之後，就有一個報表可用來顯示服務運作的方式。(在 Office 365 安全性 & 規範中心中，移至**報表** > **儀表板**。)

[![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 為 Office 365 全域管理員、 安全性系統管理員或安全性讀者，移至[https://protection.office.com](https://protection.office.com)並登入。
    
2. 移至 [**報表** > **儀表板**。（若要取得這些報告的說明，請參閱[進階威脅保護的檢視報告](view-reports-for-atp.md)）。
    
3. 是否需要進行調整您的安全性原則。若要取得與此說明，請參閱下列資源：
      - [Office 365 中的 ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)
      - [Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
      - [Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>提交給 Microsoft 進行分析可疑的檔案

- 如果您收到您懷疑可能是惡意程式碼檔案，您可以提交給 Microsoft 進行分析該檔案。請造訪[Windows 防禦者安全性智慧提交入口網站](https://go.microsoft.com/fwlink/?linkid=857185)。

- 如果您要取得您想要提交給 Microsoft 進行分析的電子郵件訊息 （使用或不含附件），請使用[報告郵件增益集](enable-the-report-message-add-in.md)。 
  

