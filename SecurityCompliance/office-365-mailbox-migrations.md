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
description: 指令程式使用 Office 365 信箱移轉的簡短摘要。
ms.openlocfilehash: f21462b1f4a1838ee617e0d429ba73f01ca2db90
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262575"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 信箱移轉
使用 Exchange 型混合式部署時，客戶可以選擇將內部部署 Exchange 信箱移至[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織，或 Exchange Online 信箱移至[Exchange 內部部署](https://docs.microsoft.com/Exchange/exchange-server)組織。 內部部署與 Exchange Online 組織之間移動信箱時，所使用的移轉批次。 客戶可以檢閱統計資料，以及使用下列 cmdlet 的信箱移轉的其他資訊：

- [Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供預設統計資料，針對使用者信箱，其中包括狀態、 信箱大小，封存信箱大小和完成百分比。
- [Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -提供信箱物件及屬性，在組織中的摘要清單。
- [取得位收件者](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)-提供擁有郵件功能的現有物件，例如信箱、 郵件使用者、 連絡人和通訊群組清單。
- [Get-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供持續的信箱移轉的詳細的狀態。
- [Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -提供移動和移轉使用者的信箱的相關資訊。
- [Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供目前的移轉批次的狀態的相關資訊。
- [Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -提供特定使用者的移轉狀態的詳細的資訊。
- [Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供信箱，例如大小、 訊息數量和上次存取的時間的相關資訊。

如需有關其他 cmdlet 的詳細資訊，請參閱 < <b0>Exchange Online 中的移動與移轉 cmdlet</b0>。
