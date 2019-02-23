---
title: 啟用 Office 365-說明系統中沒有限制之封存
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 系統管理員： 了解如何啟用自動展開 Office 365，您的使用者與不受限制的存放區提供其 Exchange Online 信箱的封存。您可以啟用自動展開封存為整個組織或只是特定的使用者。
ms.openlocfilehash: 39098ffc78d0379436cafb20e5a484ec0e7aa283
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215393"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>啟用 Office 365-說明系統中沒有限制之封存

您可以使用 Office 365 中的 「 Exchange Online 的自動展開封存 」 功能以啟用封存信箱的無限制的儲存空間。自動展開封存開啟時，會自動新增額外儲存空間至使用者的封存信箱時加以式升級的儲存限制。結果是不受限制的信箱儲存容量。您可以開啟自動展開封存的組織中所有人或只是特定的使用者。如需關於自動展開封存，請參閱[Overview of Office 365 中沒有限制之封存](unlimited-archiving.md)。

## <a name="before-you-begin"></a>開始之前

- 您必須是 Office 365 組織或組織管理角色群組成員 Exchange Online 組織中的啟用整個組織或特定使用者自動展開封存的全域管理員。或者，您必須是已指派啟用自動展開封存特定使用者的郵件收件者角色的角色群組的成員。
    
- 使用者的封存信箱具有您可以啟用自動展開封存之前予以啟用。使用者必須具有啟用封存信箱的 Exchange Online 計劃 2 授權。如果使用者已指派 Exchange Online 計劃 1 授權，則您必須將它們指派不同 Exchange Online 封存授權啟用封存信箱。請參閱[啟用封存信箱在 Office 365 安全性&amp;規範中心](enable-archive-mailboxes.md)。
    
- 您也可以使用 PowerShell 啟用封存信箱。請參閱[的詳細資訊](#more-information)] 區段中的可用來啟用您組織中的所有使用者的封存信箱的 PowerShell 命令的範例。 
    
- 自動展開封存也支援共用的信箱。若要啟用共用信箱的封存，Exchange Online 計劃 2 授權或 Exchange Online 計劃 1 授權來搭配 Exchange Online 封存的授權，則需要。
    
- 您無法使用 Exchange 系統管理中心或安全性&amp;規範中心以啟用自動展開封存。您必須使用 Exchange Online PowerShell。若要連線至 Exchange Online 組織使用遠端 PowerShell，請參閱[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>啟用整個組織的自動展開封存

您可以啟用自動展開整個組織的封存。您開啟之後，自動展開封存將會啟用現有使用者信箱以及所建立的新使用者信箱。當您建立新使用者信箱時，請務必讓自動展開的封存功能可讓新的使用者信箱的運作啟用使用者的主要封存信箱。
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 若要啟用整個組織的自動展開封存 Exchange Online PowerShell 中執行下列命令。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>啟用自動展開特定使用者的封存

而非啟用自動展開您組織中每個使用者的封存，您可以僅啟用它對特定使用者。因為只有一些使用者可能會有非常大的封存儲存區需要您可能會這麼做。
  
當您啟用自動展開特定使用者的封存和上的使用者的信箱中保留或指派給 Office 365 保留原則，會進行下列兩種設定變更：
  
- 使用者的主要封存信箱儲存配額會增加 10 GB （從 100 GB，以 110 GB)。封存警告配額也增加 10 GB （從 100 gb 的 90 GB)。
    
- 在使用者的主要信箱 [可復原的項目] 資料夾的存放區配額會增加 10 GB （也從 100 GB，以 110 GB)。可復原的項目警告配額也增加 10 GB （從 100 gb 的 90 GB)。這些變更適用於僅限中的信箱上保留或會指派給 Office 365 保留原則。
    
