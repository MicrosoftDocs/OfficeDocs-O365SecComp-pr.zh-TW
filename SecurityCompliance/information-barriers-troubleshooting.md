---
title: 疑難排解資訊障礙
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文做為疑難排解資訊障礙的指南。
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131347"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="f958c-103">疑難排解資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f958c-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="f958c-104">[資訊障礙 (預覽)](information-barriers.md)可協助您的組織遵守法律需求和行業規定。</span><span class="sxs-lookup"><span data-stu-id="f958c-104">[Information barriers (Preview)](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="f958c-105">例如, 透過資訊障礙, 您可以限制特定使用者群組之間的通訊, 以避免利益衝突或其他問題。</span><span class="sxs-lookup"><span data-stu-id="f958c-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="f958c-106">(若要深入瞭解如何設定資訊障礙, 請參閱[定義資訊障礙的原則 (預覽)](information-barriers-policies.md)。)</span><span class="sxs-lookup"><span data-stu-id="f958c-106">(To learn more about how to set up information barriers, see [Define policies for information barriers (Preview)](information-barriers-policies.md).)</span></span>

<span data-ttu-id="f958c-107">如果人員在資訊障礙即將發生時遇到意外的問題, 您可以採取一些步驟來解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="f958c-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="f958c-108">請使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="f958c-108">Use this article as a guide.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="f958c-109">開始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="f958c-109">Before you begin...</span></span>

