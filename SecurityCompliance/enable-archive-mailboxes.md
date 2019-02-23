---
title: 啟用封存信箱在 Office 365 安全性&amp;規範中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 安全性&amp;規範中心啟用封存信箱來支援您的組織訊息保留 eDiscovery 和保留需求。
ms.openlocfilehash: 10e20d09c531d6758d8011030aea64a6c30cdf9b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217283"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a>啟用封存信箱在 Office 365 安全性&amp;規範中心
  
Office 365 （也稱為就地封存） 中的封存提供使用者與其他信箱的儲存空間。開啟封存信箱之後，使用者可以存取和使用 Microsoft Outlook 和 Outlook web （前身為 Outlook Web App） 上的儲存其封存信箱中的郵件。使用者也可以移動或複製主要信箱和封存信箱之間的郵件。他們也可以從其封存信箱中的 [可復原的項目] 資料夾復原刪除的項目使用復原刪除的項目工具。 
  
> [!TIP]
> Office 365 提供封存存放區與 「 自動展開的封存功能的數量不受限制。如果自動展開封存已開啟，然後到達使用者的封存信箱中的初始儲存配額，Office 365 會自動新增額外儲存空間。這表示使用者不會執行移出信箱的儲存空間和您不必最初管理的任何項目之後啟用封存信箱並開啟自動展開您的組織的封存。如需詳細資訊，請參閱 ＜ [Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。 
  
## <a name="before-you-begin"></a>開始之前

您必須指派 「 郵件收件者 」 角色在 Exchange Online 啟用或停用封存信箱。根據預設，此角色指派給 Exchange 系統管理中心的 [**權限**] 頁面上的收件者管理及組織管理角色群組。如果您沒有看到 [**封存**] 頁面上的 [安全性]&amp;規範中心，詢問您要指派必要權限的管理員。 
  
## <a name="enable-an-archive-mailbox"></a>啟用封存信箱
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **封存**。
    
    會顯示 [**封存**] 頁面。**封存信箱**] 欄會指出是否啟用或停用每個使用者的封存信箱。 
    
4. 在信箱清單中，選取要為其啟用封存信箱的使用者。
    
    ![若要啟用封存信箱所選使用者的詳細資料窗格中按一下 [啟用]](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. 在所選使用者的詳細資料窗格中，按一下 [**啟用**]。 
    
    顯示一則警告訊息表示是否您啟用封存信箱，在使用者的信箱超過指派給信箱的封存原則的項目要移至新的封存信箱。預設封存原則指派給 Exchange Online 信箱的保留原則屬於將項目移至封存信箱項目已傳遞至信箱或使用者所建立的日期之後的兩個年度。如需詳細資訊，請參閱本文中的 [**詳細資訊**] 區段。 
    
6. 按一下 [**是]** 以啟用封存信箱。 
    
    可能需要一些時間建立封存信箱。建立、 後**封存信箱： 已啟用**會顯示所選使用者的詳細資料] 窗格中。您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。 
    
> [!TIP]
> 您可以也大量-啟用封存信箱中選取多位使用者與停用封存信箱 （使用 shift 鍵或 Ctrl 鍵）。選取多個信箱、 之後按一下 [詳細資料窗格中的 [**啟用**]。 
  
## <a name="disable-an-archive-mailbox"></a>停用封存信箱
  
您也可以使用 [**封存**] 頁面上的 [安全性]&amp;規範中心來停用使用者的封存信箱。停用封存信箱後，您可以將其重新連結至使用者的主要信箱停用它的 30 天內。在此例中，會還原封存信箱的原始內容。30 天後原始的封存信箱的內容會永久刪除和無法復原。因此，如果您重新啟用封存超過 30 天後停用它，會建立新的封存信箱。 
  
請注意預設封存原則指派給使用者的信箱移至封存信箱的項目日期之後的兩個年度項目被傳遞。如果您停用使用者的封存信箱，信箱項目將會採取任何動作與他們將保留於使用者的主要信箱。
  
若要停用封存信箱：
  
1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在 [安全性] 的左窗格中&amp;規範中心，按一下 [**資料控管** \> **封存**。
    
    會顯示 [**封存**] 頁面。**封存信箱**] 欄會指出是否啟用或停用每個使用者的封存信箱。 
    
4. 在信箱清單中，選取要為其停用封存信箱的使用者。
    
5. 在 [詳細資料] 窗格中，按一下 [**停用**]。 
    
    警告訊息會顯示預警您必須重新啟用封存信箱的 30 天的 30 天後封存中的所有資訊會永久都刪除。 
    
6. 按一下 [**是]** 以停用封存信箱。 
    
    可能需要一些時間來停用封存信箱。當停用時，**封存信箱： 已停用**會顯示所選使用者的詳細資料] 窗格中。您可能必須按一下 [**重新整理**![重新整理] 圖示](media/O365-MDM-Policy-RefreshIcon.gif)要更新的詳細資料窗格中的資訊。 
    
> [!TIP]
> 您可以也大量-停用封存信箱中選取多位使用者以啟用的封存信箱 （使用 shift 鍵或 Ctrl 鍵）。選取多個信箱、 之後按一下 [詳細資料窗格中**停用**。 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>使用 Exchange Online PowerShell 來啟用或停用封存信箱

您也可以使用 Exchange Online PowerShell 啟用封存信箱。若要使用 PowerShell 的主要原因是您快速可以啟用封存信箱的所有使用者在組織中。

第一個步驟是連線至 Exchange Online PowerShell。指示，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

您連線至 Exchange Online 後，您可以執行下列各節中啟用或停用封存信箱的命令。

### <a name="enable-archive-mailboxes"></a>啟用封存信箱

執行下列命令以啟用單一使用者的封存信箱。
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

執行下列命令以啟用 （封存信箱目前未啟用） 您組織中的所有使用者的封存信箱。
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>停用封存信箱

執行下列命令以停用單一使用者的封存信箱。
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

執行下列命令以停用 （目前啟用封存信箱） 您組織中的所有使用者的封存信箱。
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>詳細資訊
  
- 封存信箱協助您和使用者以符合您的組織保留 eDiscovery 和保留需求。例如，您可用於您組織的 Exchange 保留原則信箱內容移至使用者的封存信箱。當您使用 「 內容搜尋工具安全性&amp;也可搜尋規範中心來搜尋特定的內容、 使用者的封存信箱的使用者的信箱。並放置訴訟暫止狀態或 Office 365 保留原則套用至使用者的信箱、 時也會保留在封存信箱中的項目。
  
- 啟用封存信箱時，使用者可以封存信箱中儲存的郵件。使用者可以使用 Microsoft Outlook 與 web 上的 Outlook 來存取封存信箱。使用下列任一這些用戶端應用程式，使用者可以檢視他們的封存信箱中的郵件及移動或複製主要信箱和封存信箱之間的郵件。使用者可以復原刪除的項目從其封存信箱中的 [可復原的項目] 資料夾使用復原刪除的項目工具。 
  
- 啟用信箱的封存之後, 您的組織可以利用預設 Exchange 保留原則的 （也稱為 「 郵件記錄管理或 MRM 原則 」） 會自動指派給每個信箱。啟用封存信箱時，預設 Exchange 保留原則會自動執行下列作業： 
  
    - 將使用者主要信箱中兩年以上的郵件移到其封存信箱。 
    
    - 將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。
    
- 如需封存信箱及 Exchange 保留原則的詳細資訊，請參閱：
  
    
  - [保留標記和保留原則](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [預設的保留原則 in Exchange Online](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [設定 Office 365 組織中信箱的封存及刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
