---
title: 如何找出位於 Exchange Online 信箱的保留類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何識別不同類型的可以放在 Office 365 信箱的保留。 這些類型的保留包含訴訟暫止、 eDiscovery 保留和 Office 365 保留原則。 您也可以判定是否使用者已被排除全組織保留原則
ms.openlocfilehash: 29ae9d7ba8be2bf0064c163605aee9ad8fd5fd07
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154195"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="0e03f-105">如何找出位於 Exchange Online 信箱的保留類型</span><span class="sxs-lookup"><span data-stu-id="0e03f-105">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="0e03f-106">本文說明如何識別保留暫留在 Office 365 中的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-106">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="0e03f-107">Office 365 提供許多組織可以防止永久刪除信箱內容的方法。</span><span class="sxs-lookup"><span data-stu-id="0e03f-107">Office 365 offers a number of ways that your organization can prevent mailbox content from being permanently deleted.</span></span> <span data-ttu-id="0e03f-108">這可讓您的組織來保留以符合規範 regulars 的內容或期間內的法律或其他類型的調查。</span><span class="sxs-lookup"><span data-stu-id="0e03f-108">This allows your organization to retain content to meet compliance regulars or for the duration of legal or other types of investigations.</span></span> <span data-ttu-id="0e03f-109">以下是 Office 365 的保留功能 （也稱為*保留*） 的清單：</span><span class="sxs-lookup"><span data-stu-id="0e03f-109">Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="0e03f-110">**訴訟暫止**-已套用至 Exchange Online 中的使用者信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-110">**Litigation Hold** - Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="0e03f-111">**eDiscovery 保留**-在安全性與合規性中心 eDiscovery 案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-111">**eDiscovery hold** - Holds that are associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="0e03f-112">eDiscovery 保留可以套用到使用者信箱，並在對應的信箱上 Office 365 群組和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0e03f-112">eDiscovery holds can be applied to user mailboxes, and on the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="0e03f-113">**就地保留**位在 Exchange 系統管理員使用就地 eDiscovery & 保留工具已套用至使用者信箱的保留中心在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0e03f-113">**In-Place Hold** - Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="0e03f-114">**Office 365 保留原則**-Office 365 群組及 Microsoft Teams 保留使用者信箱在 Exchange Online 和對應的信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="0e03f-114">**Office 365 retention policy** - Retains content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="0e03f-115">您可以建立保留原則會儲存在使用者信箱中的商務交談保留 Skype。</span><span class="sxs-lookup"><span data-stu-id="0e03f-115">You can create a retention policy retains Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="0e03f-116">有兩種類型的 Office 365 保留原則，可以指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-116">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="0e03f-117">**特定位置保留原則**，這些是指派給特定使用者的內容位置原則。</span><span class="sxs-lookup"><span data-stu-id="0e03f-117">**Specific location retention policies** - These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="0e03f-118">您在 Exchange Online PowerShell 中使用**Get-mailbox**指令程式，來取得指派給特定信箱的保留原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0e03f-118">You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="0e03f-119">**整個組織的保留原則**，這些是指派給組織中的所有內容位置原則。</span><span class="sxs-lookup"><span data-stu-id="0e03f-119">**Organization-wide retention policies** - These are policies that are assigned to all content locations in your organization.</span></span> <span data-ttu-id="0e03f-120">您在 Exchange Online PowerShell 中使用**Get-organizationconfig**指令程式，來取得全組織保留原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0e03f-120">You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>
  <span data-ttu-id="0e03f-121">如需詳細資訊，請參閱 「 將保留原則套用至整個組織或特定位置 」 一節中[概觀的 Office 365 保留原則](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="0e03f-121">For more information, see the "Applying a retention policy to an entire organization or specific locations" section in [Overview of Office 365 retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

- <span data-ttu-id="0e03f-122">**Office 365 保留標籤**-如果使用者將 （一個已設定為保留內容或保留，然後刪除內容） 的 Office 365 保留標籤套用至*任何*資料夾或項目在其信箱，保留置於信箱，就如同信箱已處於訴訟暫止狀態或指派給 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e03f-122">**Office 365 retention labels** - If a user applies an Office 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox just as if the mailbox was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span> <span data-ttu-id="0e03f-123">如需詳細資訊，請參閱本文[Identifying 的信箱，所以已保留標籤套用至資料夾或項目保留](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)一節。</span><span class="sxs-lookup"><span data-stu-id="0e03f-123">For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="0e03f-124">若要管理保留的信箱，您可能要識別，讓您可以執行工作，例如變更保留持續時間、 暫時或永久移除保留，或從 Office 365 保留原則中排除信箱置於信箱的保留的類型。</span><span class="sxs-lookup"><span data-stu-id="0e03f-124">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Office 365 retention policy.</span></span> <span data-ttu-id="0e03f-125">在這些情況下，第一個步驟是識別保留暫留信箱的類型。</span><span class="sxs-lookup"><span data-stu-id="0e03f-125">In these cases, the first step is to identify the type of hold placed on the mailbox.</span></span> <span data-ttu-id="0e03f-126">因為多個保留 （與不同類型的保留） 可以放在單一信箱，您必須識別放置在信箱上，如果您想要移除或變更這些保留的所有保留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-126">And because multiple holds (and different types of holds) can be placed on a single mailbox, you'll have to identify all holds placed on a mailbox if you want to remove or change those holds.</span></span>

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="0e03f-127">步驟 1： 取得的 GUID，保留暫留信箱</span><span class="sxs-lookup"><span data-stu-id="0e03f-127">Step 1: Obtaining the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="0e03f-128">您可以執行下列兩個指令程式在 Exchange Online PowerShell，以取得的信箱置於保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-128">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox.</span></span> <span data-ttu-id="0e03f-129">取得 GUID 之後，您會使用它來識別特定保留在 [步驟 2。</span><span class="sxs-lookup"><span data-stu-id="0e03f-129">After you obtain a GUID, you use it to identify the specific hold in Step 2.</span></span> <span data-ttu-id="0e03f-130">請注意的訴訟暫止會保留不識別 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-130">Note that Litigation Holds are not identified by a GUID.</span></span> <span data-ttu-id="0e03f-131">[啟用或停用信箱的訴訟資料暫留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-131">Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="0e03f-132">**Get-mailbox** -使用此指令程式，若要判斷是否啟用信箱的訴訟暫止，並取得 Guid ediscovery 保留、 就地保留，以及 Office 365 保留原則，特別是指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-132">**Get-Mailbox** - Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox.</span></span> <span data-ttu-id="0e03f-133">此 cmdlet 的輸出也會指出是否信箱具有已明確排除全組織保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e03f-133">The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="0e03f-134">**Get-organizationconfig** -使用此指令程式來取得全組織保留原則的 Guid。</span><span class="sxs-lookup"><span data-stu-id="0e03f-134">**Get-OrganizationConfig** - Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="0e03f-135">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="0e03f-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="0e03f-136">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="0e03f-136">Get-Mailbox</span></span>

<span data-ttu-id="0e03f-137">執行下列命令，以取得保留和 Office 365 保留原則套用至信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0e03f-137">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="0e03f-138">如果 InPlaceHolds 屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-138">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="0e03f-139">下表描述如何識別不同類型的保留根據*InPlaceHolds*屬性中的值，當您執行**Get-mailbox**指令程式。</span><span class="sxs-lookup"><span data-stu-id="0e03f-139">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="0e03f-140">保留類型</span><span class="sxs-lookup"><span data-stu-id="0e03f-140">Hold type</span></span>  |<span data-ttu-id="0e03f-141">範例值</span><span class="sxs-lookup"><span data-stu-id="0e03f-141">Example value</span></span>  |<span data-ttu-id="0e03f-142">如何找出保留</span><span class="sxs-lookup"><span data-stu-id="0e03f-142">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0e03f-143">訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="0e03f-143">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="0e03f-144">如果*LitigationHoldEnabled*屬性設為，將會啟用信箱的訴訟資料暫留`True`。</span><span class="sxs-lookup"><span data-stu-id="0e03f-144">Litigation Hold is enabled for a mailbox if the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="0e03f-145">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="0e03f-145">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="0e03f-146">*InPlaceHolds 屬性*會包含任何保留在安全性與合規性中心 eDiscovery 案例相關聯的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-146">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="0e03f-147">您可以分清這是 eDiscovery 保留，因為 GUID 開頭`UniH`（這表示整合保留） 的前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-147">You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="0e03f-148">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="0e03f-148">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="0e03f-149">或</span><span class="sxs-lookup"><span data-stu-id="0e03f-149">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="0e03f-150">*InPlaceHolds*屬性包含信箱處於就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-150">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="0e03f-151">您可以分清這是在原有範圍暫止因為 GUID 也不會啟動與前置詞或它的開頭`cld`前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-151">You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="0e03f-152">Office 365 保留原則特別套用到信箱</span><span class="sxs-lookup"><span data-stu-id="0e03f-152">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="0e03f-153">或</span><span class="sxs-lookup"><span data-stu-id="0e03f-153">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="0e03f-154">InPlaceHolds 屬性會包含任何特定位置保留原則套用到信箱的 Guid。</span><span class="sxs-lookup"><span data-stu-id="0e03f-154">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox.</span></span> <span data-ttu-id="0e03f-155">您可以識別保留原則，因為 GUID 開頭`mbx`或`skp`前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-155">You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix.</span></span> <span data-ttu-id="0e03f-156">`skp`前置詞會指示的保留原則套用至 Skype，商務交談在使用者的信箱中的。</span><span class="sxs-lookup"><span data-stu-id="0e03f-156">The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="0e03f-157">排除在整個組織的 Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="0e03f-157">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="0e03f-158">如果信箱排除全組織的 Office 365 保留原則，排除信箱的保留原則的 GUID 會顯示在 InPlaceHolds 屬性，而且由`-mbx`前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-158">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="0e03f-159">Get-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="0e03f-159">Get-OrganizationConfig</span></span>
<span data-ttu-id="0e03f-160">如果*InPlaceHolds*屬性是空的當您執行**Get-mailbox**指令程式時，仍可能有一或多個全組織的 Office 365 保留原則套用到信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-160">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="0e03f-161">下列命令在 Exchange Online PowerShell 中執行到整個組織的 Office 365 保留原則來取得 Guid 的清單。</span><span class="sxs-lookup"><span data-stu-id="0e03f-161">Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="0e03f-162">如果 InPlaceHolds 屬性中有太多的值，而且並非所有的顯示，您可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令，以顯示的個別行上的每個 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-162">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="0e03f-163">下表說明不同類型的全組織保留，以及如何識別每個包含*InPlaceHolds*屬性中，當您執行**Get-organizationconfig**指令程式的 Guid 為基礎的類型。</span><span class="sxs-lookup"><span data-stu-id="0e03f-163">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="0e03f-164">保留類型</span><span class="sxs-lookup"><span data-stu-id="0e03f-164">Hold type</span></span>  |<span data-ttu-id="0e03f-165">範例值</span><span class="sxs-lookup"><span data-stu-id="0e03f-165">Example value</span></span>  |<span data-ttu-id="0e03f-166">描述</span><span class="sxs-lookup"><span data-stu-id="0e03f-166">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0e03f-167">Office 365 保留原則套用至 Exchange 信箱、 Exchange 公用資料夾及小組聊天</span><span class="sxs-lookup"><span data-stu-id="0e03f-167">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="0e03f-168">整個組織的保留原則套用至 Exchange 信箱、 Exchange 公用資料夾和 Microsoft teams 1xN 聊天室以開頭的 Guid 來識別`mbx`前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-168">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix.</span></span> <span data-ttu-id="0e03f-169">請注意 1xN 聊天會儲存在個別的交談參與者的信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-169">Note that 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="0e03f-170">Office 365 保留原則套用至 Office 365 群組及小組通道訊息</span><span class="sxs-lookup"><span data-stu-id="0e03f-170">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="0e03f-171">整個組織的保留原則套用至 Office 365 群組和 Microsoft Teams 中的通道郵件以開頭的 Guid 來識別`grp`前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-171">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix.</span></span> <span data-ttu-id="0e03f-172">請注意通道訊息會存放在 Microsoft 小組與相關聯的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-172">Note that channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="0e03f-173">如需資訊的保留原則套用至 Microsoft Teams，請參閱 「 microsoft Teams 位置 」 一節[的保留原則概觀](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="0e03f-173">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="0e03f-174">了解保留原則的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="0e03f-174">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="0e03f-175">除了前置詞 （mbx、 skp 或群組） 可識別 InPlaceHolds 屬性做為 Office 365 保留原則中的項目，此值也包含可識別已設定原則的保留動作的類型後置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-175">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy.</span></span> <span data-ttu-id="0e03f-176">例如，動作後置詞會反白顯示在下列範例中以粗體字型：</span><span class="sxs-lookup"><span data-stu-id="0e03f-176">For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="0e03f-177">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="0e03f-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="0e03f-178">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="0e03f-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="0e03f-179">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="0e03f-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="0e03f-180">下表定義三個可能的保留動作：</span><span class="sxs-lookup"><span data-stu-id="0e03f-180">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="0e03f-181">值</span><span class="sxs-lookup"><span data-stu-id="0e03f-181">Value</span></span>  |<span data-ttu-id="0e03f-182">描述</span><span class="sxs-lookup"><span data-stu-id="0e03f-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0e03f-183">**1**</span><span class="sxs-lookup"><span data-stu-id="0e03f-183">**1**</span></span>     | <span data-ttu-id="0e03f-184">會指出保留原則設為刪除項目;項目時，不會保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e03f-184">Indicates the retention policy is configured to delete items; the policy doesn't retain items.</span></span>        |
|<span data-ttu-id="0e03f-185">**2**</span><span class="sxs-lookup"><span data-stu-id="0e03f-185">**2**</span></span>    |    <span data-ttu-id="0e03f-186">會指出保留原則設為保留項目;在保留期間到期之後，原則不會刪除項目。</span><span class="sxs-lookup"><span data-stu-id="0e03f-186">Indicates the retention policy is configured to hold items; the policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="0e03f-187">**3**</span><span class="sxs-lookup"><span data-stu-id="0e03f-187">**3**</span></span>     |   <span data-ttu-id="0e03f-188">會指出保留原則設為保留項目，然後在保留期間到期後刪除，它們。</span><span class="sxs-lookup"><span data-stu-id="0e03f-188">Indicates the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="0e03f-189">如需有關保留動作的詳細資訊，請參閱 <<c0>保留原則概觀中的 「 時間在特定期間內保留內容 」 一節。</span><span class="sxs-lookup"><span data-stu-id="0e03f-189">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a><span data-ttu-id="0e03f-190">步驟 2： 使用 GUID 來識別保留</span><span class="sxs-lookup"><span data-stu-id="0e03f-190">Step 2: Using the GUID to identify the hold</span></span>

<span data-ttu-id="0e03f-191">取得保留套用到信箱的 GUID 之後下, 一個步驟是使用該 GUID 來識別保留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-191">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold.</span></span> <span data-ttu-id="0e03f-192">下列各節說明如何識別保留 （及其他資訊） 的名稱使用保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-192">The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="0e03f-193">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="0e03f-193">eDiscovery holds</span></span>

<span data-ttu-id="0e03f-194">安全性 & 合規性中心 PowerShell 找出電子文件探索保留套用到信箱中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0e03f-194">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox.</span></span> <span data-ttu-id="0e03f-195">使用 （不包括 UniH 前置詞） 的 GUID ediscovery 保留您在步驟 1 中識別。</span><span class="sxs-lookup"><span data-stu-id="0e03f-195">Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="0e03f-196">第一個命令會建立變數，包含保留; 的相關資訊此變數會用於其他命令。</span><span class="sxs-lookup"><span data-stu-id="0e03f-196">The first command creates a variable that contains information about the hold; this variable is used in the other commands.</span></span> <span data-ttu-id="0e03f-197">第二個命令會顯示保留相關聯的 eDiscovery 案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-197">The second command displays the name of the eDiscovery case the hold is associated with.</span></span> <span data-ttu-id="0e03f-198">第三個命令會顯示的保留名稱並保留套用至信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="0e03f-198">The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="0e03f-199">若要連接到安全性 & 合規性中心 PowerShell，請參閱[連線到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="0e03f-199">To connect to Security & Compliance Center PowerShell, see  [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="0e03f-200">就地保留</span><span class="sxs-lookup"><span data-stu-id="0e03f-200">In-Place Holds</span></span>

<span data-ttu-id="0e03f-201">若要識別為 「 就地保留套用到信箱的 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0e03f-201">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox.</span></span> <span data-ttu-id="0e03f-202">針對您在步驟 1 中識別為 「 就地保留使用 GUID。</span><span class="sxs-lookup"><span data-stu-id="0e03f-202">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> <span data-ttu-id="0e03f-203">此命令會顯示的保留名稱並保留套用至信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="0e03f-203">The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="0e03f-204">請注意，如果 GUID 為 「 就地保留 」 狀態的開頭`cld`前置詞，請務必執行上述命令時包含前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e03f-204">Note that if the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="0e03f-205">Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="0e03f-205">Office 365 retention policies</span></span>

<span data-ttu-id="0e03f-206">執行下列命令中安全性 & 合規性中心 PowerShell 身分識別的 Office 365 保留原則 （全組織或特定位置），會套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-206">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox.</span></span> <span data-ttu-id="0e03f-207">使用您在步驟 1 中識別的 GUID （不包括 mbx、 skp 或群組的前置詞或動作後置字元）。</span><span class="sxs-lookup"><span data-stu-id="0e03f-207">Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="0e03f-208">識別信箱，所以已保留標籤套用至資料夾或項目保留</span><span class="sxs-lookup"><span data-stu-id="0e03f-208">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="0e03f-209">每當使用者套用保留標籤設定為保留內容或保留，然後刪除任何資料夾或項目在其信箱的內容， *ComplianceTagHoldApplied*信箱屬性設為**True**。</span><span class="sxs-lookup"><span data-stu-id="0e03f-209">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="0e03f-210">發生這種情況，信箱會被視為在保存時，就如同它已處於訴訟暫止狀態或指派給 Office 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="0e03f-210">When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span> <span data-ttu-id="0e03f-211">當*ComplianceTagHoldApplied*屬性設定為**True**時，可能會發生下列情形：</span><span class="sxs-lookup"><span data-stu-id="0e03f-211">When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="0e03f-212">如果刪除信箱或使用者的 Office 365 使用者帳戶時，信箱會變成[非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0e03f-212">If the mailbox or the user's Office 365 user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="0e03f-213">您無法停用信箱 （主要信箱還是封存信箱，如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="0e03f-213">You won't be able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="0e03f-214">可能比預期會再保留信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="0e03f-214">Items in the mailbox may be retained longer than expected.</span></span> <span data-ttu-id="0e03f-215">這是因為信箱處於保留狀態，因此沒有項目將會永久刪除 （清除）。</span><span class="sxs-lookup"><span data-stu-id="0e03f-215">This is because the mailbox is on hold and therefore no items will be permanently deleted (purged).</span></span>

<span data-ttu-id="0e03f-216">若要檢視*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0e03f-216">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="0e03f-217">如需保留標籤的詳細資訊，請參閱 < <b0>Office 365 的概觀保留標籤</b0>。</span><span class="sxs-lookup"><span data-stu-id="0e03f-217">For more information about retention labels, see [Overview of Office 365 retention labels](labels.md).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="0e03f-218">管理信箱的延遲</span><span class="sxs-lookup"><span data-stu-id="0e03f-218">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="0e03f-219">從信箱移除任何類型的保留後， *DelayHoldApplied*信箱屬性的值設為**True**。</span><span class="sxs-lookup"><span data-stu-id="0e03f-219">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="0e03f-220">發生此情況下一次受管理的資料夾助理員處理信箱，並會偵測已移除保留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-220">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="0e03f-221">這稱為*延遲保留*，表示實際移除保留已延遲，30 天的時間可以防止資料被永久刪除 （清除） 的信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-221">This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.</span></span> <span data-ttu-id="0e03f-222">這讓系統管理員有機會搜尋或復原之後實際移除保留為止，將清除的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="0e03f-222">This gives admins an opportunity to search for or recover mailbox items that will be purged after the hold is actually removed.</span></span> <span data-ttu-id="0e03f-223">當延遲暫留時保留該信箱時，信箱會仍被視為不受限制的持續期間，保留為信箱是否訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="0e03f-223">When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="0e03f-224">30 天後，延遲保留到期，與 Office 365 會自動嘗試移除延遲保留 （ *DelayHoldApplied*屬性設定為**False**），以便將實際移除保留。</span><span class="sxs-lookup"><span data-stu-id="0e03f-224">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold will be actually removed.</span></span> <span data-ttu-id="0e03f-225">*DelayHoldApplied*屬性設**為 False**之後, 會標示為待移除的項目都將予以受管理的資料夾助理員處理信箱時的下一個時間。</span><span class="sxs-lookup"><span data-stu-id="0e03f-225">After the *DelayHoldApplied* property to **False**, items that are marked for removal will be purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="0e03f-226">若要檢視信箱*DelayHoldApplied*屬性的值，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="0e03f-226">To view the value for the *DelayHoldApplied* property for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="0e03f-227">若要移除的延遲保留到期之前，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0e03f-227">To remove the delay hold before it expires, you can run the following command in Exchange Online PowerShell:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="0e03f-228">請注意，您必須獲指派法律保留角色在 Exchange Online 使用*RemoveDelayHoldApplied*參數</span><span class="sxs-lookup"><span data-stu-id="0e03f-228">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter</span></span> 

<span data-ttu-id="0e03f-229">若要移除的延遲保留非使用中信箱上，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0e03f-229">To remove the delay hold on an inactive mailbox, run the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> <span data-ttu-id="0e03f-230">在上述命令中指定非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="0e03f-230">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="0e03f-231">使用下列值之一，有助於防止不小心指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-231">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="0e03f-232">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0e03f-232">Next steps</span></span>

<span data-ttu-id="0e03f-233">識別保留已套用至信箱之後，您可以執行工作，例如變更暫時的保留持續時間或永久移除保留，或在 Office 365 保留原則的情況下從原則中排除不在作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-233">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or in the case of Office 365 retention policies, excluding an inactive mailbox from the policy.</span></span> <span data-ttu-id="0e03f-234">如需執行保留與相關的工作的詳細資訊，請參閱下列主題的其中一種：</span><span class="sxs-lookup"><span data-stu-id="0e03f-234">For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="0e03f-235">執行[Set-retentioncompliancepolicy AddExchangeLocationException\<使用者 mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令中安全性 & 合規性中心 PowerShell，從全組織的 Office 365 保留原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="0e03f-235">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy.</span></span> <span data-ttu-id="0e03f-236">請注意，此命令僅可用於保留原則*ExchangeLocation*屬性的值等於`All`。</span><span class="sxs-lookup"><span data-stu-id="0e03f-236">Note that this command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="0e03f-237">執行[Set-mailbox ExcludeFromOrgHolds\<保留 GUID 不含前置詞或 suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令在整個組織的 Office 365 保留原則中排除不在作用中信箱的 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0e03f-237">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="0e03f-238">變更 Office 365 中的非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="0e03f-238">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="0e03f-239">刪除 Office 365 中的非使用中信箱</span><span class="sxs-lookup"><span data-stu-id="0e03f-239">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="0e03f-240">刪除雲端式信箱中可復原的項目資料夾中的保留項目</span><span class="sxs-lookup"><span data-stu-id="0e03f-240">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
