---
title: 在安全性 & 規範中心啟用封存信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用安全性 & 在 Office 365 規範中心啟用封存信箱以支援您的組織郵件保留、 eDiscovery 和保留需求。
ms.openlocfilehash: d363943910d970576976d8386196b450dd5694f3
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31813964"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a>在安全性 & 規範中心啟用封存信箱
  
封存 （也稱為 「 就地封存） 的 Office 365 中提供使用者額外信箱儲存空間。 開啟封存信箱之後，使用者可以存取，並使用 Microsoft Outlook 和 Outlook 網頁 （原先稱為 Outlook Web App） 上的，將郵件儲存在他們的封存信箱。 使用者也可以移動或複製其主要信箱和封存信箱之間的郵件。 他們也可以使用 「 復原刪除的項目 」 工具，從其封存信箱中的 [可復原的項目] 資料夾復原刪除的項目。 
  
> [!TIP]
> Office 365 提供無限制的封存儲存與自動展開封存功能數量。 當自動展開封存已開啟，且然後達到使用者的封存信箱中的儲存配額時，Office 365 會自動加入額外的儲存空間。 這表示，使用者將不會執行信箱儲存空間不足，並不會有任何項目最初管理後啟用封存信箱，並開啟自動展開封存為您的組織。 如需詳細資訊，請參閱 [在 Office 365 中的無限制封存的概觀](unlimited-archiving.md)。 
  
## <a name="before-you-begin"></a>開始之前

您必須獲指派 「 郵件收件者角色在 Exchange Online 來啟用或停用封存信箱。 根據預設，此角色被指派給在 Exchange 系統管理中心中的**權限**] 頁面上的收件者管理與組織管理角色群組。 如果您沒有看到安全性 & 合規性中心中的 [**封存**] 頁面上，要求您的系統管理員指派必要權限。 
  
## <a name="enable-an-archive-mailbox"></a>啟用封存信箱
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **封存**。
    
    [封存]**** 頁面隨即出現。 [封存信箱] **** 欄會指出每個使用者的封存信箱是啟用還是停用。 
    
4. 在信箱清單中，選取要為其啟用封存信箱的使用者。
    
    ![若要啟用封存信箱所選使用者的詳細資料窗格中按一下 [啟用](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. 在所選使用者詳細資料窗格中，按一下 [**啟用**]。 
    
    說，是否您啟用封存信箱，在使用者的信箱會超過封存原則指派給信箱的項目要移至新的封存信箱會顯示警告。 預設封存原則指派給 Exchange Online 信箱的保留原則的一部分，將項目移至封存信箱兩年後的項目已傳遞至信箱或使用者所建立的日期。 如需詳細資訊，請參閱這篇文章中的**詳細資訊**一節。 
    
6. 按一下 [是]**** 啟用封存信箱。 
    
    可能需要一些時間才能建立封存信箱。 建立時，**封存信箱： 啟用**會顯示在詳細資料窗格中選取的使用者。 您可能需要按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。 
    
> [!TIP]
> 您也可以選取多個信箱 (使用 Shift 或 Ctrl 鍵) 來大量啟用封存。選取多個信箱後，按一下詳細資料窗格中的 [啟用]****。 
  
## <a name="disable-an-archive-mailbox"></a>停用封存信箱
  
您也可以使用安全性 & 合規性中心中的 [**封存**] 頁面上，停用使用者的封存信箱。 停用封存信箱之後，可以在停用它的 30 天內重新連線至使用者的主要信箱。 在此情況下，系統會還原封存信箱的原始內容。 30 天後，便會永久刪除原始封存信箱的內容，無法再復原。 因此，如果您在停用封存超過 30 天之後才重新啟用它，系統會建立新的封存信箱。 
  
請注意，預設封存原則指派給使用者的信箱移至封存信箱的項目兩年的日期之後的項目會傳遞。 如果您停用使用者的封存信箱，將會對信箱項目採取任何動作，他們會一直保留在使用者的主要信箱。
  
若要停用封存信箱：
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在 [安全性 & 合規性中心的左窗格中，按一下 [**資料控管** \> **封存**。
    
    [封存]**** 頁面隨即出現。[封存信箱] **** 欄會指出每個使用者的封存信箱是啟用還是停用。 
    
4. 在信箱清單中，選取要為其停用封存信箱的使用者。
    
5. 在詳細資料窗格中，按一下 [停用]****。 
    
    會顯示警告訊息，指出您有 30 天的時間可以重新啟用封存信箱，並，30 天後，在封存中的所有資訊將會永久都刪除。 
    
6. 按一下 [是]**** 停用封存信箱。 
    
    可能需要一些時間才能停用封存信箱。 停用它時，**封存信箱： 停用**會顯示在詳細資料窗格中選取的使用者。 您可能需要按一下 [**重新整理**![重新整理圖示](media/O365-MDM-Policy-RefreshIcon.gif)以更新詳細資料窗格中的資訊。 
    
> [!TIP]
> 您也可以選取多個已啟用封存信箱的使用者 (使用 Shift 或 Ctrl 鍵) 來大量停用封存信箱。選取多個信箱後，按一下詳細資料窗格中的 [停用]****。 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>使用 Exchange Online PowerShell 來啟用或停用封存信箱

您也可以使用 Exchange Online PowerShell 來啟用封存信箱。 若要使用 PowerShell 的主要原因是，您可以快速貴組織中啟用所有使用者的封存信箱。

第一個步驟是連線至 Exchange Online PowerShell。 如需相關指示，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。

在您連線至 Exchange Online 之後，您可以在以下小節以啟用或停用封存信箱中執行命令。

### <a name="enable-archive-mailboxes"></a>啟用封存信箱

執行下列命令，以啟用單一使用者的封存信箱。
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

執行下列命令，以啟用的組織 （其封存信箱目前未啟用） 中的所有使用者的封存信箱。
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>停用封存信箱

執行下列命令，以停用單一使用者的封存信箱。
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

執行下列命令，以停用的組織 （目前已啟用封存信箱） 中的所有使用者的封存信箱。
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>詳細資訊
  
- 封存信箱幫助您和您的使用者以符合您的組織保留、 eDiscovery 和保留需求。 例如，您可以使用您組織的 Exchange 保留原則，將信箱內容移至使用者的封存信箱。 當您使用安全性 & 合規性中心中的 「 內容搜尋 」 工具來搜尋特定內容的使用者的信箱時，也會搜尋使用者的封存信箱。 然後放置訴訟暫止狀態或 Office 365 保留原則套用至使用者的信箱時，也會保留在封存信箱中的項目。
  
- 啟用封存信箱時，使用者可以將郵件儲存在其封存信箱。 使用者可以使用 Microsoft Outlook 和網頁型 Outlook 來存取他們的封存信箱。 只要使用這些用戶端應用程式，使用者就能檢視其封存信箱中的郵件，並且在其主要信箱與其封存信箱之間移動或複製郵件。 使用者也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。 
  
- 在啟用信箱的封存之後, 您的組織可以利用之預設 Exchange 保留原則 （也稱為 「 通訊記錄管理 」 或 「 MRM 原則 」） 會自動指派給每個信箱。 啟用封存信箱時，預設 Exchange 保留原則自動會執行下列動作： 
  
    - 將使用者主要信箱中兩年以上的郵件移到其封存信箱。 
    
    - 將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。
    
- 如需有關封存信箱和 Exchange 保留原則的詳細資訊，請參閱：
    
  - [保留標記和保留原則](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [預設保留原則在 Exchange Online ](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [設定 Office 365 組織中信箱的封存和刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
