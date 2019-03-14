---
title: 開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
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
description: 了解如何開啟 ATP SharePoint、 OneDrive 及 microsoft Teams，包括如何設定警示，偵測到的檔案。
ms.openlocfilehash: 30eb28bfc5156664656ca1c200f9e999661b3b0c
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2019
ms.locfileid: "30242145"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams

[適用於 SharePoint、 OneDrive 及 Microsoft Teams 的 office 365 ATP](atp-for-spo-odb-and-teams.md)會保護您的組織不小心共用惡意檔案。 偵測到惡意檔案時，該檔案被封鎖，讓任何人可以開啟、 複製、 移動或共用直到由組織的安全性小組會採取進一步的動作。 閱讀本篇文章以開啟 ATP SharePoint、 OneDrive 及 microsoft Teams，設定提醒通知關於偵測到的檔案，並採取接下來的步驟。 
  
若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。 下表說明一些範例：

|角色  |位置/方式指派  |
|---------|---------|
|Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP

**開始此程序，請確定稽核記錄已經開啟的 Office 365 環境**。 這通常是由已指派 Exchange Online 的稽核記錄 」 角色的人員。 如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](turn-audit-log-search-on-or-off.md)。
  
1. 移至 [ [https://protection.office.com](https://protection.office.com)，並以您的公司或學校帳戶登入。
    
2. 在 Office 365 安全性&amp;合規性中心，在左側的導覽窗格中，**威脅管理**] 下選擇 [**原則**] \> **安全附件**。 <br/>![安全性&amp;合規性中心，選擇 [威脅管理\>原則](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. 選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**。<br/>![開啟進階的威脅防護的 SharePoint Online、 商務用 OneDrive 和 Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. 按一下 [儲存]****。
    
5. 檢閱 （並適當地編輯） 貴組織的[安全附件原則](set-up-atp-safe-attachments-policies.md)和[安全連結原則](set-up-atp-safe-links-policies.md)。
    
6. （建議使用）以全域管理員或 SharePoint Online 系統管理員，執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** 指令程式搭配**DisallowInfectedFileDownload**參數設為*true*。 <br/>
      - 設定的參數 *，則為 true*的區塊 （除了刪除） 的所有動作偵測到的檔案。 人員無法開啟、 移動、 複製或共用偵測到的檔案。
      - 此參數設*為 false*會封鎖刪除及下載以外的所有動作。 人員可以選擇接受的風險，並下載偵測到的檔案。  
   
7. 允許 30 分鐘，進行您的變更，即會散佈至所有 Office 365 資料中心。
    
8. （建議使用）請繼續進行設定提醒偵測到的檔案。
    
若要深入了解使用 PowerShell 與 Office 365，請參閱[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。 

若要深入了解使用者經驗時已偵測到視為惡意的檔案，請參閱[在 SharePoint Online、 OneDrive 或 Microsoft Teams 中找到惡意檔案時，該怎麼辦](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。 
  
## <a name="set-up-alerts-for-detected-files"></a>偵測到檔案的提醒設定

若要收到通知，當中 SharePoint Online、 OneDrive for Business 或 Microsoft Teams 的檔案已經被識別為惡意，您可以設定警示。
  
1. 在[Office 365 安全性&amp;合規性中心](https://protection.office.com)，選擇 [**提醒** \> **管理警示**。
    
2. 選擇 [**新的警示原則**。
    
3. 指定提醒的名稱。 例如，您無法在文件庫中輸入惡意檔案。
    
4. 輸入警示的描述。 例如，您可以輸入通知系統管理員在 SharePoint Online、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案時。
    
5. 在 [**傳送此提醒時...** ] 區段中，執行下列動作： 
    
    a. 在 [**活動**] 清單中，選擇 [**在檔案中的偵測到惡意程式碼**]。
    
    b. 將 [**使用者**] 欄位保留空白。 
    
6. 在 **...傳送到此提醒**] 區段中，選取一或多個全域系統管理員、 安全性系統管理員或安全性讀者應該會偵測到惡意檔案時收到通知。 
    
7. 按一下 [儲存]****。
    
若要深入了解提醒，請參閱[建立 Office 365 安全性中的活動警訊&amp;合規性中心](create-activity-alerts.md)。 
  
## <a name="next-steps"></a>後續步驟

1. [檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [在 Office 365 中系統管理員身分管理被隔離的郵件和檔案](manage-quarantined-messages-and-files.md)
    

  

