---
title: 設定 Office 365 ATP 安全連結原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: 設定安全的連結原則來保護您的組織不在 Word、 Excel、 PowerPoint 及 Visio 檔案，以及在電子郵件訊息中的惡意連結。
ms.openlocfilehash: fb2af8e29bfe2de027a2d0e88cf9bcc07299fba9
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706087"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>設定 Office 365 ATP 安全連結原則

[ATP 安全連結](atp-safe-links.md)的[Office 365 進階威脅保護](office-365-atp.md)(ATP) 的功能可協助保護您的組織中用於網路釣魚和其他攻擊的惡意連結。如果您有必要[的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)、 您可以設定 ATP 安全連結原則以協助確保當使用者按一下 [網站位址 (Url)、 貴組織保護。ATP 安全連結原則可以設定要掃描電子郵件中的 Url 及 Office 文件中的 Url。
  
[ATP 持續所加入的新功能](office-365-atp.md#new-features-are-continually-being-added-to-atp)。隨著增加新功能，您可能需要調整您現有的 ATP 安全連結原則。

## <a name="what-to-do"></a>該怎麼辦 
  
1. [請先檢閱必要條件](#review-the-prerequisites)。
    
2. [檢閱並編輯預設 ATP 安全連結原則可套用到所有人](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如，您可以[設定 ATP 安全連結您自訂封鎖 Url 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。
    
3. [新增或編輯原則的特定電子郵件收件者](#add-a-policy-for-specific-email-recipients)，包括[您自訂 「 未修正"Url 清單 ATP 安全連結的設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
4. [了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文中），包括 [最近變更的設定
    
## <a name="step-1-review-the-prerequisites"></a>步驟 1： 檢閱必要條件

- 請確定您的組織具有[Office 365 進階威脅保護](office-365-atp.md)。
    
- 請確定您已定義或編輯 ATP 原則的必要權限。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。

- 請確定 Office 用戶端設定為使用[經過驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)（這是 Office 文件中的 ATP 安全連結保護）。
    
- [了解 ATP 安全連結原則選項](#learn-about-atp-safe-links-policy-options)（在本文）。 

- 可讓您新增或更新原則散佈到所有 Office 365 資料中心的最多 30 分鐘。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>步驟 2： 定義 （或檢閱） 套用至所有人 ATP 安全連結原則

當您有[Office 365 進階威脅保護](office-365-atp.md)時，您必須套用至組織中所有人預設 ATP 安全連結原則。請務必檢閱，並視需要編輯預設原則。
  
1. 移至 [[https://security.microsoft.com](https://security.microsoft.com)和登入工作或學校帳戶。 
    
2. 在左導覽列中， **Threat management**] 下選擇**原則\>****安全的連結**。
    
3. **套用至整個組織的原則**] 區段中選取 [**預設**]，然後選擇**編輯**（[編輯] 按鈕以鉛筆）。<br/>![按一下 [編輯] 以編輯您的預設原則的安全連結保護](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. 在 [**封鎖下列 Url** ] 區段中，指定您想要避免造訪您組織中的一或多個 Url。（請參閱[Set up 自訂封鎖 Url 清單使用 ATP 安全連結](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。
    
5. **套用至內容除了電子郵件設定**] 區段中選取 （或清除） [您想要使用的選項。（我們建議您選取的所有選項）。 
    
6. 選擇 [**儲存**]。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>步驟 3： 新增 （或編輯） ATP 安全連結原則套用至特定電子郵件收件者

您已檢閱 （或編輯） 套用至所有人預設 ATP 安全連結原則之後下, 一步是定義會套用至特定收件者的其他原則。例如，您可以指定例外狀況為預設原則所定義的其他原則。 
  
1. 移至 [[https://security.microsoft.com](https://security.microsoft.com)和登入工作或學校帳戶。 
    
2. 在左導覽列中， **Threat management**] 下選擇 [**原則**]。
    
3. 選擇 [**安全的連結**。
    
4. 在 [**原則套用至特定收件者**] 區段中選擇 [**新增**] ([新增] 按鈕的格式類似於加號 ( **+**))。<br/>![選擇 [新增] 可為特定電子郵件收件者新增的安全連結原則](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. 指定原則的名稱、描述及設定。<br/>**範例：** 若要設定稱為 「 沒有直接點選"不允許人員的特定群組中按一下透過特定的網站不 ATP 安全連結保護組織的原則，您可能會指定下列建議設定： 
    
  - 在 [**名稱**] 方塊中輸入沒有直接點選。
    
  - 在 [**描述**] 方塊中輸入像轉人員從透過按一下沒有 ATP 安全連結驗證的網站特定群組中的描述。
    
  - **選取動作**] 區段中選擇 [**上**]。
    
  - 選取 [**使用安全附件掃描可下載的內容**。
    
  - 使用此選項時，選取 [**套用至組織內傳送訊息的安全連結**。
    
  - 選取 [**不允許使用者透過按一下以原始 URL**。
    
  - （這是選用的）**未修正下列 Url** ] 區段中指定被視為安全組織的一或多個 Url。（請參閱[Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）
    
  - **套用至**] 區段中選擇 [**收件者是成員**，然後按您想要包含在您的原則中的群組。選擇 [**新增**]，然後選擇 [ **[確定]**。
    
6. 選擇 [**儲存**]。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>步驟 4︰ 了解 ATP 安全連結原則選項

當您設定或編輯 ATP 安全連結原則時，會看到數個可用選項。您會知道這些選項為何下, 表說明每一個和其效果。有兩種主要定義或編輯 ATP 安全連結原則，請記得：
- 套用至所有人的[預設原則](#default-policy-options) 
- 其他[原則所定義的特定收件者](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>預設原則選項

預設原則選項套用至組織中所有的人。

|此選項  |執行動作  |
|---------|---------|
| **封鎖下列 Url** <br/>    | 可讓您的組織具有自訂清單的自動封鎖的 Url。當使用者按一下此清單中的 URL 時，他們會前往說明 URL 封鎖的原因[警告] 頁面](atp-safe-links-warning-pages.md)。<br/> 若要深入了解，請參閱 [Set up 自訂封鎖 Url 清單使用 ATP 安全連結      |
| **Office 365 ProPlus iOS 適用於 Office 及 android （英文）** <br/>    | 選取此選項時，ATP 保護套用至 Url 的文件內的安全連結中開啟 Office 365 ProPlus （Word、 Excel 及 PowerPoint Windows 或 Mac OS） iOS 或 Android 裝置上 Windows 及 Office Online (Word Visio 2016 上的 Office 文件線上、 PowerPoint Online、 Excel Online 和 OneNote Online），提供使用者已登入 Office 365。 <br/><br/>如果您看到只**在 Windows 的 Office 2016**，然後功能更新已無法連至 Office 365 環境尚未 （和它們即將推出）。加上 then，直到 ATP 安全連結保護適用於 Word 2016、 Excel 2016、 PowerPoint 2016 或 Visio 2016 Windows 上執行。            |
| **當使用者按一下 ATP 安全連結時不要追蹤** <br/>  | 選取此選項時，按一下資料中的不會儲存在 Word、 Excel、 PowerPoint 及 Visio 文件中的 Url。  <br/> |
|**不讓使用者按一下 [透過 ATP 原始 URL 的安全連結** <br/> |選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>套用至特定電子郵件收件者的原則

|此選項  |執行動作  |
|---------|---------|
|**Off** <br/> |不會掃描電子郵件訊息中的 Url。  <br/> 可讓您定義的例外狀況規則，例如不會掃描一組特定的收件者的電子郵件訊息中 Url 的規則。  <br/> |
|**在** <br/> |當使用者按一下 [Url] 中的電子郵件，路由使用者可透過 ATP 安全連結保護修正 Url。  <br/> 檢查當您按一下針對封鎖或惡意 Url 清單的 URL。  <br/> |
|**使用安全附件掃描的可下載內容** <br/> |選取此選項時，會掃描指向可下載內容的 Url。  <br/> |
|**套用至組織內傳送訊息的安全連結** <br/> | 當可用及選取此選項即 ATP 安全連結保護會套用至組織中所提供的電子郵件帳戶的人員之間所寄送的郵件都架設在 Office 365 的電子郵件。  <br/> |
|**不會追蹤使用者點選** <br/> |選取此選項時，按一下資料中的 Url 來自外部寄件者的電子郵件中不會儲存。目前不支援 URL click 追蹤組織內傳送的電子郵件訊息內的連結。  <br/> |
|**不允許使用者透過按一下以原始 URL** <br/> |選取此選項時，使用者無法繼續過去的[警告] 頁面上](atp-safe-links-warning-pages.md)決定為惡意的 URL。  <br/> |
|**未修正下列 Url** <br/> |以離開 Url。保留自訂清單的安全不需要一組特定的組織中的電子郵件收件者的掃描的 Url。 請參閱 ＜ [Set up 自訂 「 未修正"Url 清單使用 ATP 安全連結](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)如需詳細資訊，包括支援的萬用字元星號最近的變更 (\*)。<br/> |
   
## <a name="next-steps"></a>後續步驟

一旦您 ATP 安全連結原則已備妥，您可以看到 ATP 如何為貴組織運作檢視報告。請參閱下列資源以深入了解：

- [Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)

- [使用瀏覽器安全性&amp;規範中心](use-explorer-in-security-and-compliance.md) 