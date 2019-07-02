---
title: Office 365 信箱移轉
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 信箱遷移所使用之 Cmdlet 的簡短摘要。
ms.openlocfilehash: 3858af0c246cdef07164b6414a87cf110cf65055
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622423"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 信箱移轉
使用 Exchange 型混合式部署時, 客戶可以選擇將內部部署 Exchange 信箱移至[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織, 或將 exchange Online 信箱移至[exchange 內部部署](https://docs.microsoft.com/Exchange/exchange-server)組織。 在內部部署與 Exchange Online 組織之間移動信箱時, 會使用遷移批次。

客戶可以使用下列 Cmdlet 來查看信箱遷移的統計資料和其他資訊:

- [Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): 提供使用者信箱的預設統計資料, 其中包括狀態、信箱大小、封存信箱大小, 以及完成百分比。
- [取得信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): 提供組織中信箱物件和屬性的摘要清單。
- [收件](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)者: 提供擁有郵件功能的現有物件 (例如信箱、郵件使用者、連絡人及通訊群組) 的清單。
- [New-moverequest 程式](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): 提供進行中信箱遷移的詳細狀態。
- [MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): 提供信箱移動和遷移使用者的相關資訊。
- [Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): 提供目前遷移批次狀態的資訊。
- [Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): 提供特定使用者之遷移狀態的詳細資訊。
- [Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): 提供信箱的相關資訊, 例如大小、郵件數目, 以及上次存取時間。

如需 Cmdlet 的詳細資訊, 請參閱[Exchange Online 中的移動和遷移 Cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。
