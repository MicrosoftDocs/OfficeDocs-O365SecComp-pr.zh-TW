---
title: 在 Office 365 ATP 開啟 SharePoint、 OneDrive 及 Microsoft 小組
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: 了解如何開啟 ATP for SharePoint、 OneDrive 及小組，包括如何設定提醒的偵測到的檔案。
ms.openlocfilehash: 770af7078166857bcb9784112710262b7de788bb
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014885"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>在 Office 365 ATP 開啟 SharePoint、 OneDrive 及 Microsoft 小組

[Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](atp-for-spo-odb-and-teams.md)提供貴組織保護不慎共用惡意的檔案。當偵測到惡意檔案時，該檔案會封鎖，讓任何人可以開啟、 複製、 移動或共用直到組織的安全性小組所採取其他動作。閱讀本篇文章以開啟 ATP for SharePoint、 OneDrive 及小組設定提醒通知關於偵測到的檔案並執行您的下一個步驟。 
  
若要執行本文所述的工作，您必須指派 Office 365 及安全性的必要權限&amp;規範中心。
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP

 **開始此程序，確定稽核記錄已經開啟 Office 365 環境**。這通常是由某人具有 「 稽核記錄 」 角色指派 Exchange Online。如需詳細資訊，請參閱[開啟 Office 365 稽核記錄搜尋開啟或關閉](turn-audit-log-search-on-or-off.md)。
  
1. 以全域管理員或安全性管理員中，移至[https://protection.office.com](https://protection.office.com)，並登入工作或學校帳戶。
    
2. Office 365 安全性&amp;規範中心的左的功能窗格的 [**威脅管理**] 下選擇**原則** \> **安全的附件**。 <br/>![安全性&amp;規範中心選擇 Threat management\>原則](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. 選取 [**開啟 SharePoint、 OneDrive 及 Microsoft 小組 ATP**。<br/>![開啟進階的威脅 Protection for SharePoint Online、 OneDrive for Business 和 Microsoft 小組](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. 按一下 **[儲存]**。
    
5. 檢閱 （和視需要編輯） 您組織的[安全附件原則](set-up-atp-safe-attachments-policies.md)和[安全連結原則](set-up-atp-safe-links-policies.md)。
    
6. （建議）以全域管理員或 SharePoint Online 管理員、 執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet 搭配**DisallowInfectedFileDownload**參數設為*true*。 <br/>
      - 設定參數，*則為 true*組塊 （除了刪除） 的所有動作的偵測到的檔案。使用者無法開啟、 移動、 複製或共用偵測到的檔案。
      - 將此參數設定為*false*會封鎖刪除和下載以外的所有動作。使用者可以選擇接受風險和下載偵測到的檔案。  
   
7. 可讓您的變更傳播到所有 Office 365 資料中心的最多 30 分鐘。
    
8. （建議）請繼續進行設定提醒的偵測到的檔案。
    
若要深入了解 Office 365 搭配使用 PowerShell，請參閱[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。 

若要深入了解使用者經驗時已偵測到為惡意的檔案，請參閱[如何在 SharePoint Online、 OneDrive 或 Microsoft 小組中找到惡意檔案時](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。 
  
## <a name="set-up-alerts-for-detected-files"></a>設定提醒的偵測到的檔案

若要在 SharePoint Online、 OneDrive for Business 或 Microsoft 小組檔案被識別為 [惡意時收到通知，您可以設定提醒。
  
1. 在[Office 365 安全性&amp;規範中心](https://protection.office.com)，選擇**警示** \> **管理提醒**。
    
2. 選擇 [**新增提醒的原則**。
    
3. 指定提醒的名稱。例如，您無法輸入惡意檔案庫中。
    
4. 輸入警示的描述。例如，您無法輸入告知 admins 時 SharePoint Online、 OneDrive 或 Microsoft 小組中偵測到惡意的檔案。
    
5. **傳送此提醒時...** ] 區段中執行下列動作： 
    
    a.[**活動**] 清單中選擇 [**檔案中的偵測到惡意程式碼**]。
    
    b.保留**使用者**欄位空白。 
    
6. **傳送到此警示...** ] 區段中選取一或多個全域管理員、 安全性管理員或安全性讀者應該會偵測到惡意檔案時收到通知。 
    
7. 按一下 **[儲存]**。
    
若要深入了解提醒，請參閱[建立 Office 365 安全性活動提醒&amp;規範中心](create-activity-alerts.md)。 
  
## <a name="next-steps"></a>後續步驟

1. [檢視 SharePoint、 OneDrive 或 Microsoft 小組中偵測到惡意檔案的資訊](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [在 Office 365 系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)
    

  

