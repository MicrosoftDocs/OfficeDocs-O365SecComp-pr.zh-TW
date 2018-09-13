---
title: Office 365 信箱移轉
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Cmdlet 可用於適用於 Office 365 信箱移轉簡短摘要。
ms.openlocfilehash: 86896d956072b5c11e3b3292363bb32312ff1187
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527007"
---
# <a name="office-365-mailbox-migrations"></a><span data-ttu-id="e5f70-103">Office 365 信箱移轉</span><span class="sxs-lookup"><span data-stu-id="e5f70-103">Office 365 Mailbox Migrations</span></span>
<span data-ttu-id="e5f70-p101">Exchange 型混合部署，客戶可以選擇內部部署 Exchange 信箱移至[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織或將 Exchange Online 信箱移至[Exchange 內部](https://docs.microsoft.com/Exchange/exchange-server)部署組織。遷移批次所使用的內部部署和 Exchange Online 組織之間移動信箱時。客戶可以檢閱統計資料和信箱移轉使用下列 cmdlet 的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="e5f70-p101">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization. Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations. Customers can review statistics and other information about mailbox migrations using the following cmdlets:</span></span>

- <span data-ttu-id="e5f70-107">[Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供預設統計資料的使用者信箱，包括狀態、 信箱大小，封存信箱大小和完成百分比。</span><span class="sxs-lookup"><span data-stu-id="e5f70-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size and percentage complete.</span></span>
- <span data-ttu-id="e5f70-108">[Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -提供信箱物件和屬性在組織中的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="e5f70-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="e5f70-109">[取得位收件者](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)-提供擁有郵件功能的現有物件，例如信箱、 郵件使用者、 連絡人及通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="e5f70-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts and distribution groups.</span></span>
- <span data-ttu-id="e5f70-110">[Get-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供持續的信箱移轉的詳細的狀態。</span><span class="sxs-lookup"><span data-stu-id="e5f70-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="e5f70-111">[Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -提供移動和移轉使用者的信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e5f70-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="e5f70-112">[Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供目前的遷移批次狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e5f70-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="e5f70-113">[Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -提供特定使用者的遷移狀態相關的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="e5f70-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="e5f70-114">[Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供信箱，例如大小、 訊息、 數目和上次存取的時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e5f70-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="e5f70-115">如需其他 cmdlet 的詳細資訊，請參閱[Exchange Online 中的移動和遷移指令程式](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="e5f70-115">For more information on additional cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>