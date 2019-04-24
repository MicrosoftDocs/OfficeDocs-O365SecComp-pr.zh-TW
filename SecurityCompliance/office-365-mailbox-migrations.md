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
# <a name="office-365-mailbox-migrations"></a><span data-ttu-id="714ec-103">Office 365 信箱移轉</span><span class="sxs-lookup"><span data-stu-id="714ec-103">Office 365 Mailbox Migrations</span></span>
<span data-ttu-id="714ec-104">使用 Exchange 型混合式部署時，客戶可以選擇將內部部署 Exchange 信箱移至[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織，或 Exchange Online 信箱移至[Exchange 內部部署](https://docs.microsoft.com/Exchange/exchange-server)組織。</span><span class="sxs-lookup"><span data-stu-id="714ec-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="714ec-105">內部部署與 Exchange Online 組織之間移動信箱時，所使用的移轉批次。</span><span class="sxs-lookup"><span data-stu-id="714ec-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span> <span data-ttu-id="714ec-106">客戶可以檢閱統計資料，以及使用下列 cmdlet 的信箱移轉的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="714ec-106">Customers can review statistics and other information about mailbox migrations using the following cmdlets:</span></span>

- <span data-ttu-id="714ec-107">[Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供預設統計資料，針對使用者信箱，其中包括狀態、 信箱大小，封存信箱大小和完成百分比。</span><span class="sxs-lookup"><span data-stu-id="714ec-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size and percentage complete.</span></span>
- <span data-ttu-id="714ec-108">[Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -提供信箱物件及屬性，在組織中的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="714ec-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="714ec-109">[取得位收件者](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)-提供擁有郵件功能的現有物件，例如信箱、 郵件使用者、 連絡人和通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="714ec-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts and distribution groups.</span></span>
- <span data-ttu-id="714ec-110">[Get-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供持續的信箱移轉的詳細的狀態。</span><span class="sxs-lookup"><span data-stu-id="714ec-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="714ec-111">[Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -提供移動和移轉使用者的信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="714ec-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="714ec-112">[Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供目前的移轉批次的狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="714ec-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="714ec-113">[Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -提供特定使用者的移轉狀態的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="714ec-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="714ec-114">[Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供信箱，例如大小、 訊息數量和上次存取的時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="714ec-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="714ec-115">如需有關其他 cmdlet 的詳細資訊，請參閱 < <b0>Exchange Online 中的移動與移轉 cmdlet</b0>。</span><span class="sxs-lookup"><span data-stu-id="714ec-115">For more information on additional cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
