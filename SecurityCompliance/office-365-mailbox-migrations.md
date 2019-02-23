---
title: Office 365 信箱移轉
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Cmdlet 可用於適用於 Office 365 信箱移轉簡短摘要。
ms.openlocfilehash: 8e0f23a3efbbcf6f84364c09e667678972120e18
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219143"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 信箱移轉
Exchange 型混合部署，客戶可以選擇內部部署 Exchange 信箱移至[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織或將 Exchange Online 信箱移至[Exchange 內部](https://docs.microsoft.com/Exchange/exchange-server)部署組織。遷移批次所使用的內部部署和 Exchange Online 組織之間移動信箱時。客戶可以檢閱統計資料和信箱移轉使用下列 cmdlet 的其他資訊：

- [Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供預設統計資料的使用者信箱，包括狀態、 信箱大小，封存信箱大小和完成百分比。
- [Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -提供信箱物件和屬性在組織中的摘要清單。
- [取得位收件者](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)-提供擁有郵件功能的現有物件，例如信箱、 郵件使用者、 連絡人及通訊群組清單。
- [Get-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供持續的信箱移轉的詳細的狀態。
- [Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -提供移動和移轉使用者的信箱的相關資訊。
- [Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供目前的遷移批次狀態的相關資訊。
- [Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -提供特定使用者的遷移狀態相關的詳細的資訊。
- [Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供信箱，例如大小、 訊息、 數目和上次存取的時間的相關資訊。

如需其他 cmdlet 的詳細資訊，請參閱[Exchange Online 中的移動和遷移指令程式](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。
