---
title: 復原非使用中信箱 Office 365 中
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果將離職員工返回您的組織，或是新進員工雇用採取將承接已離開員工工作職責，您可以復原非使用中信箱 Office 365 中的內容。 當您復原非使用中的信箱時，它會轉換為新的信箱，其中包含非作用中信箱的內容。 '
ms.openlocfilehash: c7f942c518dcc74a4bdb37d67e27e8a63879ab46
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261541"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>復原非使用中信箱 Office 365 中

非使用中信箱 （也就是一種虛刪除的信箱） 用來他或她離開組織之後保留離職員工的電子郵件。 如果該員工返回您的組織或另一位員工承擔離職員工的工作職責，有兩種方法可將非作用中信箱的內容提供給使用者： 
  
- **復原非使用中信箱**如果離職員工返回您的組織，或是新進員工雇用採取離職員工的工作職責，您可以復原非使用中信箱的內容。 此方法會將作用中的信箱轉換至新的作用中信箱，其中包含非作用中信箱的內容。 它會復原之後，非使用中的信箱不存在。 本主題中的程序將說明此方法。 
    
- **還原非使用中信箱**如果另一位員工承擔離職員工的工作職責或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 到現有的信箱不在作用中信箱的內容。 您也可以從非使用中信箱還原封存。 此方法的程序，請參閱 <<c0>還原 Office 365 中的非使用中信箱。
    
請參閱 <<c0>的詳細資訊] 區段中如需詳細資訊可用來復原和還原非使用中的信箱之間的差異，以及復原非使用中信箱時，會發生什麼情況的描述。
  
> [!NOTE]
> 我們已建立新的就地保留 」 來停用信箱的期限延後。 但有些時候以後，您無法建立新的就地保留在 Exchange Online。 到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。 不過，仍會支援「就地保留」上現有的非作用中信箱，並且您可以繼續管理非作用信箱上的「就地保留」。 這包括變更就地保留期間以及透過移除就地保留以永久刪除非作用中的信箱。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。 您無法使用 Exchange 系統管理中心 (EAC)。 如需逐步指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
- 執行下列命令，以取得您組織中的非使用中信箱的身分識別資訊。 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    若要復原特定的非使用中信箱使用這個命令所傳回的資訊。
    
- 如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。
    
## <a name="recover-an-inactive-mailbox"></a>復原非作用中的信箱

若要復原非使用中信箱搭配*InactiveMailbox*參數**New-mailbox**指令程式。 
  
