---
title: 變更 Office 365 中不在作用中信箱的保留期間
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 信箱進行非使用中之後，您可以變更保留或 Office 365 保留原則指派給非使用中信箱的工期。保留期間可復原的項目] 資料夾，可以保留中定義多久的項目。
ms.openlocfilehash: 3f92d51505ba8a9a9f4b8e78d0fb79036b6db489
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220613"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="0aeef-104">變更 Office 365 中不在作用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="0aeef-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="0aeef-p102">非使用中的信箱用來保留先前員工的電子郵件之後他離開貴組織。信箱成為非使用中時訴訟暫止狀態、 就地保留、 Office 365 保留原則或保留與 eDiscovery 案例相關聯處於信箱，並刪除對應的 Office 365 使用者帳戶。不在作用中信箱的內容會保留它進行非使用中之前被指定信箱的保留期間。保留期間可復原的項目] 資料夾，可以保留中定義多久的項目。保留期間到期的可復原的項目] 資料夾中的項目、 時項目會永久刪除 （清除） 從非使用中的信箱。進行不在作用中信箱之後，您可以變更保留或 Office 365 保留原則指派給非使用中信箱的工期。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p102">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization. A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. The hold duration defines how long items in the Recoverable Items folder are held. When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0aeef-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="0aeef-116">開始之前</span><span class="sxs-lookup"><span data-stu-id="0aeef-116">Before you begin</span></span>

