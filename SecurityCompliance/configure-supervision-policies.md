---
title: 為您的組織設定監督原則
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 若要擷取員工通訊，檢閱設定主管檢閱原則。
ms.openlocfilehash: 92630b1405af6e297390751d9b00e24a82e03087
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958615"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="2719c-103">為您的組織設定監督原則</span><span class="sxs-lookup"><span data-stu-id="2719c-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="2719c-104">使用監督原則來擷取員工通訊，由內部或外部的檢閱者檢查。</span><span class="sxs-lookup"><span data-stu-id="2719c-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="2719c-105">如需監督原則可幫助您監視組織中的通訊的詳細資訊，請參閱 < <b0>Office 365 中的監督原則</b0>。</span><span class="sxs-lookup"><span data-stu-id="2719c-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2719c-106">受到監督原則的使用者必須擁有可以是 Microsoft 365 E5 合規性授權 Office 365 企業版 E3 授權來搭配進階合規性的附加元件，或包含在 Office 365 企業版 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="2719c-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
<span data-ttu-id="2719c-107">如果您未擁有現有的企業版 E5 方案，以及要嘗試監督，您可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2719c-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="2719c-108">請遵循下列步驟來設定和使用 Office 365 組織中監督：</span><span class="sxs-lookup"><span data-stu-id="2719c-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="2719c-109">**步驟 1 （選用）** - [設定群組的監督 （選用）](#step-1---set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="2719c-109">**Step 1 (optional)** - [Set up groups for Supervision (optional)](#step-1---set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="2719c-110">開始使用監督之前，請決定誰需要檢閱的通訊，以及誰可以執行檢閱。</span><span class="sxs-lookup"><span data-stu-id="2719c-110">Before you start using supervision, determine who needs communications reviewed and who will perform reviews.</span></span> <span data-ttu-id="2719c-111">如果您想要開始使用少數使用者查看監督的運作方式，您可以略過現在群組設定。</span><span class="sxs-lookup"><span data-stu-id="2719c-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="2719c-112">**步驟 2 （必要）** - [進行 （必要） 組織中可用的監督](#step-2---make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="2719c-112">**Step 2 (required)** - [Make supervision available in your organization (required)](#step-2---make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="2719c-113">將自己新增至主管檢閱角色群組，以便讓您可以設定原則。</span><span class="sxs-lookup"><span data-stu-id="2719c-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="2719c-114">擁有此角色指派給任何人可以存取合規性中心中的 [**監督**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2719c-114">Anyone who has this role assigned can access the **Supervision** page in the Compliance Center.</span></span> <span data-ttu-id="2719c-115">如果 reviewable 電子郵件裝載於 Exchange Online，每位檢閱者必須具有[Exchange online 的遠端 PowerShell 存取](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2719c-115">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2719c-116">**步驟 3 （選用）** - [建立自訂機密資訊類型和自訂的關鍵字字典](#step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="2719c-116">**Step 3 (optional)** - [Create custom sensitive information types and custom keyword dictionaries](#step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="2719c-117">如果您需要的自訂機密資訊類型或自訂的關鍵字字典監督原則，您需要建立啟動監督精靈之前。</span><span class="sxs-lookup"><span data-stu-id="2719c-117">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="2719c-118">**步驟 4 （必要）** - [設定的監督原則](#step-4---set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="2719c-118">**Step 4 (required)** - [Set up a supervision policy](#step-4---set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="2719c-119">您可以建立監督原則與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="2719c-119">You create supervision policies in the Compliance Center.</span></span> <span data-ttu-id="2719c-120">這些原則定義哪些通訊會受到檢閱您組織中，並指定誰可以執行檢閱。</span><span class="sxs-lookup"><span data-stu-id="2719c-120">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="2719c-121">通訊包括電子郵件和 Microsoft Teams 的通訊，以及第 3 廠商平台 （例如 Facebook、 Twitter 等等） 的通訊</span><span class="sxs-lookup"><span data-stu-id="2719c-121">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="2719c-122">**步驟 5-（選用）**[測試您的監督原則](#step-5---test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="2719c-122">**Step 5 - (optional)** [Test your supervision policy](#step-5---test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="2719c-123">測試您的監督原則，以確定它所需的功能。</span><span class="sxs-lookup"><span data-stu-id="2719c-123">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="2719c-124">請務必確定您符合性策略會議標準。</span><span class="sxs-lookup"><span data-stu-id="2719c-124">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="2719c-125">**步驟 6-（選用）**[設定 Outlook 的檢閱者不想要使用 Office 365 監督儀表板或 （先前稱為 Outlook Web App） 網頁型 Outlook 來檢閱監督的通訊](#step-6---configure-outlook-for-reviewers-optional)</span><span class="sxs-lookup"><span data-stu-id="2719c-125">**Step 6 - (optional)** [Configure Outlook for reviewers who do not want to use Office 365 supervision dashboard or Outlook on the web (formerly known as Outlook Web App) to review supervised communications](#step-6---configure-outlook-for-reviewers-optional)</span></span>

    <span data-ttu-id="2719c-126">設定 Outlook，才能讓檢閱者存取 Outlook 用戶端內的監督功能讓他們可以評估並加以分類每個項目。</span><span class="sxs-lookup"><span data-stu-id="2719c-126">Configure Outlook to give reviewers access to the supervision functionality within the Outlook client so they can assess and categorize each item.</span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="2719c-127">步驟 1-設定群組的監督 （選用）</span><span class="sxs-lookup"><span data-stu-id="2719c-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="2719c-128">當您建立的監督原則時，您可以定義誰可以檢閱其通訊和使用者執行評論。</span><span class="sxs-lookup"><span data-stu-id="2719c-128">When you create a supervision policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="2719c-129">在原則中，您將使用電子郵件地址來識別的個人或群組的人員。</span><span class="sxs-lookup"><span data-stu-id="2719c-129">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="2719c-130">為了簡化您的設定，您可以建立的人員檢閱其通訊群組和群組的檢閱這些通訊的人。</span><span class="sxs-lookup"><span data-stu-id="2719c-130">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="2719c-131">如果您使用的群組，您可能需要數個選項。</span><span class="sxs-lookup"><span data-stu-id="2719c-131">If you're using groups, you may need several.</span></span> <span data-ttu-id="2719c-132">例如，您要監視的人員，或如果您想要指定群組不是要為指導的兩個不同的群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="2719c-132">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="2719c-133">使用下表來協助您在您的組織監督原則中設定群組：</span><span class="sxs-lookup"><span data-stu-id="2719c-133">Use the following chart to help you configure groups in your organization for supervision policies:</span></span>

| <span data-ttu-id="2719c-134">**原則成員**</span><span class="sxs-lookup"><span data-stu-id="2719c-134">**Policy Member**</span></span> | <span data-ttu-id="2719c-135">**支援的群組**</span><span class="sxs-lookup"><span data-stu-id="2719c-135">**Supported Groups**</span></span> | <span data-ttu-id="2719c-136">**不支援的群組**</span><span class="sxs-lookup"><span data-stu-id="2719c-136">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="2719c-137">監督的使用者</span><span class="sxs-lookup"><span data-stu-id="2719c-137">Supervised users</span></span> | <span data-ttu-id="2719c-138">通訊群組</span><span class="sxs-lookup"><span data-stu-id="2719c-138">Distribution groups</span></span> <br> <span data-ttu-id="2719c-139">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="2719c-139">Office 365 groups</span></span> | <span data-ttu-id="2719c-140">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="2719c-140">Dynamic distribution groups</span></span> |
| <span data-ttu-id="2719c-141">檢閱者</span><span class="sxs-lookup"><span data-stu-id="2719c-141">Reviewers</span></span> | <span data-ttu-id="2719c-142">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="2719c-142">Mail-enabled security groups</span></span>  | <span data-ttu-id="2719c-143">通訊群組</span><span class="sxs-lookup"><span data-stu-id="2719c-143">Distribution groups</span></span> <br> <span data-ttu-id="2719c-144">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="2719c-144">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="2719c-145">若要管理大型企業組織中監督的使用者，您可能需要跨大型群組監視所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2719c-145">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="2719c-146">您可以使用 PowerShell 來設定全域監督原則中的 [指派] 群組的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="2719c-146">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="2719c-147">這可讓您監視數千名使用者與單一原則，並保留已更新為新員工加入您的組織在監督原則。</span><span class="sxs-lookup"><span data-stu-id="2719c-147">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="2719c-148">建立專用的[通訊群組](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)全域監督原則具有下列內容： 請確定此通訊群組未用於其他目的或其他 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="2719c-148">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="2719c-149">**MemberDepartRestriction = 關閉**。</span><span class="sxs-lookup"><span data-stu-id="2719c-149">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="2719c-150">可確保使用者不能移除自行從通訊群組。</span><span class="sxs-lookup"><span data-stu-id="2719c-150">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="2719c-151">**MemberJoinRestriction = 關閉**。</span><span class="sxs-lookup"><span data-stu-id="2719c-151">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="2719c-152">可確保使用者無法將自己新增至通訊群組。</span><span class="sxs-lookup"><span data-stu-id="2719c-152">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="2719c-153">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="2719c-153">**ModerationEnabled = True**.</span></span> <span data-ttu-id="2719c-154">確保傳送至此群組的所有郵件都都會受到核准，而且不會群組用來傳達外監督原則設定。</span><span class="sxs-lookup"><span data-stu-id="2719c-154">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. <span data-ttu-id="2719c-155">選取要追蹤新增至您組織中監督原則的使用者未使用的[Exchange 的自訂屬性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)。</span><span class="sxs-lookup"><span data-stu-id="2719c-155">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="2719c-156">若要將使用者新增至監督原則的週期性排程上執行下列 PowerShell 指令碼：</span><span class="sxs-lookup"><span data-stu-id="2719c-156">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="2719c-157">如需設定群組的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="2719c-157">For more information about setting up groups, see:</span></span>
- [<span data-ttu-id="2719c-158">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="2719c-158">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="2719c-159">管理啟用郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="2719c-159">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="2719c-160">Office 365 群組概觀</span><span class="sxs-lookup"><span data-stu-id="2719c-160">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="2719c-161">步驟 2-進行監督 （必要） 組織中可用</span><span class="sxs-lookup"><span data-stu-id="2719c-161">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="2719c-162">若要讓**監督**在規範中心中可用的功能表選項，您必須獲指派的主管檢閱管理員角色。</span><span class="sxs-lookup"><span data-stu-id="2719c-162">To make **Supervision** available as a menu option in the Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="2719c-163">若要這麼做，您可以也將自己新增為主管檢閱角色群組的成員，或您可以建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="2719c-163">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="2719c-164">將成員新增至 [主管檢閱] 角色群組</span><span class="sxs-lookup"><span data-stu-id="2719c-164">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="2719c-165">登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="2719c-165">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2719c-166">在合規性中心] 中，前往 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="2719c-166">In the Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="2719c-167">選取 [**主管檢閱**] 角色群組，然後按一下 [編輯] 圖示。</span><span class="sxs-lookup"><span data-stu-id="2719c-167">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="2719c-168">在 [**成員**] 區段中，新增您想要管理貴組織的監督的人員。</span><span class="sxs-lookup"><span data-stu-id="2719c-168">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="2719c-169">建立新的角色群組</span><span class="sxs-lookup"><span data-stu-id="2719c-169">Create a new role group</span></span>

1. <span data-ttu-id="2719c-170">登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="2719c-170">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2719c-171">在合規性中心] 中，移至**權限**，然後按一下 [新增 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="2719c-171">In the Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="2719c-172">在 [**角色**] 區段中，按一下 [新增 (**+**) 和向下**主管檢閱管理員**捲動。</span><span class="sxs-lookup"><span data-stu-id="2719c-172">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="2719c-173">將此角色新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="2719c-173">Add this role to the role group.</span></span>

4. <span data-ttu-id="2719c-174">在 [**成員**] 區段中，新增您想要管理貴組織的監督的人員。</span><span class="sxs-lookup"><span data-stu-id="2719c-174">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="2719c-175">如需有關角色群組和權限的詳細資訊，請參閱 <<c0>合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="2719c-175">For more information about role groups and permissions, see [Permissions in the Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="2719c-176">啟用遠端 PowerShell 存取的檢閱者 （如果電子郵件裝載於 Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="2719c-176">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="2719c-177">請遵循[啟用或停用存取 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指引。</span><span class="sxs-lookup"><span data-stu-id="2719c-177">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="2719c-178">步驟 3： 建立自訂機密資訊類型，以及自訂的關鍵字字典 （選用）</span><span class="sxs-lookup"><span data-stu-id="2719c-178">Step 3 - Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="2719c-179">若要從現有的自訂機密資訊類型或自訂的關鍵字字典中監督原則] 精靈中挑選，必須先建立這些項目，如有需要。</span><span class="sxs-lookup"><span data-stu-id="2719c-179">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="2719c-180">建立自訂的關鍵字字典/lexicon （選用）</span><span class="sxs-lookup"><span data-stu-id="2719c-180">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="2719c-181">使用文字編輯器 （例如記事本），來建立新的檔案，其中包含您想要監視的監督原則的關鍵字字詞。</span><span class="sxs-lookup"><span data-stu-id="2719c-181">Use a text editor (like Notepad), to create a new file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="2719c-182">請確定每個字詞是位於個別一行，並以**Unicode/utf-16 (一點 Endian)** 格式儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="2719c-182">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="2719c-183">建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="2719c-183">Create custom sensitive information types</span></span>

1. <span data-ttu-id="2719c-184">建立新的敏感資訊類型，並在 Office 365 安全性 & 合規性中心中新增您的自訂字典。</span><span class="sxs-lookup"><span data-stu-id="2719c-184">Create a new sensitive information type and add your custom dictionary in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="2719c-185">瀏覽至 **[分類]** \> **敏感資訊類型]，** 然後依照中**新的敏感資訊類型精靈**的步驟。</span><span class="sxs-lookup"><span data-stu-id="2719c-185">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="2719c-186">在這裡您將會：</span><span class="sxs-lookup"><span data-stu-id="2719c-186">Here you will:</span></span>

    - <span data-ttu-id="2719c-187">定義的名稱和描述的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="2719c-187">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="2719c-188">定義接近度信賴等級，主要模式元素</span><span class="sxs-lookup"><span data-stu-id="2719c-188">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="2719c-189">匯入您的自訂字典比對元素的需求</span><span class="sxs-lookup"><span data-stu-id="2719c-189">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="2719c-190">檢閱您的選項，並建立敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="2719c-190">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="2719c-191">如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)和[建立關鍵字字典](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="2719c-191">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="2719c-192">建立自訂字典/lexicon 之後，您可以檢視透過[取得 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)指令程式設定的關鍵字或新增和移除使用[組 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)指令程式的字詞。</span><span class="sxs-lookup"><span data-stu-id="2719c-192">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="2719c-193">步驟 4-設定 （必要） 的監督原則</span><span class="sxs-lookup"><span data-stu-id="2719c-193">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="2719c-194">登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="2719c-194">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2719c-195">在合規性中心] 中，選取 [**監督**]。</span><span class="sxs-lookup"><span data-stu-id="2719c-195">In the Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="2719c-196">選取 [**建立**，然後遵循精靈來設定下列頁面的原則。</span><span class="sxs-lookup"><span data-stu-id="2719c-196">Select **Create** and then follow the wizard to set up the following pages of the policy.</span></span> <span data-ttu-id="2719c-197">使用這個精靈，您會：</span><span class="sxs-lookup"><span data-stu-id="2719c-197">Using the wizard, you will:</span></span>

    - <span data-ttu-id="2719c-198">授與此原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="2719c-198">Give the policy a name and description.</span></span>
    - <span data-ttu-id="2719c-199">選擇使用者或群組来監管，包括 [選擇使用者] 或 [您想要排除的群組。</span><span class="sxs-lookup"><span data-stu-id="2719c-199">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="2719c-200">定義監督原則條件。</span><span class="sxs-lookup"><span data-stu-id="2719c-200">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="2719c-201">選擇您想要包含敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2719c-201">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="2719c-202">這是您可以在其中選取預設及自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2719c-202">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="2719c-203">定義要檢閱的通訊的百分比。</span><span class="sxs-lookup"><span data-stu-id="2719c-203">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="2719c-204">選擇 [原則的檢閱者]。</span><span class="sxs-lookup"><span data-stu-id="2719c-204">Choose the reviewers for the policy.</span></span> <span data-ttu-id="2719c-205">檢閱者可以是個別使用者或[擁有郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="2719c-205">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="2719c-206">所有檢閱者必須擁有 Exchange Online 上主控的信箱。</span><span class="sxs-lookup"><span data-stu-id="2719c-206">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="2719c-207">檢閱您的原則選項，並建立原則。</span><span class="sxs-lookup"><span data-stu-id="2719c-207">Review your policy selections and create the policy.</span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="2719c-208">步驟 5-測試 （選擇性） 您監督原則</span><span class="sxs-lookup"><span data-stu-id="2719c-208">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="2719c-209">建立監督原則之後，它是不錯的選項進行測試以確定您定義的條件都要正確地強制執行該原則所。</span><span class="sxs-lookup"><span data-stu-id="2719c-209">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="2719c-210">如果您的監督原則包含敏感資訊類型，您也可能會想要[測試您的資料遺失防護 (DLP) 原則](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="2719c-210">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="2719c-211">請遵循下列步驟來測試您的監督原則：</span><span class="sxs-lookup"><span data-stu-id="2719c-211">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="2719c-212">開啟電子郵件用戶端或 Microsoft Teams 以登入您想要測試該的原則所定義的監督使用者。</span><span class="sxs-lookup"><span data-stu-id="2719c-212">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="2719c-213">傳送電子郵件或符合您已定義的監督原則中之準則的 Microsoft Teams 聊天室。</span><span class="sxs-lookup"><span data-stu-id="2719c-213">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="2719c-214">這可以是關鍵字附件大小、 網域、 等等。請確定您判斷您在原則中的現有條件化設定是否限制太多或太廣義。</span><span class="sxs-lookup"><span data-stu-id="2719c-214">This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="2719c-215">受到定義原則的電子郵件中處理幾近即時和可以用來測試後的原則設定。</span><span class="sxs-lookup"><span data-stu-id="2719c-215">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="2719c-216">Microsoft Teams 中的聊天室 」 可能需要最多 24 小時才完全處理程序中的原則。</span><span class="sxs-lookup"><span data-stu-id="2719c-216">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="2719c-217">登入您的 Office 365 租用戶為監督原則中指定檢閱者。</span><span class="sxs-lookup"><span data-stu-id="2719c-217">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="2719c-218">瀏覽至**監督** > *您的自訂原則* > **開啟**檢視該原則的報告。</span><span class="sxs-lookup"><span data-stu-id="2719c-218">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a><span data-ttu-id="2719c-219">步驟 6-設定 Outlook 的檢閱者 （選用）</span><span class="sxs-lookup"><span data-stu-id="2719c-219">Step 6 - Configure Outlook for reviewers (optional)</span></span>

<span data-ttu-id="2719c-220">想要檢閱的通訊，而不是在 Office 365 中的監督儀表板使用 Outlook 的檢閱者必須設定他們的 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2719c-220">Reviewers that want to use Outlook instead of the Supervision dashboard in Office 365 to review communications must configure their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="2719c-221">步驟 1： 複製監督信箱的地址</span><span class="sxs-lookup"><span data-stu-id="2719c-221">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="2719c-222">若要設定的 Outlook 桌面檢閱或 outlook 網頁版，您需要建立一部分監督原則設定的監督信箱地址。</span><span class="sxs-lookup"><span data-stu-id="2719c-222">To configure review for Outlook desktop or Outlook for the web, you need the address for the supervision mailbox created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2719c-223">如果別人建立原則，您需要取得這個地址，才能安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="2719c-223">If someone else created the policy, you need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="2719c-224">**若要尋找的監督信箱地址**</span><span class="sxs-lookup"><span data-stu-id="2719c-224">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="2719c-225">登入[合規性中心](https://compliance.microsoft.com)使用您組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="2719c-225">Sign into the [Compliance Center](https://compliance.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="2719c-226">移至**監督**。</span><span class="sxs-lookup"><span data-stu-id="2719c-226">Go to **Supervision**.</span></span>

3. <span data-ttu-id="2719c-227">選取您想要檢閱的通訊監督原則。</span><span class="sxs-lookup"><span data-stu-id="2719c-227">Select a supervision policy for the communications you want to review.</span></span>

4. <span data-ttu-id="2719c-228">在 [原則的詳細資訊彈出式視窗中，[**監督信箱**，複製地址。</span><span class="sxs-lookup"><span data-stu-id="2719c-228">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="2719c-229">![['監督信箱'] 區段中的監督原則的詳細資料彈出式視窗顯示反白顯示的監督信箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="2719c-229">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a><span data-ttu-id="2719c-230">步驟 2： 設定 Outlook 存取的監督信箱</span><span class="sxs-lookup"><span data-stu-id="2719c-230">Step 2: Configure the supervision mailbox for Outlook access</span></span>

<span data-ttu-id="2719c-231">接下來，檢閱者需要執行的一些 Exchange Online PowerShell 命令，讓他們可以將 Outlook 連線至監督的信箱。</span><span class="sxs-lookup"><span data-stu-id="2719c-231">Next, reviewers need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="2719c-232">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2719c-232">Connect to Exchange Online PowerShell.</span></span> [<span data-ttu-id="2719c-233">該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="2719c-233">How do I do this?</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. <span data-ttu-id="2719c-234">執行下列命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步驟 1 中複製的地址，且*使用者*的檢閱者會連線到步驟 3 中的監督信箱的名稱。</span><span class="sxs-lookup"><span data-stu-id="2719c-234">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will connect to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="2719c-235">等候至少一個小時再移至步驟 3。</span><span class="sxs-lookup"><span data-stu-id="2719c-235">Wait at least an hour before moving on to Step 3.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="2719c-236">步驟 3： 建立的 Outlook 設定檔，以連線至監督信箱</span><span class="sxs-lookup"><span data-stu-id="2719c-236">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="2719c-237">最後一個步驟中，檢閱者需要建立的 Outlook 設定檔，以連線至監督信箱。</span><span class="sxs-lookup"><span data-stu-id="2719c-237">For the final step, reviewers need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="2719c-238">若要建立新的 Outlook 設定檔，您將使用在 Windows [控制台] 中的 「 信箱 」 設定。</span><span class="sxs-lookup"><span data-stu-id="2719c-238">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel.</span></span> <span data-ttu-id="2719c-239">若要取得這些設定您所採取的路徑可能需取決於您使用的 Windows 作業系統 （Windows 7、 Windows 8 或 Windows 10），以及安裝的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="2719c-239">The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="2719c-240">開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2719c-240">Open the Control Panel.</span></span> <span data-ttu-id="2719c-241">在視窗頂端的 [**搜尋**] 方塊中，輸入**郵件**。</span><span class="sxs-lookup"><span data-stu-id="2719c-241">In the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="2719c-242">(不確定如何取得 Control Panel 嗎？</span><span class="sxs-lookup"><span data-stu-id="2719c-242">(Not sure how to get to the Control Panel?</span></span> <span data-ttu-id="2719c-243">請參閱[所在控制台？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="2719c-243">See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="2719c-244">開啟 [**郵件**應用程式]。</span><span class="sxs-lookup"><span data-stu-id="2719c-244">Open the **Mail** app.</span></span>

3. <span data-ttu-id="2719c-245">在 [**郵件設定的 Outlook**，按一下 [**顯示設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="2719c-245">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="2719c-246">!['郵件安裝程式-Outlook' 與' 顯示設定檔] 按鈕以反白顯示的對話方塊](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="2719c-246">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="2719c-247">在 [**郵件**] 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="2719c-247">In **Mail**, click **Add**.</span></span> <span data-ttu-id="2719c-248">然後，在**新的設定檔**，輸入監督信箱 （例如**監督**） 的名稱。</span><span class="sxs-lookup"><span data-stu-id="2719c-248">Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="2719c-249">![在 [設定檔名稱] 方塊中顯示的名稱 '監督' ['新設定檔'] 對話方塊](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="2719c-249">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="2719c-250">在 [**連線至 Office 365 的 Outlook**中，按一下 [**連線到不同的帳戶。**</span><span class="sxs-lookup"><span data-stu-id="2719c-250">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="2719c-251">![具有反白顯示的 [連線到不同的帳戶] 連結的 ' 連線到 Office 365 的 Outlook' 訊息](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="2719c-251">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="2719c-252">在 [**自動帳戶設定**] 中，選擇 [**手動安裝程式或其他伺服器類型**，，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2719c-252">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="2719c-253">在 [**選擇您的帳戶類型**] 中，選擇 [ **Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="2719c-253">In **Choose Your Account Type**, choose **Office 365**.</span></span> <span data-ttu-id="2719c-254">然後，在 [**電子郵件地址**] 方塊中，輸入您先前複製的監督信箱地址。</span><span class="sxs-lookup"><span data-stu-id="2719c-254">Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="2719c-255">![顯示 '電子郵件地址] 方塊中反白顯示在 Outlook 中的 [新增帳戶] 對話方塊的' 選擇您的帳戶類型] 頁面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="2719c-255">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="2719c-256">出現提示時，輸入您的 Office 365 認證。</span><span class="sxs-lookup"><span data-stu-id="2719c-256">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="2719c-257">如果成功，您會看到**監督-\<原則名稱\>** 資料夾列在 Outlook 中的 [資料夾清單] 檢視中。</span><span class="sxs-lookup"><span data-stu-id="2719c-257">If successful, you'll see the **Supervision — \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="2719c-258">PowerShell 參考</span><span class="sxs-lookup"><span data-stu-id="2719c-258">PowerShell reference</span></span>

<span data-ttu-id="2719c-259">如有需要您可以建立及管理監督原則搭配下列 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2719c-259">If needed, you can create and manage supervision policies with the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="2719c-260">新 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2719c-260">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2719c-261">取得 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2719c-261">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2719c-262">Set-supervisoryreviewpolicyv2</span><span class="sxs-lookup"><span data-stu-id="2719c-262">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2719c-263">Remove-supervisoryreviewpolicyv2</span><span class="sxs-lookup"><span data-stu-id="2719c-263">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2719c-264">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="2719c-264">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="2719c-265">Set-supervisoryreviewrule</span><span class="sxs-lookup"><span data-stu-id="2719c-265">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="2719c-266">取得 SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="2719c-266">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="2719c-267">取得 SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="2719c-267">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="2719c-268">取得 SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="2719c-268">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)