---
title: 如何找出位於 Exchange Online 信箱的保留類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.openlocfilehash: d24e51bca0e3d290f110b1ab40f3ee9ae7993678
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527019"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="16736-102">如何找出位於 Exchange Online 信箱的保留類型</span><span class="sxs-lookup"><span data-stu-id="16736-102">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="16736-103">本文說明如何識別放入 Office 365 中的 Exchange Online 信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="16736-103">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="16736-p101">Office 365 提供數種貴組織可防止信箱內容會永久刪除的方式。這可讓您的組織內容以符合規範 regulars 保留或法律或其他類型的調查的持續期間。以下是 Office 365 中的保留功能 （也稱為保留） 的清單：</span><span class="sxs-lookup"><span data-stu-id="16736-p101">Office 365 offers a number of ways that your organization can prevent mailbox content from being permanently deleted. This allows your organization to retain content to meet compliance regulars or for the duration of legal or other types of investigations. Here's a list of the retention features (also called holds) in Office 365:</span></span>

- <span data-ttu-id="16736-107">**訴訟暫止狀態**-已套用至 Exchange Online 中的使用者信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="16736-107">**Litigation Hold** - Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="16736-p102">**eDiscovery 保留**-保留相關聯的安全性與規範中心 eDiscovery 案例。eDiscovery 保留會套用至使用者信箱與對應的信箱上為 Office 365 群組和 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="16736-p102">**eDiscovery hold** - Holds that are associated with an eDiscovery case in the Security & Compliance Center. eDiscovery holds can be applied to user mailboxes, and on the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="16736-110">**就地保留**-使用就地 eDiscovery 和保留工具在 Exchange 系統中已套用至使用者信箱的保留中心在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="16736-110">**In-Place Hold** - Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="16736-p103">**Office 365 保留原則**-Office 365 群組及 Microsoft 小組會保留在 Exchange Online 和對應的信箱中的使用者信箱中的內容。您可以建立保留原則會儲存在使用者信箱中的商務交談的保留 Skype。</span><span class="sxs-lookup"><span data-stu-id="16736-p103">**Office 365 retention policy** - Retains content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams. You can create a retention policy retains Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="16736-113">有兩種類型的 Office 365 可以指派給信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="16736-113">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="16736-p104">**特定位置保留原則**-這些是指派給特定使用者的內容位置原則。您可以在 Exchange Online PowerShell 中使用 Get-mailbox 指令程式取得指派至特定信箱的保留原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16736-p104">**Specific location retention policies** - These are policies that are assigned to the content locations of specific users. You use the Get-Mailbox cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="16736-p105">**全組織的保留原則**-這些是指派給您組織中的所有內容位置原則。您可以在 Exchange Online PowerShell 中使用 Get-organizationconfig 指令程式取得整個組織的保留原則的相關資訊。如需詳細資訊，請參閱 Office 365 概觀 （英文) 的保留原則的 「 套用至整個組織或特定位置的保留原則 」 一節。</span><span class="sxs-lookup"><span data-stu-id="16736-p105">**Organization-wide retention policies** - These are policies that are assigned to all content locations in your organization. You use the Get-OrganizationConfig cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies. For more information, see the "Applying a retention policy to an entire organization or specific locations" section in Overview of Office 365 retention policies.</span></span>