- <span data-ttu-id="0aeef-p104">您必須使用 Exchange Online PowerShell 訴訟暫止狀態不在作用中的信箱上變更保留持續時間。您無法使用 Exchange 系統管理中心 (EAC)。但是您可以使用 Exchange Online PowerShell 或 EAC 來變更為就地保留的保留期間。您可以使用 Office 365 安全性&amp;規範中心或安全性&amp;規範中心 PowerShell 來變更 Office 365 保留原則的保留期間。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p104">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. You can use the Office 365 Security &amp; Compliance Center or the Security &amp; Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="0aeef-121">若要連線至 Exchange Online PowerShell 或安全性&amp;規範中心 PowerShell，請參閱下列主題的其中一個：</span><span class="sxs-lookup"><span data-stu-id="0aeef-121">To connect to Exchange Online PowerShell or Security &amp; Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="0aeef-122">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0aeef-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="0aeef-123">連接到 Office 365 安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aeef-123">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="0aeef-p105">保留 eDiscovery 案例相關聯的記事會無限期保留，這表示沒有可變更沒有保留持續時間。項目會保留不限次數或直到移除保留及刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p105">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed. Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="0aeef-126">如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0aeef-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="0aeef-127">步驟 1： 識別非使用中信箱的保留</span><span class="sxs-lookup"><span data-stu-id="0aeef-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="0aeef-128">因為不同類型的保留或一或多個 Office 365 保留原則可能會被放置在非使用中的信箱，第一個步驟是識別非使用中信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="0aeef-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="0aeef-129">執行下列命令在 Exchange Online PowerShell 來顯示您組織中所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="0aeef-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="0aeef-p106">**LitigationHoldEnabled**屬性值為**True**表示非使用中信箱處於訴訟暫止狀態。若為 「 就地保留 eDiscovery 保留，或 Office 365 保留原則處於非使用中的信箱，保留或保留原則的 GUID 被顯示為**InPlaceHolds**屬性的值。例如，以下顯示 5 的非使用中信箱的結果。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p106">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property. For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
<span data-ttu-id="0aeef-133">下表列出用來停用每個信箱的五個不同的保留類型。</span><span class="sxs-lookup"><span data-stu-id="0aeef-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="0aeef-134">**非使用中信箱**</span><span class="sxs-lookup"><span data-stu-id="0aeef-134">**Inactive mailbox**</span></span>|<span data-ttu-id="0aeef-135">**保留類型**</span><span class="sxs-lookup"><span data-stu-id="0aeef-135">**Hold type**</span></span>|<span data-ttu-id="0aeef-136">**如何識別在非使用中信箱的保留**</span><span class="sxs-lookup"><span data-stu-id="0aeef-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0aeef-137">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="0aeef-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="0aeef-138">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="0aeef-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="0aeef-139">*LitigationHoldEnabled*屬性設為`True`。</span><span class="sxs-lookup"><span data-stu-id="0aeef-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="0aeef-140">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="0aeef-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="0aeef-141">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="0aeef-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="0aeef-p107">*InPlaceHolds*屬性會包含非使用中信箱處於就地保留 GUID。您可以分清這是就地保留因為識別碼不會開始使用前置詞。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p107">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox. You can tell this is an In-Place Hold because the ID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="0aeef-144">您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`命令以取得關於就地保留資訊不在作用中的信箱上的 Exchange Online PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="0aeef-144">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="0aeef-145">伊 Necaise</span><span class="sxs-lookup"><span data-stu-id="0aeef-145">Mario Necaise</span></span>  <br/> |<span data-ttu-id="0aeef-146">在 [安全性] 中的整個組織的 Office 365 保留原則&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="0aeef-146">Organization-wide Office 365 retention policy in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="0aeef-p108">*InPlaceHolds*屬性是空的。這指出一或多個整個組織或 （Exchange 全） Office 365 保留原則套用至非使用中的信箱。在此例中，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令在 Exchange Online PowerShell 取得整個組織的 Office 365 保留原則之 Guid 的清單。整個組織的保留原則套用至 Exchange 信箱開始 GUID`mbx`首碼 ；例如`mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p108">The  *InPlaceHolds*  property is empty. This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox. In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  </span></span><br/> <br/><span data-ttu-id="0aeef-151">Identity 為 Office 365 保留原則套用至非使用中的信箱，以執行下列命令安全性&amp;規範中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0aeef-151">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="0aeef-152">收件者 Olson</span><span class="sxs-lookup"><span data-stu-id="0aeef-152">Carol Olson</span></span>  <br/> |<span data-ttu-id="0aeef-153">在 [安全性] 中的 office 365 保留原則&amp;規範中心套用至特定信箱</span><span class="sxs-lookup"><span data-stu-id="0aeef-153">Office 365 retention policy in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="0aeef-p109">*InPlaceHolds*屬性會包含 Office 365 保留原則套用至非使用中信箱的 GUID。您可以分清這是因為 GUID 開頭套用至特定信箱的保留原則`mbx`前置詞。請注意，如果保留原則套用至非使用中信箱的 GUID 入門`skp`前置詞表示將保留原則套用至 Skype 商務交談。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p109">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox. You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix. Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.  </span></span><br/><br/> <span data-ttu-id="0aeef-157">Identity 為 Office 365 保留原則套用至非使用中的信箱，以執行下列命令安全性&amp;規範中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0aeef-157">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="0aeef-158">請務必移除`mbx`或`skp`prefix 當您執行此命令。</span><span class="sxs-lookup"><span data-stu-id="0aeef-158">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="0aeef-159">林肯 McMahon</span><span class="sxs-lookup"><span data-stu-id="0aeef-159">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="0aeef-160">eDiscovery 案例保留安全性&amp;規範中心</span><span class="sxs-lookup"><span data-stu-id="0aeef-160">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="0aeef-p110">*InPlaceHolds*屬性會包含處於非使用中信箱的 eDiscovery 案件保留 GUID。您可以分清這是因為 GUID 開頭的 eDiscovery 案件保留`UniH`前置詞。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p110">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="0aeef-p111">您可以使用`Get-CaseHoldPolicy`指令程式的安全性&amp;規範中心 PowerShell 取得不在作用中信箱的保留相關聯的 eDiscovery 案例的相關資訊。例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`顯示處於非使用中信箱的大小寫保留的名稱。請務必移除`UniH`prefix 當您執行此命令。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p111">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  </span></span><br/><br/> <span data-ttu-id="0aeef-166">若要識別非使用中信箱的保留相關聯的 eDiscovery 案例，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0aeef-166">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="0aeef-p112">**附註：** 我們不建議使用 eDiscovery 保留為非作用中的信箱。那是因為 eDiscovery 案例適用於特定的時間繫結案例相關的法律問題。有些時候法律案例可能將會結束與將會移除與案例相關聯的保留和 eDiscovery 案例將會關閉 （或刪除）。事實上，如果處於非使用中信箱的保留相關聯 eDiscovery 案例、 和發行保留或關閉或刪除 eDiscovery 案例、 非使用中的信箱將會永久刪除。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p112">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted). In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="0aeef-171">如需 Office 365 的保留原則的詳細資訊，請參閱 ＜ [Overview of 保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0aeef-171">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="0aeef-172">步驟 2： 變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="0aeef-172">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="0aeef-173">在您識別何種類型的保留處於非使用中信箱之後 （以及是否有多個保留） 下, 一步是要變更保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="0aeef-173">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="0aeef-174">變更的訴訟暫止狀態的持續時間</span><span class="sxs-lookup"><span data-stu-id="0aeef-174">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="0aeef-p113">以下是如何使用 Exchange Online PowerShell 來變更為非使用中的信箱處於訴訟暫止狀態的保留期間。您無法使用 EAC。執行下列命令以變更保留期間。在這個範例中，保留持續時間會變更為不受限制的一段時間。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p113">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox. You can't use the EAC. Run the following command to change the hold duration. In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="0aeef-179">結果是不在作用中的信箱中的項目會保留無限期或直到撤除或保留持續時間變更為不同的值。</span><span class="sxs-lookup"><span data-stu-id="0aeef-179">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="0aeef-p114">識別非使用中信箱的最佳方式是使用其**辨別名稱**或**Exchange 的 GUID**值。使用下列值之一有助於防止不慎指定了錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p114">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="0aeef-182">變更為就地保留期間</span><span class="sxs-lookup"><span data-stu-id="0aeef-182">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="0aeef-183">您可以使用 EAC 或 Exchange Online PowerShell 變更為就地保留的保留期間。</span><span class="sxs-lookup"><span data-stu-id="0aeef-183">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="0aeef-184">使用 EAC 來變更保留期間</span><span class="sxs-lookup"><span data-stu-id="0aeef-184">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="0aeef-p115">如果您知道您想要變更為 「 就地保留的名稱，請移至下一個步驟。否則請執行下列命令以取得處於非使用中的信箱就地保留的名稱。使用就地保留 GUID 您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中取得。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p115">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="0aeef-188">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="0aeef-188">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="0aeef-189">選取您想要變更為 「 就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="0aeef-189">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="0aeef-190">在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**就地保留功能**。</span><span class="sxs-lookup"><span data-stu-id="0aeef-190">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="0aeef-191">根據目前的下列其中之一不要保留持續時間：</span><span class="sxs-lookup"><span data-stu-id="0aeef-191">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="0aeef-192">按一下 [**無限期保留**無限一段時間保留項目。</span><span class="sxs-lookup"><span data-stu-id="0aeef-192">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="0aeef-p116">按一下以在特定期間內保留項目**指定天數以保留項目相對於其接收日期**。輸入您想要保留的項目保留的天數。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p116">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period. Type the number of days that you want to hold items for.</span></span> 
    
    ![變更就地保留之持續期間的螢幕擷取畫面](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="0aeef-196">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0aeef-196">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="0aeef-197">使用 Exchange Online PowerShell 來變更保留持續時間</span><span class="sxs-lookup"><span data-stu-id="0aeef-197">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="0aeef-p117">如果您知道您想要變更為 「 就地保留的名稱，請移至下一個步驟。否則請執行下列命令以取得處於非使用中的信箱就地保留的名稱。使用就地保留 GUID 您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中取得。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p117">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="0aeef-p118">執行下列命令以變更保留期間。在這個範例中，保留持續時間會變更為 2,555 天 （大約 7 年）。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p118">Run the following command to change the hold duration. In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="0aeef-203">若要變更保留持續時間為不受限制的一段時間，請使用 _-ItemHoldPeriod 無限制_。</span><span class="sxs-lookup"><span data-stu-id="0aeef-203">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="0aeef-204">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0aeef-204">More information</span></span>

- <span data-ttu-id="0aeef-p119">**的保留持續時間計算方式為在非使用中的信箱項目？** 將信箱項目所接收或建立的原始日期被計算持續時間。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p119">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="0aeef-p120">**保留期間到期時會發生什麼事？** 保留期間到期的可復原的項目] 資料夾中的信箱項目、 時項目會永久刪除 （清除） 從非使用中的信箱。如果沒有指定放置在非使用中信箱的保留給沒有工期，將 （除非不在作用中信箱的保留期間會在變更） 永遠不會清除 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p120">**What happens when the hold duration expires?** When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="0aeef-p121">**仍不在作用中的信箱上處理 Exchange 保留原則吗？** 如果 （通訊記錄管理或 MRM，Exchange Online 中的功能） Exchange 保留原則套用到信箱已進行非使用中時，將會刪除原則 」 （這是設定為**刪除**保留動作的保留標記）繼續處理非使用中的信箱。這表示與刪除原則標記的項目移至 [可復原的項目] 資料夾保留期間到期時。項目的保留期間到期時將這些項目然後會清除從非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p121">**Is an Exchange retention policy still processed on inactive mailboxes?** If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires. Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="0aeef-p122">反之，會略過任何封存原則 （這是以**movetoarchive：** 保留動作來設定的保留標記） 所包含的指派給非使用中信箱的保留原則。這表示在非使用中信箱與封存原則標記的項目保持在主要信箱的保留期間到期時。它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。使用者無法登入非使用中的信箱，因為沒有理由使用的資料中心的資源來處理封存原則。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p122">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="0aeef-p123">**來檢查新保留持續時間，請執行下列命令。** 第一個命令會針對訴訟暫止狀態 ；第二個是就地保留功能。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p123">**To check the new hold duration, run one of the following commands.** The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="0aeef-p124">**Like 一般信箱受管理的資料夾助理員 (MFA) 也處理非使用中的信箱。** 在 Exchange Online MFA 程序一次大約每 7 天的信箱。變更非使用中信箱的保留期間之後，您可以使用**Start-managedfolderassistant**指令程式可以立即開始處理非使用中信箱的新保留持續時間。執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p124">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.** In Exchange Online, the MFA processes mailboxes approximately once every 7 days. After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox. Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="0aeef-p125">**如果許多的保留會放在非使用中的信箱，不會顯示 Guid 的保留的所有。** 您可以執行下列命令以顯示 （除了訴訟保留） 放置在非使用中的信箱的所有保留的 Guid。</span><span class="sxs-lookup"><span data-stu-id="0aeef-p125">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.** You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