1. 建立包含非作用中信箱的內容的變數。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > 在上述命令中，使用 [ **DistinguishedName** ] 或 [ **ExchangeGUID**屬性的值來識別非使用中的信箱。 這些屬性是唯一的組織中每個信箱，而是可能作用中或非使用中的信箱可能會有相同的主要 SMTP 位址。 
  
2. 本範例會使用在前一個命令中所取得的屬性，並會復原至使用者 Ann Beebe 的作用中信箱的非使用中信箱。 是確定貴組織中唯一的*名稱*和*MicrosoftOnlineServicesID*參數所指定的值。 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    復原非使用中信箱的主要 SMTP 位址必須*MicrosoftOnlineServicesID*參數所指定的一個相同的值。 
    
復原非使用中信箱之後，也會建立新的 Office 365 使用者帳戶。 您必須指派授權來啟用此使用者帳戶。 若要在 Microsoft 365 系統管理中心中指派授權，請參閱[指派或解除指派商務用 Office 365 的授權](https://go.microsoft.com/fwlink/p/?LinkId=276798)。
  
## <a name="more-information"></a>詳細資訊

- **復原和還原非使用中信箱的主要差異是什麼？** 當您復原非使用中的信箱時，信箱基本上轉換成新的信箱、 仍會保留的內容和非使用中信箱的資料夾結構，以及信箱連結到新的使用者帳戶。 它會復原後，在作用中的信箱不存在，任何新的信箱中的內容所做的變更會影響原先的內容保留在作用中信箱。 相反地，當您還原非使用中信箱時，內容只會複製到另一個信箱。 非使用中的信箱會保留，並會維持不在作用中的信箱。 任何目標信箱中的內容所做的變更不會影響原始內容保留在作用中的信箱。 非使用中信箱仍可使用就地 eDiscovery 搜尋、 其內容可以還原至另一個信箱，或復原或刪除日後。 
    
- **當您復原非使用中信箱時，會發生什麼事？** 當您復原非使用中的信箱，會發生下列情形： 
    
  - 已移除訴訟暫止狀態 （如果已啟用非使用中信箱）。
    
  - 會移除就地保留。 這表示，在作用中信箱也會移除為來源信箱從任何原有範圍暫止或就地 eDiscovery 搜尋。 
    
  - 非使用中的信箱已從任何 Office 365 保留原則，其中套用到它。
    
  - （這由**RetainDeletedItemsFor**信箱屬性所定義） 的單一項目復原期間設為 30 天。 一般而言，當建立新的信箱是在 Exchange Online，此保留期間設為 14 天。 這個值設為 30 天的最大值可讓您更多時間來復原已永久刪除 （或清除） 的任何資料從非使用中信箱。 您也可以停用單一項目復原，或設定單一項目復原期間回到預設值是 14 天。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](https://go.microsoft.com/fwlink/?linkid=856769)。
    
  - 已啟用保留功能，且保留保留期間設為 30 天。 這表示預設 Exchange 保留原則和指派給新信箱的保留原則不會處理 30 天內任何全組織或整個 Exchange 的 Office 365。 這可以讓傳回員工或復原非使用中信箱的時間的新擁有者來管理舊郵件。 否則，Exchange 或 Office 365 保留原則可能會刪除舊的信箱項目 （或將項目移至封存信箱，如果已啟用） 已過期根據對 Exchange 或 Office 365 保留原則設定的設定。 30 天之後，保留到期、 **RetentionHoldEnabled**信箱屬性設為**False**，並受管理的資料夾助理員開始處理指派給信箱的原則。 如果您不需要此額外的時間，您可以只移除保留功能。 或者，您可以使用**Set-mailbox EndDateForRetentionHold**命令增加保留持續的時間。 如需詳細資訊，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **上設定保留要復原的信箱如果您需要保留非使用中信箱的原始狀態。** 若要防止永久刪除任何郵件從復原非使用中信箱的新信箱擁有者或保留原則，您可以讓信箱處於訴訟暫止的詳細資訊，請參閱[為信箱設定訴訟暫止](https://go.microsoft.com/fwlink/?linkid=856286)。
    
- **復原非使用中信箱時是否可以使用哪些使用者識別碼？** 當您復原非使用中的信箱時，您指定給*MicrosoftOnlineServicesID*參數的值可以是不同於原始已非使用中信箱相關聯。 您也可以使用原始使用者識別碼。 但是，如先前所述，請確定所使用的*名稱*和*MicrosoftOnlineServicesID*值是組織內唯一的當您復原非使用中信箱。 
    
- **如果不在作用中信箱的信箱保留期間尚未過期嗎？** 如果不在作用中信箱是不是虛刪除小於 30 天，您無法使用**New-mailbox InactiveMailbox**命令復原。 您必須復原來還原對應的 Office 365 使用者帳戶。 如需詳細資訊，請參閱[刪除或還原使用者](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **如何知道是否非使用中信箱的虛刪除信箱保留期間已經過期？** 執行下列命令。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    如果沒有**ExternalDirectoryObjectId**屬性的值，在信箱保留期間到期，您可以藉由執行**New-mailbox InactiveMailbox**命令復原非使用中信箱。 如果沒有**ExternalDirectoryObjectId**屬性的值，虛刪除信箱保留期間尚未到期，而且您必須還原 Office 365 使用者帳戶來復原信箱。 請參閱[刪除或還原使用者](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **請考慮之後復原非使用中的信箱啟用封存信箱。** 這可讓傳回使用者或新進員工將舊的郵件移至封存信箱。 當保留到期時，封存原則，而且是預設 Exchange 保留原則指派給 Exchange Online 信箱會移動兩年的項目或更舊版本至封存信箱的一部分。 如果您未啟用封存信箱，超過兩年內的項目會保留在使用者的主要信箱。 如需詳細資訊，請參閱[中 Office 365 安全性的啟用封存信箱&amp;合規性中心](enable-archive-mailboxes.md)。
 