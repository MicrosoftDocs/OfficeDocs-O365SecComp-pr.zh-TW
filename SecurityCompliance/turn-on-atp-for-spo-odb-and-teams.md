---
title: 開啟 Office 365 ATP for SharePoint、OneDrive 及 Microsoft 小組
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: 瞭解如何為 SharePoint、OneDrive 及小組開啟 ATP, 包括如何設定偵測到之檔案的警示。
ms.openlocfilehash: f3be5b3cf73a04de10185428b84b5862906c3db7
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652666"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟 Office 365 ATP for SharePoint、OneDrive 及 Microsoft 小組

> [!IMPORTANT]
> 本文適用于擁有[Office 365 高級威脅防護](office-365-atp.md)的商務客戶。 如果您是尋找 Outlook 中安全連結相關資訊的家庭使用者, 請參閱[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

[Office 365 ATP For SharePoint、OneDrive 及 Microsoft 團隊](atp-for-spo-odb-and-teams.md)可防止您的組織不慎共用惡意檔案。 偵測到惡意檔案時, 該檔案會遭到封鎖, 讓任何人都無法開啟、複製、移動或共用該檔案, 直到組織的安全小組採取進一步的動作為止。 請閱讀本文以開啟 ATP for SharePoint、OneDrive 及小組、設定通知, 以獲得偵測到的檔案通知, 並採取下一步。 
  
若要定義 (或編輯) ATP 原則, 您必須獲指派適當的角色。 下表說明一些範例:

|角色  |指派的位置/方式  |
|---------|---------|
|Office 365 全域系統管理員 |註冊購買 Office 365 的人員預設為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP

**開始此程式之前, 請確定已開啟 Office 365 環境的審核記錄**功能。 這通常是由已在 Exchange Online 中指派「Audit 記錄」角色的人員所完成。 如需詳細資訊, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。
  
1. 移至[https://protection.office.com](https://protection.office.com), 然後使用您的公司或學校帳戶登入。
    
2. 在 [Office 365 安全性&amp;規範中心] 的左功能窗格中, 選擇 [**威脅管理**] 下的 [**原則** \> **安全附件**]。 <br/>![在安全性&amp;與合規性中心, 選擇 [ \>威脅管理原則]](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. 選取 [**開啟適用于 SharePoint、OneDrive 及 Microsoft 團隊的 ATP**]。<br/>![開啟適用于 SharePoint Online、商務用 OneDrive 和 Microsoft 小組的高級威脅防護](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. 按一下 [儲存]****。
    
5. 請查看 (並視需要編輯) 您組織的[安全附件原則](set-up-atp-safe-attachments-policies.md)和[安全連結原則](set-up-atp-safe-links-policies.md)。
    
6. 採取以全域管理員或 SharePoint Online 系統管理員身分執行 Set-spotenant 指令**[程式](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)**, 並將**DisallowInfectedFileDownload**參數設為*true*。 <br/>
      - 將參數設定為*true*會封鎖偵測到之檔案的所有動作 (刪除除外)。 使用者無法開啟、移動、複製或共用偵測到的檔案。
      - 將參數設定為*false*會封鎖除了 Delete 和下載以外的所有動作。 使用者可以選擇接受風險並下載偵測到的檔案。  
   
7. 允許最多30分鐘, 以將您的變更傳播至所有 Office 365 資料中心。
    
8. 採取繼續設定偵測到之檔案的警示。
    
若要深入瞭解如何搭配使用 PowerShell 與 Office 365, 請參閱使用[Powershell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。 

若要深入瞭解在檔案被偵測到有惡意時的使用者經驗, 請參閱在[SharePoint Online、OneDrive 或 Microsoft 團隊中找到惡意檔案時, 要採取的](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)動作。 
  
## <a name="set-up-alerts-for-detected-files"></a>設定偵測到檔案的警示

若要在 SharePoint Online、商務用 OneDrive 或 Microsoft 團隊中的檔案被識別為惡意時收到通知, 您可以設定警示。
  
1. 在 [ [Office 365 安全性&amp;與規範中心](https://protection.office.com)] 中, 選擇 [**警示** \> ] [**管理提醒**]。
    
2. 選擇 [**新增警示原則**]。
    
3. 指定警示的名稱。 例如, 您可以在文件庫中輸入惡意檔案。
    
4. 輸入警示的描述。 例如, 您可以在 SharePoint Online、OneDrive 或 Microsoft 團隊中偵測到惡意檔案時, 輸入通知系統管理員。
    
5. 在 [**傳送此提醒的時間**...] 區段中, 執行下列動作: 
    
    a. 在 [**活動**] 清單中, 選擇 [檔案**中偵測到惡意**代碼]。
    
    b. 將 [**使用者**] 欄位保留空白。 
    
6. 在 [**傳送此提醒 ...** ] 區段中, 選取一或多個全域系統管理員、安全性系統管理員, 或在偵測到惡意檔案時會收到通知的安全性讀取者。 
    
7. 按一下 [儲存]****。
    
若要深入瞭解提醒, 請參閱[在 Office 365 安全性&amp;與合規性中心建立活動警示](create-activity-alerts.md)。 
  
## <a name="next-steps"></a>後續步驟

1. [查看 SharePoint、OneDrive 或 Microsoft 團隊中偵測到之惡意檔案的相關資訊](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [以 Office 365 的系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)
    

  

