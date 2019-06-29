---
title: 資訊屏障原則的屬性
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
description: 請使用本文做為資訊屏障原則中可使用的各種屬性參考。
ms.openlocfilehash: 896b87a3ccc696d3a8193e37237fe555d326ca52
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394308"
---
# <a name="attributes-for-information-barrier-policies-preview"></a><span data-ttu-id="b0832-103">資訊障礙原則的屬性 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-103">Attributes for information barrier policies (Preview)</span></span>

<span data-ttu-id="b0832-104">Azure Active Directory 中的某些屬性可以用來分割使用者。</span><span class="sxs-lookup"><span data-stu-id="b0832-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="b0832-105">一旦定義區段後, 這些區段就可以做為資訊屏障原則的篩選器。</span><span class="sxs-lookup"><span data-stu-id="b0832-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="b0832-106">例如, 您可能會使用**部門**, 依組織中的部門定義使用者區段 (假設沒有單一員工同時對兩個部門運作)。</span><span class="sxs-lookup"><span data-stu-id="b0832-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="b0832-107">本文說明如何將屬性與資訊障礙搭配使用, 並提供可使用的屬性清單。</span><span class="sxs-lookup"><span data-stu-id="b0832-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="b0832-108">若要深入瞭解資訊障礙, 請參閱下列資源:</span><span class="sxs-lookup"><span data-stu-id="b0832-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="b0832-109">資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-109">Information barriers (Preview)</span></span>](information-barriers.md)
- [<span data-ttu-id="b0832-110">定義 Microsoft 團隊中資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-110">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="b0832-111">編輯 (或移除) 資訊屏障原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-111">Edit (or remove) information barrier policies (Preview)</span></span>](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="b0832-112">如何使用資訊屏障原則中的屬性</span><span class="sxs-lookup"><span data-stu-id="b0832-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="b0832-113">本文所列的屬性可用於定義或編輯使用者的區段。</span><span class="sxs-lookup"><span data-stu-id="b0832-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="b0832-114">在[資訊屏障原則](information-barriers-policies.md)中, 您定義的區段會做為參數 (稱為*UserGroupFilter*值)。</span><span class="sxs-lookup"><span data-stu-id="b0832-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="b0832-115">決定要用來定義區段的屬性。</span><span class="sxs-lookup"><span data-stu-id="b0832-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="b0832-116">(請參閱本文中的[參考](#reference)一節)。</span><span class="sxs-lookup"><span data-stu-id="b0832-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="b0832-117">請確定使用者帳戶的值已填入您在步驟1中選取的屬性。</span><span class="sxs-lookup"><span data-stu-id="b0832-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="b0832-118">查看使用者帳戶詳細資料, 如有必要, 編輯使用者帳戶以包含屬性值。</span><span class="sxs-lookup"><span data-stu-id="b0832-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    <span data-ttu-id="b0832-119">若要使用 PowerShell 來執行這項操作, 請參閱使用[Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b0832-119">To do this using PowerShell, see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

    <span data-ttu-id="b0832-120">若要在 Azure Active Directory 中執行此作業, 請參閱[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="b0832-120">To do this in Azure Active Directory, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="b0832-121">[使用 PowerShell 定義區段](information-barriers-policies.md#define-segments-using-powershell), 類似下列範例:</span><span class="sxs-lookup"><span data-stu-id="b0832-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="b0832-122">範例</span><span class="sxs-lookup"><span data-stu-id="b0832-122">Example</span></span>  |<span data-ttu-id="b0832-123">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0832-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="b0832-124">使用部門屬性定義稱為 Segment1 的區段</span><span class="sxs-lookup"><span data-stu-id="b0832-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="b0832-125">使用 MemberOf 屬性定義稱為 SegmentA 的區段 (假設此屬性包含組名, 例如 "BlueGroup")</span><span class="sxs-lookup"><span data-stu-id="b0832-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="b0832-126">使用 ExtensionAttribute1 定義稱為 DayTraders 的區段 (假設此屬性包含職稱, 例如 "DayTrader")</span><span class="sxs-lookup"><span data-stu-id="b0832-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="b0832-127">當您定義線段時, 請對您的所有區段使用相同的屬性。</span><span class="sxs-lookup"><span data-stu-id="b0832-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="b0832-128">例如, 如果您使用*部門*來定義某些區段, 請使用*部門*定義所有的區段。</span><span class="sxs-lookup"><span data-stu-id="b0832-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="b0832-129">請勿使用*部門*和其他使用*MemberOf*的其他區段來定義。</span><span class="sxs-lookup"><span data-stu-id="b0832-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="b0832-130">請確定您的區段沒有重迭;每個使用者都應該指派給一個區段。</span><span class="sxs-lookup"><span data-stu-id="b0832-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="b0832-131">參考</span><span class="sxs-lookup"><span data-stu-id="b0832-131">Reference</span></span>

<span data-ttu-id="b0832-132">下表列出您可以與資訊障礙搭配使用的屬性。</span><span class="sxs-lookup"><span data-stu-id="b0832-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="b0832-133">Azure Active Directory 屬性名稱 (LDAP 顯示名稱)</span><span class="sxs-lookup"><span data-stu-id="b0832-133">Azure Active Directory property name (LDAP display name)</span></span>  |<span data-ttu-id="b0832-134">Exchange 屬性名稱</span><span class="sxs-lookup"><span data-stu-id="b0832-134">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="b0832-135">合作者</span><span class="sxs-lookup"><span data-stu-id="b0832-135">Co</span></span>       | <span data-ttu-id="b0832-136">合作者</span><span class="sxs-lookup"><span data-stu-id="b0832-136">Co</span></span>        |
|<span data-ttu-id="b0832-137">Company</span><span class="sxs-lookup"><span data-stu-id="b0832-137">Company</span></span>     |<span data-ttu-id="b0832-138">Company</span><span class="sxs-lookup"><span data-stu-id="b0832-138">Company</span></span>         |
|<span data-ttu-id="b0832-139">部門</span><span class="sxs-lookup"><span data-stu-id="b0832-139">Department</span></span>     |<span data-ttu-id="b0832-140">部門</span><span class="sxs-lookup"><span data-stu-id="b0832-140">Department</span></span>         |
|<span data-ttu-id="b0832-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="b0832-141">ExtensionAttribute1</span></span> |<span data-ttu-id="b0832-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="b0832-142">CustomAttribute1</span></span>  |
|<span data-ttu-id="b0832-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="b0832-143">ExtensionAttribute2</span></span> |<span data-ttu-id="b0832-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="b0832-144">CustomAttribute2</span></span>  |
|<span data-ttu-id="b0832-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="b0832-145">ExtensionAttribute3</span></span> |<span data-ttu-id="b0832-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="b0832-146">CustomAttribute3</span></span>  |
|<span data-ttu-id="b0832-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="b0832-147">ExtensionAttribute4</span></span> |<span data-ttu-id="b0832-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="b0832-148">CustomAttribute4</span></span>  |
|<span data-ttu-id="b0832-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="b0832-149">ExtensionAttribute5</span></span> |<span data-ttu-id="b0832-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="b0832-150">CustomAttribute5</span></span>  |
|<span data-ttu-id="b0832-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="b0832-151">ExtensionAttribute6</span></span> |<span data-ttu-id="b0832-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="b0832-152">CustomAttribute6</span></span>  |
|<span data-ttu-id="b0832-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="b0832-153">ExtensionAttribute7</span></span> |<span data-ttu-id="b0832-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="b0832-154">CustomAttribute7</span></span>  |
|<span data-ttu-id="b0832-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="b0832-155">ExtensionAttribute8</span></span> |<span data-ttu-id="b0832-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="b0832-156">CustomAttribute8</span></span>  |
|<span data-ttu-id="b0832-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="b0832-157">ExtensionAttribute9</span></span> |<span data-ttu-id="b0832-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="b0832-158">CustomAttribute9</span></span>  |
|<span data-ttu-id="b0832-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="b0832-159">ExtensionAttribute10</span></span> |<span data-ttu-id="b0832-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="b0832-160">CustomAttribute10</span></span>  |
|<span data-ttu-id="b0832-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="b0832-161">ExtensionAttribute11</span></span> |<span data-ttu-id="b0832-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="b0832-162">CustomAttribute11</span></span>  |
|<span data-ttu-id="b0832-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="b0832-163">ExtensionAttribute12</span></span> |<span data-ttu-id="b0832-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="b0832-164">CustomAttribute12</span></span>  |
|<span data-ttu-id="b0832-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="b0832-165">ExtensionAttribute13</span></span> |<span data-ttu-id="b0832-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="b0832-166">CustomAttribute13</span></span>  |
|<span data-ttu-id="b0832-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="b0832-167">ExtensionAttribute14</span></span> |<span data-ttu-id="b0832-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="b0832-168">CustomAttribute14</span></span>  |
|<span data-ttu-id="b0832-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="b0832-169">ExtensionAttribute15</span></span> |<span data-ttu-id="b0832-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="b0832-170">CustomAttribute15</span></span>  |
|<span data-ttu-id="b0832-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="b0832-171">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="b0832-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="b0832-172">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="b0832-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="b0832-173">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="b0832-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="b0832-174">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="b0832-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="b0832-175">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="b0832-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="b0832-176">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="b0832-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="b0832-177">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="b0832-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="b0832-178">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="b0832-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="b0832-179">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="b0832-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="b0832-180">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="b0832-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="b0832-181">MailNickname</span></span> |<span data-ttu-id="b0832-182">別名</span><span class="sxs-lookup"><span data-stu-id="b0832-182">Alias</span></span> |
|<span data-ttu-id="b0832-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="b0832-183">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="b0832-184">Office</span><span class="sxs-lookup"><span data-stu-id="b0832-184">Office</span></span> |
|<span data-ttu-id="b0832-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="b0832-185">PostalCode</span></span> |<span data-ttu-id="b0832-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="b0832-186">PostalCode</span></span> |
|<span data-ttu-id="b0832-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b0832-187">ProxyAddresses</span></span> |<span data-ttu-id="b0832-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="b0832-188">EmailAddresses</span></span> |
|<span data-ttu-id="b0832-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="b0832-189">StreetAddress</span></span> |<span data-ttu-id="b0832-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="b0832-190">StreetAddress</span></span> |
|<span data-ttu-id="b0832-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="b0832-191">TargetAddress</span></span> |<span data-ttu-id="b0832-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="b0832-192">ExternalEmailAddress</span></span> |
|<span data-ttu-id="b0832-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="b0832-193">UsageLocation</span></span> |<span data-ttu-id="b0832-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="b0832-194">UsageLocation</span></span> |
|<span data-ttu-id="b0832-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b0832-195">UserPrincipalName</span></span>  |<span data-ttu-id="b0832-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b0832-196">UserPrincipalName</span></span>  |
|<span data-ttu-id="b0832-197">郵件</span><span class="sxs-lookup"><span data-stu-id="b0832-197">Mail</span></span>   |<span data-ttu-id="b0832-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="b0832-198">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="b0832-199">描述</span><span class="sxs-lookup"><span data-stu-id="b0832-199">Description</span></span>    |<span data-ttu-id="b0832-200">描述</span><span class="sxs-lookup"><span data-stu-id="b0832-200">Description</span></span>    |
|<span data-ttu-id="b0832-201">屬於</span><span class="sxs-lookup"><span data-stu-id="b0832-201">MemberOf</span></span>   |<span data-ttu-id="b0832-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="b0832-202">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="b0832-203">相關主題</span><span class="sxs-lookup"><span data-stu-id="b0832-203">Related topics</span></span>

[<span data-ttu-id="b0832-204">定義 Microsoft 團隊中資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-204">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="b0832-205">疑難排解資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-205">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="b0832-206">資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="b0832-206">Information barriers (Preview)</span></span>](information-barriers.md)