<span data-ttu-id="16736-p106">若要管理保留信箱，您必須識別，讓您可以執行工作，例如變更保留持續時間、 暫時或永久移除保留，或從 Office 365 保留原則除外信箱被放置在信箱的保留的類型。在下列情況下，第一個步驟是保留的識別信箱的類型。與多個保留 （和不同類型的保留） 可以放在單一信箱，因為您必須識別如果您想要移除或變更這些保留放在信箱上的所有保留。</span><span class="sxs-lookup"><span data-stu-id="16736-p106">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Office 365 retention policy. In these cases, the first step is to identify the type of hold placed on the mailbox. And because multiple holds (and different types of holds) can be placed on a single mailbox, you'll have to identify all holds placed on a mailbox if you want to remove or change those holds.</span></span>

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="16736-122">步驟 1： 取得保留 GUID 放在信箱上</span><span class="sxs-lookup"><span data-stu-id="16736-122">Step 1: Obtaining the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="16736-p107">您可以執行下列兩個指令程式在 Exchange Online PowerShell 取得會放在信箱保留的 GUID。取得 GUID 之後，您會使用它來識別特定保留在步驟 2。請注意訴訟保留不所識別的 GUID。[啟用或停用信箱的訴訟保留。</span><span class="sxs-lookup"><span data-stu-id="16736-p107">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox. After you obtain a GUID, you use it to identify the specific hold in Step 2. Note that Litigation Holds are not identified by a GUID. Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="16736-p108">**Get-mailbox** -使用此指令程式來決定是否啟用信箱的訴訟暫止狀態，並取得 Guid ediscovery 保留、 就地保留，及 Office 365 明確指派給信箱的保留原則。此 cmdlet 的輸出也會表示若信箱已明確地從排除整個組織的保留原則。</span><span class="sxs-lookup"><span data-stu-id="16736-p108">**Get-Mailbox** - Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox. The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="16736-129">**Get-organizationconfig** -使用此指令程式來取得整個組織的保留原則的 Guid。</span><span class="sxs-lookup"><span data-stu-id="16736-129">**Get-OrganizationConfig** - Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="16736-130">若要連線至 Exchange Online PowerShell，請參閱[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="16736-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="16736-131">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="16736-131">Get-Mailbox</span></span>

<span data-ttu-id="16736-132">執行下列命令以取得保留及 Office 365 保留原則套用到信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16736-132">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="16736-133">如果 InPlaceHolds 屬性中有太多值並不是所有的顯示，則可以執行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個 GUID 分列一行。</span><span class="sxs-lookup"><span data-stu-id="16736-133">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="16736-134">下表說明如何識別不同類型的保留當您執行**Get-mailbox**指令程式根據*InPlaceHolds*屬性中的值。</span><span class="sxs-lookup"><span data-stu-id="16736-134">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="16736-135">保留類型</span><span class="sxs-lookup"><span data-stu-id="16736-135">Hold type</span></span>  |<span data-ttu-id="16736-136">範例值</span><span class="sxs-lookup"><span data-stu-id="16736-136">Example value</span></span>  |<span data-ttu-id="16736-137">如何識別保留</span><span class="sxs-lookup"><span data-stu-id="16736-137">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="16736-138">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="16736-138">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="16736-139">如果*LitigationHoldEnabled*屬性設為訴訟資料暫留啟用信箱的`True`。</span><span class="sxs-lookup"><span data-stu-id="16736-139">Litigation Hold is enabled for a mailbox if the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="16736-140">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="16736-140">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="16736-p109">*InPlaceHolds 屬性*會包含任何保留與 eDiscovery 案例中的安全性與規範中心相關聯的 GUID。您可以分清這是因為 GUID 開頭的 eDiscovery 保留`UniH`前置詞 （這表示整合保留）。</span><span class="sxs-lookup"><span data-stu-id="16736-p109">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center. You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="16736-143">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="16736-143">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="16736-144">或</span><span class="sxs-lookup"><span data-stu-id="16736-144">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="16736-p110">*InPlaceHolds*屬性會包含信箱處於就地保留 GUID。您可以分清這是就地保留因為 GUID 也不會啟動具有前置詞或其開頭`cld`前置詞。</span><span class="sxs-lookup"><span data-stu-id="16736-p110">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="16736-147">Office 365 特別套用到信箱的保留原則</span><span class="sxs-lookup"><span data-stu-id="16736-147">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="16736-148">或</span><span class="sxs-lookup"><span data-stu-id="16736-148">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="16736-p111">InPlaceHolds 屬性會包含任何特定位置保留原則套用至信箱的 Guid。您可以識別保留原則因為 GUID 開頭`mbx`或`skp`前置詞。`skp`前置詞表示保留原則套用至 Skype 商務使用者的信箱中的交談。</span><span class="sxs-lookup"><span data-stu-id="16736-p111">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox. You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix. The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="16736-152">排除全組織的 Office 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="16736-152">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="16736-153">如果信箱排除在整個組織的 Office 365 保留原則、 排除信箱的保留原則的 GUID InPlaceHolds 屬性中會顯示與所識別`-mbx`前置詞。</span><span class="sxs-lookup"><span data-stu-id="16736-153">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="16736-154">Get-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="16736-154">Get-OrganizationConfig</span></span>
<span data-ttu-id="16736-p112">如果當您執行**Get-mailbox**指令程式*InPlaceHolds*屬性是空的仍可能會有一或多個整個組織的 Office 365 保留原則套用至信箱。執行下列命令在 Exchange Online PowerShell 可取得整個組織的 Office 365 保留原則清單的 Guid。</span><span class="sxs-lookup"><span data-stu-id="16736-p112">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox. Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="16736-157">如果 InPlaceHolds 屬性中有太多值並不是所有的顯示，則可以執行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以顯示每個 GUID 分列一行。</span><span class="sxs-lookup"><span data-stu-id="16736-157">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="16736-158">下表說明不同類型的全組織保留，以及如何識別每種類型根據執行**Get-organizationconfig**指令程式時*InPlaceHolds*屬性中所含的 Guid。</span><span class="sxs-lookup"><span data-stu-id="16736-158">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="16736-159">保留類型</span><span class="sxs-lookup"><span data-stu-id="16736-159">Hold type</span></span>  |<span data-ttu-id="16736-160">範例值</span><span class="sxs-lookup"><span data-stu-id="16736-160">Example value</span></span>  |<span data-ttu-id="16736-161">描述</span><span class="sxs-lookup"><span data-stu-id="16736-161">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="16736-162">Office 365 的保留原則套用至 Exchange 信箱、 Exchange 公共資料夾及小組聊天室</span><span class="sxs-lookup"><span data-stu-id="16736-162">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="16736-p113">整個組織的保留原則套用至 Exchange 信箱、 Exchange 公共資料夾及 1xN 聊天室中的 Microsoft 小組所識別的開頭的 Guid`mbx`前置詞。請注意 1xN 聊天會儲存在個別的交談參與者的信箱。</span><span class="sxs-lookup"><span data-stu-id="16736-p113">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix. Note that 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="16736-165">Office 365 的保留原則套用至 Office 365 群組及小組通道郵件</span><span class="sxs-lookup"><span data-stu-id="16736-165">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="16736-p114">整個組織的保留原則套用至 Office 365 群組和通道郵件中的 Microsoft 小組所識別的開頭的 Guid`grp`前置詞。請注意通道訊息會儲存群組信箱相關聯的 Microsoft 小組中。</span><span class="sxs-lookup"><span data-stu-id="16736-p114">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix. Note that channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="16736-168">如需詳細資訊保留原則套用至 Microsoft 小組請參閱 「 小組位置 」] 區段中[的保留原則的概觀](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="16736-168">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="16736-169">了解保留原則的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="16736-169">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="16736-p115">除了前置詞 （mbx、 skp、 或群組） 可識別 InPlaceHolds 屬性為 Office 365 保留原則中的項目，此值也包含尾碼可識別的保留原則設定的動作類型。例如會在下列範例中的粗體類型醒目提示的動作後置詞：</span><span class="sxs-lookup"><span data-stu-id="16736-p115">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy. For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="16736-172">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="16736-172">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="16736-173">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="16736-173">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="16736-174">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="16736-174">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="16736-175">下表定義的三種可能的保留動作：</span><span class="sxs-lookup"><span data-stu-id="16736-175">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="16736-176">值</span><span class="sxs-lookup"><span data-stu-id="16736-176">Value</span></span>  |<span data-ttu-id="16736-177">描述</span><span class="sxs-lookup"><span data-stu-id="16736-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="16736-178">**1**</span><span class="sxs-lookup"><span data-stu-id="16736-178">**1**</span></span>     | <span data-ttu-id="16736-179">會指出保留原則已刪除的項目 ；原則不會保留的項目。</span><span class="sxs-lookup"><span data-stu-id="16736-179">Indicates the retention policy is configured to delete items; the policy doesn't retain items.</span></span>        |
|<span data-ttu-id="16736-180">**2**</span><span class="sxs-lookup"><span data-stu-id="16736-180">**2**</span></span>    |    <span data-ttu-id="16736-181">會指出保留原則設定為要保留的項目 ；之後保留期間到期原則不會刪除項目。</span><span class="sxs-lookup"><span data-stu-id="16736-181">Indicates the retention policy is configured to hold items; the policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="16736-182">**3**</span><span class="sxs-lookup"><span data-stu-id="16736-182">**3**</span></span>     |   <span data-ttu-id="16736-183">會指出保留原則設定為保留的項目並再予以刪除之後保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="16736-183">Indicates the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="16736-184">如需保留動作的詳細資訊，請參閱"的特定期間內保留內容"] 區段中的[保留原則的概觀](retention-policies.md#retaining-content-for-a-specific-period-of-time)。</span><span class="sxs-lookup"><span data-stu-id="16736-184">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a><span data-ttu-id="16736-185">步驟 2： 使用 GUID 來找出保留</span><span class="sxs-lookup"><span data-stu-id="16736-185">Step 2: Using the GUID to identify the hold</span></span>

<span data-ttu-id="16736-p116">取得保留套用到信箱的 GUID 之後下, 一步是用以識別保留的 GUID。下列各節說明如何識別保留 （和其他資訊） 的名稱使用保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="16736-p116">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold. The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="16736-188">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="16736-188">eDiscovery holds</span></span>

<span data-ttu-id="16736-p117">安全性及規範中心 PowerShell，以識別套用至信箱 eDiscovery 保留中執行下列命令。使用 GUID （不包括 UniH 前置詞） 的 ediscovery （英文） 保留您在步驟 1 中識別。第一個命令會建立包含保留; 的相關資訊的變數其他命令中使用這個變數。第二個命令會顯示保留相關聯的 eDiscovery 案例的名稱。第三個命令會顯示的保留名稱並保留套用至信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="16736-p117">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox. Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1. The first command creates a variable that contains information about the hold; this variable is used in the other commands. The second command displays the name of the eDiscovery case the hold is associated with. The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="16736-194">若要連線至安全性與規範中心 PowerShell，請參閱[Connect to Office 365 的安全性與規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="16736-194">To connect to Security & Compliance Center PowerShell, see  [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="16736-195">就地保留</span><span class="sxs-lookup"><span data-stu-id="16736-195">In-Place Holds</span></span>

<span data-ttu-id="16736-p118">在識別為 「 就地保留套用到信箱的 Exchange Online PowerShell 中執行下列命令。使用您在步驟 1 中識別為 「 就地保留 GUID。此命令會顯示的保留名稱並保留套用至信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="16736-p118">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1. The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="16736-199">請注意，如果 GUID 的就地保留開頭`cld`首碼，請務必執行上述命令時包含前置詞。</span><span class="sxs-lookup"><span data-stu-id="16736-199">Note that if the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="16736-200">Office 365 的保留原則</span><span class="sxs-lookup"><span data-stu-id="16736-200">Office 365 retention policies</span></span>

<span data-ttu-id="16736-p119">執行下列命令的安全性與規範中心 PowerShell 身分識別會套用至信箱的 Office 365 保留原則 （整個組織或特定的位置）。使用您在步驟 1 中識別的 GUID （不包括的 mbx、 skp、 或群組的前置字元或的動作後置字元）。</span><span class="sxs-lookup"><span data-stu-id="16736-p119">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox. Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="next-steps"></a><span data-ttu-id="16736-203">後續步驟</span><span class="sxs-lookup"><span data-stu-id="16736-203">Next steps</span></span>

<span data-ttu-id="16736-p120">識別套用到信箱的保留之後，您可以執行工作如變更保留的期限暫時或永久移除保留，或者在 Office 365 的保留原則除外非使用中的信箱原則。如需執行保留的相關工作的詳細資訊，請參閱下列主題的其中一個：</span><span class="sxs-lookup"><span data-stu-id="16736-p120">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or in the case of Office 365 retention policies, excluding an inactive mailbox from the policy. For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="16736-p121">執行[組 RetentionCompliancePolicy AddExchangeLocationException\<使用者信箱 >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令的安全性及規範中心 PowerShell，以從全組織的 Office 365 保留原則中排除信箱。請注意此命令可只用於保留原則其中*ExchangeLocation*屬性的值等於`All`。</span><span class="sxs-lookup"><span data-stu-id="16736-p121">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy. Note that this command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="16736-208">執行[Set-mailbox ExcludeFromOrgHolds\<保留 GUID 而首碼或尾碼 >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)在整個組織的 Office 365 保留原則中排除不在作用中信箱的 Exchange Online PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="16736-208">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="16736-209">變更 Office 365 中不在作用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="16736-209">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="16736-210">刪除非作用中的信箱在 Office 365</span><span class="sxs-lookup"><span data-stu-id="16736-210">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="16736-211">刪除雲端式信箱中可復原的項目資料夾中的保留項目</span><span class="sxs-lookup"><span data-stu-id="16736-211">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
