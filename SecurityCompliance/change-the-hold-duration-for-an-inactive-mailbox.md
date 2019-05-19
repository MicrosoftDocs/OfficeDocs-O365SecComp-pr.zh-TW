---
title: 變更 Office 365 中的非使用中信箱的保留期間
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 信箱進行非使用中之後，您可以變更 Office 365 保留原則指派給非使用中信箱的保留持續的時間。 保留期間定義中可復原的項目] 資料夾會保留多久的項目。
ms.openlocfilehash: 7840131af3df32b8b8e5a0faa1b101f9ec8ef541
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155565"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="defc5-104">變更 Office 365 中的非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="defc5-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="defc5-105">非使用中信箱用來他或她離開組織之後保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="defc5-105">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="defc5-106">信箱成為非使用中時訴訟暫止狀態，就地保留，Office 365 保留原則，或與 eDiscovery 案例相關聯保留信箱，並刪除對應的 Office 365 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="defc5-106">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted.</span></span> <span data-ttu-id="defc5-107">已進行非使用中之前，已處於信箱的保留期間內仍會保留不在作用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="defc5-107">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="defc5-108">保留期間定義中可復原的項目] 資料夾會保留多久的項目。</span><span class="sxs-lookup"><span data-stu-id="defc5-108">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="defc5-109">當保留期間到期的 [可復原的項目] 資料夾中的項目時，此項目會永久刪除 （清除） 從非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-109">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="defc5-110">信箱進行非使用中之後，您可以變更 Office 365 保留原則指派給非使用中信箱的保留持續的時間。</span><span class="sxs-lookup"><span data-stu-id="defc5-110">After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="defc5-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="defc5-116">開始之前</span><span class="sxs-lookup"><span data-stu-id="defc5-116">Before you begin</span></span>

- <span data-ttu-id="defc5-117">您必須使用 Exchange Online PowerShell，若要變更的訴訟資料暫留在非使用中信箱的保留期間。</span><span class="sxs-lookup"><span data-stu-id="defc5-117">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="defc5-118">您無法使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="defc5-118">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="defc5-119">但是，您可以使用 Exchange Online PowerShell 或 EAC 來變更為 「 就地保留的保留期間。</span><span class="sxs-lookup"><span data-stu-id="defc5-119">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="defc5-120">若要變更 Office 365 保留原則的保留期間，您可以使用安全性與合規性中心或安全性 & 合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="defc5-120">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="defc5-121">若要連接至 Exchange Online PowerShell 或安全性 & 合規性中心 PowerShell，請參閱下列其中一個下列主題：</span><span class="sxs-lookup"><span data-stu-id="defc5-121">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="defc5-122">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="defc5-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="defc5-123">連線至 Office 365 Security& 合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="defc5-123">Connect to Office 365 Security& Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="defc5-124">請注意，保留與 eDiscovery 案例相關聯會無限期保留，這表示不沒有可以變更任何保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="defc5-124">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed.</span></span> <span data-ttu-id="defc5-125">項目會保留不限次數，或直到移除保留及刪除非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-125">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="defc5-126">如需非使用中信箱的詳細資訊，請參閱 <<c0>在 Office 365 中的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="defc5-127">步驟 1： 識別非使用中信箱上保留</span><span class="sxs-lookup"><span data-stu-id="defc5-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="defc5-128">因為不同類型的保留 」 或 「 一或多個 Office 365 保留原則也可能會放置在非使用中信箱上，第一個步驟是識別非使用中信箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="defc5-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="defc5-129">PowerShell 中執行下列命令在 Exchange Online 來顯示貴組織中的所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="defc5-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="defc5-130">**LitigationHoldEnabled**屬性的**則為 True**的值會指出作用中的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="defc5-130">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="defc5-131">如果為 「 就地保留 eDiscovery 保留，或 Office 365 保留原則會被放置在非使用中信箱上，保留或保留原則的 GUID 被顯示為**InPlaceHolds**屬性的值。</span><span class="sxs-lookup"><span data-stu-id="defc5-131">If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="defc5-132">例如，下列顯示 5 的非使用中信箱的結果。</span><span class="sxs-lookup"><span data-stu-id="defc5-132">For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
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
   
