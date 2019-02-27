---
title: 啟用 Office 365中的信箱稽核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 在 Office 365 中，您可以開啟信箱稽核記錄來依信箱擁有者、 委派及系統管理員記錄信箱存取。根據預設，Office 365 中的信箱稽核無法開啟。啟用信箱稽核記錄功能信箱之後，您可以搜尋活動在信箱上執行的 Office 365 稽核記錄。
ms.openlocfilehash: a9bc84bad8532dd546d5ce3e2f149151967050d6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295916"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>啟用 Office 365中的信箱稽核
  
在 Office 365 中，您可以開啟信箱稽核記錄來依信箱擁有者、 委派及系統管理員記錄信箱存取。根據預設，Office 365 中的信箱稽核無法開啟。這表示信箱稽核事件將不會出現在結果搜尋信箱活動的 Office 365 稽核記錄時。但是您開啟信箱稽核記錄功能的使用者信箱後，您可以搜尋信箱活動的稽核記錄。此外，當信箱稽核記錄已啟動，由系統管理員、 委派、 執行某些動作及預設會記錄擁有者。記錄 （及然後搜尋） 其他動作，請參閱步驟 3。

## <a name="before-you-begin"></a>開始之前
  
- 您必須使用 Exchange Online PowerShell 來啟用信箱稽核記錄。您不能使用 Office 365 安全性&amp;規範中心 」 或 「 Exchange 系統管理中心。
    
- 您無法啟用信箱稽核記錄與 Office 365 群組或小組中的 Microsoft 小組關聯的信箱。
    
- 獲指派使用者信箱「完整存取」權限的系統管理員會被視為委派使用者。
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>步驟 1： 連線至 Exchange Online PowerShell

1. 在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。
   
    ```
    $UserCredential = Get-Credential
    ```

2. 在**Windows PowerShell 認證要求**] 對話方塊中，輸入使用者名稱與 Office 365 全域管理員帳戶密碼，並再按一下 [**確定]**。
    
3. 執行下列命令：
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. 執行下列命令。

    ```
    Import-PSSession $Session
    ```
   
4. 若要確認您已連線至 Exchange Online 組織，執行下列命令以取得貴組織中所有信箱的清單：
    
    ```
    Get-Mailbox
    ```
  
