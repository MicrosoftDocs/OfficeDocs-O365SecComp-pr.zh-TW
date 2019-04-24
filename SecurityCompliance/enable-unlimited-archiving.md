---
title: 啟用 Office 365-系統管理說明中的無限制封存
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 系統管理員： 了解如何啟用自動展開封存在 Office 365 中，可提供您的使用者與不受限制的儲存區，讓其 Exchange Online 信箱。 您可以啟用自動展開封存的整個組織或只是針對特定使用者。
ms.openlocfilehash: e41ebc0605b7e6ce2178791de27421a82e2b6cf6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256834"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>啟用 Office 365-系統管理說明中的無限制封存

若要啟用封存信箱的無限制的儲存空間，您可以在 Office 365 中使用的 Exchange Online 自動展開封存功能。 自動展開封存開啟時，會自動新增額外的儲存空間至使用者的封存信箱時它逼近儲存量限制。 結果是不受限制的信箱儲存容量。 您可以開啟自動展開封存組織中的每個人，或只是針對特定使用者。 如需自動展開封存，請參閱[在 Office 365 中的無限制封存概觀](unlimited-archiving.md)。

## <a name="before-you-begin"></a>開始之前

- 您必須是全域系統管理員在 Office 365 組織或 Exchange Online 組織中啟用自動展開封存的整個組織或針對特定使用者的組織管理角色群組的成員。 或者，您必須是已指派 「 郵件收件者角色，才能啟用自動展開封存針對特定使用者的角色群組的成員。
    
- 使用者的封存信箱具有您可以啟用自動展開封存之前，先啟用。 使用者必須被指派 Exchange Online Plan 2 授權，才能啟用封存信箱。 如果 Exchange Online Plan 1 授權指派給使用者，您必須將它們指派不同 Exchange Online Archiving 授權，才能啟用封存信箱。 請參閱[啟用封存信箱中的安全性 & 合規性中心](enable-archive-mailboxes.md)。
    
- 您也可以使用 PowerShell 來啟用封存信箱。 請參閱 <<c0>的詳細資訊] 區段中，您可以使用啟用您的組織中的所有使用者的封存信箱的 PowerShell 命令的範例。 
    
- 自動展開封存也支援共用信箱。 若要啟用信箱的共用信箱的封存，Exchange Online Plan 2 授權或具有 Exchange Online Archiving 授權的 Exchange Online Plan 1 授權就需要。
    
- 若要啟用自動展開封存，您無法使用 Exchange 系統管理中心或安全性 & 合規性中心。 您必須使用 Exchange Online PowerShell。 若要連接至您 Exchange Online 組織中使用遠端 PowerShell，請參閱 < <b0>Connect to Exchange Online PowerShell</b0>。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>啟用整個組織的自動展開封存

您可以啟用自動展開封存的整個組織。 您開啟之後，自動展開封存會啟用現有使用者信箱，以及所建立的新使用者信箱。 當您建立新的使用者信箱時，請務必啟用使用者的主要的封存信箱，以便自動展開封存功能適用於新的使用者信箱。
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 若要啟用自動展開封存整個組織的 Exchange Online PowerShell 中執行下列命令。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>啟用自動展開封存針對特定使用者

而不是啟用自動展開封存的組織中每位使用者，您可以只啟用它針對特定使用者。 因為只將部分使用者可能需要非常大型的封存儲存空間，您可以這麼做。
  
當您啟用特定使用者的自動展開封存和保留上的使用者信箱中或指派給 Office 365 保留原則，會進行下列兩種組態變更：
  
- 使用者的主要的封存信箱的儲存配額增加 10 GB （從為 110 GB 的 100 GB)。 封存警告配額也增加 10 GB （從 90 GB，以 100 GB)。
    
- 使用者的主要信箱中的 [可復原的項目] 資料夾的儲存配額增加 10 GB （也從為 110 GB 的 100 GB)。 10 GB （從 90 GB，以 100 GB) 也增加可復原的項目警告配額。 只有當上的信箱中保留或指派給 Office 365 保留原則，這些變更皆適用。
    
