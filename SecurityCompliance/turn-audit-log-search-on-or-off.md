---
title: 開啟或關閉 Office 365 稽核記錄搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以開啟安全性 & 合規性中心中的稽核記錄搜尋功能。 如果您變更您記住，您可以啟動隨時如果 off。 關閉稽核記錄搜尋時，系統管理員無法在組織中搜尋使用者和系統管理員活動的 Office 365 稽核記錄檔。
ms.openlocfilehash: 0619b19f9dc6e8bdc21e26275f02a81948b40bf4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265371"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>開啟或關閉 Office 365 稽核記錄搜尋

您 （或另一個系統管理員） 必須開啟稽核記錄，才能開始搜尋 Office 365 稽核記錄檔。 安全性 & 合規性中心中的稽核記錄搜尋開啟時，從您的組織的使用者和系統管理員活動是記錄在稽核記錄檔，並保留 90 天。 不過，您的組織可能不希望筆記錄，並保留稽核記錄資料。 或者，您可能要存取您的稽核資料使用的協力廠商安全性資訊和事件管理 (SIEM) 應用程式。 在這些情況下，全域系統管理員可以關閉在 Office 365 中的稽核記錄搜尋。
  
## <a name="before-you-begin"></a>開始之前

- 您必須被指派 「 稽核記錄 」 角色在 Exchange Online 在 Office 365 組織中開啟或關閉開啟稽核記錄搜尋。 根據預設，此角色被指派給在 Exchange 系統管理中心中的**權限**] 頁面上相符性管理] 和 [組織管理角色群組。 在 Office 365 中的全域系統管理員是 「 組織管理 」 角色群組的成員在 Exchange Online。 
    
    > [!IMPORTANT]
    > 使用者必須被指派權限在 Exchange Online 若要開啟或關閉稽核記錄搜尋。 如果您將使用者指派 「 稽核記錄 」 角色中安全性 & 合規性中心的**權限**] 頁面上，他們將無法開啟或關閉稽核記錄搜尋。 這是因為基礎指令程式是 Exchange Online cmdlet。 
  
- 如果您關閉 Office 365 中的稽核記錄搜尋時，您無法使用 Office 365 管理活動 API 來存取組織的稽核資料。 遵循本文中的稽核記錄搜尋關閉表示當您搜尋使用安全性 & 合規性中心的稽核記錄檔或 Exchange Online 中執行**Search-unifiedauditlog**指令程式，將會傳回任何結果PowerShell。 這也表示您的稽核記錄不會是可透過 Office 365 管理活動 API。  
    
- 如需搜尋 Office 365 稽核記錄的逐步指示，請參閱 <<c0>的搜尋稽核記錄中的安全性 &amp; 合規性中心。
    
## <a name="turn-on-audit-log-search"></a>開啟稽核記錄搜尋

您可以使用安全性 & 合規性管理中心或 PowerShell 將開啟 Office 365 中的稽核記錄搜尋。 它可能需要數小時之後您開啟稽核記錄搜尋之前搜尋稽核記錄時，可以傳回的結果。 您必須被指派 「 稽核記錄 」 角色在 Exchange Online 開啟稽核記錄搜尋。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>使用安全性 & 合規性中心來開啟稽核記錄搜尋

1. 在 [安全性 & 合規性中心，移至**搜尋** \> **稽核記錄搜尋**。
    
2. 按一下 [**開始錄製使用者和系統管理員活動**]。
    
    ![按一下 [開始錄製使用者和系統管理員活動來開啟稽核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    指出使用者和組織中的系統管理員活動，將會錄製到 Office 365 稽核記錄，並可供檢視報表中會顯示對話方塊。 
    
3. 按一下 [開啟]****。
    
    會顯示訊息，指出準備稽核記錄檔以及您可以在幾個小時後準備已完成執行搜尋。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 來開啟稽核記錄搜尋

1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 執行下列 PowerShell 命令，以開啟 [Office 365 中的稽核記錄搜尋。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    會顯示一則訊息，指出它可能需要 60 分鐘的時間，變更才會生效。
  
## <a name="turn-off-audit-log-search"></a>關閉稽核記錄搜尋

您必須使用遠端 PowerShell 連線至 Exchange Online 組織來關閉稽核記錄搜尋。 類似於開啟稽核記錄搜尋，您必須被指派 「 稽核記錄 」 角色在 Exchange Online 關閉稽核記錄搜尋。
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 執行下列 PowerShell 命令，以關閉 [Office 365 中的稽核記錄搜尋。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 在一段時間之後, 確認稽核記錄搜尋已關閉 (disabled)。 方法有兩種：
    
    - 在 PowerShell 中，執行下列命令：

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        值`False` _UnifiedAuditLogIngestionEnabled_屬性表示該稽核記錄搜尋已關閉。 
    
    - 在 [安全性 & 合規性中心，移至**搜尋** \> **稽核記錄搜尋**]，然後按一下 [**搜尋**。
    
      會顯示一則訊息，指出尚未開啟稽核記錄搜尋。 
    
      ![如果稽核已關閉，會顯示一則訊息](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
