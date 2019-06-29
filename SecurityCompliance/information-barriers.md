---
title: 資訊障礙概述
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
description: 使用資訊障礙, 以確保在組織內使用 Microsoft 小組來進行通訊合規性。
ms.openlocfilehash: 9750eab3c91b40cc96e16a386dbf59ba767ae877
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394278"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="40924-103">資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="40924-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="40924-104">概觀</span><span class="sxs-lookup"><span data-stu-id="40924-104">Overview</span></span>

<span data-ttu-id="40924-105">Microsoft 雲端服務包含強大的通訊和共同作業功能。</span><span class="sxs-lookup"><span data-stu-id="40924-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="40924-106">但是, 假設您想要限制兩個群組之間的通訊, 以避免組織中發生利益衝突的情況。</span><span class="sxs-lookup"><span data-stu-id="40924-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="40924-107">或者, 您可能想要限制組織內特定人員之間的通訊, 以保護內部資訊。</span><span class="sxs-lookup"><span data-stu-id="40924-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="40924-108">Microsoft 365 可跨群組和組織進行通訊與共同作業, 因此有一種方法可以限制特定使用者群組之間的通訊 (必要時)？</span><span class="sxs-lookup"><span data-stu-id="40924-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="40924-109">有了資訊障礙, 您可以!</span><span class="sxs-lookup"><span data-stu-id="40924-109">With information barriers, you can!</span></span> 