如需詳細資訊或如果您無法連線到您的 Exchange Online 組織，請參閱[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。
  
## <a name="step-2-enable-mailbox-audit-logging"></a>步驟 2：啟用信箱稽核記錄

連線至 Exchange Online 組織之後，使用 PowerShell 針對信箱啟用信箱稽核記錄。或者，您可以啟用信箱稽核貴組織中的所有信箱。
  
本範例啟用信箱稽核記錄 Pilar Pinilla 信箱。
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

此範例會啟用組織中所有使用者信箱的信箱稽核記錄。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>步驟 3：指定要稽核的擁有者動作

當您啟用信箱稽核時，預設稽核信箱擁有者執行某些動作。您必須指定稽核其他擁有者動作。請參閱在[信箱稽核動作](#mailbox-auditing-actions)] 區段中的清單和說明會記錄預設的擁有者動作及其他要稽核的動作的表格。 
  
本範例會新增到信箱的 Pilar Pinilla 信箱稽核**MailboxLogin**和**HardDelete**擁有者動作。本範例會假設該信箱稽核已經啟用此信箱。 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

本範例個 Don 館信箱啟用信箱稽核記錄並指定僅信箱擁有者執行**MailboxLogin**動作都將被記錄。請注意此範例會覆寫預設 UpdateFolderPermissions 巨集指令。 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
本範例會將**MailboxLogin**、 **HardDelete**和**SoftDelete**擁有者動作新增至組織中的所有信箱。本範例會假設該信箱稽核已經啟用的所有信箱。 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已成功啟用信箱的信箱稽核記錄，請使用 **Get-Mailbox** Cmdlet 來擷取該信箱的稽核設定。 
  
此範例會擷取 Pilar Pinilla 的稽核設定。

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
此範例會擷取您組織中所有使用者信箱的稽核設定。

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
提供驗證**AuditEnabled**屬性信箱的**則為 True**值該信箱稽核記錄已啟用。 
    
## <a name="mailbox-auditing-actions"></a>信箱稽核的動作
  
下表列出可以信箱所記錄的動作稽核記錄。表格包含可針對不同的使用者登入類型記錄的動作。在表格中，**無**表示巨集指令不會記錄以登入類型。星號 ( **\*** ) 會指出動作會記錄預設時信箱稽核記錄已啟用信箱。 
  
|**動作**|**描述**|**Admin**|**委派\*\*\***|**擁有者**|
|:-----|:-----|:-----|:-----|:-----|
|**Copy** <br/> |郵件已複製到另一個資料夾。  <br/> |是  <br/> |否   <br/> |否  <br/> |
|**Create** <br/> |在信箱 ； 中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目例如，會建立新的會議邀請。請注意不稽核建立、 傳送或接收郵件。此外，不稽核建立信箱資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**FolderBind** <br/> |已存取信箱資料夾。系統管理員或代理人開啟信箱時也會記錄此動作。  <br/> |是  <br/> |[是]\*\*  <br/> |否  <br/> |
|**HardDelete** <br/> |郵件已經從 [可復原的項目] 資料夾清除。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**MailboxLogin** <br/> |使用者已登入其信箱。  <br/> |否  <br/> |否  <br/> |是  <br/> |
|**MessageBind** <br/> |在預覽窗格中檢視郵件或將它開啟。  <br/> |是  <br/> |否   <br/> |否  <br/> |
|**Move** <br/> |郵件已移到另一個資料夾。  <br/> |是  <br/> |是   <br/> |可以  <br/> |
|**MoveToDeletedItems** <br/> |郵件已遭刪除並移至 [刪除的郵件] 資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**SendAs** <br/> |已使用 SendAs 權限傳送郵件。這表示，另一個使用者已傳送郵件，就像此郵件是來自信箱擁有者一樣。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SendOnBehalf** <br/> |已使用 SendOnBehalf 權限傳送郵件。這表示，另一個使用者已代表信箱擁有者傳送郵件。此郵件會向收件者指示，此郵件是代表誰傳送，以及實際傳送郵件的人是誰。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SoftDelete** <br/> |郵件已永久刪除或從 [刪除的郵件] 資料夾刪除。虛刪除的項目會移至 [可復原的項目] 資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**更新** <br/> |郵件或其屬性已變更。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**UpdateCalendarDelegation** <br/> |行事曆委派已指派給信箱。行事曆委派可讓其他人在相同的組織權限管理信箱擁有者的行事曆。  <br/> |是\*  <br/> |否  <br/> |是\*  <br/> |
|**UpdateFolderPermissions** <br/> |已變更的資料夾權限。資料夾的權限控制您組織中的使用者可以存取信箱和那些資料夾中的郵件中的資料夾。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateInboxRules** <br/> |收件匣規則已新增、 移除或變更。收件匣規則可用來處理郵件的收件匣根據指定的條件和符合規則的條件，例如將郵件移至指定的資料夾或刪除郵件時採取的動作。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>如果已啟用信箱，稽核預設。<br/><br/>  <sup>\*\*</sup>合併資料夾繫結動作委派所執行的項目。24 小時的時間範圍內的個別資料夾存取產生一個日誌項目。<br/><br/><sup>\*\*\*</sup>已指派完整存取權給使用者的信箱的系統管理員會被視為委派使用者。 
  
如果您不再需要特定類型的信箱稽核的動作，您應修改停用這些動作的信箱稽核記錄設定。直到達到稽核記錄項目保留時間限制未清除現有的記錄項目。如需稽核記錄項目保留期間的詳細資訊，請參閱 ＜[的搜尋稽核登入 Office 365 安全性 & 規範中心](search-the-audit-log-in-security-and-compliance.md#before-you-begin)的 「 之前 」 一節。
  
## <a name="more-infotab"></a>[其他資訊](#tab/)
  
- 使用 Office 365 稽核記錄來搜尋信箱活動已登入。您可以搜尋特定的使用者信箱的活動。下列螢幕擷取畫面顯示您可以在 Office 365 稽核記錄檔中搜尋的信箱活動清單。請注意這些活動本主題的 「 信箱稽核動作 」 一節所述的相同動作。
    
    ![您可以搜尋信箱稽核動作的 Office 365 稽核記錄中的活動] 下拉式清單中選取 ["的 Exchange 信箱活動"](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    下表說明每個信箱活動您可以搜尋並顯示對應的信箱稽核巨集指令。
    
    |**在稽核記錄中的活動**|**信箱稽核巨集指令**|
    |:-----|:-----|
    |建立的信箱項目  <br/> |建立  <br/> |
    |複製到另一個資料夾的郵件  <br/> |複製  <br/> |
    |使用者登入信箱  <br/> |MailboxLogin  <br/> |
    |傳送郵件使用傳送代理者權限  <br/> |SendOnBehalf  <br/> |
    |從信箱清除的郵件  <br/> |HardDelete  <br/> |
    |移至刪除的郵件] 資料夾的郵件  <br/> |MoveToDeletedItems  <br/> |
    |移至另一個資料夾的郵件  <br/> |Move  <br/> |
    |傳送郵件使用下列傳送] 權限  <br/> |SendAs  <br/> |
    |更新的郵件  <br/> |更新  <br/> |
    |從 [刪除的郵件] 資料夾刪除的郵件  <br/> |SoftDelete  <br/> |
    |新增至資料夾的權限  <br/> |UpdateFolderPermissions  <br/> |
    |已修改的權限的資料夾  <br/> |UpdateFolderPermissions  <br/> |
    |已移除從資料夾的權限  <br/> |UpdateFolderPermissions  <br/> |
    |新增或移除使用者行事曆] 資料夾的代理人存取權  <br/> |UpdateCalendarDelegation  <br/> |
   
    請注意上述的螢幕擷取畫面所示的**已新增委派信箱權限**與**已移除委派信箱權限**活動不相關信箱稽核的動作。這些指示是否以系統管理員指派或移除的 FullAccess 信箱權限。 
    
    Office 365 稽核記錄的相關資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。
    
- 在下列案例中，信箱會被視為只能由系統管理員存取：
    
  - 在 Exchange Online 或 Office 365 中的內容搜尋中的就地 eDiscovery 來搜尋信箱。
    
  - [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用來存取信箱。 
    
- 啟用信箱的稽核記錄時，也可指定針對各個登入類型 (系統管理員、代理人或擁有者) 將記錄哪些使用者動作 (例如存取、移動或刪除郵件)。 
    
- 若要停用信箱稽核記錄，請執行下列命令：

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- 當您執行**Get-mailbox**指令程式時不顯示各類型的使用者稽核的動作。但是您可以執行下列命令以顯示特定使用者登入類型的所有稽核的動作。 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- 您也可以匯出信箱稽核記錄，並指定要包含的一或多個使用者的項目。報告和稽核記錄中的每個項目包含有關誰執行巨集指令與時所執行的動作，以及動作是否成功的資訊。如需詳細資訊，請參閱[匯出信箱稽核記錄](https://go.microsoft.com/fwlink/p/?LinkID=404104)。
