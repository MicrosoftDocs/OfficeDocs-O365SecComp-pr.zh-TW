---
title: 復原 Office 365 中不在作用中信箱
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
description: '如果先前的員工會傳回您組織中，或將新的員工雇用採取 departed 員工的工作職責，您可以復原 Office 365 中的非使用中信箱的內容。當您復原不在作用中的信箱時，它會轉換成新的信箱包含非作用中信箱的內容。 '
ms.openlocfilehash: f5c844b5841518f1aa74a122d4c43663ebcccd14
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295836"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>復原 Office 365 中不在作用中信箱

（這是一種虛刪除信箱） 的非使用中信箱用來保留先前員工的電子郵件之後他離開貴組織。如果該員工會傳回您組織或另一位員工則是在先前的員工的工作職責上，有兩種方式您可以決定將非使用中信箱的內容提供給使用者： 
  
- **復原不在作用中的信箱**如果先前的員工會傳回您組織中，或將新的員工雇用才會在先前的員工的工作職責，您可以復原不在作用中信箱的內容。此方法會將非使用中信箱轉換至新的作用中信箱包含非作用中信箱的內容。它會復原之後，非使用中的信箱不存在。本主題中的程序說明此方法。 
    
- **還原非使用中的信箱**如果另一位員工採用在先前的員工、 工作職責或另一位使用者需要存取非使用中信箱的內容，您可以還原 （或合併） 至現有的信箱不在作用中信箱的內容。您也可以從非使用中信箱還原封存。此方法的程序，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。
    
