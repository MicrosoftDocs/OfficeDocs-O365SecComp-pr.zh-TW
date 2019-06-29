---
title: 編輯資訊屏障原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 瞭解如何編輯或移除資訊障礙的原則。
ms.openlocfilehash: c3dca18ad217b89d9f9ae78b590cfb07f4631f37
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394328"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a><span data-ttu-id="d4f08-103">編輯 (或移除) 資訊屏障原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="d4f08-103">Edit (or remove) information barrier policies (Preview)</span></span>

<span data-ttu-id="d4f08-104">[定義資訊屏障原則](information-barriers-policies.md)之後, 您可能需要變更這些原則或使用者區段, 做為[疑難排解](information-barriers-troubleshooting.md)或定期維護的一部分。</span><span class="sxs-lookup"><span data-stu-id="d4f08-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="d4f08-105">請使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="d4f08-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="d4f08-106">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="d4f08-106">What do you want to do?</span></span>

|<span data-ttu-id="d4f08-107">動作</span><span class="sxs-lookup"><span data-stu-id="d4f08-107">Action</span></span>  |<span data-ttu-id="d4f08-108">描述</span><span class="sxs-lookup"><span data-stu-id="d4f08-108">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="d4f08-109">編輯使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="d4f08-109">Edit user account attributes</span></span>](#edit-user-account-attributes)     |<span data-ttu-id="d4f08-110">在 Azure Active Directory 中填入可用於定義區段的屬性。</span><span class="sxs-lookup"><span data-stu-id="d4f08-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="d4f08-111">編輯使用者帳戶屬性如果使用者未包含在應該是的區段中, 請變更使用者所在的區段, 或使用不同的屬性來定義區段。</span><span class="sxs-lookup"><span data-stu-id="d4f08-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span>         |
|[<span data-ttu-id="d4f08-112">編輯區段</span><span class="sxs-lookup"><span data-stu-id="d4f08-112">Edit a segment</span></span>](#edit-a-segment)     |<span data-ttu-id="d4f08-113">當您想要變更區段的定義方式時, 請編輯區段。</span><span class="sxs-lookup"><span data-stu-id="d4f08-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="d4f08-114">例如, 您可能已經定義了使用*部門*的區段, 而且現在想要使用另一個屬性 (例如*MemberOf*)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span>         |
|[<span data-ttu-id="d4f08-115">編輯原則</span><span class="sxs-lookup"><span data-stu-id="d4f08-115">Edit a policy</span></span>](#edit-a-policy)     |<span data-ttu-id="d4f08-116">當您想要變更原則的運作方式時, 請編輯資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="d4f08-117">例如, 您可以決定只允許在特定的區段之間進行通訊, 而不是封鎖兩個網段之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="d4f08-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span>         |
|[<span data-ttu-id="d4f08-118">將原則設定為非使用中狀態</span><span class="sxs-lookup"><span data-stu-id="d4f08-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status)     |<span data-ttu-id="d4f08-119">當您想要變更原則, 或不想讓原則生效時, 請將原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="d4f08-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span>         |
|[<span data-ttu-id="d4f08-120">移除原則</span><span class="sxs-lookup"><span data-stu-id="d4f08-120">Remove a policy</span></span>](#remove-a-policy)     |<span data-ttu-id="d4f08-121">當您不再需要特定原則時, 移除資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span>         |
|[<span data-ttu-id="d4f08-122">停止原則應用程式</span><span class="sxs-lookup"><span data-stu-id="d4f08-122">Stop a policy application</span></span>](#stop-a-policy-application)     |<span data-ttu-id="d4f08-123">當您想要停止套用資訊屏障原則的程式時, 請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="d4f08-123">Do this when you want to stop the process of applying information barrier policies.</span></span><br/><span data-ttu-id="d4f08-124">請注意, 停止原則應用程式並不會立即執行, 而且也不會復原已套用至使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-124">Note that stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span>         |
|[<span data-ttu-id="d4f08-125">定義資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="d4f08-125">Define policies for information barriers (Preview)</span></span>](information-barriers-policies.md)     |<span data-ttu-id="d4f08-126">定義資訊屏障原則當您尚未就地使用這些原則時, 必須限制或限制特定使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="d4f08-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span>         |
|[<span data-ttu-id="d4f08-127">疑難排解資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="d4f08-127">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)     |<span data-ttu-id="d4f08-128">當您遇到資訊障礙的意外問題時, 請參閱本文。</span><span class="sxs-lookup"><span data-stu-id="d4f08-128">Refer to this article when you run into unexpected issues with information barriers.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="d4f08-129">若要執行本文所述的工作, 您必須被指派適當的角色, 例如下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="d4f08-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="d4f08-130">-Microsoft 365 企業通用系統管理員</span><span class="sxs-lookup"><span data-stu-id="d4f08-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="d4f08-131">-Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="d4f08-131">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="d4f08-132">-合規性管理員</span><span class="sxs-lookup"><span data-stu-id="d4f08-132">- Compliance Administrator</span></span><br/><span data-ttu-id="d4f08-133">-IB 規範管理 (這是新的角色!)</span><span class="sxs-lookup"><span data-stu-id="d4f08-133">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="d4f08-134">若要深入瞭解資訊障礙的必要條件, 請參閱[必要條件 (適用于資訊屏障原則)](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="d4f08-135">請務必連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-135">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="d4f08-136">編輯使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="d4f08-136">Edit user account attributes</span></span>

<span data-ttu-id="d4f08-137">使用此程式可編輯分割使用者所使用的屬性。</span><span class="sxs-lookup"><span data-stu-id="d4f08-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="d4f08-138">例如, 如果您使用的是部門屬性, 且有一或多個使用者帳戶目前未列出部門的任何值, 則必須編輯這些使用者帳戶, 以包含部門資訊。</span><span class="sxs-lookup"><span data-stu-id="d4f08-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="d4f08-139">使用者帳戶屬性可用來定義資料段, 以便指派資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="d4f08-140">若要查看特定使用者帳戶的詳細資料, 例如屬性值和指派的區段, 請使用 InformationBarrierRecipientStatus 指令**程式**搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="d4f08-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

    |<span data-ttu-id="d4f08-141">語法</span><span class="sxs-lookup"><span data-stu-id="d4f08-141">Syntax</span></span>  |<span data-ttu-id="d4f08-142">範例</span><span class="sxs-lookup"><span data-stu-id="d4f08-142">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   <span data-ttu-id="d4f08-143">您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="d4f08-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p>   <span data-ttu-id="d4f08-144">(您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="d4f08-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span>      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   <span data-ttu-id="d4f08-145">在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="d4f08-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>         |

2. <span data-ttu-id="d4f08-146">決定您要為使用者帳戶設定檔編輯的屬性。</span><span class="sxs-lookup"><span data-stu-id="d4f08-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="d4f08-147">如需詳細資訊, 請參閱[資訊障礙原則 (預覽) 的屬性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-147">Refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="d4f08-148">編輯一或多個使用者帳戶, 以包含您在上一個步驟中選取之屬性的值。</span><span class="sxs-lookup"><span data-stu-id="d4f08-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="d4f08-149">若要這麼做, 請使用下列其中一個程式:</span><span class="sxs-lookup"><span data-stu-id="d4f08-149">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="d4f08-150">若要編輯單一帳戶, 請參閱[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="d4f08-151">若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶), 請參閱使用[Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="d4f08-152">編輯區段</span><span class="sxs-lookup"><span data-stu-id="d4f08-152">Edit a segment</span></span>

<span data-ttu-id="d4f08-153">使用此程式編輯使用者區段的定義。</span><span class="sxs-lookup"><span data-stu-id="d4f08-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="d4f08-154">例如, 您可能會變更某段的名稱, 或用來判斷該區段中所包含之人員的篩選。</span><span class="sxs-lookup"><span data-stu-id="d4f08-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="d4f08-155">若要查看所有現有的區段, 請使用**OrganizationSegment 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="d4f08-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="d4f08-156">句法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="d4f08-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="d4f08-157">您會看到每個區段和詳細資料的清單, 例如區段類型、其 UserGroupFilter 值、建立日期或上次修改者、GUID 等等。</span><span class="sxs-lookup"><span data-stu-id="d4f08-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="d4f08-158">列印或儲存您的區段清單供日後參考。</span><span class="sxs-lookup"><span data-stu-id="d4f08-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="d4f08-159">例如, 如果您想要編輯某個區段, 您將需要知道其名稱或識別值 (這會與 Identity 參數搭配使用)。</span><span class="sxs-lookup"><span data-stu-id="d4f08-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="d4f08-160">若要編輯區段, 請使用**OrganizationSegment 指令程式**搭配**Identity**參數及相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d4f08-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    |<span data-ttu-id="d4f08-161">語法</span><span class="sxs-lookup"><span data-stu-id="d4f08-161">Syntax</span></span>  |<span data-ttu-id="d4f08-162">範例</span><span class="sxs-lookup"><span data-stu-id="d4f08-162">Example</span></span>  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p><span data-ttu-id="d4f08-163">在此範例中, 針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的區段, 我們會將部門名稱更新為 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="d4f08-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>         |

<span data-ttu-id="d4f08-164">當您完成組織的資料段編輯時, 您可以[定義](information-barriers-policies.md#part-2-define-information-barrier-policies)或[編輯](#edit-a-policy)資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="d4f08-165">編輯原則</span><span class="sxs-lookup"><span data-stu-id="d4f08-165">Edit a policy</span></span>

1. <span data-ttu-id="d4f08-166">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="d4f08-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="d4f08-167">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="d4f08-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="d4f08-168">在結果清單中, 識別您要變更的原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="d4f08-169">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="d4f08-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="d4f08-170">使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並指定您想要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="d4f08-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="d4f08-171">範例: 假設已定義原則來封鎖*研究*資料段與*銷售*和*行銷*資料段的通訊。</span><span class="sxs-lookup"><span data-stu-id="d4f08-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="d4f08-172">原則是使用此 Cmdlet 定義的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="d4f08-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="d4f08-173">假設我們想要變更它, 讓*研究*部門中的人員只能與*HR*區段中的人通訊。</span><span class="sxs-lookup"><span data-stu-id="d4f08-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="d4f08-174">若要進行這種變更, 我們會使用此 Cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="d4f08-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="d4f08-175">在此範例中, 我們將 "SegmentsBlocked" 變更為 "SegmentsAllowed", 並指定*HR*區段。</span><span class="sxs-lookup"><span data-stu-id="d4f08-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="d4f08-176">當您完成編輯原則時, 請務必套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="d4f08-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="d4f08-177">(請參閱套用[資訊屏障原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="d4f08-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="d4f08-178">將原則設定為非使用中狀態</span><span class="sxs-lookup"><span data-stu-id="d4f08-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="d4f08-179">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="d4f08-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="d4f08-180">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="d4f08-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="d4f08-181">在結果清單中, 識別您要變更 (或移除) 的原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="d4f08-182">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="d4f08-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="d4f08-183">若要將原則的狀態設定為非使用中, 請使用**InformationBarrierPolicy**指令程式搭配 Identity 參數, 並將 State 參數設為非使用中。</span><span class="sxs-lookup"><span data-stu-id="d4f08-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="d4f08-184">語法</span><span class="sxs-lookup"><span data-stu-id="d4f08-184">Syntax</span></span>  |<span data-ttu-id="d4f08-185">範例</span><span class="sxs-lookup"><span data-stu-id="d4f08-185">Example</span></span>  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p><span data-ttu-id="d4f08-186">在此範例中, 我們將*43c37853-ea10-4b90-a23d-ab8c9377247*的資訊屏障原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="d4f08-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>         |

3. <span data-ttu-id="d4f08-187">若要套用您的變更, 請使用**InformationBarrierPoliciesApplication 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="d4f08-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="d4f08-188">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="d4f08-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="d4f08-189">針對您的組織, 會套用使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="d4f08-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="d4f08-190">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="d4f08-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="d4f08-191">(一般來說, 處理5000使用者帳戶需要大約一小時的時間。)</span><span class="sxs-lookup"><span data-stu-id="d4f08-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="d4f08-192">此時, 一或多個資訊屏障原則會設為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="d4f08-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="d4f08-193">從這裡, 您可以執行下列任何一項操作:</span><span class="sxs-lookup"><span data-stu-id="d4f08-193">From here, you can do any of the following:</span></span>
- <span data-ttu-id="d4f08-194">保留原樣 (原則設定為非作用中的狀態對使用者不會有任何影響)</span><span class="sxs-lookup"><span data-stu-id="d4f08-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="d4f08-195">編輯原則</span><span class="sxs-lookup"><span data-stu-id="d4f08-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="d4f08-196">移除原則</span><span class="sxs-lookup"><span data-stu-id="d4f08-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="d4f08-197">移除原則</span><span class="sxs-lookup"><span data-stu-id="d4f08-197">Remove a policy</span></span>

1. <span data-ttu-id="d4f08-198">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="d4f08-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="d4f08-199">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="d4f08-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="d4f08-200">在結果清單中, 識別您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="d4f08-201">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="d4f08-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="d4f08-202">請確定原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="d4f08-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="d4f08-203">使用**InformationBarrierPolicy**指令程式搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="d4f08-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="d4f08-204">語法</span><span class="sxs-lookup"><span data-stu-id="d4f08-204">Syntax</span></span>  |<span data-ttu-id="d4f08-205">範例</span><span class="sxs-lookup"><span data-stu-id="d4f08-205">Example</span></span>  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p><span data-ttu-id="d4f08-206">在此範例中, 我們將移除 GUID 為*43c37853-ea10-4b90-a23d-ab8c93772471*的原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span>          |

    <span data-ttu-id="d4f08-207">出現提示時, 請確認變更。</span><span class="sxs-lookup"><span data-stu-id="d4f08-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="d4f08-208">針對您要移除的每個原則, 重複步驟1-2。</span><span class="sxs-lookup"><span data-stu-id="d4f08-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="d4f08-209">當您完成移除原則時, 請套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="d4f08-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="d4f08-210">若要這麼做, 請使用**InformationBarrierPoliciesApplication 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="d4f08-210">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="d4f08-211">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="d4f08-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="d4f08-212">針對您的組織, 會套用使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="d4f08-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="d4f08-213">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="d4f08-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="d4f08-214">停止原則應用程式</span><span class="sxs-lookup"><span data-stu-id="d4f08-214">Stop a policy application</span></span>

<span data-ttu-id="d4f08-215">如果您已開始套用資訊屏障原則, 而您想要停止套用這些原則, 請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="d4f08-215">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="d4f08-216">請記住, 此程式會花大約30-35 分鐘的時間來開始。</span><span class="sxs-lookup"><span data-stu-id="d4f08-216">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="d4f08-217">若要查看最新資訊屏障原則應用程式的狀態, 請使用**InformationBarrierPoliciesApplicationStatus**指令程式。</span><span class="sxs-lookup"><span data-stu-id="d4f08-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="d4f08-218">句法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="d4f08-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="d4f08-219">記下應用程式的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d4f08-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="d4f08-220">使用**InformationBarrierPoliciesApplication**指令程式搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="d4f08-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="d4f08-221">語法</span><span class="sxs-lookup"><span data-stu-id="d4f08-221">Syntax</span></span>  |<span data-ttu-id="d4f08-222">範例</span><span class="sxs-lookup"><span data-stu-id="d4f08-222">Example</span></span>  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p><span data-ttu-id="d4f08-223">在此範例中, 我們將停止套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="d4f08-223">In this example, we are stopping information barrier policies from being applied.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="d4f08-224">相關文章</span><span class="sxs-lookup"><span data-stu-id="d4f08-224">Related articles</span></span>

[<span data-ttu-id="d4f08-225">取得資訊障礙的概況</span><span class="sxs-lookup"><span data-stu-id="d4f08-225">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="d4f08-226">定義資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="d4f08-226">Define policies for information barriers (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="d4f08-227">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="d4f08-227">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="d4f08-228">資訊障礙原則的屬性 (預覽)</span><span class="sxs-lookup"><span data-stu-id="d4f08-228">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="d4f08-229">疑難排解資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="d4f08-229">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
