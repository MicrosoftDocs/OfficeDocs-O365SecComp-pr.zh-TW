---
title: 資訊障礙概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用資訊障礙, 以確保在組織內使用 Microsoft 小組來進行通訊合規性。
ms.openlocfilehash: 6565fc28d70ac6ff9a6f4df6edc75b89d19ae29a
ms.sourcegitcommit: 1c254108c522d0cb44023565268b5041d07748aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2019
ms.locfileid: "35279471"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="fe949-103">資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="fe949-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="fe949-104">概觀</span><span class="sxs-lookup"><span data-stu-id="fe949-104">Overview</span></span>

<span data-ttu-id="fe949-105">Microsoft 雲端服務包含強大的通訊和共同作業功能。</span><span class="sxs-lookup"><span data-stu-id="fe949-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="fe949-106">但是, 假設您想要限制兩個群組之間的通訊, 以避免組織中發生利益衝突的情況。</span><span class="sxs-lookup"><span data-stu-id="fe949-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="fe949-107">或者, 您可能想要限制組織內特定人員之間的通訊, 以保護內部資訊。</span><span class="sxs-lookup"><span data-stu-id="fe949-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="fe949-108">Microsoft 365 可跨群組和組織進行通訊與共同作業, 因此有一種方法可以限制特定使用者群組之間的通訊 (必要時)？</span><span class="sxs-lookup"><span data-stu-id="fe949-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="fe949-109">有了資訊障礙, 您可以!</span><span class="sxs-lookup"><span data-stu-id="fe949-109">With information barriers, you can!</span></span> 

<span data-ttu-id="fe949-110">資訊障礙現在是在預覽中, 從 Microsoft 團隊開始。</span><span class="sxs-lookup"><span data-stu-id="fe949-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="fe949-111">當您的組織可使用這些功能時, 合規性管理員或資訊障礙管理員可以定義原則, 以允許或防止 Microsoft 小組中的使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="fe949-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="fe949-112">資訊屏障原則可用於下列情況:</span><span class="sxs-lookup"><span data-stu-id="fe949-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="fe949-113">一天 trader 無法呼叫行銷小組中的人員</span><span class="sxs-lookup"><span data-stu-id="fe949-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="fe949-114">使用機密公司資訊的財務人員無法接收來自其組織內特定群組的通話</span><span class="sxs-lookup"><span data-stu-id="fe949-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="fe949-115">具有交易秘密材料的內部小組無法與組織內特定群組中的人員進行線上通話或聊天</span><span class="sxs-lookup"><span data-stu-id="fe949-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="fe949-116">研究小組只能與產品開發小組通話或聊天</span><span class="sxs-lookup"><span data-stu-id="fe949-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="fe949-117">針對上述所有範例案例 (以及更多), 您可以定義資訊屏障原則, 以防止或允許 Microsoft 小組中的通訊。</span><span class="sxs-lookup"><span data-stu-id="fe949-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="fe949-118">這類原則可防止使用者不應該呼叫或聊天, 或讓人員只能與 Microsoft 小組中的特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="fe949-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="fe949-119">在有效的資訊屏障原則中, 每當這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他人通訊時, 就會進行檢查以防止 (或允許) 通訊 (如資訊屏障原則所定義)。</span><span class="sxs-lookup"><span data-stu-id="fe949-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="fe949-120">若要深入瞭解資訊障礙的使用者經驗, 請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="fe949-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="fe949-121">資訊障礙不適用於電子郵件通訊或透過 SharePoint Online 或 OneDrive 的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="fe949-121">Information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="fe949-122">此外, 資訊障礙與[規範界限](set-up-compliance-boundaries.md)無關。</span><span class="sxs-lookup"><span data-stu-id="fe949-122">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="fe949-123">必要的授權和許可權</span><span class="sxs-lookup"><span data-stu-id="fe949-123">Required licenses and permissions</span></span>

