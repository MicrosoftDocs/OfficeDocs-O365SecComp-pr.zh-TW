---
title: 還原 Office 365 中的非使用中信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新員工或另一位使用者需要存取 Office 365 中不在作用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。
ms.openlocfilehash: 671b13b913cddcfc3a7784d621b01b864b07e4e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214233"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>還原 Office 365 中的非使用中信箱

（這是一種虛刪除信箱） 的非使用中信箱用來保留先前員工的電子郵件之後他離開貴組織。如果另一位員工採用 departed 員工的工作職責上或該員工會傳回您組織，有兩種方式您可以決定將非使用中信箱的內容提供給使用者： 
  
- **還原非使用中的信箱**如果另一位員工採用 departed 員工、 工作職責上或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。您也可以從非使用中信箱還原封存。會還原後，非使用中的信箱已受保護而保留為非使用中的信箱。本主題說明的程序還原非使用中的信箱。 
    
- **復原不在作用中的信箱**如果 departed 的員工會傳回您組織中，或將新的員工雇用採取 departed 員工的工作職責，您可以復原不在作用中信箱的內容。此方法會將非使用中信箱轉換成新的信箱包含非作用中信箱的內容。它會復原之後，非使用中的信箱不存在。逐步程序，請參閱[Office 365 中的不在作用中信箱復原](recover-an-inactive-mailbox.md)。
    
請參閱如需詳細資訊還原與復原非使用中的信箱之間的差異本文中**的詳細資訊**] 區段。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。您無法使用 Exchange 系統管理中心 (EAC)。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 執行下列命令在 Exchange Online PowerShell 取得組織中不在作用中信箱的身分識別資訊。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     使用這個命令所傳回的資訊來還原特定的非使用中信箱。
    
- 如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="restore-an-inactive-mailbox"></a>還原非使用中的信箱

搭配_SourceMailbox_和_TargetMailbox_參數的**New-mailboxrestorerequest**指令程式來還原到現有的信箱不在作用中信箱的內容。如需使用此 cmdlet 的詳細資訊，請參閱[New-mailboxrestorerequest](https://go.microsoft.com/fwlink/?linkid=856298)。
  
1. 建立包含非作用中信箱之屬性的變數。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。 
  
2. 還原現有的信箱不在作用中信箱的內容。不在作用中的信箱 （來源信箱） 的內容會合併到現有的信箱 （目標信箱） 中所對應的資料夾。
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   或者，您可以指定最上層資料夾中用來從非使用中信箱還原內容的目標信箱。如果指定的目標資料夾或目標資料夾結構不存在的目標信箱中，它會建立在還原程序期間。 
    
    此範例會複製的信箱項目從非使用中的信箱至名為 「 不在作用中信箱 」 資料夾的子資料夾中的目標信箱的最上層資料夾結構。
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>從非使用中的信箱還原封存

如果不在作用中的信箱已封存信箱，您也可以還原它至現有的信箱的封存信箱。若要從非使用中信箱還原封存，您必須將_SourceIsArchive_和_TargetIsAchive_參數新增至用來還原非使用中信箱的命令。 
  
1. 建立包含非作用中信箱之屬性的變數。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。 
  
2. 從非使用中的信箱 （來源封存） 的封存的內容還原至現有的信箱 （目標封存） 封存中。在這個範例中，從來源封存的內容會複製到名為 「 不在作用中信箱封存 」 的目標信箱封存中的資料夾。

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>詳細資訊

- **什麼是復原及還原不在作用中信箱的主要差異？** 當您復原不在作用中的信箱時，信箱基本上會轉換為新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。它復原、 非使用中的信箱不存在，以及對新的信箱中的內容進行任何變更會影響原本的內容之後保留在非使用中的信箱。反之，當您還原非使用中的信箱，內容純粹都會複製到另一個信箱。非使用中的信箱已受保護而會維持不在作用中的信箱。目標信箱中的內容進行任何變更將不會影響保存在非使用中信箱的原始內容。非使用中信箱仍可使用 Office 365 安全性[內容搜尋工具](run-a-content-search-in-the-security-and-compliance-center.md)來搜尋&amp;規範中心及其內容可以還原至另一個信箱或復原或刪除日後。 
    
- **如何尋找非使用中信箱？** 若要取得組織中不在作用中信箱的清單和顯示還原非使用中信箱的有用的資訊，您可以執行此命令。 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **使用訴訟暫止狀態或 Office 365 保留原則來保留非使用中信箱內容。** 如果您想要還原後保留的非使用中的信箱狀態，您可以置於目標信箱[訴訟暫止狀態](https://go.microsoft.com/fwlink/?linkid=856286)或[Office 365 保留原則](retention-policies.md)套用之前還原非使用中的信箱。如此可防止從非使用中信箱的所有項目永久刪除之後所要還原的目標信箱。 
    
- **啟用保留目標信箱上再還原非使用中的信箱。** 從非使用中信箱的信箱項目可能是舊，因為您可能會考慮之前還原非使用中的信箱啟用目標信箱的保留。當您將放上保留信箱保留，直到移除保留或直到保留期間到期將不會處理保留原則指派給它。這可讓管理舊郵件從非使用中信箱擁有者的目標信箱時間。否則請保留原則可能會刪除舊項目 （或將項目移至封存信箱，如果已啟用） 已過期根據目標信箱的保留設定。如需詳細資訊，請參閱[就地保留信箱保留在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **AllowLegacyDNMismatch 交換器做什麼？** 在要還原的非使用中的信箱上一個範例中， **AllowLegacyDNMismatch**參數用來允許不在作用中信箱還原至不同的目標信箱。在一般還原案例中，目標是要還原的內容來源和目標信箱位於相同的信箱的位置。因此預設會**New-mailboxrestorerequest**指令程式會檢查確定來源與目標信箱上的**LegacyExchangeDN**屬性的值相同。這可幫助會防止您意外錯誤的目標信箱將還原的來源信箱。如果您嘗試還原非使用中的信箱，而不使用**AllowLegacyDNMismatch**參數，如果來源與目標信箱有不同屬性的值**LegacyExchangeDN**命令可能會失敗。 
    
- **您可以使用其他參數使用 New-mailboxrestorerequest 指令程式來實作的非使用中信箱的不同還原案例。** 例如，您可以執行此命令以從非使用中信箱的封存還原成的目標信箱的主要信箱。 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  您也可以還原至的目標信箱封存的非使用中的主要信箱執行此命令。

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **執行 TargetRootFolder 參數執行什麼？** 如先前所述，您可以使用**TargetRootFolder**參數來指定資料夾中 （也稱為根目錄） 的資料夾結構的頂端在要還原的非使用中信箱內容的目標信箱。如果您未使用此參數，從非使用中信箱的信箱項目已合併成對應的預設資料夾的目標信箱，以及自訂資料夾的根目錄的目標信箱中重新建立。下圖反白顯示這些未使用和使用**TargetRootFolder**參數之間的差異。 
    
    **目標信箱時不會使用 TargetRootFolder 參數中的資料夾階層**
    
    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **在 [目標信箱 TargetRootFolder 參數使用時的資料夾階層**
    
    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](media/300da592-7323-48db-b8a4-07012259d113.png)

  

