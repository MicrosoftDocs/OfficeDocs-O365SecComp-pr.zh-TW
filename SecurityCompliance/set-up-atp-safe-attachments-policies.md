---
title: 設定 Office 365 ATP 安全附件原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 定義要保護您的組織電子郵件中的惡意檔案的安全附件原則。
ms.openlocfilehash: 47587d9e189a6fcda2cac964130d0b257b4f4166
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862415"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>設定 Office 365 ATP 安全附件原則

人員定期傳送、 接收和共用附件，例如文件、 簡報、 試算表等等。 您不一定容易分辨附件是否安全或惡意只要查看電子郵件訊息。 而您想要的最後一件事是惡意的附件，透過取得組織的混亂。 幸好，可協助[Office 365 進階威脅防護](office-365-atp.md)(ATP)。 您可以設定[ATP 安全附件](atp-safe-attachments.md)原則，以協助確保您的組織不受攻擊保護由不安全的電子郵件附件。 
  
## <a name="what-to-do"></a>要執行的動作 
  
1. 請先檢閱必要條件
    
2. 設定 ATP 安全附件原則
    
3. 了解 ATP 安全附件原則選項
    
## <a name="step-1-review-the-prerequisites"></a>步驟 1： 檢閱必要條件

- 請確定您的組織有[Office 365 進階威脅防護](office-365-atp.md)。
    
- 請確定您具有必要的權限。 若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。 下表說明一些範例： <br>

    |角色  |位置/方式指派  |
    |---------|---------|
    |Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
    |安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或  <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
    若要深入了解角色和權限，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。

- [了解 ATP 安全附件原則選項](#step-3-learn-about-atp-safe-attachments-policy-options)（本文）。 一些選項，例如 [監視] 或 [取代選項]，可能會導致次要的電子郵件延遲時所掃描的附件。 若要避免郵件延遲，請考慮使用[動態傳遞和預覽](dynamic-delivery-and-previewing.md)。
    
- 允許最多 30 分鐘，即會散佈至所有 Office 365 資料中心新增或更新原則。
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>步驟 2： 設定 （或編輯） ATP 安全附件原則
  
1. 移至 [[https://protection.office.com](https://protection.office.com)並以您的公司或學校帳戶登入。 
    
2. 在 Office 365 安全性&amp;合規性中心，在左側的導覽窗格中，**威脅管理**] 下選擇 [**原則**] \> **安全附件**。
    
3. 如果您看到**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**，我們建議您選取這個選項。 這可讓[Office 365 進階威脅防護 SharePoint、 OneDrive 及 Microsoft Teams](atp-for-spo-odb-and-teams.md)的 Office 365 環境。 
    
4. 選擇 [**新增**] ([新增] 按鈕的格式類似於加上加號 ( **+**))，開始建立您的原則。
    
5. 指定名稱、 描述及原則設定。<br/><br/>**範例：** 若要設定稱為 「 無延遲 「 立即傳遞所有人的郵件，然後 reattaches 附件之後他們正在掃描, 的原則，您可以指定下列設定： 
    
      - 在 [**名稱**] 方塊中，輸入沒有延遲。
    
      - 在 [**描述**] 方塊中，輸入描述類似，立即傳送郵件和 reattaches 附件掃描之後。
    
      - 在 [回應] 區段中，選擇 [**動態傳遞**選項]。 （[深入了解更多關於動態傳遞和預覽使用 ATP 安全附件](dynamic-delivery-and-previewing.md)）。
    
      - 在**重新導向附件**] 區段中，選取 [啟用重新導向，並輸入您的 Office 365 全域系統管理員、 安全性系統管理員或將調查惡意附件安全性分析師的電子郵件地址] 選項。 
    
      - 在**套用至**] 區段中，選擇 [**收件者網域是**，，然後選取您的網域。 選擇 [**新增**]，然後選擇 [**確定]**。
    
6. 選擇 [**儲存**]。
    
請考慮組織的多個 ATP 安全附件原則設定。 這些原則會套用在它們列在**ATP 安全附件**] 頁面上的順序。 已定義或編輯原則之後，允許至少 30 分鐘，才會生效，整個 Microsoft 資料中心原則。 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>步驟 3： 了解 ATP 安全附件原則選項