<span data-ttu-id="fe949-124">**目前, 資訊障礙功能是在私人預覽中**。</span><span class="sxs-lookup"><span data-stu-id="fe949-124">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="fe949-125">這些功能通常會包含在訂閱中, 例如:</span><span class="sxs-lookup"><span data-stu-id="fe949-125">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="fe949-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fe949-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="fe949-127">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fe949-127">Office 365 E5</span></span>
- <span data-ttu-id="fe949-128">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="fe949-128">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="fe949-129">Microsoft 365 E5 資訊保護和合規性</span><span class="sxs-lookup"><span data-stu-id="fe949-129">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="fe949-130">如需詳細資訊, 請參閱[規範解決方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="fe949-130">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="fe949-131">若要[定義或編輯資訊屏障原則](information-barriers-policies.md), 您必須被指派下列其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="fe949-131">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="fe949-132">Microsoft 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="fe949-132">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="fe949-133">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="fe949-133">Office 365 global administrator</span></span>
- <span data-ttu-id="fe949-134">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="fe949-134">Compliance administrator</span></span>
- <span data-ttu-id="fe949-135">資訊障礙管理員</span><span class="sxs-lookup"><span data-stu-id="fe949-135">Information barriers administrator</span></span>

<span data-ttu-id="fe949-136">您必須熟悉 PowerShell Cmdlet, 才能定義、驗證或編輯資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="fe949-136">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="fe949-137">雖然我們在操作[方法資訊](information-barriers-policies.md)中提供了幾個 PowerShell Cmdlet 範例, 但是您必須瞭解組織的其他詳細資料, 例如參數。</span><span class="sxs-lookup"><span data-stu-id="fe949-137">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="fe949-138">資訊障礙原則的概念</span><span class="sxs-lookup"><span data-stu-id="fe949-138">Concepts of information barrier policies</span></span>

<span data-ttu-id="fe949-139">瞭解資訊屏障原則的基礎概念會很有説明:</span><span class="sxs-lookup"><span data-stu-id="fe949-139">It's helpful to know the underlying concepts of information barrier policies:</span></span>

- <span data-ttu-id="fe949-140">**使用者帳戶屬性**是在 Azure Active Directory (或 Exchange Online) 中定義的。</span><span class="sxs-lookup"><span data-stu-id="fe949-140">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="fe949-141">這些屬性可以包括部門、職稱、位置、小組名稱及其他工作設定檔詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fe949-141">These attributes can include department, job title, location, team name, and other job profile details.</span></span> 

- <span data-ttu-id="fe949-142">**區段**是使用選取的**使用者帳戶屬性**, 在 [Office 365 安全性 & 合規性中心] 中定義的使用者集合。</span><span class="sxs-lookup"><span data-stu-id="fe949-142">**Segments** are sets of users that are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**.</span></span> <span data-ttu-id="fe949-143">(請參閱[支援的屬性清單](information-barriers-attributes.md))。</span><span class="sxs-lookup"><span data-stu-id="fe949-143">(See the [list of supported attributes](information-barriers-attributes.md).)</span></span> 

- <span data-ttu-id="fe949-144">**資訊屏障原則**會決定通訊限制或限制。</span><span class="sxs-lookup"><span data-stu-id="fe949-144">**Information barrier policies** determine communication limits or restrictions.</span></span> <span data-ttu-id="fe949-145">當您定義資訊屏障原則時, 您可以選擇兩種原則:</span><span class="sxs-lookup"><span data-stu-id="fe949-145">When you define information barrier policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="fe949-146">「封鎖」原則會防止一個區段與另一個區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="fe949-146">"Block" policies prevent one segment from communicating with another segment.</span></span>
    - <span data-ttu-id="fe949-147">「允許」原則允許一段時間只與特定的其他區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="fe949-147">"Allow" policies allow one segment to communicate with only certain other segments.</span></span>

- <span data-ttu-id="fe949-148">**原則應用程式**是在定義所有資訊屏障原則之後完成, 而且您已準備好將它們套用到您的組織中。</span><span class="sxs-lookup"><span data-stu-id="fe949-148">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe949-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="fe949-149">Next steps</span></span>

- [<span data-ttu-id="fe949-150">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="fe949-150">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="fe949-151">請參閱可用於資訊屏障原則的屬性</span><span class="sxs-lookup"><span data-stu-id="fe949-151">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="fe949-152">定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="fe949-152">Define policies for information barriers</span></span>](information-barriers-policies.md) 

