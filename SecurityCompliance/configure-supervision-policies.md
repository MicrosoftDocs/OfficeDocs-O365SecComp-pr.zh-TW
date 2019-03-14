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
ms.openlocfilehash: 2e321989934402b833d6190f65d696f4eb7919ca
ms.sourcegitcommit: 547a05da067a8f66fdaccf1cc399afcf863f5a87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2019
ms.locfileid: "30474154"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="bd610-103">為您的組織設定監督原則</span><span class="sxs-lookup"><span data-stu-id="bd610-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="bd610-104">使用監督原則來擷取員工通訊，由內部或外部的檢閱者檢查。</span><span class="sxs-lookup"><span data-stu-id="bd610-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="bd610-105">如需監督原則可幫助您監視組織中的通訊的詳細資訊，請參閱 < <b0>Office 365 中的監督原則</b0>。</span><span class="sxs-lookup"><span data-stu-id="bd610-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd610-106">受到監督原則的使用者必須擁有可以是 Microsoft 365 E5 合規性授權 Office 365 企業版 E3 授權來搭配進階合規性的附加元件，或包含在 Office 365 企業版 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="bd610-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
<span data-ttu-id="bd610-107">如果您未擁有現有的企業版 E5 方案，以及要嘗試監督，您可以[註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="bd610-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="bd610-108">請遵循下列步驟來設定和使用 Office 365 組織中監督：</span><span class="sxs-lookup"><span data-stu-id="bd610-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="bd610-109">**步驟 1 （選用）** - [設定的監督的群組](configure-supervision-policies.md#exampledist)</span><span class="sxs-lookup"><span data-stu-id="bd610-109">**Step 1 (optional)** - [Set up groups for Supervision](configure-supervision-policies.md#exampledist)</span></span>

    <span data-ttu-id="bd610-110">開始使用監督之前，請決定誰將其通訊檢閱，以及誰可以執行這些檢閱。</span><span class="sxs-lookup"><span data-stu-id="bd610-110">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews.</span></span> <span data-ttu-id="bd610-111">如果您想要開始使用少數使用者查看監督的運作方式，您可以略過現在群組設定。</span><span class="sxs-lookup"><span data-stu-id="bd610-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="bd610-112">**步驟 2 （必要）** - [讓組織中可用的監督](configure-supervision-policies.md#MakeAvailable)</span><span class="sxs-lookup"><span data-stu-id="bd610-112">**Step 2 (required)** - [Make supervision available in your organization](configure-supervision-policies.md#MakeAvailable)</span></span>

    <span data-ttu-id="bd610-113">將自己新增至主管檢閱角色群組，以便讓您可以設定原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="bd610-114">擁有此角色指派給任何人可以存取 [**監督**頁面的 [**資料控管**安全性 & 合規性中心中。</span><span class="sxs-lookup"><span data-stu-id="bd610-114">Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security & Compliance Center.</span></span> <span data-ttu-id="bd610-115">若要檢閱的電子郵件裝載於 Exchange Online，每一位檢閱還必須[至 Exchange Online 的遠端 PowerShell 存取](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bd610-115">If email to be reviewed is hosted on Exchange Online, each reviewer must also have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bd610-116">**步驟 3 （選用）** - [設定自訂的敏感資訊類型或自訂的關鍵字字典/lexicons](configure-supervision-policies.md#sensitiveinfo)</span><span class="sxs-lookup"><span data-stu-id="bd610-116">**Step 3 (optional)** - [Configure custom sensitive information types or custom keyword dictionaries/lexicons](configure-supervision-policies.md#sensitiveinfo)</span></span>

    <span data-ttu-id="bd610-117">如果您需要使用的自訂機密資訊類型或自訂的關鍵字字典監督原則，您需要建立啟動監督精靈之前。</span><span class="sxs-lookup"><span data-stu-id="bd610-117">If you need to use a custom sensitive info type or a custom keyword dictionary for your supervision policy, you'll need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="bd610-118">**步驟 4 （必要）** - [設定的監督原則](configure-supervision-policies.md#setupsuper)</span><span class="sxs-lookup"><span data-stu-id="bd610-118">**Step 4 (required)** - [Set up a supervision policy](configure-supervision-policies.md#setupsuper)</span></span>

    <span data-ttu-id="bd610-119">在安全性 & 合規性中心，您將建立監督原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-119">You'll create supervision policies in the Security & Compliance Center.</span></span> <span data-ttu-id="bd610-120">這些原則定義哪些通訊會受到檢閱您組織中，並指定誰應該執行的檢閱。</span><span class="sxs-lookup"><span data-stu-id="bd610-120">These policies define which communications are subject to review in your organization and specifies who should perform reviews.</span></span> <span data-ttu-id="bd610-121">通訊包括電子郵件和 Microsoft Teams 的通訊，以及第 3 廠商平台 （例如 Facebook、 Twitter 等等） 的通訊</span><span class="sxs-lookup"><span data-stu-id="bd610-121">Communications include email and Microsoft Teams communications, as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="bd610-122">**步驟 5-（選用）**[測試您的新監督原則](configure-supervision-policies.md#TestPolicy)</span><span class="sxs-lookup"><span data-stu-id="bd610-122">**Step 5 - (optional)** [Test your new supervision policy](configure-supervision-policies.md#TestPolicy)</span></span>

    <span data-ttu-id="bd610-123">測試您的監督原則，以確保其運作視是確保您的合規性策略會議標準的重要部分。</span><span class="sxs-lookup"><span data-stu-id="bd610-123">Testing your supervision policy to make sure it is functioning as desired is an important part of ensuring that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="bd610-124">**步驟 6-（選用）**[設定 Outlook 的檢閱者不想要使用 Office 365 監督儀表板或 （先前稱為 Outlook Web App） 網頁型 Outlook 來檢閱監督的通訊](configure-supervision-policies.md#UseOutlook)</span><span class="sxs-lookup"><span data-stu-id="bd610-124">**Step 6 - (optional)** [Configure Outlook for reviewers who do not want to use Office 365 supervision dashboard or Outlook on the web (formerly known as Outlook Web App) to review supervised communications](configure-supervision-policies.md#UseOutlook)</span></span>

    <span data-ttu-id="bd610-125">Outlook 可以設定讓檢閱者存取 Outlook 用戶端內的監督功能讓他們可以評估並加以分類每個項目。</span><span class="sxs-lookup"><span data-stu-id="bd610-125">Outlook can be configured to give reviewers access to the supervision functionality within the Outlook client so they can assess and categorize each item.</span></span>

<span data-ttu-id="bd610-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-126"></span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="bd610-127">步驟 1-設定群組的監督 （選用）</span><span class="sxs-lookup"><span data-stu-id="bd610-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="bd610-128">當您建立的監督原則時，您將決定誰會有檢閱其通訊，以及誰可以執行這些檢閱。</span><span class="sxs-lookup"><span data-stu-id="bd610-128">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews.</span></span> <span data-ttu-id="bd610-129">在原則中，您將使用電子郵件地址來識別的個人或群組的人員。</span><span class="sxs-lookup"><span data-stu-id="bd610-129">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="bd610-130">為了簡化您的設定，建立的人必須檢閱其通訊群組和群組的人會檢閱這些通訊。</span><span class="sxs-lookup"><span data-stu-id="bd610-130">To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications.</span></span> <span data-ttu-id="bd610-131">如果您使用的群組，您可能需要數個 — 例如，如果您想要監視的人員，兩個不同的群組之間的通訊，或如果您想要指定不打算要指導的群組。</span><span class="sxs-lookup"><span data-stu-id="bd610-131">If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised.</span></span> <span data-ttu-id="bd610-132">如需如何進行此作業的詳細資訊，請參閱[範例通訊群組](configure-supervision-policies.md#GroupExample)。</span><span class="sxs-lookup"><span data-stu-id="bd610-132">See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span>
  
<span data-ttu-id="bd610-133">若要監管之間或在組織中的群組中的通訊，設定通訊群組在 Exchange 系統管理中心 (前往 [**收件者** \> **群組**)。</span><span class="sxs-lookup"><span data-stu-id="bd610-133">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**).</span></span> <span data-ttu-id="bd610-134">如需設定通訊群組的詳細資訊，請參閱[管理通訊群組](http://go.microsoft.com/fwlink/?LinkId=613635)</span><span class="sxs-lookup"><span data-stu-id="bd610-134">For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd610-135">您也可以使用動態通訊群組或安全性群組的監督如果您偏好。</span><span class="sxs-lookup"><span data-stu-id="bd610-135">You can also use dynamic distribution groups or security groups for supervision if you prefer.</span></span> <span data-ttu-id="bd610-136">若要協助您決定這些是否更妥善地符合貴組織需要，請參閱[管理擁有郵件功能的安全性群組](http://go.microsoft.com/fwlink/?LinkId=627033)及[管理動態通訊群組](http://go.microsoft.com/fwlink/?LinkId=627058)。</span><span class="sxs-lookup"><span data-stu-id="bd610-136">To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span>
  
<span data-ttu-id="bd610-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-137"></span></span>

### <a name="example-distribution-groups"></a><span data-ttu-id="bd610-138">通訊群組範例</span><span class="sxs-lookup"><span data-stu-id="bd610-138">Example distribution groups</span></span>

<span data-ttu-id="bd610-139">此範例會包含已針對名為 Contoso Financial International 財務組織設定的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="bd610-139">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span>
  
<span data-ttu-id="bd610-140">在 Contoso Financial International，必須指導取樣的美國代理人之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="bd610-140">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised.</span></span> <span data-ttu-id="bd610-141">不過，該群組內的法務人員不需要監督。</span><span class="sxs-lookup"><span data-stu-id="bd610-141">However, compliance officers within that group do not require supervision.</span></span> <span data-ttu-id="bd610-142">此範例中，我們可以建立下列群組：</span><span class="sxs-lookup"><span data-stu-id="bd610-142">For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="bd610-143">**設定此通訊群組**</span><span class="sxs-lookup"><span data-stu-id="bd610-143">**Set up this distribution group**</span></span>|<span data-ttu-id="bd610-144">**群組地址 （別名）**</span><span class="sxs-lookup"><span data-stu-id="bd610-144">**Group address (alias)**</span></span>|<span data-ttu-id="bd610-145">**描述**</span><span class="sxs-lookup"><span data-stu-id="bd610-145">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd610-146">所有美國代理人</span><span class="sxs-lookup"><span data-stu-id="bd610-146">All US brokers</span></span> | <span data-ttu-id="bd610-147">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd610-147">US_Brokers@Contoso.com</span></span> | <span data-ttu-id="bd610-148">此群組包含所有美國-任職 Contoso 的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bd610-148">This group includes email addresses for all US-based brokers who work for Contoso.</span></span> |
| <span data-ttu-id="bd610-149">所有美國法務人員</span><span class="sxs-lookup"><span data-stu-id="bd610-149">All US compliance officers</span></span> | <span data-ttu-id="bd610-150">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd610-150">US_Compliance@Contoso.com</span></span>  | <span data-ttu-id="bd610-151">此群組包含所有美國法務人員 Contoso 的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bd610-151">This group includes email addresses for all US-based compliance officers who work for Contoso.</span></span> <span data-ttu-id="bd610-152">由於這個群組是所有美國代理人的子集，因此您可以使用這個別名來免除法務人員從監督原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-152">Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span> |
  
<span data-ttu-id="bd610-153"><a name="MakeAvailable"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-153"></span></span>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="bd610-154">步驟 2-進行監督 （必要） 組織中可用</span><span class="sxs-lookup"><span data-stu-id="bd610-154">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="bd610-155">若要讓**監督**中安全性 & 合規性中心中可用的功能表選項，您必須獲指派的主管檢閱管理員角色。</span><span class="sxs-lookup"><span data-stu-id="bd610-155">To make **Supervision** available as a menu option in the Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="bd610-156">若要這麼做，您可以也將自己新增為主管檢閱角色群組的成員，或您可以建立新的角色群組。</span><span class="sxs-lookup"><span data-stu-id="bd610-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="bd610-157">將成員新增至 [主管檢閱] 角色群組</span><span class="sxs-lookup"><span data-stu-id="bd610-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="bd610-158">登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="bd610-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="bd610-159">在安全性 & 合規性中心，前往 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="bd610-159">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="bd610-160">選取 [**主管檢閱**] 角色群組，然後按一下 [編輯] 圖示。</span><span class="sxs-lookup"><span data-stu-id="bd610-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="bd610-161">在 [**成員**] 區段中，新增您想要管理貴組織的監督的人員。</span><span class="sxs-lookup"><span data-stu-id="bd610-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="bd610-162">建立新的角色群組</span><span class="sxs-lookup"><span data-stu-id="bd610-162">Create a new role group</span></span>

1. <span data-ttu-id="bd610-163">登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="bd610-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="bd610-164">在安全性 & 合規性中心，前往 [**權限**，然後按一下 [新增] (**+**)。</span><span class="sxs-lookup"><span data-stu-id="bd610-164">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="bd610-165">在 [**角色**] 區段中，按一下 [新增 (**+**) 和向下**主管檢閱管理員**捲動。</span><span class="sxs-lookup"><span data-stu-id="bd610-165">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="bd610-166">將此角色新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="bd610-166">Add this role to the role group.</span></span>

4. <span data-ttu-id="bd610-167">在 [**成員**] 區段中，新增您想要管理貴組織的監督的人員。</span><span class="sxs-lookup"><span data-stu-id="bd610-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="bd610-168">如需有關角色群組和權限的詳細資訊，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bd610-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="bd610-169">啟用遠端 PowerShell 存取的檢閱者 （如果電子郵件裝載於 Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="bd610-169">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="bd610-170">請遵循[啟用或停用存取 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指引。</span><span class="sxs-lookup"><span data-stu-id="bd610-170">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

<span data-ttu-id="bd610-171"><a name="sensitiveinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-171"></span></span>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a><span data-ttu-id="bd610-172">步驟 3： 建立自訂機密資訊類型或自訂的關鍵字字典 （選用）</span><span class="sxs-lookup"><span data-stu-id="bd610-172">Step 3 - Create custom sensitive information types or custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="bd610-173">若要從現有的自訂機密資訊類型或自訂的關鍵字字典中監督原則] 精靈中挑選，必須先建立這些項目，如有需要。</span><span class="sxs-lookup"><span data-stu-id="bd610-173">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="bd610-174">建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="bd610-174">Create custom sensitive information types</span></span>

1. <span data-ttu-id="bd610-175">在 Office 365 安全性 & 合規性中心中建立新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="bd610-175">Create a new sensitive information type in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="bd610-176">瀏覽至 **[分類]** \> **敏感資訊類型]，** 然後依照中**新的敏感資訊類型精靈**的步驟。</span><span class="sxs-lookup"><span data-stu-id="bd610-176">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="bd610-177">在這裡您將會：</span><span class="sxs-lookup"><span data-stu-id="bd610-177">Here you will:</span></span>

    - <span data-ttu-id="bd610-178">定義的名稱和描述的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="bd610-178">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="bd610-179">定義接近度信賴等級，主要模式元素</span><span class="sxs-lookup"><span data-stu-id="bd610-179">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="bd610-180">檢閱您的選項，並建立敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="bd610-180">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="bd610-181">如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="bd610-181">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

### <a name="create-custom-keyword-dictionarylexicon"></a><span data-ttu-id="bd610-182">建立自訂的關鍵字字典/lexicon</span><span class="sxs-lookup"><span data-stu-id="bd610-182">Create custom keyword dictionary/lexicon</span></span>

1. <span data-ttu-id="bd610-183">使用文字編輯器 （例如記事本），建立新的檔案，其中包含您想要監視的監督原則的關鍵字字詞。</span><span class="sxs-lookup"><span data-stu-id="bd610-183">Using a text editor (like Notepad), create a new file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="bd610-184">請確定每個字詞是位於個別一行，並以**Unicode/utf-16 (一點 Endian)** 格式儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="bd610-184">Make sure each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>
2. <span data-ttu-id="bd610-185">關鍵字檔案匯入您的 Office 365 租用戶使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="bd610-185">Import the keyword file into your Office 365 tenant using PowerShell.</span></span> <span data-ttu-id="bd610-186">若要連接到 Office 365 powershell，請參閱[Connect to Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bd610-186">To connect to Office 365 with PowerShell, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

    <span data-ttu-id="bd610-187">您已連線至 Office 365 with PowerShell 之後，請執行下列命令，以匯入您的關鍵字字典：</span><span class="sxs-lookup"><span data-stu-id="bd610-187">After you've connected to Office 365 with PowerShell, run the following commands to import your keyword dictionary:</span></span>

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    <span data-ttu-id="bd610-188">如需詳細資訊，請參閱 <<c0>建立關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="bd610-188">For more detailed information, see [Create a keyword dictionary](create-a-keyword-dictionary.md).</span></span>

3. <span data-ttu-id="bd610-189">在 Office 365 安全性 & 合規性中心中建立新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="bd610-189">Create a new sensitive information type in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="bd610-190">瀏覽至 **[分類]** \> **敏感資訊類型]，** 然後依照中**新的敏感資訊類型精靈**的步驟。</span><span class="sxs-lookup"><span data-stu-id="bd610-190">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="bd610-191">在這裡您將會：</span><span class="sxs-lookup"><span data-stu-id="bd610-191">Here you will:</span></span>

    - <span data-ttu-id="bd610-192">定義的名稱和描述的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="bd610-192">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="bd610-193">新增您的自訂字典比對元素的需求</span><span class="sxs-lookup"><span data-stu-id="bd610-193">Add your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="bd610-194">檢閱您的選項，並建立敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="bd610-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="bd610-195">建立自訂字典/lexicon 之後，您可以檢視使用[Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)指令程式的設定的關鍵字或新增和移除使用[組 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)指令程式的字詞。</span><span class="sxs-lookup"><span data-stu-id="bd610-195">After the custom dictionary/lexicon is created, you can view the configured keywords using the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

    <span data-ttu-id="bd610-196">如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="bd610-196">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

<span data-ttu-id="bd610-197"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-197"></span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="bd610-198">步驟 4-設定 （必要） 的監督原則</span><span class="sxs-lookup"><span data-stu-id="bd610-198">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="bd610-199">登入[https://protection.office.com](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="bd610-199">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="bd610-200">在 [安全性 & 合規性中心中，選取**監督**。</span><span class="sxs-lookup"><span data-stu-id="bd610-200">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="bd610-201">選取 [**建立**，然後遵循精靈來設定下列頁面的原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-201">Select **Create** and then follow the wizard to set up the following pages of the policy.</span></span> <span data-ttu-id="bd610-202">使用這個精靈，您會：</span><span class="sxs-lookup"><span data-stu-id="bd610-202">Using the wizard, you will:</span></span>

    - <span data-ttu-id="bd610-203">授與此原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="bd610-203">Give the policy a name and description.</span></span>
    - <span data-ttu-id="bd610-204">選擇使用者或群組来監管，包括 [選擇使用者] 或 [您想要排除的群組。</span><span class="sxs-lookup"><span data-stu-id="bd610-204">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="bd610-205">定義監督原則條件。</span><span class="sxs-lookup"><span data-stu-id="bd610-205">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="bd610-206">選擇您想要包含敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="bd610-206">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="bd610-207">這是您可以在其中選取預設及自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="bd610-207">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="bd610-208">定義要檢閱的通訊的百分比。</span><span class="sxs-lookup"><span data-stu-id="bd610-208">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="bd610-209">選擇 [原則的檢閱者]。</span><span class="sxs-lookup"><span data-stu-id="bd610-209">Choose the reviewers for the policy.</span></span> <span data-ttu-id="bd610-210">檢閱者可以是個別使用者或[擁有郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="bd610-210">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span>
    - <span data-ttu-id="bd610-211">檢閱您的原則選項，並建立原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-211">Review your policy selections and create the policy.</span></span>

<span data-ttu-id="bd610-212"><a name="TestPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-212"></span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="bd610-213">步驟 5-測試 （選擇性） 您監督原則</span><span class="sxs-lookup"><span data-stu-id="bd610-213">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="bd610-214">建立監督原則之後，它是不錯的選項進行測試以確定您定義的條件都要正確地強制執行該原則所。</span><span class="sxs-lookup"><span data-stu-id="bd610-214">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="bd610-215">如果您的監督原則包含敏感資訊類型，您也可能會想要[測試您的資料遺失防護 (DLP) 原則](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="bd610-215">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="bd610-216">請遵循下列步驟來測試您的監督原則：</span><span class="sxs-lookup"><span data-stu-id="bd610-216">Follow the steps below to test your supervision policy:</span></span>

1. <span data-ttu-id="bd610-217">開啟電子郵件用戶端或 Microsoft Teams 以登入您想要測試該的原則所定義的監督使用者。</span><span class="sxs-lookup"><span data-stu-id="bd610-217">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="bd610-218">傳送電子郵件或符合您已定義的監督原則中之準則的 Microsoft Teams 聊天室。</span><span class="sxs-lookup"><span data-stu-id="bd610-218">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="bd610-219">這可以是關鍵字附件大小、 網域、 等等。請確定您判斷您在原則中的現有條件化設定為太嚴格或太廣義。</span><span class="sxs-lookup"><span data-stu-id="bd610-219">This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy is too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="bd610-220">受到定義原則的電子郵件中處理幾近即時和可以用來測試後的原則設定。</span><span class="sxs-lookup"><span data-stu-id="bd610-220">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="bd610-221">Microsoft Teams 中的聊天室 」 可能需要最多 24 小時才完全處理程序中的原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-221">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="bd610-222">登入您的 Office 365 租用戶為監督原則中指定檢閱者。</span><span class="sxs-lookup"><span data-stu-id="bd610-222">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="bd610-223">瀏覽至**監督** > *您的自訂原則* > **開啟**檢視該原則的報告。</span><span class="sxs-lookup"><span data-stu-id="bd610-223">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

<span data-ttu-id="bd610-224"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="bd610-224"></span></span>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a><span data-ttu-id="bd610-225">步驟 6-設定 Outlook 的檢閱者 （選用）</span><span class="sxs-lookup"><span data-stu-id="bd610-225">Step 6 - Configure Outlook for reviewers (optional)</span></span>

<span data-ttu-id="bd610-226">想要使用 Outlook，而不是使用 Office 365 中的監督儀表板，以檢閱通訊的檢閱者必須設定他們的 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="bd610-226">Reviewers that want to use Outlook instead of using the Supervision dashboard in Office 365 to review communications must configure their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="bd610-227">步驟 1： 複製監督信箱的地址</span><span class="sxs-lookup"><span data-stu-id="bd610-227">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="bd610-228">若要設定的 Outlook 桌面檢閱或 outlook 網頁版，您需要的地址監督信箱監督原則安裝過程所建立。</span><span class="sxs-lookup"><span data-stu-id="bd610-228">To configure review for Outlook desktop or Outlook for the web, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd610-229">如果別人建立原則，您需要取得這個地址，才能安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="bd610-229">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="bd610-230">**若要尋找的監督信箱地址**</span><span class="sxs-lookup"><span data-stu-id="bd610-230">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="bd610-231">登入[安全性&amp;合規性中心](https://protection.office.com)使用 Office 365 組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="bd610-231">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="bd610-232">移至**監督**。</span><span class="sxs-lookup"><span data-stu-id="bd610-232">Go to **Supervision**.</span></span>

3. <span data-ttu-id="bd610-233">按一下會收集您想要檢閱的通訊的監督原則。</span><span class="sxs-lookup"><span data-stu-id="bd610-233">Click the supervision policy that's gathering the communications you want to review.</span></span>

4. <span data-ttu-id="bd610-234">在 [原則的詳細資訊彈出式視窗中，[**監督信箱**，複製地址。</span><span class="sxs-lookup"><span data-stu-id="bd610-234">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="bd610-235">![['監督信箱'] 區段中的監督原則的詳細資料彈出式視窗顯示反白顯示的監督信箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="bd610-235">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a><span data-ttu-id="bd610-236">步驟 2： 設定 Outlook 存取的監督信箱</span><span class="sxs-lookup"><span data-stu-id="bd610-236">Step 2: Configure the supervision mailbox for Outlook access</span></span>

<span data-ttu-id="bd610-237">下一步]，檢閱者將必須重新執行幾位 Exchange Online PowerShell 命令，讓他們可以將 Outlook 連線至監督的信箱。</span><span class="sxs-lookup"><span data-stu-id="bd610-237">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="bd610-238">連線至 Exchange Online PowerShell (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="bd610-238">Connect to Exchange Online PowerShell.</span></span> [<span data-ttu-id="bd610-239">該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="bd610-239">How do I do this?</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. <span data-ttu-id="bd610-240">執行下列命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步驟 1 中複製的地址，且*使用者*的檢閱者會連線至步驟 3 中的監督信箱的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd610-240">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="bd610-241">等候至少一個小時再移至步驟 3 下方。</span><span class="sxs-lookup"><span data-stu-id="bd610-241">Wait at least an hour before moving on to Step 3 below.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="bd610-242">步驟 3： 建立的 Outlook 設定檔，以連線至監督信箱</span><span class="sxs-lookup"><span data-stu-id="bd610-242">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="bd610-243">最後一個步驟中，檢閱者將會需要建立的 Outlook 設定檔，以連線至監督信箱。</span><span class="sxs-lookup"><span data-stu-id="bd610-243">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="bd610-244">若要建立新的 Outlook 設定檔，您將使用在 Windows [控制台] 中的 「 信箱 」 設定。</span><span class="sxs-lookup"><span data-stu-id="bd610-244">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel.</span></span> <span data-ttu-id="bd610-245">若要取得這些設定您所採取的路徑可能需取決於您使用的 Windows 作業系統 （Windows 7、 Windows 8 或 Windows 10），以及安裝的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="bd610-245">The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="bd610-246">開啟 [控制台] 中，並在視窗頂端的 [**搜尋**] 方塊中，輸入**郵件**。</span><span class="sxs-lookup"><span data-stu-id="bd610-246">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="bd610-247">(不確定如何取得 Control Panel 嗎？</span><span class="sxs-lookup"><span data-stu-id="bd610-247">(Not sure how to get to the Control Panel?</span></span> <span data-ttu-id="bd610-248">請參閱[所在控制台？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="bd610-248">See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="bd610-249">開啟 [**郵件**應用程式]。</span><span class="sxs-lookup"><span data-stu-id="bd610-249">Open the **Mail** app.</span></span>

3. <span data-ttu-id="bd610-250">在 [**郵件設定的 Outlook**，按一下 [**顯示設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="bd610-250">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="bd610-251">!['郵件安裝程式-Outlook' 與' 顯示設定檔] 按鈕以反白顯示的對話方塊](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="bd610-251">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="bd610-252">在 [**郵件**] 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bd610-252">In **Mail**, click **Add**.</span></span> <span data-ttu-id="bd610-253">然後，在**新的設定檔**，輸入監督信箱 （例如**監督**） 的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd610-253">Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="bd610-254">![在 [設定檔名稱] 方塊中顯示的名稱 '監督' ['新設定檔'] 對話方塊](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="bd610-254">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="bd610-255">在 [**連線至 Office 365 的 Outlook**中，按一下 [**連線到不同的帳戶。**</span><span class="sxs-lookup"><span data-stu-id="bd610-255">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="bd610-256">![具有反白顯示的 [連線到不同的帳戶] 連結的 ' 連線到 Office 365 的 Outlook' 訊息](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="bd610-256">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="bd610-257">在 [**自動帳戶設定**] 中，選擇 [**手動安裝程式或其他伺服器類型**，，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bd610-257">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="bd610-258">在 [**選擇您的帳戶類型**] 中，選擇 [ **Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="bd610-258">In **Choose Your Account Type**, choose **Office 365**.</span></span> <span data-ttu-id="bd610-259">然後，在 [**電子郵件地址**] 方塊中，輸入您先前複製的監督信箱地址。</span><span class="sxs-lookup"><span data-stu-id="bd610-259">Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="bd610-260">![顯示 '電子郵件地址] 方塊中反白顯示在 Outlook 中的 [新增帳戶] 對話方塊的' 選擇您的帳戶類型] 頁面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="bd610-260">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="bd610-261">出現提示時，輸入您的 Office 365 認證。</span><span class="sxs-lookup"><span data-stu-id="bd610-261">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="bd610-262">如果成功，您會看到**監督-\<原則名稱\>** 資料夾列在 Outlook 中的 [資料夾清單] 檢視中。</span><span class="sxs-lookup"><span data-stu-id="bd610-262">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="bd610-263">PowerShell 參考</span><span class="sxs-lookup"><span data-stu-id="bd610-263">PowerShell reference</span></span>

<span data-ttu-id="bd610-264">如有需要您可以建立及管理監督原則使用下列 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bd610-264">If needed, you can create and manage supervision policies using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="bd610-265">新 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="bd610-265">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="bd610-266">取得 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="bd610-266">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="bd610-267">Set-supervisoryreviewpolicyv2</span><span class="sxs-lookup"><span data-stu-id="bd610-267">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="bd610-268">Remove-supervisoryreviewpolicyv2</span><span class="sxs-lookup"><span data-stu-id="bd610-268">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="bd610-269">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="bd610-269">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="bd610-270">Set-supervisoryreviewrule</span><span class="sxs-lookup"><span data-stu-id="bd610-270">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="bd610-271">取得 SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="bd610-271">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="bd610-272">取得 SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="bd610-272">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="bd610-273">取得 SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="bd610-273">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)