此額外的空間新增至防止任何儲存空間可能發生的問題之前自動展開封存已佈建。請注意該額外儲存空間*不是*新增當您啟用整個組織前一節所述的自動展開封存。 
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 若要啟用自動展開封存特定使用者的 Exchange Online PowerShell 中執行下列命令。如先前所述，您可以開啟自動展開該使用者的封存之前必須啟用使用者的封存信箱 （主要封存）。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> 在 Exchange 混合部署中，您無法使用**Enable-mailbox AutoExpandingArchive**命令來啟用自動展開封存特定主要信箱位於內部部署使用者和其封存信箱不在雲端架構。若要啟用自動展開 Exchange 混合部署中的雲端式封存信箱的封存，您必須執行**Set-organizationconfig AutoExpandingArchive**命令在 Exchange Online PowerShell 來啟用自動展開的封存整個組織。如果使用者的主要和封存信箱都雲端，您可以啟用自動展開該特定使用者的封存使用**Enable-mailbox AutoExpandingArchive**命令。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>確認已啟用 [自動展開封存

若要確認您的組織會啟用自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

值為`True`表示已為組織啟用 [自動展開封存。 
  
若要確認自動展開封存為特定使用者啟用，請在 Exchange Online PowerShell 中執行下列命令。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
值為`True`表示已為使用者啟用 [自動展開封存。 
  
您啟用自動展開封存之後請記住下列事項：
  
- 如果您執行**Set-organizationconfig AutoExpandingArchive**命令，以啟用自動展開您的組織封存時，您不需要執行個別信箱**啟用信箱 AutoExpandingArchive** 。請注意執行**Set-organizationconfig**指令程式來啟用自動展開封存的組織不會變更使用者信箱上的*AutoExpandingArchiveEnabled*屬性`True`。
    
- 同樣地，您啟用自動展開封存時，不變更*ArchiveQuota*和*ArchiveWarningQuota*信箱屬性的值。事實上，當您啟用使用者信箱的自動展開封存和*AutoExpandingArchiveEnabled*屬性設為`True`、 *ArchiveQuota*和*ArchiveWarningQuota*屬性只會略過。以下是這些信箱屬性的範例之後自動展開封存啟用使用者的信箱。 
    
    ![在您啟用自動展開封存之後會略過 ArchiveQuota 和 ArchiveWarningQuota 屬性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>詳細資訊

- 您也可以使用 PowerShell 啟用封存信箱。例如，您可以執行下列命令在 Exchange Online PowerShell 啟用封存信箱不已啟用的所有使用者的封存信箱。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 您開啟自動展開您的組織或特定使用者的封存之後，封存信箱 （包括可復原的項目] 資料夾） 達到 90 GB 時的封存信箱會轉換為自動展開封存。可能很多達 30 天的額外儲存空間來佈建。
    
- 您開啟自動展開封存後，它不能已關閉。
    
- 自動展開封存支援具有內部部署主要信箱的使用者的 Exchange 混合部署中的雲端式封存信箱。但是，自動展開封存啟用雲端式封存信箱後，您無法關閉-委員會回內部部署 Exchange 組織的封存信箱。
    
- 使用者可以存取封存信箱中的其他儲存區中的項目使用的 Outlook 用戶端的清單，請參閱"Outlook 需求存取自動展開封存中的項目 」 一節中[的不受限制的概觀 （英文） 封存 Office 365 中](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).
    
- 如先前所述，10 GB 新增至使用者的主要封存信箱儲存配額 （以及可復原的項目] 資料夾至信箱時保留） 當您執行的命令會**啟用信箱 AutoExpandingArchive** 。這會提供額外儲存空間之前的自動展開儲存空間佈建 （這可能需要最多 30 天）。當您執行**Set-organizationconfig AutoExpandingArchive**啟用自動展開您的組織中所有信箱的封存時未加上此額外儲存空間空格。如果您啟用自動展開封存整個組織中，但需要新增額外的 10 GB 的特定使用者的儲存空間，您可以**啟用信箱 AutoExpandingArchive**上執行命令的信箱。請注意您會收到錯誤預警已經啟用自動展開封存，但其他的儲存空間新增至信箱。 
