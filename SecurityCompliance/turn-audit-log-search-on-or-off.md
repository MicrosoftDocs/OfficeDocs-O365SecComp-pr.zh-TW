---
title: 開啟或關閉 Office 365 稽核記錄搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在 Office 365 安全性稽核記錄搜尋功能中開啟&amp;規範中心。如果您變更您注意，您可以開啟時關閉任何時候。關閉稽核記錄搜尋時，系統管理員無法在組織中搜尋使用者與系統管理活動的 Office 365 稽核記錄。
ms.openlocfilehash: f0532ae7ba205001d89164ac3f00822d14aa81cd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218003"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>開啟或關閉 Office 365 稽核記錄搜尋

您 （或另一個系統管理員） 必須開啟稽核記錄才能開始搜尋的 Office 365 稽核記錄。當稽核記錄搜尋 Office 365 安全性&amp;規範中心已開啟、 從您的組織的使用者和系統活動會記錄在稽核記錄檔和保留期為 90 天。不過，您的組織可能不要記錄保留稽核記錄資料。或可能會使用第三方安全性資訊和事件管理 (SIEM) 應用程式存取稽核資料。在這些案例中的全域系統管理員可以關閉在 Office 365 中的稽核記錄搜尋。
  
## <a name="before-you-begin"></a>開始之前

- 您必須指派稽核記錄 」 角色在 Exchange Online 在 Office 365 組織中開啟或關閉開啟稽核記錄搜尋。根據預設，此角色指派給 Exchange 系統管理中心的 [**權限**] 頁面上相符性管理] 和 [組織管理角色群組。Office 365 中的全域系統管理員為組織管理角色群組的成員在 Exchange Online。 
    
    > [!IMPORTANT]
    > 使用者必須獲得權限在 Exchange Online 以開啟或關閉的稽核記錄搜尋。如果您在 [安全性]**權限**] 頁面上的稽核記錄 」 角色指派使用者&amp;規範中心他們將無法開啟或關閉的稽核記錄搜尋。這是因為基礎指令程式是 Exchange Online 指令程式。 
  
- 如果您關閉 Office 365 中的稽核記錄搜尋時，您仍可用 Office 365 管理活動 API 來存取稽核資料的組織。關閉 [透過遵循本文中的 [稽核記錄搜尋表示當您使用安全性稽核記錄檔中搜尋將會傳回任何結果&amp;規範中心或 Exchange Online 中執行**搜尋 UnifiedAuditLog**指令程式時間PowerShell。不過，如果您已獲得授權存取您的組織稽核資料透過 Office 365 管理活動 API 任何應用程式，這些應用程式會繼續運作。 
    
- 如需搜尋 Office 365 的逐步指示稽核記錄，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。
    
## <a name="turn-on-audit-log-search"></a>開啟稽核記錄搜尋

您可以使用安全性&amp;規範中心或 PowerShell 開啟 Office 365 中的稽核記錄搜尋。可能需要數小時後才可以傳回結果搜尋稽核記錄時開啟稽核記錄搜尋。您必須指派稽核記錄 」 角色在 Exchange Online 開啟稽核記錄搜尋。
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a>使用安全性&amp;規範中心開啟稽核記錄搜尋

1. 安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **稽核記錄搜尋**。
    
2. 按一下 [**開始錄製使用者與系統活動**。
    
    ![按一下 [開始錄製使用者和系統管理員活動]，來開啟稽核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    說明使用者及組織中的系統活動會錄製到 Office 365 稽核記錄，適用於報表中檢視被顯示的對話方塊。 
    
3. 按一下 [開啟]****。
    
    顯示訊息指出做準備的稽核記錄及您可在幾小時準備完成後執行搜尋。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 來開啟稽核記錄搜尋

1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 執行下列 PowerShell 命令，以開啟 [Office 365 中的稽核記錄搜尋。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    會顯示訊息指出它可能需要最多 60 分鐘，變更才會生效。
  
## <a name="turn-off-audit-log-search"></a>關閉 [稽核記錄搜尋

您必須使用遠端 PowerShell 連線至 Exchange Online 組織來關閉 [稽核記錄搜尋。類似於開啟稽核記錄搜尋，您必須指派稽核記錄 」 角色在 Exchange Online，即可關閉稽核記錄搜尋。
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 執行下列 PowerShell 命令，以關閉 [Office 365 中的稽核記錄搜尋。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 之後 while 確認稽核記錄搜尋已關機 （停用）。有兩種方式可以執行這項作業：
    
    - 在 PowerShell 中執行下列命令：

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        值`False`的_UnifiedAuditLogIngestionEnabled_屬性會指出稽核記錄搜尋已關閉。 
    
    - 安全性&amp;規範管理中心，移至**搜尋&amp;調查** \> **稽核記錄搜尋**，然後按一下 [**搜尋**。
    
      預警開啟稽核記錄搜尋不會顯示訊息。 
    
      ![一則訊息，則 dispayed 稽核已關閉](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
