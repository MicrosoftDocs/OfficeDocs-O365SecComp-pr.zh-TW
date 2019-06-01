---
title: 針對資訊障礙原則屬性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 用做參考的這篇文章，您可以使用資訊障礙原則中的各種屬性。
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668288"
---
# <a name="attributes-for-information-barrier-policies-preview"></a><span data-ttu-id="7b5bd-103">資訊障礙原則 （預覽） 的屬性</span><span class="sxs-lookup"><span data-stu-id="7b5bd-103">Attributes for information barrier policies (Preview)</span></span>

<span data-ttu-id="7b5bd-104">Azure Active Directory 中的某些屬性可以用於將使用者分。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="7b5bd-105">線段然後作為篩選資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-105">Segments are then used as filters for information barrier policies.</span></span> <span data-ttu-id="7b5bd-106">例如，您可以使用**部門**部門所定義的使用者區段 （在同一時間假設兩個部門的任何單一員工 works） 組織內。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="7b5bd-107">本文提供可用的屬性的清單。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-107">This article provides a list of attributes that can be used.</span></span> <span data-ttu-id="7b5bd-108">若要深入了解資訊障礙，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7b5bd-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="7b5bd-109">資訊障礙 （預覽）</span><span class="sxs-lookup"><span data-stu-id="7b5bd-109">Information barriers (Preview)</span></span>](information-barriers.md)
- [<span data-ttu-id="7b5bd-110">在 Microsoft Teams （預覽） 中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="7b5bd-110">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="7b5bd-111">如何在資訊障礙原則中使用屬性</span><span class="sxs-lookup"><span data-stu-id="7b5bd-111">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="7b5bd-112">本文中所列的屬性可用來定義 （或編輯） 的使用者區段。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-112">The attributes listed in this article can be used to define (or edit) segments of users.</span></span> <span data-ttu-id="7b5bd-113">區段做為參數 (UserGroupFilter) 中的資訊障礙原則，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="7b5bd-113">Segments are used as parameters (UserGroupFilter) in information barrier policies, as shown in the following examples:</span></span>

|<span data-ttu-id="7b5bd-114">範例</span><span class="sxs-lookup"><span data-stu-id="7b5bd-114">Example</span></span>  |<span data-ttu-id="7b5bd-115">指令程式</span><span class="sxs-lookup"><span data-stu-id="7b5bd-115">Cmdlet</span></span>  |
|---------|---------|
|<span data-ttu-id="7b5bd-116">定義稱為 Segment1 線段使用的部門屬性</span><span class="sxs-lookup"><span data-stu-id="7b5bd-116">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|<span data-ttu-id="7b5bd-117">定義線段，稱為 SegmentA （假設此屬性包含群組名稱，例如 「 BlueGroup 」），使用 MemberOf 屬性</span><span class="sxs-lookup"><span data-stu-id="7b5bd-117">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|<span data-ttu-id="7b5bd-118">定義線段，稱為 DayTraders 使用 ExtensionAttribute1 （假設此屬性包含工作標題，例如 「 DayTrader 」）</span><span class="sxs-lookup"><span data-stu-id="7b5bd-118">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

<span data-ttu-id="7b5bd-119">當您定義的區段時，使用您的所有區段相同的屬性。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-119">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="7b5bd-120">例如，如果您定義使用*部門*一些區段，定義所有使用*部門*的線段。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-120">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="7b5bd-121">未定義使用*部門*和其他人使用*MemberOf*一些區段。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-121">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="7b5bd-122">請確定您的區段不會重疊;每位使用者應該指派給一個區段。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-122">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

<span data-ttu-id="7b5bd-123">若要深入了解，請參閱[使用 PowerShell 的定義區段](information-barriers-policies.md#define-segments-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-123">To learn more, see [Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell).</span></span>

## <a name="reference"></a><span data-ttu-id="7b5bd-124">參考</span><span class="sxs-lookup"><span data-stu-id="7b5bd-124">Reference</span></span>

<span data-ttu-id="7b5bd-125">下表列出您可以使用資訊障礙的屬性。</span><span class="sxs-lookup"><span data-stu-id="7b5bd-125">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="7b5bd-126">Azure Active Directory 屬性名稱 （LDAP 顯示名稱）</span><span class="sxs-lookup"><span data-stu-id="7b5bd-126">Azure Active Directory property name (LDAP display name)</span></span>  |<span data-ttu-id="7b5bd-127">Exchange 屬性名稱</span><span class="sxs-lookup"><span data-stu-id="7b5bd-127">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="7b5bd-128">共同撰寫</span><span class="sxs-lookup"><span data-stu-id="7b5bd-128">Co</span></span>       | <span data-ttu-id="7b5bd-129">共同撰寫</span><span class="sxs-lookup"><span data-stu-id="7b5bd-129">Co</span></span>        |
|<span data-ttu-id="7b5bd-130">Company</span><span class="sxs-lookup"><span data-stu-id="7b5bd-130">Company</span></span>     |<span data-ttu-id="7b5bd-131">Company</span><span class="sxs-lookup"><span data-stu-id="7b5bd-131">Company</span></span>         |
|<span data-ttu-id="7b5bd-132">部門</span><span class="sxs-lookup"><span data-stu-id="7b5bd-132">Department</span></span>     |<span data-ttu-id="7b5bd-133">部門</span><span class="sxs-lookup"><span data-stu-id="7b5bd-133">Department</span></span>         |
|<span data-ttu-id="7b5bd-134">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="7b5bd-134">ExtensionAttribute1</span></span> |<span data-ttu-id="7b5bd-135">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7b5bd-135">CustomAttribute1</span></span>  |
|<span data-ttu-id="7b5bd-136">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="7b5bd-136">ExtensionAttribute2</span></span> |<span data-ttu-id="7b5bd-137">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7b5bd-137">CustomAttribute2</span></span>  |
|<span data-ttu-id="7b5bd-138">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="7b5bd-138">ExtensionAttribute3</span></span> |<span data-ttu-id="7b5bd-139">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7b5bd-139">CustomAttribute3</span></span>  |
|<span data-ttu-id="7b5bd-140">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="7b5bd-140">ExtensionAttribute4</span></span> |<span data-ttu-id="7b5bd-141">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7b5bd-141">CustomAttribute4</span></span>  |
|<span data-ttu-id="7b5bd-142">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="7b5bd-142">ExtensionAttribute5</span></span> |<span data-ttu-id="7b5bd-143">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7b5bd-143">CustomAttribute5</span></span>  |
|<span data-ttu-id="7b5bd-144">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="7b5bd-144">ExtensionAttribute6</span></span> |<span data-ttu-id="7b5bd-145">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="7b5bd-145">CustomAttribute6</span></span>  |
|<span data-ttu-id="7b5bd-146">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="7b5bd-146">ExtensionAttribute7</span></span> |<span data-ttu-id="7b5bd-147">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="7b5bd-147">CustomAttribute7</span></span>  |
|<span data-ttu-id="7b5bd-148">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="7b5bd-148">ExtensionAttribute8</span></span> |<span data-ttu-id="7b5bd-149">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="7b5bd-149">CustomAttribute8</span></span>  |
|<span data-ttu-id="7b5bd-150">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="7b5bd-150">ExtensionAttribute9</span></span> |<span data-ttu-id="7b5bd-151">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="7b5bd-151">CustomAttribute9</span></span>  |
|<span data-ttu-id="7b5bd-152">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="7b5bd-152">ExtensionAttribute10</span></span> |<span data-ttu-id="7b5bd-153">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="7b5bd-153">CustomAttribute10</span></span>  |
|<span data-ttu-id="7b5bd-154">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="7b5bd-154">ExtensionAttribute11</span></span> |<span data-ttu-id="7b5bd-155">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="7b5bd-155">CustomAttribute11</span></span>  |
|<span data-ttu-id="7b5bd-156">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="7b5bd-156">ExtensionAttribute12</span></span> |<span data-ttu-id="7b5bd-157">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="7b5bd-157">CustomAttribute12</span></span>  |
|<span data-ttu-id="7b5bd-158">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="7b5bd-158">ExtensionAttribute13</span></span> |<span data-ttu-id="7b5bd-159">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="7b5bd-159">CustomAttribute13</span></span>  |
|<span data-ttu-id="7b5bd-160">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="7b5bd-160">ExtensionAttribute14</span></span> |<span data-ttu-id="7b5bd-161">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="7b5bd-161">CustomAttribute14</span></span>  |
|<span data-ttu-id="7b5bd-162">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="7b5bd-162">ExtensionAttribute15</span></span> |<span data-ttu-id="7b5bd-163">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="7b5bd-163">CustomAttribute15</span></span>  |
|<span data-ttu-id="7b5bd-164">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7b5bd-164">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="7b5bd-165">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7b5bd-165">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="7b5bd-166">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7b5bd-166">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="7b5bd-167">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7b5bd-167">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="7b5bd-168">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7b5bd-168">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="7b5bd-169">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7b5bd-169">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="7b5bd-170">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7b5bd-170">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="7b5bd-171">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7b5bd-171">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="7b5bd-172">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7b5bd-172">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="7b5bd-173">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7b5bd-173">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="7b5bd-174">MailNickname</span><span class="sxs-lookup"><span data-stu-id="7b5bd-174">MailNickname</span></span> |<span data-ttu-id="7b5bd-175">別名</span><span class="sxs-lookup"><span data-stu-id="7b5bd-175">Alias</span></span> |
|<span data-ttu-id="7b5bd-176">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="7b5bd-176">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="7b5bd-177">Office</span><span class="sxs-lookup"><span data-stu-id="7b5bd-177">Office</span></span> |
|<span data-ttu-id="7b5bd-178">PostalCode</span><span class="sxs-lookup"><span data-stu-id="7b5bd-178">PostalCode</span></span> |<span data-ttu-id="7b5bd-179">PostalCode</span><span class="sxs-lookup"><span data-stu-id="7b5bd-179">PostalCode</span></span> |
|<span data-ttu-id="7b5bd-180">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7b5bd-180">ProxyAddresses</span></span> |<span data-ttu-id="7b5bd-181">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="7b5bd-181">EmailAddresses</span></span> |
|<span data-ttu-id="7b5bd-182">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="7b5bd-182">StreetAddress</span></span> |<span data-ttu-id="7b5bd-183">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="7b5bd-183">StreetAddress</span></span> |
|<span data-ttu-id="7b5bd-184">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="7b5bd-184">TargetAddress</span></span> |<span data-ttu-id="7b5bd-185">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="7b5bd-185">ExternalEmailAddress</span></span> |
|<span data-ttu-id="7b5bd-186">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="7b5bd-186">UsageLocation</span></span> |<span data-ttu-id="7b5bd-187">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="7b5bd-187">UsageLocation</span></span> |
|<span data-ttu-id="7b5bd-188">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7b5bd-188">UserPrincipalName</span></span>  |<span data-ttu-id="7b5bd-189">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7b5bd-189">UserPrincipalName</span></span>  |
|<span data-ttu-id="7b5bd-190">郵件</span><span class="sxs-lookup"><span data-stu-id="7b5bd-190">Mail</span></span>   |<span data-ttu-id="7b5bd-191">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="7b5bd-191">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="7b5bd-192">描述</span><span class="sxs-lookup"><span data-stu-id="7b5bd-192">Description</span></span>    |<span data-ttu-id="7b5bd-193">描述</span><span class="sxs-lookup"><span data-stu-id="7b5bd-193">Description</span></span>    |
|<span data-ttu-id="7b5bd-194">MemberOf</span><span class="sxs-lookup"><span data-stu-id="7b5bd-194">MemberOf</span></span>   |<span data-ttu-id="7b5bd-195">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="7b5bd-195">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="7b5bd-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="7b5bd-196">Related topics</span></span>

[<span data-ttu-id="7b5bd-197">在 Microsoft Teams （預覽） 中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="7b5bd-197">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="7b5bd-198">疑難排解資訊障礙 （預覽）</span><span class="sxs-lookup"><span data-stu-id="7b5bd-198">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="7b5bd-199">資訊障礙 （預覽）</span><span class="sxs-lookup"><span data-stu-id="7b5bd-199">Information barriers (Preview)</span></span>](information-barriers.md)