<span data-ttu-id="f958c-110">若要執行本文所述的工作, 您必須被指派適當的角色, 例如下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="f958c-110">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="f958c-111">Microsoft 365 企業版全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f958c-111">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="f958c-112">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f958c-112">Office 365 Global Administrator</span></span>
- <span data-ttu-id="f958c-113">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="f958c-113">Compliance Administrator</span></span>
- <span data-ttu-id="f958c-114">IB 規範管理 (這是新的角色!)</span><span class="sxs-lookup"><span data-stu-id="f958c-114">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="f958c-115">若要深入瞭解資訊障礙的必要條件, 請參閱[必要條件 (適用于資訊屏障原則)](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="f958c-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="f958c-116">請務必連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="f958c-116">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="f958c-117">問題: 仍允許在 Microsoft 小組中封鎖的使用者之間進行通訊</span><span class="sxs-lookup"><span data-stu-id="f958c-117">Issue: Communications are still allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="f958c-118">在這種情況下, 雖然資訊屏障已定義、使用中且已套用, 但是應該防止相互通訊的人員仍然可以在 Microsoft 小組中進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f958c-118">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other still can in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f958c-119">待辦事項</span><span class="sxs-lookup"><span data-stu-id="f958c-119">What to do</span></span>

<span data-ttu-id="f958c-120">確認有問題的使用者包含在資訊屏障原則中。</span><span class="sxs-lookup"><span data-stu-id="f958c-120">Verify that the users in question are included in an information barrier policy.</span></span> <span data-ttu-id="f958c-121">使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="f958c-121">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

<span data-ttu-id="f958c-122">句法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="f958c-122">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 

<span data-ttu-id="f958c-123">您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f958c-123">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 

<span data-ttu-id="f958c-124">範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="f958c-124">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 

<span data-ttu-id="f958c-125">在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="f958c-125">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 

<span data-ttu-id="f958c-126">(您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`) 此 Cmdlet 會傳回使用者的相關資訊, 例如屬性值以及所套用的任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f958c-126">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`) This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>


|<span data-ttu-id="f958c-127">結果</span><span class="sxs-lookup"><span data-stu-id="f958c-127">Results</span></span>  |<span data-ttu-id="f958c-128">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f958c-128">Next steps</span></span>  |
|---------|---------|
|<span data-ttu-id="f958c-129">沒有列出所選使用者的區段</span><span class="sxs-lookup"><span data-stu-id="f958c-129">No segments are listed for the selected user(s)</span></span>     |<span data-ttu-id="f958c-130">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f958c-130">Do one of the following:</span></span><br/><span data-ttu-id="f958c-131">-在 Azure Active Directory 中編輯使用者設定檔, 以將使用者指派至現有的區段</span><span class="sxs-lookup"><span data-stu-id="f958c-131">- Assign users to an existing segment by editing their user profiles in Azure Active Directory</span></span><br/><span data-ttu-id="f958c-132">-使用[支援的資訊障礙屬性來](information-barriers-attributes.md)定義區段</span><span class="sxs-lookup"><span data-stu-id="f958c-132">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md)</span></span>         |
|<span data-ttu-id="f958c-133">會列出區段, 但不會將資訊屏障原則指派給這些區段</span><span class="sxs-lookup"><span data-stu-id="f958c-133">Segments are listed but no information barrier policies are assigned to those segments</span></span>     |<span data-ttu-id="f958c-134">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f958c-134">Do one of the following:</span></span><br/><span data-ttu-id="f958c-135">- 為問題的每個區段[定義資訊障礙原則](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="f958c-135">- [Define an information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span><br/><span data-ttu-id="f958c-136">- [編輯資訊障礙原則](information-barriers-policies.md#edit-a-policy), 並將其指派給正確的網段</span><span class="sxs-lookup"><span data-stu-id="f958c-136">- [Edit an information barrier policy](information-barriers-policies.md#edit-a-policy) and assign it to the correct segment</span></span>         |
|<span data-ttu-id="f958c-137">列出區段, 每個區段都包含在資訊屏障原則中</span><span class="sxs-lookup"><span data-stu-id="f958c-137">Segments are listed and each is included in an information barrier policy</span></span>     |<span data-ttu-id="f958c-138">-執行`Get-InformationBarrierPolicy` Cmdlet 以確認資訊屏障原則已啟用</span><span class="sxs-lookup"><span data-stu-id="f958c-138">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="f958c-139">-執行`Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 以確認原則已套用</span><span class="sxs-lookup"><span data-stu-id="f958c-139">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="f958c-140">-執行`Start-InformationBarrierPoliciesApplication` Cmdlet 以套用所有使用中的資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="f958c-140">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span>          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="f958c-141">問題: Microsoft 小組中意外封鎖人員進行通訊</span><span class="sxs-lookup"><span data-stu-id="f958c-141">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="f958c-142">在這種情況下, 人員會報告在 Microsoft 小組中進行通訊的意外問題。</span><span class="sxs-lookup"><span data-stu-id="f958c-142">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="f958c-143">範例:</span><span class="sxs-lookup"><span data-stu-id="f958c-143">Examples:</span></span>
- <span data-ttu-id="f958c-144">使用者無法找到或與 Microsoft 小組中的另一位使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="f958c-144">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="f958c-145">使用者無法在 Microsoft 小組中看到或選取另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="f958c-145">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="f958c-146">使用者可以看到另一位使用者, 但無法選取或傳送郵件給 Microsoft 小組中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="f958c-146">A user can see another user, but cannot select or send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f958c-147">待辦事項</span><span class="sxs-lookup"><span data-stu-id="f958c-147">What to do</span></span>

1. <span data-ttu-id="f958c-148">決定使用者是否受到資訊屏障原則的影響。</span><span class="sxs-lookup"><span data-stu-id="f958c-148">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="f958c-149">若要這麼做, 請使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="f958c-149">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="f958c-150">語法為`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="f958c-150">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="f958c-151">您可以使用唯一識別每個收件者的任何識別值, 例如名稱、別名、辨別名稱 (DN)、正常化 DN、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f958c-151">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="f958c-152">範例： `Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="f958c-152">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="f958c-153">在此範例中, 我們使用了 Identity 參數的別名 (*meganb*)。</span><span class="sxs-lookup"><span data-stu-id="f958c-153">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="f958c-154">此 Cmdlet 會傳回信息, 指出使用者是否受到資訊屏障原則的影響。</span><span class="sxs-lookup"><span data-stu-id="f958c-154">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="f958c-155">(請參閱 \* ExoPolicyId: \<GUID>。)</span><span class="sxs-lookup"><span data-stu-id="f958c-155">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="f958c-156">如果資訊屏障原則中未包含使用者, 請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="f958c-156">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="f958c-157">否則，請繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="f958c-157">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="f958c-158">找出資訊屏障原則中所包含的區段。</span><span class="sxs-lookup"><span data-stu-id="f958c-158">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="f958c-159">若要這麼做, 請`Get-InformationBarrierPolicy`搭配 Identity 參數使用 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f958c-159">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="f958c-160">使用詳細資料, 例如您在上一個步驟中收到的原則 GUID (ExoPolicyId) 做為 identity 值。</span><span class="sxs-lookup"><span data-stu-id="f958c-160">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="f958c-161">範例： `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="f958c-161">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="f958c-162">在此範例中, 我們將取得有關 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*的資訊屏障原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f958c-162">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="f958c-163">執行 Cmdlet 之後, 請在 [結果] 中, 尋找**AssignedSegment**、 **SegmentsAllowed**及**SegmentsBlocked**值。</span><span class="sxs-lookup"><span data-stu-id="f958c-163">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="f958c-164">範例: 執行`Get-InformationBarrierPolicy` Cmdlet 之後, 我們在結果清單中看到下列內容:</span><span class="sxs-lookup"><span data-stu-id="f958c-164">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="f958c-165">在這種情況下, 我們可以看到資訊障礙原則會影響銷售和研究資料段中的人員。</span><span class="sxs-lookup"><span data-stu-id="f958c-165">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="f958c-166">在這種情況下, 銷售人員會無法與「調查」中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f958c-166">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="f958c-167">如果看起來正確, 則資訊壁壘會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="f958c-167">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="f958c-168">如果不是, 請繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="f958c-168">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="f958c-169">請確定已正確定義您的區段。</span><span class="sxs-lookup"><span data-stu-id="f958c-169">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="f958c-170">若要這麼做, 請`Get-OrganizationSegment`使用 Cmdlet, 並查看結果清單。</span><span class="sxs-lookup"><span data-stu-id="f958c-170">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="f958c-171">若要查看特定區段的詳細資料, 請`Get-OrganizationSegment`使用 Cmdlet 搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="f958c-171">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="f958c-172">範例： `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="f958c-172">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="f958c-173">在此範例中, 我們會取得 GUID 為*c96e0837-c232-4a8a-841e-ef45787d8fcd*之區段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f958c-173">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="f958c-174">查看區段的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f958c-174">Review the details for the segment.</span></span> <span data-ttu-id="f958c-175">如有必要, 請[編輯區段](information-barriers-policies.md#edit-a-segment), 然後重新使用`Start-InformationBarrierPoliciesApplication` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f958c-175">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="f958c-176">如果您仍然遇到資訊屏障原則的問題, 請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="f958c-176">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="f958c-177">問題: 資訊屏障應用程式花費的時間太長</span><span class="sxs-lookup"><span data-stu-id="f958c-177">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="f958c-178">執行**InformationBarrierPoliciesApplication** Cmdlet 之後, 程式會花很長的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="f958c-178">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f958c-179">待辦事項</span><span class="sxs-lookup"><span data-stu-id="f958c-179">What to do</span></span>

<span data-ttu-id="f958c-180">請記住, 當您執行原則應用程式 Cmdlet 時, 系統會為組織中的所有帳戶套用 (或移除) 資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f958c-180">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="f958c-181">如果您有許多使用者, 將需要一段時間進行處理。</span><span class="sxs-lookup"><span data-stu-id="f958c-181">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="f958c-182">(一般來說, 處理5000使用者帳戶需要大約一小時的時間。)</span><span class="sxs-lookup"><span data-stu-id="f958c-182">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="f958c-183">使用**InformationBarrierPoliciesApplicationStatus**指令程式來確認最近原則應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="f958c-183">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    <span data-ttu-id="f958c-184">句法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="f958c-184">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="f958c-185">(若要顯示*所有*資訊屏障原則應用程式的狀態, 請使用此 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f958c-185">(To display status for *all* information barrier policy applications, use this cmdlet:</span></span><br/>
    <span data-ttu-id="f958c-186">`Get-InformationBarrierPoliciesApplicationStatus -All $true`)</span><span class="sxs-lookup"><span data-stu-id="f958c-186"></span></span>

    <span data-ttu-id="f958c-187">這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。</span><span class="sxs-lookup"><span data-stu-id="f958c-187">This will display information about whether policy application completed, failed, or is in progress..</span></span>

2. <span data-ttu-id="f958c-188">根據上一個步驟的結果, 執行下列其中一個步驟:</span><span class="sxs-lookup"><span data-stu-id="f958c-188">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="f958c-189">狀態</span><span class="sxs-lookup"><span data-stu-id="f958c-189">Status</span></span>  |<span data-ttu-id="f958c-190">下一步</span><span class="sxs-lookup"><span data-stu-id="f958c-190">Next step</span></span>  |
    |---------|---------|
    |<span data-ttu-id="f958c-191">**尚未啟動**</span><span class="sxs-lookup"><span data-stu-id="f958c-191">**Not started**</span></span>     |<span data-ttu-id="f958c-192">如果在執行**InformationBarrierPoliciesApplication**指令程式後已超過45分鐘, 請檢查您的 audit 記錄檔, 以查看原則定義中是否有任何錯誤, 或應用程式尚未啟動的其他原因。</span><span class="sxs-lookup"><span data-stu-id="f958c-192">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    |<span data-ttu-id="f958c-193">**失敗**</span><span class="sxs-lookup"><span data-stu-id="f958c-193">**Failed**</span></span>     |<span data-ttu-id="f958c-194">如果應用程式失敗, 請檢查您的審核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="f958c-194">If the application has failed, review your audit log.</span></span> <span data-ttu-id="f958c-195">此外, 請參閱您的部門和原則。</span><span class="sxs-lookup"><span data-stu-id="f958c-195">Also review your segments and policies.</span></span> <span data-ttu-id="f958c-196">是否有任何使用者被指派至多個區段？</span><span class="sxs-lookup"><span data-stu-id="f958c-196">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="f958c-197">是否有任何區段被指派一個以上的 poliicy？</span><span class="sxs-lookup"><span data-stu-id="f958c-197">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="f958c-198">如有必要, 請[編輯區段](information-barriers-policies.md#edit-a-segment)和 (或)[編輯原則](information-barriers-policies.md#edit-a-policy), 然後再次執行**InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f958c-198">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>  |
    |<span data-ttu-id="f958c-199">**進行中。**</span><span class="sxs-lookup"><span data-stu-id="f958c-199">**In progress**</span></span>     |<span data-ttu-id="f958c-200">如果應用程式仍在進行中, 則允許更多時間完成。</span><span class="sxs-lookup"><span data-stu-id="f958c-200">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="f958c-201">如果有數天, 請收集您的審查記錄檔, 然後與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="f958c-201">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f958c-202">相關主題</span><span class="sxs-lookup"><span data-stu-id="f958c-202">Related topics</span></span>

[<span data-ttu-id="f958c-203">定義 Microsoft 團隊中資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f958c-203">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="f958c-204">資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f958c-204">Information barriers (Preview)</span></span>](information-barriers.md)



