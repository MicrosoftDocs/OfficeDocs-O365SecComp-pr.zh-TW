---
title: 還原 Office 365 中的非使用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新進員工或另一位使用者需要存取 Office 365 中的非使用中信箱的內容，您可以還原 （或合併） 到現有的信箱不在作用中信箱的內容。
ms.openlocfilehash: 1b80cf5bf9361959f1622b7b42f5c7598609539c
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999306"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>還原 Office 365 中的非使用中信箱

非使用中信箱 （也就是一種虛刪除的信箱） 用來他或她離開組織之後保留離職員工的電子郵件。 如果另一位員工承擔承接已離開員工工作職責，或者該員工返回您的組織，有兩種方法可將非作用中信箱的內容提供給使用者： 
  
- **還原非使用中信箱**如果另一位員工承擔承接已離開員工的工作職責或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 到現有的信箱不在作用中信箱的內容。 您也可以從非使用中信箱還原封存。 它會還原後，非使用中的信箱會保留，並會保留為非使用中的信箱。 本主題說明用來還原非使用中信箱的程序。 
    
- **復原非使用中信箱**如果承接已離開的員工返回您的組織，或是新進員工雇用採取承接已離開員工工作職責，您可以復原非使用中信箱的內容。 此方法會將作用中的信箱轉換成新的信箱，其中包含非作用中信箱的內容。 它會復原之後，非使用中的信箱不存在。 如需逐步程序，請參閱[復原非使用中信箱 Office 365 中](recover-an-inactive-mailbox.md)。
    
請參閱這篇文章，如需詳細資訊還原和復原非使用中的信箱之間的差異**的詳細資訊**一節。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。 您無法使用 Exchange 系統管理中心 (EAC)。 如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
- 下列命令在 Exchange Online PowerShell 中執行若要取得您組織中的非使用中信箱的身分識別資訊。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     若要還原特定的非使用中信箱使用這個命令所傳回的資訊。
    
- 如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。
    
## <a name="restore-an-inactive-mailbox"></a>還原非使用中的信箱