<span data-ttu-id="defc5-133">下表列出的五個不同的保留類型用來停用每個信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="defc5-134">**非使用中信箱**</span><span class="sxs-lookup"><span data-stu-id="defc5-134">**Inactive mailbox**</span></span>|<span data-ttu-id="defc5-135">**保留類型**</span><span class="sxs-lookup"><span data-stu-id="defc5-135">**Hold type**</span></span>|<span data-ttu-id="defc5-136">**如何識別非使用中信箱上保留**</span><span class="sxs-lookup"><span data-stu-id="defc5-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="defc5-137">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="defc5-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="defc5-138">訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="defc5-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="defc5-139">*LitigationHoldEnabled*屬性設為`True`。</span><span class="sxs-lookup"><span data-stu-id="defc5-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="defc5-140">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="defc5-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="defc5-141">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="defc5-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="defc5-142">*InPlaceHolds*屬性會包含在原有範圍暫止，處於非使用中信箱的 GUID。</span><span class="sxs-lookup"><span data-stu-id="defc5-142">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="defc5-143">您可以告訴這是在原有範圍暫止因為識別碼不會啟動與前置詞。</span><span class="sxs-lookup"><span data-stu-id="defc5-143">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="defc5-144">您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`命令在 Exchange Online PowerShell，以取得在作用中信箱 「 就地保留 」 狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="defc5-144">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="defc5-145">伊 Necaise</span><span class="sxs-lookup"><span data-stu-id="defc5-145">Mario Necaise</span></span>  <br/> |<span data-ttu-id="defc5-146">安全性 & 合規性中心中的全組織的 Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="defc5-146">Organization-wide Office 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="defc5-147">*InPlaceHolds*屬性是空的。</span><span class="sxs-lookup"><span data-stu-id="defc5-147">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="defc5-148">這表示，一或多個全組織或 （Exchange 全） Office 365 保留原則套用至非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-148">This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="defc5-149">在此情況下，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令在 Exchange Online PowerShell，以取得整個組織的 Office 365 保留原則 Guid 的清單。</span><span class="sxs-lookup"><span data-stu-id="defc5-149">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="defc5-150">整個組織的保留原則套用至 Exchange 信箱的開頭的 GUID`mbx`字首;例如`mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="defc5-150">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="defc5-151">會套用至非使用中信箱的身分識別 Office 365 保留原則，請在安全性 & 合規性中心 PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="defc5-151">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="defc5-152">收件者 Olson</span><span class="sxs-lookup"><span data-stu-id="defc5-152">Carol Olson</span></span>  <br/> |<span data-ttu-id="defc5-153">安全性 & 套用至特定信箱的合規性中心中的 office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="defc5-153">Office 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="defc5-154">*InPlaceHolds*屬性包含 Office 365 保留原則套用至非使用中信箱的 GUID。</span><span class="sxs-lookup"><span data-stu-id="defc5-154">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="defc5-155">您可以分清這是因為 GUID 開頭套用至特定信箱的保留原則`mbx`前置詞。</span><span class="sxs-lookup"><span data-stu-id="defc5-155">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="defc5-156">請注意，如果保留原則套用至非使用中信箱的 GUID 入門`skp`前置詞，表示會保留原則套用至 Skype for Business 交談。</span><span class="sxs-lookup"><span data-stu-id="defc5-156">Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="defc5-157">會套用至非使用中信箱的身分識別 Office 365 保留原則，請在安全性 & 合規性中心 PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="defc5-157">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="defc5-158">請務必移除`mbx`或`skp`當您執行此命令的前置詞。</span><span class="sxs-lookup"><span data-stu-id="defc5-158">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="defc5-159">林肯 McMahon</span><span class="sxs-lookup"><span data-stu-id="defc5-159">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="defc5-160">安全性 & 合規性中心中保留電子文件探索案例</span><span class="sxs-lookup"><span data-stu-id="defc5-160">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="defc5-161">*InPlaceHolds*屬性包含 eDiscovery 案例保留處於非使用中信箱的 GUID。</span><span class="sxs-lookup"><span data-stu-id="defc5-161">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="defc5-162">您可以分清這是 eDiscovery 案例保留，因為 GUID 開頭`UniH`前置詞。</span><span class="sxs-lookup"><span data-stu-id="defc5-162">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="defc5-163">您可以使用`Get-CaseHoldPolicy`安全性 & 以取得在作用中的信箱保留相關聯的 eDiscovery 案例的相關資訊的合規性中心 PowerShell 中的指令程式。</span><span class="sxs-lookup"><span data-stu-id="defc5-163">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="defc5-164">例如，您可以執行此命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`來顯示在作用中的信箱上的案例保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="defc5-164">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="defc5-165">請務必移除`UniH`當您執行此命令的前置詞。</span><span class="sxs-lookup"><span data-stu-id="defc5-165">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="defc5-166">若要識別非使用中信箱上的保留相關聯的 eDiscovery 案例，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="defc5-166">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="defc5-167">**附註：** 我們不建議使用 eDiscovery 保留非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-167">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="defc5-168">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span><span class="sxs-lookup"><span data-stu-id="defc5-168">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="defc5-169">有些時候，法律案件最終會將可能並將移除保留與案例相關聯的 eDiscovery 案例將會關閉 （或刪除）。</span><span class="sxs-lookup"><span data-stu-id="defc5-169">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="defc5-170">事實上，如果處於非使用中信箱的保留相關聯的 eDiscovery 案例，並釋放保留或關閉或刪除 eDiscovery 案例，在作用中信箱將會永久刪除。</span><span class="sxs-lookup"><span data-stu-id="defc5-170">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="defc5-171">如需有關 Office 365 保留原則的詳細資訊，請參閱[保留原則的概觀](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="defc5-171">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="defc5-172">步驟 2： 變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="defc5-172">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="defc5-173">識別何種類型的保留處於非使用中信箱之後 （以及是否有多項保留） 下, 一步是要變更保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="defc5-173">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="defc5-174">變更的訴訟暫止持續時間</span><span class="sxs-lookup"><span data-stu-id="defc5-174">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="defc5-175">以下是如何使用 Exchange Online PowerShell 來變更保留持續時間處於非使用中信箱訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="defc5-175">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="defc5-176">您無法使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="defc5-176">You can't use the EAC.</span></span> <span data-ttu-id="defc5-177">執行下列命令，以變更保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="defc5-177">Run the following command to change the hold duration.</span></span> <span data-ttu-id="defc5-178">在這個範例中，保留期間會變更為不受限制的一段時間。</span><span class="sxs-lookup"><span data-stu-id="defc5-178">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="defc5-179">結果是不在作用中信箱中的項目會保留無限期或直到移除保留或保留持續時間變更為不同的值。</span><span class="sxs-lookup"><span data-stu-id="defc5-179">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="defc5-180">若要識別非使用中信箱的最佳方式是使用其**辨別名稱**或**Exchange GUID**值。</span><span class="sxs-lookup"><span data-stu-id="defc5-180">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value.</span></span> <span data-ttu-id="defc5-181">使用下列值之一，有助於防止不小心指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-181">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="defc5-182">變更為 「 就地保留的持續時間</span><span class="sxs-lookup"><span data-stu-id="defc5-182">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="defc5-183">若要變更為 「 就地保留的保留期間，您可以使用 EAC 或 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="defc5-183">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="defc5-184">使用 EAC 來變更保留持續時間</span><span class="sxs-lookup"><span data-stu-id="defc5-184">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="defc5-185">如果您知道想要變更為 「 就地保留的名稱，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="defc5-185">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="defc5-186">否則，執行下列命令，以取得處於非使用中的信箱就地保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="defc5-186">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="defc5-187">使用就地保留 GUID，您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中所取得。</span><span class="sxs-lookup"><span data-stu-id="defc5-187">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="defc5-188">在 EAC 中，移至 [**規範管理** \> **就地 eDiscovery&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="defc5-188">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="defc5-189">選取您要變更為 「 就地保留，然後按一下 [**編輯**![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="defc5-189">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="defc5-190">在**就地 eDiscovery&amp;保留**屬性] 頁面上，按一下 [**原有範圍暫止**。</span><span class="sxs-lookup"><span data-stu-id="defc5-190">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="defc5-191">根據目前的下列其中一個保留持續時間:</span><span class="sxs-lookup"><span data-stu-id="defc5-191">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="defc5-192">按一下 [無限制一段時間保留項目 [**無限期保留**]。</span><span class="sxs-lookup"><span data-stu-id="defc5-192">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="defc5-193">按一下**指定的天數將其接收日期的項目保留**在特定期間內保留項目。</span><span class="sxs-lookup"><span data-stu-id="defc5-193">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period.</span></span> <span data-ttu-id="defc5-194">輸入您想要的項目保留天數。</span><span class="sxs-lookup"><span data-stu-id="defc5-194">Type the number of days that you want to hold items for.</span></span> 
    
    ![變更就地保留之持續期間的螢幕擷取畫面](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="defc5-196">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="defc5-196">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="defc5-197">使用 Exchange Online PowerShell 來變更保留持續時間</span><span class="sxs-lookup"><span data-stu-id="defc5-197">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="defc5-198">如果您知道想要變更為 「 就地保留的名稱，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="defc5-198">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="defc5-199">否則，執行下列命令，以取得處於非使用中的信箱就地保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="defc5-199">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="defc5-200">使用就地保留 GUID，您在[步驟 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中所取得。</span><span class="sxs-lookup"><span data-stu-id="defc5-200">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="defc5-201">執行下列命令，以變更保留持續時間。</span><span class="sxs-lookup"><span data-stu-id="defc5-201">Run the following command to change the hold duration.</span></span> <span data-ttu-id="defc5-202">在這個範例中，保留期間會變更為 2,555 天 （約 7 年）。</span><span class="sxs-lookup"><span data-stu-id="defc5-202">In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="defc5-203">若要變更保留持續時間為無限制的一段時間，請使用 _-ItemHoldPeriod 無限制_。</span><span class="sxs-lookup"><span data-stu-id="defc5-203">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="defc5-204">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="defc5-204">More information</span></span>

- <span data-ttu-id="defc5-205">**針對非使用中的信箱中的項目如何計算保留持續時間？**</span><span class="sxs-lookup"><span data-stu-id="defc5-205">**How is the hold duration calculated for an item in an inactive mailbox?**</span></span> <span data-ttu-id="defc5-206">持續時間被計算的原始日期信箱項目所接收或建立。</span><span class="sxs-lookup"><span data-stu-id="defc5-206">The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="defc5-207">**保留期間到期時，會發生什麼事？**</span><span class="sxs-lookup"><span data-stu-id="defc5-207">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="defc5-208">當保留期間到期的 [可復原的項目] 資料夾中的信箱項目時，此項目會永久刪除 （清除） 從非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="defc5-208">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="defc5-209">如果沒有指定處於非使用中的信箱保留無期間，[可復原的項目] 資料夾中的項目永遠不會清除 （除非非使用中信箱的保留期間變更）。</span><span class="sxs-lookup"><span data-stu-id="defc5-209">If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="defc5-210">**Exchange 保留原則仍上處理非使用中信箱嗎？**</span><span class="sxs-lookup"><span data-stu-id="defc5-210">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="defc5-211">如果它成為非使用中時，（通訊記錄管理 」 或 「 MRM，Exchange Online 中的功能） 的 Exchange 保留原則套用至信箱，將會刪除原則 （也就是設定以**刪除**保留動作的保留標記）繼續處理非使用中信箱上。</span><span class="sxs-lookup"><span data-stu-id="defc5-211">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="defc5-212">這表示與刪除原則標記的項目移至 [可復原的項目] 資料夾保留期間到期時。</span><span class="sxs-lookup"><span data-stu-id="defc5-212">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="defc5-213">然後會清除這些項目從非使用中的信箱項目保留期間到期時。</span><span class="sxs-lookup"><span data-stu-id="defc5-213">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="defc5-214">相反地，會略過任何封存原則 （也就是以**MoveToArchive** ： 保留動作設定的保留標記） 所隨附指派給非使用中信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="defc5-214">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored.</span></span> <span data-ttu-id="defc5-215">這表示在非使用中信箱與封存原則標記的項目保留在主要信箱保留期間到期時。</span><span class="sxs-lookup"><span data-stu-id="defc5-215">That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires.</span></span> <span data-ttu-id="defc5-216">它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="defc5-216">They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="defc5-217">因為使用者無法登入非使用中的信箱，則無須耗用資料中心的資源來處理封存原則。</span><span class="sxs-lookup"><span data-stu-id="defc5-217">Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="defc5-218">**若要檢查新的保留期間，請執行下列其中一個下列命令。**</span><span class="sxs-lookup"><span data-stu-id="defc5-218">**To check the new hold duration, run one of the following commands.**</span></span> <span data-ttu-id="defc5-219">第一個命令為訴訟暫止狀態;第二個適用於原有範圍暫止。</span><span class="sxs-lookup"><span data-stu-id="defc5-219">The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="defc5-220">**與一般信箱相同受管理的資料夾助理員 (MFA) 也會處理非使用中信箱。**</span><span class="sxs-lookup"><span data-stu-id="defc5-220">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="defc5-221">在 Exchange Online 中，MFA 會處理信箱一次大約每隔 7 天。</span><span class="sxs-lookup"><span data-stu-id="defc5-221">In Exchange Online, the MFA processes mailboxes approximately once every 7 days.</span></span> <span data-ttu-id="defc5-222">在變更非使用中信箱的保留期間後，您可以使用**Start-managedfolderassistant**指令程式可以立即開始處理非使用中信箱的新保留期間。</span><span class="sxs-lookup"><span data-stu-id="defc5-222">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="defc5-223">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="defc5-223">Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="defc5-224">**如果保留許多處於非使用中的信箱，不是所有的保留將顯示的 Guid。**</span><span class="sxs-lookup"><span data-stu-id="defc5-224">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="defc5-225">您可以執行下列命令，以顯示 （除了訴訟保留） 處於非使用中信箱的所有保留的 Guid。</span><span class="sxs-lookup"><span data-stu-id="defc5-225">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
