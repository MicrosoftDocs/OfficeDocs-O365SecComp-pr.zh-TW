---
title: 設定 Office 365 ATP 安全附件原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/8/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: 定義電子郵件中的惡意檔案的保護貴組織的原則安全的附件。
ms.openlocfilehash: bc52522a45071776835efe20f57cf37c415d2436
ms.sourcegitcommit: 9826013c3e0532ae5d01b3d88a14691f8dd0f6b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2018
ms.locfileid: "25092939"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>設定 Office 365 ATP 安全附件原則

人員定期傳送、 接收及共用文件、 簡報、 試算表等的附件。您不一定容易告訴附件是否安全或惡意只是透過查看 [電子郵件訊息。而您想要的最後一項重點是以取得，透過惡意附件混亂您的組織。幸運地是，可以協助[Office 365 進階威脅保護](office-365-atp.md)(ATP)。您可以設定[ATP 安全附件](atp-safe-attachments.md)原則以協助確保貴組織保護會遭受攻擊由不安全的電子郵件附件。 
  
## <a name="what-to-do"></a>該怎麼辦 
  
1. [請先檢閱必要條件](#review-the-prerequisites)
    
2. [設定 ATP 安全附件原則](#set-up-an-atp-safe-attachments-policy)
    
3. [了解 ATP 安全附件原則選項](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a>步驟 1： 檢閱必要條件

- 請確定您的組織具有[Office 365 進階威脅保護](office-365-atp.md)。
    
- 請確定您具有必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。
    
- [了解 ATP 安全附件原則選項](#learn-about-atp-safe-attachments-policy-options)（在本文）。雖然掃描附件有一些選項，例如 [監視] 或 [取代] 選項，可能會導致次要電子郵件的延遲。若要避免郵件延遲回應，請考慮使用[動態傳遞和預覽](dynamic-delivery-and-previewing.md)。
    
- 可讓您新增或更新原則散佈到所有 Office 365 資料中心的最多 30 分鐘。
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>步驟 2： 設定 （或編輯） ATP 安全附件原則

> [!TIP]
> 您可以設定使用下列任一 ATP 安全附件原則 Office 365 安全性&amp;規範中心 」 或 「 Exchange 系統管理中心 (EAC)。**建議使用 Office 365 安全性&amp;規範中心**。 
  
1. 以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)和登入工作或學校帳戶。 
    
2. Office 365 安全性&amp;規範中心的左的功能窗格的 [**威脅管理**] 下選擇**原則** \> **安全的附件**。
    
3. 如果您看到**開啟 SharePoint、 OneDrive 及 Microsoft 小組 ATP**，我們建議您選取這個選項。這可讓[Office 365 進階威脅 Protection for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)的 Office 365 環境。 
    
4. 選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**))，開始建立您的原則。
    
5. 指定名稱、 描述與原則設定。
    
    **範例：** 若要設定的原則稱為 「 沒有延遲 」 立即將所有人的郵件，然後將它們掃描後重新附加的附件，您可能會指定下列設定： 
    
      - 在 [**名稱**] 方塊中輸入沒有延遲。
    
      - 在 [**描述**] 方塊中輸入描述 like 立即傳送郵件並將重新附加附件之後掃描。
    
      - 在 [回應] 區段中，選擇 [**動態的傳遞**選項。（[解更多關於動態傳遞和 ATP 安全附件預覽](dynamic-delivery-and-previewing.md)）。
    
      - **重新導向附件**] 區段中選取 [啟用重新導向及輸入 Office 365 全域管理員、 安全性管理員或安全性分析師將調查惡意附件的電子郵件地址] 選項。 
    
      - 在**套用至**] 區段中，選擇 [**收件者的網域是**，，然後選取您的網域。選擇 [**新增**]，然後選擇 [ **[確定]**。
    
6. 選擇 [**儲存**]。
    
請考慮組織的多個 ATP 安全附件原則設定。這些原則會套用他們正在**ATP 安全附件**] 頁面將列出的順序。已定義或編輯原則後，允許至少 30 分鐘的原則才會生效整個 Microsoft 資料中心。 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>步驟 3： 了解 ATP 安全附件原則選項

當您設定好您 ATP 安全附件的原則，您選擇針對許多選項，包括監視、 封鎖、 Replace、 動態傳遞等等。萬一您想知道這些選項所執行的動作下, 表摘要說明每個其效果。
  
|**選項**|**效果**|**當您想要使用：**|
|:-----|:-----|:-----|
|**Off** <br/> |不會掃描附件的惡意程式碼  <br/> 不會延遲郵件傳遞  <br/> |關閉掃描程式內部的寄件者、 掃描、 傳真] 或將只會將傳送已知的良好的附件的智慧主機  <br/> 防止不必要的路由的內部郵件的延遲  <br/> **此選項不建議大多數使用者使用。可讓您關閉 ATP 安全附件掃描程式內部的寄件者一小群。**           |
|**監視** <br/> |將附件的郵件，然後時會有什麼與偵測到惡意程式碼來追蹤  <br/> |請參閱偵測到惡意程式碼會在組織中的其中  <br/> |
|**封鎖** <br/> |防止從繼續偵測到惡意程式碼附件的郵件  <br/> 將偵測到惡意程式碼的郵件傳送至[Office 365 中的隔離](manage-quarantined-messages-and-files.md)其中的安全性管理員或分析師可以檢閱及釋出 （或刪除） 那些郵件  <br/> 自動封鎖未來的訊息與附件  <br/> |可重複使用相同的惡意程式碼附件的攻擊貴組織保護  <br/> |
|**取代** <br/> |會移除偵測到惡意程式碼的附件  <br/> 通知收件者已移除附件  <br/> 將偵測到惡意程式碼的郵件傳送至[Office 365 中的隔離](manage-quarantined-messages-and-files.md)其中的安全性管理員或分析師可以檢閱及釋出 （或刪除） 那些郵件  <br/> |引發給收件者的附件已移除因偵測到惡意程式碼的可見性  <br/> |
|**動態傳遞** <br/> |傳送立即訊息  <br/> 直到掃描已完成，然後將偵測到任何惡意程式碼時重新附加附件的附件取代預留位置檔案  <br/> 包含附件預覽功能大部分的 Pdf 和 Office 檔案掃描期間  <br/> 將偵測到惡意程式碼的郵件傳送至其中的安全性管理員或分析師可以檢閱及釋出 （或刪除） 那些郵件隔離  <br/> [了解動態傳遞和 ATP 安全附件預覽](dynamic-delivery-and-previewing.md) <br/> |避免郵件延遲時防止惡意檔案中的收件者  <br/> 啟用時掃描正在進行預覽附件安全模式中的收件者  <br/> |
|**啟用重新導向** <br/> |適用於選擇監視器、 封鎖或取代選項  <br/> 傳送給指定的電子郵件地址的附件安全性管理員或分析師其中調查  <br/> |啟用安全性管理員和分析師研究可疑的附件  <br/> |
   
## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[Office 365 中的 ATP 安全連結](atp-safe-links.md)
  
[設定 Office 365 中的 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[進階威脅保護的檢視報告](view-reports-for-atp.md)

[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)
  