使用**New-mailboxrestorerequest**指令程式搭配_SourceMailbox_和_TargetMailbox_參數，非使用中信箱的內容還原到現有的信箱。 如需使用此 cmdlet 的詳細資訊，請參閱[New-mailboxrestorerequest](https://go.microsoft.com/fwlink/?linkid=856298)。
  
1. 建立包含非作用中信箱的內容的變數。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGUID**屬性的值來識別非使用中的信箱。 這些屬性是唯一的組織中每個信箱，而是可能作用中或非使用中的信箱可能會有相同的主要 SMTP 位址。 
  
2. 非使用中信箱的內容還原到現有的信箱。 非使用中信箱 （來源信箱） 的內容將被合併到現有信箱 （目標信箱） 中相對應的資料夾。
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   或者，您可以指定最上層資料夾中用來從非使用中信箱還原內容的目標信箱中。 如果目標信箱中不存在的指定的目標資料夾或目標資料夾結構，則會建立在還原程序。 
    
    此範例會將信箱項目及從非使用中信箱至名為 「 非使用中信箱 」 資料夾的子資料夾複製目標信箱的最上層資料夾結構中。
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>從非使用中的信箱還原封存

如果不在作用中信箱有封存信箱，可以也將它還原到現有信箱的封存信箱。 若要從非使用中的信箱還原封存，您必須將_SourceIsArchive_和_TargetIsAchive_參數新增至用來還原非使用中信箱的命令。 
  
1. 建立包含非作用中信箱的內容的變數。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGUID**屬性的值來識別非使用中的信箱。 這些屬性是唯一的組織中每個信箱，而是可能作用中或非使用中的信箱可能會有相同的主要 SMTP 位址。 
  
2. 非使用中信箱 （來源封存） 封存的內容，還原至現有信箱 （目標封存） 封存中。 在這個範例中，從來源封存的內容複製到目標信箱的封存中名為 「 非使用中信箱封存 」 資料夾。

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>詳細資訊

- **復原和還原非使用中信箱的主要差異是什麼？** 當您復原非使用中的信箱時，信箱基本上轉換成新的信箱、 仍會保留的內容和非使用中信箱的資料夾結構，以及信箱連結到新的使用者帳戶。 它會復原後，在作用中的信箱不存在，任何新的信箱中的內容所做的變更會影響原先的內容保留在作用中信箱。 相反地，當您還原非使用中信箱時，內容只會複製到另一個信箱。 非使用中的信箱會保留，並會維持不在作用中的信箱。 任何目標信箱中的內容所做的變更不會影響原始內容保留在作用中的信箱。 非使用中信箱仍可搜尋的安全性 & 合規性中心中使用[內容搜尋工具](run-a-content-search-in-the-security-and-compliance-center.md)、 其內容可以還原至另一個信箱，或復原或刪除日後。 
    
- **您要如何找到非使用中信箱？** 若要取得您組織中的非使用中信箱的清單，並顯示適合用來還原非使用中信箱的資訊，您可以執行此命令。 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **使用訴訟暫止狀態或 Office 365 保留原則來保留非使用中信箱的內容。** 如果您想要保留狀態的非使用中的信箱還原後，您可以啟用[訴訟暫](https://go.microsoft.com/fwlink/?linkid=856286)止的目標信箱，或套用[Office 365 保留原則](retention-policies.md)，再還原非使用中信箱。 這可防止從非使用中信箱的任何項目永久刪除之後他們正在還原至目標信箱。 
    
- **還原非使用中信箱之前，請啟用保留功能，在目標信箱。** 從非使用中信箱的信箱項目可能是舊，因為您可以考慮再還原非使用中的信箱啟用保留功能，在目標信箱。 當您對信箱設定保留保留，不會處理保留原則指派給它，直到移除保留功能，或直到保留期間到期為止。 這可以讓目標信箱時間來管理舊郵件從非使用中信箱的擁有者。 否則，保留原則可能會刪除舊項目 （或將項目移至封存信箱，如果已啟用） 已過期根據設定的目標信箱的保留設定。 如需詳細資訊，請參閱[就地保留信箱保留在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **AllowLegacyDNMismatch 參數做什麼？** 在還原非使用中信箱前一個範例中， **AllowLegacyDNMismatch**參數用來允許不在作用中信箱還原至不同的目標信箱。 在一般還原案例中，目標是要還原的內容來源和目標信箱所在位置，同一個信箱。 因此依預設， **New-mailboxrestorerequest**指令程式會檢查以確定來源和目標信箱的**LegacyExchangeDN**屬性的值是相同。 這有助於防止您不小心將來源信箱還原到錯誤的目標信箱。 如果您嘗試還原非使用中的信箱，而不使用**AllowLegacyDNMismatch**參數，命令可能會失敗如果來源和目標信箱有不同的**LegacyExchangeDN**屬性的值。 
    
- **您可以使用 New-mailboxrestorerequest 指令程式搭配其他參數，來實作不同的還原案例的非使用中信箱。** 例如，您可以執行此命令以將封存從非使用中信箱還原至目標信箱的主要信箱。 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  您也可以執行此命令，來還原至目標信箱的封存的非使用中的主要信箱。

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **用途 TargetRootFolder 參數？** 如先前所述，您可以使用**TargetRootFolder**參數指定的資料夾中 （也稱為根） 的資料夾結構的頂端在目標信箱中用來還原非使用中信箱的內容。 如果您未使用此參數，從非使用中信箱的信箱項目已合併成的目標信箱的對應預設資料夾，而自訂資料夾存在於目標信箱的根目錄中重新建立。 下列圖例反白顯示這些差異不使用，而且使用**TargetRootFolder**參數。 
    
    **在目標信箱時未使用 TargetRootFolder 參數的資料夾階層**
    
    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **在目標信箱使用 TargetRootFolder 參數時的資料夾階層**
    
    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](media/300da592-7323-48db-b8a4-07012259d113.png)

  