<span data-ttu-id="40924-110">資訊障礙現在是在預覽中, 從 Microsoft 團隊開始。</span><span class="sxs-lookup"><span data-stu-id="40924-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="40924-111">當您的組織可使用這些功能時, 合規性管理員或資訊障礙管理員可以定義原則, 以允許或防止 Microsoft 小組中的使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="40924-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="40924-112">資訊屏障原則可用於下列情況:</span><span class="sxs-lookup"><span data-stu-id="40924-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="40924-113">一天 trader 無法呼叫行銷小組中的人員</span><span class="sxs-lookup"><span data-stu-id="40924-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="40924-114">使用機密公司資訊的財務人員無法接收來自其組織內特定群組的通話</span><span class="sxs-lookup"><span data-stu-id="40924-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="40924-115">具有交易秘密材料的內部小組無法與組織內特定群組中的人員進行線上通話或聊天</span><span class="sxs-lookup"><span data-stu-id="40924-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="40924-116">研究小組只能與產品開發小組通話或聊天</span><span class="sxs-lookup"><span data-stu-id="40924-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="40924-117">針對上述所有範例案例 (以及更多), 您可以定義資訊屏障原則, 以防止或允許 Microsoft 小組中的通訊。</span><span class="sxs-lookup"><span data-stu-id="40924-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="40924-118">這類原則可防止使用者不應該呼叫或聊天, 或讓人員只能與 Microsoft 小組中的特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="40924-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="40924-119">在有效的資訊屏障原則中, 每當這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他人通訊時, 就會進行檢查以防止 (或允許) 通訊 (如資訊屏障原則所定義)。</span><span class="sxs-lookup"><span data-stu-id="40924-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="40924-120">若要深入瞭解資訊障礙的使用者經驗, 請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="40924-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40924-121">目前, 資訊障礙不適用於電子郵件通訊或透過 SharePoint Online 或 OneDrive 的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="40924-121">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="40924-122">此外, 資訊障礙與[規範界限](set-up-compliance-boundaries.md)無關。</span><span class="sxs-lookup"><span data-stu-id="40924-122">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="40924-123">在您定義及套用資訊屏障原則之前, 請確定您的組織沒有生效的[Exchange 通訊錄原則](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="40924-123">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span>  

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="40924-124">資訊障礙會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="40924-124">What happens with information barriers</span></span>

<span data-ttu-id="40924-125">當資訊屏障原則到位時, 不應該與其他特定使用者通訊的人員將無法找到、選取、聊天或呼叫這些使用者。</span><span class="sxs-lookup"><span data-stu-id="40924-125">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="40924-126">透過資訊障礙, 支票會就地保留以防止未經授權的通訊。</span><span class="sxs-lookup"><span data-stu-id="40924-126">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="40924-127">資訊障礙最初僅適用于 Microsoft 團隊聊天和通道。</span><span class="sxs-lookup"><span data-stu-id="40924-127">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="40924-128">在 Microsoft 小組中, 資訊屏障原則會決定並防止下列幾種未經授權的通訊:</span><span class="sxs-lookup"><span data-stu-id="40924-128">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="40924-129">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="40924-129">Searching for a user</span></span>
- <span data-ttu-id="40924-130">將成員新增至小組</span><span class="sxs-lookup"><span data-stu-id="40924-130">Adding a member to a team</span></span>
- <span data-ttu-id="40924-131">啟動與某人的交談會話</span><span class="sxs-lookup"><span data-stu-id="40924-131">Starting a chat session with someone</span></span>
- <span data-ttu-id="40924-132">啟動群組聊天</span><span class="sxs-lookup"><span data-stu-id="40924-132">Starting a group chat</span></span>
- <span data-ttu-id="40924-133">邀請某人加入會議</span><span class="sxs-lookup"><span data-stu-id="40924-133">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="40924-134">共用螢幕</span><span class="sxs-lookup"><span data-stu-id="40924-134">Sharing a screen</span></span>
- <span data-ttu-id="40924-135">撥打電話</span><span class="sxs-lookup"><span data-stu-id="40924-135">Placing a call</span></span> 

<span data-ttu-id="40924-136">如果參與的人員包含在資訊屏障原則中, 以防止活動, 他們將無法繼續。</span><span class="sxs-lookup"><span data-stu-id="40924-136">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="40924-137">此外, 資訊屏障原則中包含的每一個人都可能會封鎖與 Microsoft 小組中的其他人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="40924-137">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="40924-138">受資訊障礙原則影響的人員是同一個小組或群組聊天的一部分, 他們可能會從交談會話中移除, 而且可能不允許與群組進行進一步的通訊。</span><span class="sxs-lookup"><span data-stu-id="40924-138">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="40924-139">若要深入瞭解資訊障礙的使用者經驗, 請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="40924-139">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="40924-140">必要的授權和許可權</span><span class="sxs-lookup"><span data-stu-id="40924-140">Required licenses and permissions</span></span>

<span data-ttu-id="40924-141">**目前資訊障礙是在預覽中**。</span><span class="sxs-lookup"><span data-stu-id="40924-141">**Currently, information barriers are in preview**.</span></span> <span data-ttu-id="40924-142">這些功能通常會包含在訂閱中, 例如:</span><span class="sxs-lookup"><span data-stu-id="40924-142">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="40924-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="40924-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="40924-144">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="40924-144">Office 365 E5</span></span>
- <span data-ttu-id="40924-145">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="40924-145">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="40924-146">Microsoft 365 E5 資訊保護和合規性</span><span class="sxs-lookup"><span data-stu-id="40924-146">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="40924-147">如需詳細資訊, 請參閱[規範解決方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="40924-147">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="40924-148">若要[定義或編輯資訊屏障原則](information-barriers-policies.md), 您必須被指派下列其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="40924-148">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="40924-149">Microsoft 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="40924-149">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="40924-150">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="40924-150">Office 365 global administrator</span></span>
- <span data-ttu-id="40924-151">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="40924-151">Compliance administrator</span></span>
- <span data-ttu-id="40924-152">IB 規範管理 (這是新的角色!)</span><span class="sxs-lookup"><span data-stu-id="40924-152">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="40924-153">(若要深入瞭解角色和許可權, 請參閱[Office 365 安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="40924-153">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="40924-154">您必須熟悉 PowerShell Cmdlet, 才能定義、驗證或編輯資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="40924-154">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="40924-155">雖然我們在操作[方法文章](information-barriers-policies.md)中提供了 PowerShell Cmdlet 的幾個範例, 但是您將需要瞭解組織的其他詳細資料, 例如參數。</span><span class="sxs-lookup"><span data-stu-id="40924-155">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40924-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="40924-156">Next steps</span></span>

- [<span data-ttu-id="40924-157">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="40924-157">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="40924-158">請參閱可用於資訊屏障原則的屬性</span><span class="sxs-lookup"><span data-stu-id="40924-158">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="40924-159">定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="40924-159">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="40924-160">編輯 (或移除) 資訊屏障原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="40924-160">Edit (or remove) information barrier policies (Preview)</span></span>](information-barriers-edit-segments-policies.md.md) 