當您設定 ATP 安全附件原則時，您選擇許多選項，包括監視、 封鎖、 取代、 動態傳遞，依此類推。 您想知道關於這些選項所執行的動作下, 表摘要說明每個及其影響。
  
|**選項**|**Effect**|**當您想要使用：**|
|:-----|:-----|:-----|
|**關閉** <br/> |不會掃描附件的惡意程式碼  <br/> 不會延遲郵件傳遞  <br/> |關閉掃描內部寄件者、 掃描器、 傳真，或只會傳送已知的良好附件的智慧主機  <br/> 防止不必要的延遲內部郵件路由傳送  <br/> **此選項不建議大多數使用者。它可讓您關閉 ATP 安全附件掃描的一小群的內部寄件者。**           |
|**監視** <br/> |會傳遞含附件的郵件，並接著會追蹤項目會發生此情況偵測到惡意程式碼  <br/> |查看貴組織中的偵測到惡意程式碼到哪裡去  <br/> |
|**封鎖** <br/> |防止繼續偵測到的惡意軟體附件的郵件  <br/> 將偵測到惡意程式碼的郵件傳送至[隔離區中 Office 365](manage-quarantined-messages-and-files.md)其中的安全性管理員或分析師可以檢閱並釋出 （或刪除） 這些郵件  <br/> 自動封鎖將來的郵件和附件  <br/> |保護貴組織從重複使用相同的惡意軟體附件的攻擊  <br/> |
|**Replace** <br/> |會移除偵測到的惡意軟體附件  <br/> 通知收件者已移除附件  <br/> 將偵測到惡意程式碼的郵件傳送至[隔離區中 Office 365](manage-quarantined-messages-and-files.md)其中的安全性管理員或分析師可以檢閱並釋出 （或刪除） 這些郵件  <br/> |引發給收件者已因為偵測到惡意程式碼中移除附件的可見性  <br/> |
|**動態傳遞** <br/> |立即將郵件傳遞  <br/> 直到掃描已完成，而且如果偵測不到任何惡意程式碼，然後 reattaches 附件的附件取代預留位置檔案  <br/> 包含附件預覽功能大部分 Pdf 和 Office 在掃描期間的檔案  <br/> 將偵測到惡意程式碼的郵件傳送至隔離區其中的安全性管理員或分析師可以檢閱並釋出 （或刪除） 這些郵件  <br/> [了解動態傳遞和預覽使用 ATP 安全附件](dynamic-delivery-and-previewing.md) <br/> |避免同時防止惡意檔案中的收件者的郵件延遲  <br/> 啟用收件者時掃描正在進行預覽在安全模式中的附件  <br/> |
|**啟用重新導向** <br/> |選擇 [監視器]、 [封鎖或 [取代] 選項時，會套用  <br/> 傳送至指定的電子郵件地址的附件安全性系統管理員或分析師可以調查其中  <br/> |啟用安全性管理員和分析師研究可疑的附件  <br/> |
   
## <a name="next-steps"></a>後續步驟

一旦您 ATP 安全附件原則就緒後，您可以瞭解 ATP 的運作方式為您的組織藉由檢視報告。 請參閱若要了解更多的下列資源：
- [檢視 Office 365 進階威脅防護報告](view-reports-for-atp.md)
- [使用檔案總管中的安全性&amp;合規性中心](use-explorer-in-security-and-compliance.md)

掌握即將 ATP 的新功能。 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)，並了解[新功能，將會新增 ATP](office-365-atp.md#new-features-in-office-365-atp)。
 