請參閱[的詳細資訊](recover-an-inactive-mailbox.md#moreinfo)] 區段中復原與還原為非作用中信箱之間差異的詳細資訊與復原非使用中的信箱時會發生什麼情況的描述。
  
> [!NOTE]
> 我們已延遲就地保留來讓信箱成為非使用中新建立的期限。但在某些未來，您將不能夠新就地保留 Exchange Online 中建立。該次僅訴訟保留與 Office 365 的保留原則可用來建立非使用中的信箱。不過，仍會支援現有的非使用中信箱上就地保留，而您可以繼續管理非使用中的信箱上的就地保留。這包括變更為 「 就地保留持續時間和永久刪除非使用中的信箱移除就地保留 」 狀態。 
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 來還原非使用中的信箱。您無法使用 Exchange 系統管理中心 (EAC)。如需逐步說明，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 執行下列命令以取得組織中不在作用中信箱的身分識別資訊。 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    使用這個命令所傳回的資訊來復原特定的非使用中信箱。
    
- 如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="recover-an-inactive-mailbox"></a>復原非使用中的信箱

搭配*InactiveMailbox*參數的**New-mailbox**指令程式來復原不在作用中的信箱。 
  
1. 建立包含非作用中信箱之屬性的變數。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > 在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。這些屬性是唯一的組織中每個信箱，而很可能使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。 
  
2. 本範例會使用在上一個命令中取得的內容並復原到 Ann Beebe 的使用者使用中信箱不在作用中的信箱。是確定組織內唯一的*名稱*和*MicrosoftOnlineServicesID*參數指定值。 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    為要復原的非使用中信箱的主要 SMTP 位址必須*MicrosoftOnlineServicesID*參數所指定的一個相同的值。 
    
不在作用中的信箱復原之後，也會建立新的 Office 365 使用者帳戶。您必須將授權指派啟動此使用者帳戶。若要指派 Office 365 系統管理中心中的授權，請參閱[指派或取消指派 Office 365 企業版授權](https://go.microsoft.com/fwlink/p/?LinkId=276798)。
  
## <a name="more-information"></a>詳細資訊

- **什麼是復原及還原不在作用中信箱的主要差異？** 當您復原不在作用中的信箱時，信箱基本上會轉換為新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。它復原、 非使用中的信箱不存在，以及對新的信箱中的內容進行任何變更會影響原本的內容之後保留在非使用中的信箱。反之，當您還原非使用中的信箱，內容純粹都會複製到另一個信箱。非使用中的信箱已受保護而會維持不在作用中的信箱。目標信箱中的內容進行任何變更將不會影響保存在非使用中信箱的原始內容。非使用中信箱仍可使用就地 eDiscovery 搜尋、 其內容可以還原至另一個信箱或復原或刪除日後。 
    
- **不在作用中的信箱復原時會發生什麼情況？** 當您復原不在作用中的信箱時，便會發生下列事項： 
    
  - 已移除訴訟資料暫留 （如果已啟用非作用中信箱）。
    
  - 會移除就地保留。這表示不在作用中信箱以任何在暫止或就地 eDiscovery 搜尋中來源信箱移除。 
    
  - 非使用中的信箱已從任何 Office 365 的保留原則移除該位置套用。
    
  - （這**RetainDeletedItemsFor**信箱屬性所定義） 的單一項目復原期間設為 30 天。一般而言，新的信箱建立時在 Exchange Online，此保留期間設為 14 天。這個設定設為 30 天的最大值可讓您更多時間以復原任何已永久刪除 （或清除） 的資料從非使用中的信箱。您也可以停用單一項目復原或設定單一項目復原期間回到預設值為 14 天。如需詳細資訊，請參閱[啟用或停用單一項目復原的信箱](https://go.microsoft.com/fwlink/?linkid=856769)。
    
  - 已啟用保留功能，並保留保留持續時間設為 30 天。這表示預設 Exchange 保留原則和指派給新的信箱的保留原則不會處理 30 天的任何整個組織或 Exchange 全 Office 365。這可讓傳回員工或非使用中的信箱復原的時間的新擁有人管理舊郵件。否則請 Exchange 或 Office 365 保留原則可能會刪除舊的信箱項目 （或將項目移至封存信箱，如果已啟用） 已過期根據設定 Exchange 或 Office 365 保留原則的設定。30 天後保留過期**RetentionHoldEnabled**信箱屬性設為**False**，且受管理的資料夾助理員開始處理指派給信箱的原則。如果您不需要此額外的時間，您可以只移除保留功能。或者，您可以使用**Set-mailbox EndDateForRetentionHold**命令增加保留持續的時間。如需詳細資訊，請參閱[就地保留信箱保留 」 狀態](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **復原的信箱上設定保留，若您要保留的非使用中信箱的原始狀態。** 若要防止永久刪除任何郵件從要復原的非使用中信箱的新信箱擁有者或保留原則，您可以信箱置於訴訟保留的詳細資訊，請參閱[Place 在訴訟暫止狀態的信箱](https://go.microsoft.com/fwlink/?linkid=856286)。
    
- **哪些使用者識別碼可以使用時的復原不在作用中的信箱？** 當您復原不在作用中的信箱時，您為*MicrosoftOnlineServicesID*參數指定的值可以是與原始一個非使用中的信箱與關聯的不同。您也可以使用原始使用者識別碼。但先前所述，確認*名稱*] 和 [ *MicrosoftOnlineServicesID*所用的值是唯一組織內時復原不在作用中的信箱。 
    
- **不在作用中信箱的信箱保留期間尚未過期怎麼辦吗？** 如果不在作用中的信箱虛刪除早於 30 天，您無法復原它使用**New-mailbox InactiveMailbox**命令。您必須復原來還原對應的 Office 365 使用者帳戶。如需詳細資訊，請參閱[刪除或還原使用者](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **如何知道不在作用中信箱的虛刪除信箱保留期間是否已經過期？** 執行下列命令。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    如果沒有**ExternalDirectoryObjectId**屬性的值，信箱保留期間內已過期，以及您可以執行**New-mailbox InactiveMailbox**命令來復原不在作用中的信箱。如果沒有**ExternalDirectoryObjectId**屬性的值，虛刪除信箱保留期間尚未過期，且必須復原信箱還原 Office 365 使用者帳戶。請參閱[刪除或還原使用者](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **不在作用中的信箱復原之後啟用封存信箱的考量事項。** 這可讓您傳回使用者或新員工將舊郵件移至封存信箱。與時保留過期的封存原則屬於預設 Exchange 保留原則指派給 Exchange Online 信箱移相關的兩個年度的項目或較舊的封存信箱。如果您不要啟用封存信箱，超過兩個年度的項目將會保留在使用者的主要信箱。如需詳細資訊，請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)。
 