此額外的空間會新增至避免可能發生之前已佈建自動展開封存的任何儲存問題。 請注意該額外儲存空間*不是*當您啟用整個組織，在上一節中所述的自動展開封存時，加入。 
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 若要啟用自動展開封存的特定使用者的 Exchange Online PowerShell 中執行下列命令。 如先前所述，必須先您可以開啟自動展開封存的使用者啟用使用者的封存信箱 （主要封存）。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> 在 Exchange 混合式部署中，您無法使用**Enable-mailbox AutoExpandingArchive**命令來啟用自動展開封存的特定使用者主要信箱位於內部部署和其封存信箱是以雲端為基礎。 若要啟用自動展開封存在 Exchange 混合式部署中的雲端式封存信箱，您必須**Set-organizationconfig AutoExpandingArchive**命令在 Exchange Online PowerShell 中執行若要啟用自動展開封存整個組織中。 如果使用者的主要和封存信箱的雲端式兩者，然後您可以使用**Enable-mailbox AutoExpandingArchive**命令啟用該特定使用者的自動展開封存。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>確認已啟用 [自動展開封存

若要確認為您的組織中啟用自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

值為`True`指出的組織已啟用自動展開封存。 
  
若要確認自動展開封存已啟用特定使用者，請在 Exchange Online PowerShell 中執行下列命令。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
值為`True`表示使用者已啟用自動展開封存。 
  
之後您啟用自動展開封存，請謹記下列事項：
  
- 如果您執行**Set-organizationconfig AutoExpandingArchive**命令，以啟用您組織的自動展開封存時，您不需要個別的信箱上執行**Enable-mailbox AutoExpandingArchive** 。 請注意該執行的**Set-organizationconfig**指令程式來啟用自動展開封存的組織並不會變更使用者信箱上的*AutoExpandingArchiveEnabled*屬性`True`。
    
- 同樣地，當您啟用自動展開封存時，不變更*ArchiveQuota*和*ArchiveWarningQuota*信箱內容的值。 事實上，當您啟用自動展開封存的使用者信箱和*AutoExpandingArchiveEnabled*屬性設為`True`，只會略過的*ArchiveQuota*和*ArchiveWarningQuota*屬性。 以下是這些信箱屬性的範例之後自動展開封存的使用者信箱已啟用。 
    
    ![啟用自動展開封存後，會略過 ArchiveQuota 和 ArchiveWarningQuota 屬性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>詳細資訊

- 您也可以使用 PowerShell 來啟用封存信箱。 例如，您可以執行下列命令在 Exchange Online PowerShell 來啟用尚未啟用封存信箱的所有使用者的封存信箱。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 開啟自動展開封存為您的組織或特定使用者之後，封存信箱會轉換為自動展開封存，當封存信箱 （包括 [可復原的項目] 資料夾） 達到 90 GB。 可能需要最多 30 天的額外儲存空間來佈建。
    
- 開啟自動展開封存之後，它不能關閉。
    
- 自動展開封存支援雲端式封存信箱在 Exchange 混合式部署中具有內部部署主要信箱的使用者。 不過，自動展開封存啟用雲端式封存信箱之後，您不能委任回至內部部署 Exchange 組織的封存信箱。 請注意，自動展開封存不支援在 Exchange Server 2010 中的內部部署信箱。
    
- Outlook 用戶端，使用者可用來存取其封存信箱中的其他儲存區中的項目清單，請參閱 「 Outlook 需求來存取自動展開封存中的項目 > 一節中[Office 365 中封存的無限制的概觀](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).
    
- 如先前所述，10 GB 新增至使用者的主要的封存信箱儲存配額 （按住不放到 [可復原的項目] 資料夾如果信箱處於） 當您執行**Enable-mailbox AutoExpandingArchive**命令。 直到自動展開儲存空間佈建 （這可能需要長達 30 天），這會提供額外的儲存空間。 當您執行**Set-organizationconfig AutoExpandingArchive**若要啟用組織中的所有信箱的自動展開都封存時，不會新增此額外儲存空間。 如果您啟用自動展開封存的整個組織中，但需要新增額外的 10 GB 的特定使用者的儲存空間，您可以在該信箱上執行**Enable-mailbox AutoExpandingArchive**命令。 請注意，您會收到錯誤，指出已啟用自動展開封存，但的額外儲存空間會新增至信箱。 

- 系統管理員無法調整儲存空間配額。

> [!IMPORTANT]
> 僅支援自動展開封存，如用於個別使用者的信箱或共用信箱不會超過 1 GB，每天的成長率。 不允許使用日誌、 傳輸規則或自動轉寄規則將郵件複製到封存信箱，如進行封存。 使用者的封存信箱僅供該使用者使用。 Microsoft 保留在使用者封存信箱中用來儲存其他使用者之封存資料的執行個體中拒絕不受限封存的權限。
