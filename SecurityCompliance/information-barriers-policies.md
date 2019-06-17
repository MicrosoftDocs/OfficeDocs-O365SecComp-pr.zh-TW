---
title: 定義資訊屏障原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 瞭解如何在 Microsoft 小組中定義資訊障礙的原則。
ms.openlocfilehash: 8d575d0cde4bfec7109cc302f68beaf1040cd894
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935945"
---
# <a name="define-policies-for-information-barriers-preview"></a><span data-ttu-id="2adf4-103">定義資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2adf4-103">Define policies for information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="2adf4-104">概觀</span><span class="sxs-lookup"><span data-stu-id="2adf4-104">Overview</span></span>

<span data-ttu-id="2adf4-105">有了資訊障礙, 您可以定義原則, 以防止特定的使用者區段相互通訊, 或允許特定的區段只能與特定的其他區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-105">With information barriers, you can define policies that are designed to prevent certain segments of users from communicating with each other, or allow specific segments to communicate only with certain other segments.</span></span> <span data-ttu-id="2adf4-106">資訊屏障原則可協助您的組織維持相關行業標準與法規的合規性, 並避免潛在的利益衝突。</span><span class="sxs-lookup"><span data-stu-id="2adf4-106">Information barrier policies can help your organization maintain compliance with relevant industry standards and regulations, and avoid potential conflicts of interest.</span></span> <span data-ttu-id="2adf4-107">若要深入瞭解, 請參閱[資訊障礙 (預覽)](information-barriers.md)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-107">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span> 

<span data-ttu-id="2adf4-108">本文說明如何規劃、定義、實施及管理資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-108">This article describes how to plan, define, implement, and manage information barrier policies.</span></span> <span data-ttu-id="2adf4-109">涉及數個步驟, 工作流程分成數個部分。</span><span class="sxs-lookup"><span data-stu-id="2adf4-109">Several steps are involved, and the work flow is divided into several parts.</span></span> <span data-ttu-id="2adf4-110">請務必先閱讀[必要條件](#prerequisites)和整個程式, 再開始定義 (或編輯) 資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-110">Make sure to read through the [prerequisites](#prerequisites) and the entire process before you begin defining (or editing) information barrier policies.</span></span>

> [!TIP]
> <span data-ttu-id="2adf4-111">本文包含一個[範例案例](#example-contosos-departments-segments-and-policies)和一個[可下載的 Excel 活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx), 可協助您規劃及定義資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-111">This article includes an [example scenario](#example-contosos-departments-segments-and-policies) and a [downloadable Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) to help you plan and define your information barrier policies.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="2adf4-112">資訊障礙原則的概念</span><span class="sxs-lookup"><span data-stu-id="2adf4-112">Concepts of information barrier policies</span></span>

<span data-ttu-id="2adf4-113">瞭解資訊屏障原則的基礎概念會很有説明:</span><span class="sxs-lookup"><span data-stu-id="2adf4-113">It's helpful to know the underlying concepts of information barrier policies:</span></span>

- <span data-ttu-id="2adf4-114">**使用者帳戶屬性**是在 Azure Active Directory (或 Exchange Online) 中定義的。</span><span class="sxs-lookup"><span data-stu-id="2adf4-114">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="2adf4-115">這些屬性可以包括部門、職稱、位置、小組名稱及其他工作設定檔詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2adf4-115">These attributes can include department, job title, location, team name, and other job profile details.</span></span> 

- <span data-ttu-id="2adf4-116">**區段**是使用選取的**使用者帳戶屬性**, 在 [Office 365 安全性 & 合規性中心] 中定義的使用者集合。</span><span class="sxs-lookup"><span data-stu-id="2adf4-116">**Segments** are sets of users that are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**.</span></span> <span data-ttu-id="2adf4-117">(請參閱[支援的屬性清單](information-barriers-attributes.md))。</span><span class="sxs-lookup"><span data-stu-id="2adf4-117">(See the [list of supported attributes](information-barriers-attributes.md).)</span></span> 

- <span data-ttu-id="2adf4-118">**資訊屏障原則**會決定通訊限制或限制。</span><span class="sxs-lookup"><span data-stu-id="2adf4-118">**Information barrier policies** determine communication limits or restrictions.</span></span> <span data-ttu-id="2adf4-119">當您定義資訊屏障原則時, 您可以選擇兩種原則:</span><span class="sxs-lookup"><span data-stu-id="2adf4-119">When you define information barrier policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="2adf4-120">「封鎖」原則, 可防止某一段與另一個區段通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-120">"Block" policies that prevent one segment from communicating with another segment</span></span>
    - <span data-ttu-id="2adf4-121">允許一段時間只與特定的其他區段進行通訊的「允許」原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-121">"Allow" policies that allow one segment to communicate with only certain other segments</span></span>

- <span data-ttu-id="2adf4-122">**原則應用程式**是在定義所有資訊屏障原則之後完成, 而且您已準備好將它們套用到您的組織中。</span><span class="sxs-lookup"><span data-stu-id="2adf4-122">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="2adf4-123">工作流程概覽</span><span class="sxs-lookup"><span data-stu-id="2adf4-123">The work flow at a glance</span></span>

|<span data-ttu-id="2adf4-124">階段</span><span class="sxs-lookup"><span data-stu-id="2adf4-124">Phase</span></span>    |<span data-ttu-id="2adf4-125">涉及的專案</span><span class="sxs-lookup"><span data-stu-id="2adf4-125">What's involved</span></span>  |
|---------|---------|
|[<span data-ttu-id="2adf4-126">確定符合必要條件</span><span class="sxs-lookup"><span data-stu-id="2adf4-126">Make sure prerequisites are met</span></span>](#prerequisites)     |<span data-ttu-id="2adf4-127">-確認您具備必要的[授權和許可權](information-barriers.md#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="2adf4-127">- Verify that you have the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions)</span></span><br/><span data-ttu-id="2adf4-128">-請確定您組織的目錄包含的資料會反映組織的結構</span><span class="sxs-lookup"><span data-stu-id="2adf4-128">- Make sure that your organization's directory includes data that reflects your organization's structure</span></span><br/><span data-ttu-id="2adf4-129">-啟用 Microsoft 小組的範圍目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="2adf4-129">- Enable scoped directory search for Microsoft Teams</span></span><br/><span data-ttu-id="2adf4-130">-請確定已開啟審核記錄</span><span class="sxs-lookup"><span data-stu-id="2adf4-130">- Make sure audit logging is turned on</span></span><br/><span data-ttu-id="2adf4-131">-使用 PowerShell (提供範例)</span><span class="sxs-lookup"><span data-stu-id="2adf4-131">- Use PowerShell (examples are provided)</span></span><br/><span data-ttu-id="2adf4-132">-提供 Microsoft 小組的系統管理員同意 (包括步驟)</span><span class="sxs-lookup"><span data-stu-id="2adf4-132">- Provide admin consent for Microsoft Teams (steps are included)</span></span>          |
|[<span data-ttu-id="2adf4-133">第1部分: 分割組織中的所有使用者</span><span class="sxs-lookup"><span data-stu-id="2adf4-133">Part 1: Segment all the users in your organization</span></span>](#part-1-segment-users)     |<span data-ttu-id="2adf4-134">-決定所需的原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-134">- Determine what policies are needed</span></span><br/><span data-ttu-id="2adf4-135">-建立要定義的區段清單</span><span class="sxs-lookup"><span data-stu-id="2adf4-135">- Make a list of segments to define</span></span><br/><span data-ttu-id="2adf4-136">-識別要使用的屬性</span><span class="sxs-lookup"><span data-stu-id="2adf4-136">- Identify which attributes to use</span></span><br/><span data-ttu-id="2adf4-137">-以原則篩選的條款定義區段</span><span class="sxs-lookup"><span data-stu-id="2adf4-137">- Define segments in terms of policy filters</span></span>        |
|[<span data-ttu-id="2adf4-138">第2部分: 定義資訊障礙原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-138">Part 2: Define information barrier policies</span></span>](#part-2-define-information-barrier-policies)     |<span data-ttu-id="2adf4-139">-定義您的原則 (尚不適用)</span><span class="sxs-lookup"><span data-stu-id="2adf4-139">- Define your policies (do not apply yet)</span></span><br/><span data-ttu-id="2adf4-140">-選擇兩種類型 (封鎖或允許)</span><span class="sxs-lookup"><span data-stu-id="2adf4-140">- Choose from two kinds (block or allow)</span></span> |
|[<span data-ttu-id="2adf4-141">第3部分: 套用資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-141">Part 3: Apply information barrier policies</span></span>](#part-3-apply-information-barrier-policies)     |<span data-ttu-id="2adf4-142">-將原則設為主動狀態</span><span class="sxs-lookup"><span data-stu-id="2adf4-142">- Set policies to active status</span></span><br/><span data-ttu-id="2adf4-143">-執行原則應用程式</span><span class="sxs-lookup"><span data-stu-id="2adf4-143">- Run the policy application</span></span><br/><span data-ttu-id="2adf4-144">-查看原則狀態</span><span class="sxs-lookup"><span data-stu-id="2adf4-144">- View policy status</span></span>         |
|<span data-ttu-id="2adf4-145">(視需要而來)[編輯區段或原則](#edit-a-segment-or-a-policy)</span><span class="sxs-lookup"><span data-stu-id="2adf4-145">(As needed) [Edit a segment or a policy](#edit-a-segment-or-a-policy)</span></span>     |<span data-ttu-id="2adf4-146">-編輯區段</span><span class="sxs-lookup"><span data-stu-id="2adf4-146">- Edit a segment</span></span><br/><span data-ttu-id="2adf4-147">-編輯或移除原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-147">- Edit or remove a policy</span></span><br/><span data-ttu-id="2adf4-148">-執行原則應用程式</span><span class="sxs-lookup"><span data-stu-id="2adf4-148">- Run the policy application</span></span><br/><span data-ttu-id="2adf4-149">-查看原則狀態</span><span class="sxs-lookup"><span data-stu-id="2adf4-149">- View policy status</span></span>         |
|<span data-ttu-id="2adf4-150">(視需要而來)[疑難排解](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="2adf4-150">(As needed) [Troubleshooting](information-barriers-troubleshooting.md)</span></span>|<span data-ttu-id="2adf4-151">-當事物未如預期運作時採取動作</span><span class="sxs-lookup"><span data-stu-id="2adf4-151">- Take action when things are not working as expected</span></span>|

## <a name="prerequisites"></a><span data-ttu-id="2adf4-152">必要條件</span><span class="sxs-lookup"><span data-stu-id="2adf4-152">Prerequisites</span></span>

<span data-ttu-id="2adf4-153">除了[必要的授權和許可權](information-barriers.md#required-licenses-and-permissions)之外, 請確定符合下列需求:</span><span class="sxs-lookup"><span data-stu-id="2adf4-153">In addition to the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions), make sure that the following requirements are met:</span></span> 
     
- <span data-ttu-id="2adf4-154">**目錄資料**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-154">**Directory data**.</span></span> <span data-ttu-id="2adf4-155">請確定您組織的結構反映在目錄資料中。</span><span class="sxs-lookup"><span data-stu-id="2adf4-155">Make sure that your organization's structure is reflected in directory data.</span></span> <span data-ttu-id="2adf4-156">若要這麼做, 請確定在 Azure Active Directory (或 Exchange Online) 中正確填入使用者帳戶屬性, 例如群組成員資格、部門名稱等等。</span><span class="sxs-lookup"><span data-stu-id="2adf4-156">To do this, make sure that user account attributes, such as group membership, department name, etc. are populated correctly in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="2adf4-157">若要深入瞭解, 請參閱下列資源:</span><span class="sxs-lookup"><span data-stu-id="2adf4-157">To learn more, see the following resources:</span></span>
  - [<span data-ttu-id="2adf4-158">資訊障礙原則的屬性 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2adf4-158">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)
  - [<span data-ttu-id="2adf4-159">使用 Azure Active Directory 新增或更新使用者的設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-159">Add or update a user's profile information using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [<span data-ttu-id="2adf4-160">使用 Office 365 PowerShell 中設定使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="2adf4-160">Configure user account properties with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- <span data-ttu-id="2adf4-161">**範圍目錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-161">**Scoped directory search**.</span></span> <span data-ttu-id="2adf4-162">在您定義組織的第一個資訊屏障原則之前, 您必須[在 Microsoft 小組中啟用範圍目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-162">Before you define your organization's first information barrier policy, you must [enable scoped directory search in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search).</span></span> <span data-ttu-id="2adf4-163">在您設定或定義資訊屏障原則之前, 請至少等候24小時之後啟用範圍目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="2adf4-163">Wait at least 24 hours after enabling scoped directory search before you set up or define information barrier policies.</span></span>

- <span data-ttu-id="2adf4-164">**審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-164">**Audit logging**.</span></span> <span data-ttu-id="2adf4-165">為了查詢原則應用程式的狀態, 必須開啟 audit 記錄。</span><span class="sxs-lookup"><span data-stu-id="2adf4-165">In order to look up the status of a policy application, audit logging must be turned on.</span></span> <span data-ttu-id="2adf4-166">在您開始定義區段或原則之前, 我們建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="2adf4-166">We recommend doing this before you begin to define segments or policies.</span></span> <span data-ttu-id="2adf4-167">若要深入瞭解, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-167">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="2adf4-168">**PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-168">**PowerShell**.</span></span> <span data-ttu-id="2adf4-169">目前, 資訊屏障原則是在 Office 365 安全性 & 合規性中心使用 PowerShell Cmdlet 來定義及管理。</span><span class="sxs-lookup"><span data-stu-id="2adf4-169">Currently, information barrier policies are defined and managed in the Office 365 Security & Compliance Center using PowerShell cmdlets.</span></span> <span data-ttu-id="2adf4-170">雖然本文提供了數個範例, 但是您必須熟悉 PowerShell Cmdlet 和參數。</span><span class="sxs-lookup"><span data-stu-id="2adf4-170">Although several examples are provided in this article, you'll need to be familiar with PowerShell cmdlets and parameters.</span></span> <span data-ttu-id="2adf4-171">連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-171">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="2adf4-172">**Microsoft 小組中資訊障礙的系統管理員同意**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-172">**Admin consent for information barriers in Microsoft Teams**.</span></span> <span data-ttu-id="2adf4-173">當您的原則就緒時, 資訊障礙就可以從交談會話中移除他們不應該在交談中的人員。</span><span class="sxs-lookup"><span data-stu-id="2adf4-173">When your policies are in place, information barriers can remove people from chat sessions they are not supposed to be in.</span></span> <span data-ttu-id="2adf4-174">這有助於確保您的組織符合原則和規定。</span><span class="sxs-lookup"><span data-stu-id="2adf4-174">This helps ensure your organization remains compliant with policies and regulations.</span></span> <span data-ttu-id="2adf4-175">使用下列程式可讓資訊障礙原則在 Microsoft 小組中如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="2adf4-175">Use the following procedure to enable information barrier policies to work as expected in Microsoft Teams.</span></span> 

   1. <span data-ttu-id="2adf4-176">執行下列 PowerShell Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2adf4-176">Run the following PowerShell cmdlets:</span></span>

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. <span data-ttu-id="2adf4-177">出現提示時, 使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2adf4-177">When prompted, sign in using your work or school account for Office 365.</span></span>

   3. <span data-ttu-id="2adf4-178">在 [**要求的許可權**] 對話方塊中, 查看資訊, 然後選擇 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="2adf4-178">In the **Permissions requested** dialog box, review the information, and then choose **Accept**.</span></span>

<span data-ttu-id="2adf4-179">當符合所有必要條件時, 請繼續進行下一節。</span><span class="sxs-lookup"><span data-stu-id="2adf4-179">When all the prerequisites are met, proceed to the next section.</span></span>

> [!TIP]
> <span data-ttu-id="2adf4-180">為協助您準備方案, 本文包含範例案例。</span><span class="sxs-lookup"><span data-stu-id="2adf4-180">To help you prepare your plan, an example scenario is included in this article.</span></span> <span data-ttu-id="2adf4-181">[請參閱 Contoso 的部門、區段及原則](#example-contosos-departments-segments-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-181">[See Contoso's departments, segments, and policies](#example-contosos-departments-segments-and-policies).</span></span><p><span data-ttu-id="2adf4-182">此外, 也可以使用可下載的 Excel 活頁簿, 協助您規劃及定義您的區段和原則 (以及建立您的 PowerShell Cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-182">In addition, a downloadable Excel workbook is available to help you plan and define your segments and policies (and create your PowerShell cmdlets).</span></span> <span data-ttu-id="2adf4-183">[取得活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-183">[Get the workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).</span></span> 

## <a name="part-1-segment-users"></a><span data-ttu-id="2adf4-184">第1部分: 分割使用者</span><span class="sxs-lookup"><span data-stu-id="2adf4-184">Part 1: Segment users</span></span>

<span data-ttu-id="2adf4-185">在這個階段中, 您可以決定所需的資訊屏障原則、建立區段清單以定義, 然後定義您的區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-185">During this phase, you determine what information barrier policies are needed, make a list of segments to define, and then define your segments.</span></span>

### <a name="determine-what-policies-are-needed"></a><span data-ttu-id="2adf4-186">決定所需的原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-186">Determine what policies are needed</span></span>

<span data-ttu-id="2adf4-187">考慮法律和行業法規, 誰是貴組織內需要資訊障礙原則的群組？</span><span class="sxs-lookup"><span data-stu-id="2adf4-187">Considering legal and industry regulations, who are the groups within your organization who will need information barrier policies?</span></span> <span data-ttu-id="2adf4-188">建立清單。</span><span class="sxs-lookup"><span data-stu-id="2adf4-188">Make a list.</span></span> <span data-ttu-id="2adf4-189">是否有任何群組應該防止與其他群組通訊？</span><span class="sxs-lookup"><span data-stu-id="2adf4-189">Are there any groups who should be prevented from communicating with another group?</span></span> <span data-ttu-id="2adf4-190">是否有任何群組應該允許只與一或兩個其他群組通訊？</span><span class="sxs-lookup"><span data-stu-id="2adf4-190">Are there any groups that should be allowed to communicate only with one or two other groups?</span></span> <span data-ttu-id="2adf4-191">請考慮您所需的原則屬於下列兩個群組之一:</span><span class="sxs-lookup"><span data-stu-id="2adf4-191">Think about the policies you need as belonging to one of two groups:</span></span>
- <span data-ttu-id="2adf4-192">「封鎖」原則防止一個群組與另一個群組通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-192">"Block" policies prevent one group from communicating with another group.</span></span>
- <span data-ttu-id="2adf4-193">「允許」原則允許群組僅與特定的其他特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-193">"Allow" policies allow a group to communicate with only certain other, specific groups.</span></span>

<span data-ttu-id="2adf4-194">當您擁有群組和原則的初始清單時, 請繼續識別您將需要的區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-194">When you have your initial list of groups and policies, proceed to identify the segments you'll need.</span></span> 

### <a name="identify-segments"></a><span data-ttu-id="2adf4-195">識別區段</span><span class="sxs-lookup"><span data-stu-id="2adf4-195">Identify segments</span></span>

<span data-ttu-id="2adf4-196">除了您的初始原則清單之外, 請列出您組織的區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-196">In addition to your initial list of policies, make a list of segments for your organization.</span></span> <span data-ttu-id="2adf4-197">您組織中的每位使用者都應屬於某個區段, 且不應屬於兩個或多個區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-197">Every user in your organization should belong to a segment, and no user should belong to two or more segments.</span></span> <span data-ttu-id="2adf4-198">每個區段只能套用一個資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-198">Each segment can have only one information barrier policy applied.</span></span> 

<span data-ttu-id="2adf4-199">決定您要用來定義資料段的組織目錄資料中的哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="2adf4-199">Determine which attributes in your organization's directory data you'll use to define segments.</span></span> <span data-ttu-id="2adf4-200">您可以使用*部門*、 *MemberOf*或任何支援的屬性。</span><span class="sxs-lookup"><span data-stu-id="2adf4-200">You can use *Department*, *MemberOf*, or any of the supported attributes.</span></span> <span data-ttu-id="2adf4-201">請確定您在為所有使用者選取的屬性中都有值。</span><span class="sxs-lookup"><span data-stu-id="2adf4-201">Make sure that you have values in the attribute you select for all users.</span></span> <span data-ttu-id="2adf4-202">[請參閱資訊障礙 (預覽) 支援的屬性清單](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-202">[See the list of supported attributes for information barriers (Preview)](information-barriers-attributes.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2adf4-203">在**繼續下一節之前, 請確定您的目錄資料具有可用來定義資料段的屬性值**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-203">**Before you proceed to the next section, make sure your directory data has values for attributes that you can use to define segments**.</span></span> <span data-ttu-id="2adf4-204">如果您的目錄資料沒有您要使用之屬性的值, 則在繼續進行資訊障礙之前, 必須更新所有使用者帳戶以包含該資訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-204">If your directory data does not have values for the attributes you want to use, then all user accounts must be updated to include that information before you proceed with information barriers.</span></span> <span data-ttu-id="2adf4-205">若要取得這項協助, 請參閱下列資源:</span><span class="sxs-lookup"><span data-stu-id="2adf4-205">To get help with this, see the following resources:</span></span><br/><span data-ttu-id="2adf4-206">- [使用 Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="2adf4-206">- [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span></span><br/><span data-ttu-id="2adf4-207">- [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="2adf4-207">- [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span></span>

### <a name="define-segments-using-powershell"></a><span data-ttu-id="2adf4-208">使用 PowerShell 定義線段</span><span class="sxs-lookup"><span data-stu-id="2adf4-208">Define segments using PowerShell</span></span>

<span data-ttu-id="2adf4-209">定義區段不會影響使用者;它只會設定要定義並套用的資訊屏障原則階段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-209">Defining segments does not effect users; it just sets the stage for information barrier policies to be defined and then applied.</span></span>

1. <span data-ttu-id="2adf4-210">若要定義組織區段, 請使用**OrganizationSegment 指令程式**搭配**UserGroupFilter**參數, 該參數對應至您要使用的[屬性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-210">To define an organizational segment, use the **New-OrganizationSegment** cmdlet with the **UserGroupFilter** parameter that corresponds to the [attribute](information-barriers-attributes.md) you want to use.</span></span> 

    <span data-ttu-id="2adf4-211">句法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-211">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="2adf4-212">範例： `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-212">Example: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span></span>

    <span data-ttu-id="2adf4-213">在此範例中, 名為*hr*的區段是使用*Hr*、[部門] 屬性中的值來定義。</span><span class="sxs-lookup"><span data-stu-id="2adf4-213">In this example, a segment called *HR* is defined using *HR*, a value in the Department attribute.</span></span>

2. <span data-ttu-id="2adf4-214">針對您要定義的每個區段, 重複步驟1。</span><span class="sxs-lookup"><span data-stu-id="2adf4-214">Repeat step 1 for each segment you want to define.</span></span>

    <span data-ttu-id="2adf4-215">在執行每個 Cmdlet 之後, 您應該會看到有關新線段的詳細資料清單。</span><span class="sxs-lookup"><span data-stu-id="2adf4-215">After you run each cmdlet, you should see a list of details about the new segment.</span></span> <span data-ttu-id="2adf4-216">詳細資料包含區段的類型、建立或上次修改的日期, 等等。</span><span class="sxs-lookup"><span data-stu-id="2adf4-216">Details include the segment's type, who created or last modified it, and so on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2adf4-217">**請確定您的區段沒有重迭**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-217">**Make sure that your segments do not overlap**.</span></span> <span data-ttu-id="2adf4-218">您組織中的每個使用者都應屬於一個 (且只有一個) 區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-218">Each user in your organization should belong to one (and only one) segment.</span></span> <span data-ttu-id="2adf4-219">任何使用者都不應該屬於兩個或多個區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-219">No user should belong to two or more segments.</span></span> <span data-ttu-id="2adf4-220">應該為組織中的所有使用者定義區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-220">Segments should be defined for all users in your organization.</span></span> <span data-ttu-id="2adf4-221">(請參閱[範例: Contoso](#contosos-defined-segments)在本文中定義的區段。)</span><span class="sxs-lookup"><span data-stu-id="2adf4-221">(See [Example: Contoso's defined segments](#contosos-defined-segments) in this article.)</span></span>

<span data-ttu-id="2adf4-222">定義您的區段之後, 請繼續定義資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-222">After you have defined your segments, proceed to define information barrier policies.</span></span>

## <a name="part-2-define-information-barrier-policies"></a><span data-ttu-id="2adf4-223">第2部分: 定義資訊障礙原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-223">Part 2: Define information barrier policies</span></span>

<span data-ttu-id="2adf4-224">決定您是否需要防止特定區段之間的通訊, 或限制特定區段的通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-224">Determine whether you need to prevent communications between certain segments, or limit communications to certain segments.</span></span> <span data-ttu-id="2adf4-225">理想情況下, 您會使用最小的原則數目, 以確保您的組織符合法律和行業的需求。</span><span class="sxs-lookup"><span data-stu-id="2adf4-225">Ideally, you'll use the minimum number of policies to ensure your organization is compliant with legal and industry requirements.</span></span>

<span data-ttu-id="2adf4-226">使用您的使用者區段清單, 以及您想要定義的資訊屏障原則, 選取案例, 然後依照步驟進行。</span><span class="sxs-lookup"><span data-stu-id="2adf4-226">With your list of user segments and the information barrier policies you want to define, select a scenario, and then follow the steps.</span></span> 

- [<span data-ttu-id="2adf4-227">案例 1: 封鎖區段之間的通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-227">Scenario 1: Block communications between segments</span></span>](#scenario-1-block-communications-between-segments)
- [<span data-ttu-id="2adf4-228">案例 2: 允許區段只與一個其他區段通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-228">Scenario 2: Allow a segment to communicate only with one other segment</span></span>](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> <span data-ttu-id="2adf4-229">請**確定您在定義原則時, 不會將多個原則指派**給一個區段。</span><span class="sxs-lookup"><span data-stu-id="2adf4-229">**Make sure that as you define policies, you do not assign more than one policy to a segment**.</span></span> <span data-ttu-id="2adf4-230">例如, 如果您為名為*sales*的部門定義一個原則, 請不要為*sales*定義額外的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-230">For example, if you define one policy for a segment called *Sales*, do not define an additional policy for *Sales*.</span></span><p><span data-ttu-id="2adf4-231">此外, 當您定義資訊屏障原則時, 請務必將這些原則設定為非使用中狀態, 直到您準備好要套用這些原則為止。</span><span class="sxs-lookup"><span data-stu-id="2adf4-231">In addition, as you define information barrier policies, make sure to set those policies to inactive status until you are ready to apply them.</span></span> <span data-ttu-id="2adf4-232">定義 (或編輯) 原則不會影響使用者, 直到這些原則設定為 [作用中] 狀態, 然後套用為止。</span><span class="sxs-lookup"><span data-stu-id="2adf4-232">Defining (or editing) policies does not affect users until those policies are set to active status and then applied.</span></span>

<span data-ttu-id="2adf4-233">(請參閱[範例: Contoso 的資訊屏障原則](#contosos-information-barrier-policies)在本文中)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-233">(See [Example: Contoso's information barrier policies](#contosos-information-barrier-policies) in this article.)</span></span>

### <a name="scenario-1-block-communications-between-segments"></a><span data-ttu-id="2adf4-234">案例 1: 封鎖區段之間的通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-234">Scenario 1: Block communications between segments</span></span>

<span data-ttu-id="2adf4-235">當您想要封鎖多個片段之間的通訊時, 您會定義兩個原則: 一個用於每個方向。</span><span class="sxs-lookup"><span data-stu-id="2adf4-235">When you want to block segments from communicating with each other, you define two policies: one for each direction.</span></span> <span data-ttu-id="2adf4-236">每個原則只會封鎖通訊一種方式。</span><span class="sxs-lookup"><span data-stu-id="2adf4-236">Each policy blocks communication one way only.</span></span>

<span data-ttu-id="2adf4-237">例如, 假設您想要封鎖區段 A 與區段 B 之間的通訊。在這種情況下, 您可以定義一個原則, 讓區段 A 無法與欄位 B 通訊, 然後定義第二個原則, 以防止段 B 與區段 A 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-237">For example, suppose you want to block communications between Segment A and Segment B. In this case, you define one policy preventing Segment A from communicating with Segment B, and then define a second policy to prevent Segment B from communicating with Segment A.</span></span>

1. <span data-ttu-id="2adf4-238">若要定義您的第一個封鎖原則, 請使用**InformationBarrierPolicy 指令程式**搭配**SegmentsBlocked**參數。</span><span class="sxs-lookup"><span data-stu-id="2adf4-238">To define your first blocking policy, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter.</span></span> 

    <span data-ttu-id="2adf4-239">句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-239">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span></span>

    <span data-ttu-id="2adf4-240">範例： `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="2adf4-240">Example: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span></span>

    <span data-ttu-id="2adf4-241">在此範例中, 我們為名為*sales*的部門定義一個名為「*銷售-調研*」的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-241">In this example, we defined a policy called *Sales-Research* for a segment called *Sales*.</span></span> <span data-ttu-id="2adf4-242">使用中和套用時, 此原則可防止*銷售*人員與「*調查*」區段中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-242">When active and applied, this policy prevents people in *Sales* from communicating with people in a segment called *Research*.</span></span>

2. <span data-ttu-id="2adf4-243">若要定義第二個封鎖區段, 請再次使用**InformationBarrierPolicy 指令程式**搭配**SegmentsBlocked**參數, 這段時間會將分次還原。</span><span class="sxs-lookup"><span data-stu-id="2adf4-243">To define your second blocking segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter again, this time with the segments reversed.</span></span>

    <span data-ttu-id="2adf4-244">範例： `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="2adf4-244">Example: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span></span>

    <span data-ttu-id="2adf4-245">在此範例中, 我們定義了一個稱為「*調查-銷售*」的原則, 以防止與銷售通訊的資訊檢索。</span><span class="sxs-lookup"><span data-stu-id="2adf4-245">In this example, we defined a policy called *Research-Sales* to prevent Research from communicating with Sales.</span></span>
 
2. <span data-ttu-id="2adf4-246">請繼續執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="2adf4-246">Proceed to one of the following:</span></span>

   - <span data-ttu-id="2adf4-247">(如有需要)[定義原則以允許區段只與一個其他的區段進行通訊](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span><span class="sxs-lookup"><span data-stu-id="2adf4-247">(If needed) [Define a policy to allow a segment to communicate only with one other segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span></span> 
   - <span data-ttu-id="2adf4-248">(在定義所有原則之後)套用[資訊屏障原則](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="2adf4-248">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a><span data-ttu-id="2adf4-249">案例 2: 允許區段只與一個其他區段通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-249">Scenario 2: Allow a segment to communicate only with one other segment</span></span>

1. <span data-ttu-id="2adf4-250">若要允許一個區段只與一個其他區段通訊, 請使用**InformationBarrierPolicy 指令程式**搭配**SegmentsAllowed**參數。</span><span class="sxs-lookup"><span data-stu-id="2adf4-250">To allow one segment to communicate with only one other segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsAllowed** parameter.</span></span> 

    <span data-ttu-id="2adf4-251">句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-251">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span></span>

    <span data-ttu-id="2adf4-252">範例： `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="2adf4-252">Example: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span></span>

    <span data-ttu-id="2adf4-253">在此範例中, 我們定義了一個名為「製造 *-HR* 」 \*\* 的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-253">In this example, we defined a policy called *Manufacturing-HR* for a segment called *Manufacturing*.</span></span> <span data-ttu-id="2adf4-254">使用中和套用時, 此原則可讓*製造*人員只能與稱為*HR*的部門中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-254">When active and applied, this policy allows people in *Manufacturing* to communicate only with people in a segment called *HR*.</span></span> <span data-ttu-id="2adf4-255">(在此情況下, 製造無法與不屬於 HR 的使用者通訊。)</span><span class="sxs-lookup"><span data-stu-id="2adf4-255">(In this case, Manufacturing cannot communicate with users who are not part of HR.)</span></span>

    <span data-ttu-id="2adf4-256">**如有需要, 您可以使用此 Cmdlet 指定多個區段, 如下列兩個範例所示。**</span><span class="sxs-lookup"><span data-stu-id="2adf4-256">**If needed, you can specify multiple segments with this cmdlet, as shown in the following two examples.**</span></span>

    <span data-ttu-id="2adf4-257">句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-257">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span></span>

    <span data-ttu-id="2adf4-258">**範例 1: 定義原則以允許多個區段只與一個其他區段通訊**</span><span class="sxs-lookup"><span data-stu-id="2adf4-258">**Example 1: Define a policy to allow multiple segments to communicate with only one other segment**</span></span>

    `New-InformationBarrierPolicy -Name "ResearchManufacturing-HR" -AssignedSegment "Research, Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    <span data-ttu-id="2adf4-259">在此範例中, 我們定義了一個原則, 讓*調研*和*製造*資料段只能與*HR*進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-259">In this example, we defined a policy that allows the *Research* and *Manufacturing* segments to communicate only with *HR*.</span></span>

    <span data-ttu-id="2adf4-260">**範例 2: 定義原則以允許多個區段只與特定的其他區段進行通訊**</span><span class="sxs-lookup"><span data-stu-id="2adf4-260">**Example 2: Define a policy to allow multiple segments to communicate with only certain other segments**</span></span>    

    `New-InformationBarrierPolicy -Name "SalesMarketing-HRManufacturing" -AssignedSegment "Sales, Marketing" -SegmentsAllowed "HR, Manufacturing" -State Inactive`

    <span data-ttu-id="2adf4-261">在此範例中, 我們定義了一個原則, 讓*銷售*和*行銷*部門只能與*HR*和*製造公司*進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-261">In this example, we defined a policy that allows the *Sales* and *Marketing* segments to communicate with only *HR* and *Manufacturing*.</span></span>

    <span data-ttu-id="2adf4-262">針對您要定義的每個原則, 重複此步驟, 讓特定的區段只能與特定的特定區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-262">Repeat this step for each policy you want to define to allow specific segments to communicate with only certain other specific segments.</span></span>

2. <span data-ttu-id="2adf4-263">請繼續執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="2adf4-263">Proceed to one of the following:</span></span>

   - <span data-ttu-id="2adf4-264">(如有需要)[定義原則以封鎖區段之間的通訊](#scenario-1-block-communications-between-segments)</span><span class="sxs-lookup"><span data-stu-id="2adf4-264">(If needed) [Define a policy to block communications between segments](#scenario-1-block-communications-between-segments)</span></span> 
   - <span data-ttu-id="2adf4-265">(在定義所有原則之後)套用[資訊屏障原則](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="2adf4-265">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

## <a name="part-3-apply-information-barrier-policies"></a><span data-ttu-id="2adf4-266">第3部分: 套用資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-266">Part 3: Apply information barrier policies</span></span>

<span data-ttu-id="2adf4-267">資訊屏障原則在您將其設為 [作用中] 狀態後, 才會生效, 然後套用原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-267">Information barrier policies are not in effect until you set them to active status, and then apply the policies.</span></span>

1. <span data-ttu-id="2adf4-268">使用**InformationBarrierPolicy**指令程式來查看已定義的原則清單。</span><span class="sxs-lookup"><span data-stu-id="2adf4-268">Use the **Get-InformationBarrierPolicy** cmdlet to see a list of policies that have been defined.</span></span> <span data-ttu-id="2adf4-269">記下每個原則的狀態和身分識別 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-269">Note the status and identity (GUID) of each policy.</span></span>

    <span data-ttu-id="2adf4-270">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2adf4-270">Syntax: `Get-InformationBarrierPolicy`</span></span>

2. <span data-ttu-id="2adf4-271">若要將原則設定為 [使用中] 狀態, 請使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並將**State**參數\*\*\*\* 設為 [作用中]。</span><span class="sxs-lookup"><span data-stu-id="2adf4-271">To set a policy to active status, use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and the **State** parameter set to **Active**.</span></span> 

    <span data-ttu-id="2adf4-272">句法`Set-InformationBarrierPolicy -Identity GUID -State Active`</span><span class="sxs-lookup"><span data-stu-id="2adf4-272">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Active`</span></span>

    <span data-ttu-id="2adf4-273">範例： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span><span class="sxs-lookup"><span data-stu-id="2adf4-273">Example: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span></span>
    
    <span data-ttu-id="2adf4-274">在此範例中, 我們設定了 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*為 [使用中] 狀態的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-274">In this example, we set an information barrier policy that has the GUID *43c37853-ea10-4b90-a23d-ab8c93772471* to active status.</span></span>

    <span data-ttu-id="2adf4-275">請視需要對每個原則重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="2adf4-275">Repeat this step as appropriate for each policy.</span></span>

3. <span data-ttu-id="2adf4-276">當您完成將資訊關卡原則設定為 [作用中] 狀態時, 請使用 Office 365 安全性 & 規範中心內的 **「開始-InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2adf4-276">When you have finished setting your information barrier policies to active status, use the **Start-InformationBarrierPoliciesApplication** cmdlet in the Office 365 Security & Compliance Center.</span></span>

    <span data-ttu-id="2adf4-277">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="2adf4-277">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="2adf4-278">在大約半小時之後, 您組織的原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="2adf4-278">After approximately a half hour, policies are applied, user by user, for your organization.</span></span> <span data-ttu-id="2adf4-279">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="2adf4-279">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="2adf4-280">(一般來說, 處理5000使用者帳戶需要大約一小時的時間。)</span><span class="sxs-lookup"><span data-stu-id="2adf4-280">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a><span data-ttu-id="2adf4-281">查看使用者帳戶、區段、原則或原則應用程式的狀態</span><span class="sxs-lookup"><span data-stu-id="2adf4-281">View status of user accounts, segments, policies, or policy application</span></span>

<span data-ttu-id="2adf4-282">您可以使用 PowerShell 來查看使用者帳戶、區段、原則和原則應用程式的狀態, 如下表所列。</span><span class="sxs-lookup"><span data-stu-id="2adf4-282">With PowerShell, you can view status of user accounts, segments, policies, and policy application, as listed in the following table.</span></span>

|<span data-ttu-id="2adf4-283">若要查看此</span><span class="sxs-lookup"><span data-stu-id="2adf4-283">To view this</span></span>  |<span data-ttu-id="2adf4-284">執行</span><span class="sxs-lookup"><span data-stu-id="2adf4-284">Do this</span></span>  |
|---------|---------|
|<span data-ttu-id="2adf4-285">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="2adf4-285">User accounts</span></span>     |<span data-ttu-id="2adf4-286">使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="2adf4-286">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <p><span data-ttu-id="2adf4-287">句法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="2adf4-287">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> <p><span data-ttu-id="2adf4-288">您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="2adf4-288">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p><span data-ttu-id="2adf4-289">範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="2adf4-289">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> <p><span data-ttu-id="2adf4-290">在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="2adf4-290">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> <p><span data-ttu-id="2adf4-291">(您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="2adf4-291">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> <p><span data-ttu-id="2adf4-292">此 Cmdlet 會傳回使用者的相關資訊, 例如屬性值以及所套用的任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-292">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>|
|<span data-ttu-id="2adf4-293">細分</span><span class="sxs-lookup"><span data-stu-id="2adf4-293">Segments</span></span>     |<span data-ttu-id="2adf4-294">使用**OrganizationSegment 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-294">Use the **Get-OrganizationSegment** cmdlet.</span></span><p><span data-ttu-id="2adf4-295">句法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="2adf4-295">Syntax: `Get-OrganizationSegment`</span></span> <p><span data-ttu-id="2adf4-296">這會顯示針對您組織所定義之所有區段的清單。</span><span class="sxs-lookup"><span data-stu-id="2adf4-296">This will display a list of all segments defined for your organization.</span></span>         |
|<span data-ttu-id="2adf4-297">資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-297">Information barrier policies</span></span>     |<span data-ttu-id="2adf4-298">使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-298">Use the **Get-InformationBarrierPolicy** cmdlet.</span></span> <p> <span data-ttu-id="2adf4-299">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2adf4-299">Syntax: `Get-InformationBarrierPolicy`</span></span> <p><span data-ttu-id="2adf4-300">這會顯示已定義的資訊屏障原則及其狀態的清單。</span><span class="sxs-lookup"><span data-stu-id="2adf4-300">This will display a list of information barrier policies that were defined, and their status.</span></span>       |
|<span data-ttu-id="2adf4-301">最新的資訊屏障原則應用程式</span><span class="sxs-lookup"><span data-stu-id="2adf4-301">The most recent information barrier policy application</span></span>     | <span data-ttu-id="2adf4-302">使用**InformationBarrierPoliciesApplicationStatus 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-302">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span> <p><span data-ttu-id="2adf4-303">句法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="2adf4-303">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span><p>    <span data-ttu-id="2adf4-304">這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-304">This will display information about whether policy application completed, failed, or is in progress.</span></span>       |
|<span data-ttu-id="2adf4-305">所有資訊屏障原則應用程式</span><span class="sxs-lookup"><span data-stu-id="2adf4-305">All information barrier policy applications</span></span>|<span data-ttu-id="2adf4-306">執行`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="2adf4-306">Use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span><p><span data-ttu-id="2adf4-307">這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-307">This will display information about whether policy application completed, failed, or is in progress.</span></span>|

## <a name="stop-a-policy-application"></a><span data-ttu-id="2adf4-308">停止原則應用程式</span><span class="sxs-lookup"><span data-stu-id="2adf4-308">Stop a policy application</span></span>

<span data-ttu-id="2adf4-309">如果您已開始套用資訊屏障原則, 而您想要停止套用這些原則, 請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="2adf4-309">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="2adf4-310">請記住, 此程式會花大約30-35 分鐘的時間來開始。</span><span class="sxs-lookup"><span data-stu-id="2adf4-310">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="2adf4-311">若要查看最新資訊屏障原則應用程式的狀態, 請使用**InformationBarrierPoliciesApplicationStatus**指令程式。</span><span class="sxs-lookup"><span data-stu-id="2adf4-311">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="2adf4-312">句法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="2adf4-312">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="2adf4-313">記下應用程式的 GUID。</span><span class="sxs-lookup"><span data-stu-id="2adf4-313">Note the application's GUID.</span></span>

2. <span data-ttu-id="2adf4-314">使用**InformationBarrierPoliciesApplication**指令程式搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="2adf4-314">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="2adf4-315">句法`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="2adf4-315">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="2adf4-316">範例： `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="2adf4-316">Example: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

## <a name="edit-a-segment-or-a-policy"></a><span data-ttu-id="2adf4-317">編輯區段或原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-317">Edit a segment or a policy</span></span>

### <a name="edit-a-segment"></a><span data-ttu-id="2adf4-318">編輯區段</span><span class="sxs-lookup"><span data-stu-id="2adf4-318">Edit a segment</span></span>

1. <span data-ttu-id="2adf4-319">若要查看所有現有的區段, 請使用**OrganizationSegment 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-319">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="2adf4-320">句法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="2adf4-320">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="2adf4-321">您會看到每個區段和詳細資料的清單, 例如區段類型、其 UserGroupFilter 值、建立日期或上次修改者、GUID 等等。</span><span class="sxs-lookup"><span data-stu-id="2adf4-321">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="2adf4-322">列印或儲存您的區段清單供日後參考。</span><span class="sxs-lookup"><span data-stu-id="2adf4-322">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="2adf4-323">例如, 如果您想要編輯某個區段, 您將需要知道其名稱或識別值 (這會與 Identity 參數搭配使用)。</span><span class="sxs-lookup"><span data-stu-id="2adf4-323">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="2adf4-324">若要編輯區段, 請使用**OrganizationSegment 指令程式**搭配**Identity**參數及相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2adf4-324">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="2adf4-325">句法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-325">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="2adf4-326">範例： `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-326">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="2adf4-327">在此範例中, 針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的區段, 我們會將部門名稱更新為 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="2adf4-327">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="2adf4-328">當您完成組織的資料段編輯後, 您可以繼續[定義](#part-2-define-information-barrier-policies)或[編輯](#edit-a-policy)資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-328">When you have finished editing segments for your organization, you can proceed to [define](#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

### <a name="edit-a-policy"></a><span data-ttu-id="2adf4-329">編輯原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-329">Edit a policy</span></span>

1. <span data-ttu-id="2adf4-330">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-330">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="2adf4-331">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2adf4-331">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="2adf4-332">在結果清單中, 識別您要變更的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-332">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="2adf4-333">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="2adf4-333">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="2adf4-334">使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並指定您想要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="2adf4-334">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="2adf4-335">語法 (封鎖分段與其他區段的通訊):</span><span class="sxs-lookup"><span data-stu-id="2adf4-335">Syntax (blocking segments from communicating with other segments):</span></span> 

    `Set-InformationBarrierPolicy -Identity GUID -SegmentsBlocked "segmentname, segmentname"` 

    <span data-ttu-id="2adf4-336">語法 (使區段只能與特定的其他區段通訊):</span><span class="sxs-lookup"><span data-stu-id="2adf4-336">Syntax (enabling segments to communicate only with certain other segments):</span></span>
    
    ``Set-InformationBarrierPolicy -Identity GUID -SegmentsAllowed "segmentname, segmentname"``

    <span data-ttu-id="2adf4-337">範例: 假設原則定義為封鎖與銷售和行銷通訊的調研。</span><span class="sxs-lookup"><span data-stu-id="2adf4-337">Example: Suppose a policy was defined to block Research from communicating with Sales and Marketing.</span></span> <span data-ttu-id="2adf4-338">原則是使用此 Cmdlet 定義的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-338">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span></span>
    
    <span data-ttu-id="2adf4-339">假設我們想要變更它, 讓調查中的人員只能與 HR 中的人通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-339">Suppose we want to change it so that people in Research can only communicate with people in HR.</span></span> <span data-ttu-id="2adf4-340">若要進行這種變更, 我們會使用此 Cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="2adf4-340">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

3. <span data-ttu-id="2adf4-341">當您完成編輯原則時, 請務必套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="2adf4-341">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="2adf4-342">(請參閱套用[資訊屏障原則](#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="2adf4-342">(See [Apply information barrier policies](#part-3-apply-information-barrier-policies).)</span></span>

### <a name="remove-a-policy"></a><span data-ttu-id="2adf4-343">移除原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-343">Remove a policy</span></span>

1. <span data-ttu-id="2adf4-344">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-344">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="2adf4-345">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2adf4-345">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="2adf4-346">在結果清單中, 識別您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-346">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="2adf4-347">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="2adf4-347">Note the policy's GUID and name.</span></span> <span data-ttu-id="2adf4-348">請確定原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="2adf4-348">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="2adf4-349">使用**InformationBarrierPolicy**指令程式搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="2adf4-349">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="2adf4-350">句法`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="2adf4-350">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="2adf4-351">範例: 假設我們想要移除 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-351">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="2adf4-352">若要這麼做, 我們會使用此 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2adf4-352">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="2adf4-353">出現提示時, 請確認變更。</span><span class="sxs-lookup"><span data-stu-id="2adf4-353">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="2adf4-354">針對您要移除的每個原則, 重複步驟1-2。</span><span class="sxs-lookup"><span data-stu-id="2adf4-354">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="2adf4-355">當您完成移除原則時, 請套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="2adf4-355">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="2adf4-356">若要這麼做, 請使用**InformationBarrierPoliciesApplication 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-356">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="2adf4-357">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="2adf4-357">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="2adf4-358">針對您的組織, 會套用使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="2adf4-358">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="2adf4-359">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="2adf4-359">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

### <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="2adf4-360">將原則設定為非使用中狀態</span><span class="sxs-lookup"><span data-stu-id="2adf4-360">Set a policy to inactive status</span></span>

1. <span data-ttu-id="2adf4-361">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-361">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="2adf4-362">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2adf4-362">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="2adf4-363">在結果清單中, 識別您要變更 (或移除) 的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-363">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="2adf4-364">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="2adf4-364">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="2adf4-365">若要將原則的狀態設定為非使用中, 請使用**InformationBarrierPolicy**指令程式搭配 Identity 參數, 並將 State 參數設為非使用中。</span><span class="sxs-lookup"><span data-stu-id="2adf4-365">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="2adf4-366">句法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="2adf4-366">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="2adf4-367">在此範例中, 我們將*43c37853-ea10-4b90-a23d-ab8c9377247*的資訊屏障原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="2adf4-367">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="2adf4-368">若要套用您的變更, 請使用**InformationBarrierPoliciesApplication 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="2adf4-368">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="2adf4-369">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="2adf4-369">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="2adf4-370">針對您的組織, 會套用使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="2adf4-370">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="2adf4-371">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="2adf4-371">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="2adf4-372">(一般來說, 處理5000使用者帳戶需要大約一小時的時間。)</span><span class="sxs-lookup"><span data-stu-id="2adf4-372">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="2adf4-373">此時, 一或多個資訊屏障原則會設為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="2adf4-373">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="2adf4-374">從這裡, 您可以執行下列任何一項操作:</span><span class="sxs-lookup"><span data-stu-id="2adf4-374">From here, you can do any of the following:</span></span>
- <span data-ttu-id="2adf4-375">保留原樣 (原則設定為非作用中的狀態, 對使用者不會有任何影響)</span><span class="sxs-lookup"><span data-stu-id="2adf4-375">Leave it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="2adf4-376">編輯原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-376">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="2adf4-377">移除原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-377">Remove a policy</span></span>](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a><span data-ttu-id="2adf4-378">範例: Contoso 的部門、區段和原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-378">Example: Contoso's departments, segments, and policies</span></span>

<span data-ttu-id="2adf4-379">若要查看組織如何定義區段和原則的方法, 請考慮下列範例。</span><span class="sxs-lookup"><span data-stu-id="2adf4-379">To see how an organization might approach defining segments and policies, consider the following example.</span></span>

### <a name="contosos-departments-and-plan"></a><span data-ttu-id="2adf4-380">Contoso 的部門與計畫</span><span class="sxs-lookup"><span data-stu-id="2adf4-380">Contoso's departments and plan</span></span>

<span data-ttu-id="2adf4-381">Contoso 有五個部門: HR、銷售、行銷、調研和製造。</span><span class="sxs-lookup"><span data-stu-id="2adf4-381">Contoso has five departments: HR, Sales, Marketing, Research, and Manufacturing.</span></span> <span data-ttu-id="2adf4-382">為了維持與業界法規的相容性, 某些部門中的人員不應該與其他部門通訊, 如下表所列:</span><span class="sxs-lookup"><span data-stu-id="2adf4-382">In order to remain compliant with industry regulations, people in some departments are not supposed to communicate with other departments, as listed in the following table:</span></span>

|<span data-ttu-id="2adf4-383">部分</span><span class="sxs-lookup"><span data-stu-id="2adf4-383">Segment</span></span>  |<span data-ttu-id="2adf4-384">可以交談</span><span class="sxs-lookup"><span data-stu-id="2adf4-384">Can talk to</span></span>  |<span data-ttu-id="2adf4-385">無法交談</span><span class="sxs-lookup"><span data-stu-id="2adf4-385">Cannot talk to</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2adf4-386">人力資源</span><span class="sxs-lookup"><span data-stu-id="2adf4-386">HR</span></span>     |<span data-ttu-id="2adf4-387">所有人</span><span class="sxs-lookup"><span data-stu-id="2adf4-387">Everyone</span></span>         |<span data-ttu-id="2adf4-388">(無限制)</span><span class="sxs-lookup"><span data-stu-id="2adf4-388">(no restrictions)</span></span>         |
|<span data-ttu-id="2adf4-389">銷售量</span><span class="sxs-lookup"><span data-stu-id="2adf4-389">Sales</span></span>     |<span data-ttu-id="2adf4-390">HR、行銷、製造業</span><span class="sxs-lookup"><span data-stu-id="2adf4-390">HR, Marketing, Manufacturing</span></span>         |<span data-ttu-id="2adf4-391">參考資料</span><span class="sxs-lookup"><span data-stu-id="2adf4-391">Research</span></span>         |
|<span data-ttu-id="2adf4-392">行銷</span><span class="sxs-lookup"><span data-stu-id="2adf4-392">Marketing</span></span>     |<span data-ttu-id="2adf4-393">所有人</span><span class="sxs-lookup"><span data-stu-id="2adf4-393">Everyone</span></span>         |<span data-ttu-id="2adf4-394">(無限制)</span><span class="sxs-lookup"><span data-stu-id="2adf4-394">(no restrictions)</span></span>         |
|<span data-ttu-id="2adf4-395">參考資料</span><span class="sxs-lookup"><span data-stu-id="2adf4-395">Research</span></span>     |<span data-ttu-id="2adf4-396">HR、行銷、製造業</span><span class="sxs-lookup"><span data-stu-id="2adf4-396">HR, Marketing, Manufacturing</span></span>        |<span data-ttu-id="2adf4-397">銷售量</span><span class="sxs-lookup"><span data-stu-id="2adf4-397">Sales</span></span>     |
|<span data-ttu-id="2adf4-398">製造</span><span class="sxs-lookup"><span data-stu-id="2adf4-398">Manufacturing</span></span> |<span data-ttu-id="2adf4-399">人力資源、行銷</span><span class="sxs-lookup"><span data-stu-id="2adf4-399">HR, Marketing</span></span> |<span data-ttu-id="2adf4-400">非 HR 或 Marketing 以外的任何人</span><span class="sxs-lookup"><span data-stu-id="2adf4-400">Anyone other than HR or Marketing</span></span> |

<span data-ttu-id="2adf4-401">考慮到這一點, Contoso 的計畫包含三種資訊屏障原則:</span><span class="sxs-lookup"><span data-stu-id="2adf4-401">With this in mind, Contoso's plan includes three information barrier policies:</span></span>

1. <span data-ttu-id="2adf4-402">旨在防止銷售人員與調查進行通訊的原則 (和另一個原則, 以防止與銷售通訊的資訊檢索)</span><span class="sxs-lookup"><span data-stu-id="2adf4-402">A policy designed to prevent Sales from communicating with Research (and another policy to prevent Research from communicating with Sales)</span></span>
2. <span data-ttu-id="2adf4-403">一種原則, 其設計目的是讓製造業只能與 HR 和 Marketing 通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-403">A policy designed to allow Manufacturing to communicate with HR and Marketing only</span></span> 

<span data-ttu-id="2adf4-404">您不需要定義 HR 或 Marketing 的原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-404">It's not necessary to define policies for HR or Marketing.</span></span>

### <a name="contosos-defined-segments"></a><span data-ttu-id="2adf4-405">Contoso 的定義區段</span><span class="sxs-lookup"><span data-stu-id="2adf4-405">Contoso's defined segments</span></span>

<span data-ttu-id="2adf4-406">Contoso 會使用 Azure Active Directory 中的部門屬性來定義區段, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2adf4-406">Contoso will use the Department attribute in Azure Active Directory to define segments, as follows:</span></span>

|<span data-ttu-id="2adf4-407">部門</span><span class="sxs-lookup"><span data-stu-id="2adf4-407">Department</span></span>  |<span data-ttu-id="2adf4-408">區段定義</span><span class="sxs-lookup"><span data-stu-id="2adf4-408">Segment Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="2adf4-409">人力資源</span><span class="sxs-lookup"><span data-stu-id="2adf4-409">HR</span></span>     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|<span data-ttu-id="2adf4-410">銷售量</span><span class="sxs-lookup"><span data-stu-id="2adf4-410">Sales</span></span>     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|<span data-ttu-id="2adf4-411">行銷</span><span class="sxs-lookup"><span data-stu-id="2adf4-411">Marketing</span></span>     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|<span data-ttu-id="2adf4-412">參考資料</span><span class="sxs-lookup"><span data-stu-id="2adf4-412">Research</span></span>     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|<span data-ttu-id="2adf4-413">製造</span><span class="sxs-lookup"><span data-stu-id="2adf4-413">Manufacturing</span></span>     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

<span data-ttu-id="2adf4-414">在定義的區段中, Contoso 會繼續定義原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-414">With the segments defined, Contoso proceeds to define policies.</span></span> 

### <a name="contosos-information-barrier-policies"></a><span data-ttu-id="2adf4-415">Contoso 的資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-415">Contoso's information barrier policies</span></span>

<span data-ttu-id="2adf4-416">Contoso 會定義三個原則, 如下表所述:</span><span class="sxs-lookup"><span data-stu-id="2adf4-416">Contoso defines three polices, as described in the following table:</span></span>

|<span data-ttu-id="2adf4-417">原則</span><span class="sxs-lookup"><span data-stu-id="2adf4-417">Policy</span></span>  |<span data-ttu-id="2adf4-418">原則定義</span><span class="sxs-lookup"><span data-stu-id="2adf4-418">Policy Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="2adf4-419">原則 1: 防止銷售與資訊檢索進行通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-419">Policy 1: Prevent Sales from communicating with Research</span></span>     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> <span data-ttu-id="2adf4-420">在此範例中, 資訊屏障原則稱為「*銷售-研究*」。</span><span class="sxs-lookup"><span data-stu-id="2adf4-420">In this example, the information barrier policy is called *Sales-Research*.</span></span> <span data-ttu-id="2adf4-421">使用且套用此原則時, 將有助於防止銷售部門中的使用者與研究資料段中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-421">When this policy is active and applied, it will help prevent users who are in the Sales segment from communicating with users in the Research segment.</span></span> <span data-ttu-id="2adf4-422">這是單向原則;它不會防止研究與銷售進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-422">This is a one-way policy; it won't prevent Research from communicating with Sales.</span></span> <span data-ttu-id="2adf4-423">為此, 需要原則2。</span><span class="sxs-lookup"><span data-stu-id="2adf4-423">For that, Policy 2 is needed.</span></span>      |
|<span data-ttu-id="2adf4-424">原則 2: 防止與銷售通訊的調研</span><span class="sxs-lookup"><span data-stu-id="2adf4-424">Policy 2: Prevent Research from communicating with Sales</span></span>     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> <span data-ttu-id="2adf4-425">在此範例中, 資訊屏障原則稱為「*調研-銷售*」。</span><span class="sxs-lookup"><span data-stu-id="2adf4-425">In this example, the information barrier policy is called *Research-Sales*.</span></span> <span data-ttu-id="2adf4-426">使用且套用此原則時, 將有助於防止研究資料段中的使用者與銷售部門中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-426">When this policy is active and applied, it will help prevent users who are in the Research segment from communicating with users in the Sales segment.</span></span>       |
|<span data-ttu-id="2adf4-427">原則 3: 允許製造業僅與 HR 和 Marketing 通訊</span><span class="sxs-lookup"><span data-stu-id="2adf4-427">Policy 3: Allow Manufacturing to communicate with HR and Marketing only</span></span>     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR, Marketing" -State Inactive` <p><span data-ttu-id="2adf4-428">在這種情況下, 資訊屏障原則稱為*車間-HRMarketing*。</span><span class="sxs-lookup"><span data-stu-id="2adf4-428">In this case, the information barrier policy is called *Manufacturing-HRMarketing*.</span></span> <span data-ttu-id="2adf4-429">使用且套用此原則時, 製造業只能與 HR 和 Marketing 通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-429">When this policy is active and applied, Manufacturing can communicate only with HR and Marketing.</span></span> <span data-ttu-id="2adf4-430">請注意, HR 和 Marketing 不會受到限制, 無法與其他段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2adf4-430">Note that HR and Marketing are not restricted from communicating with other segments.</span></span> |

<span data-ttu-id="2adf4-431">根據定義的區段和原則, Contoso 會執行**InformationBarrierPoliciesApplication**指令程式, 以套用原則。</span><span class="sxs-lookup"><span data-stu-id="2adf4-431">With segments and policies defined, Contoso applies the policies by running the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span> 

<span data-ttu-id="2adf4-432">完成後, Contoso 就符合法律和行業的需求。</span><span class="sxs-lookup"><span data-stu-id="2adf4-432">When that finishes, Contoso is compliant with legal and industry requirements.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2adf4-433">相關文章</span><span class="sxs-lookup"><span data-stu-id="2adf4-433">Related articles</span></span>

[<span data-ttu-id="2adf4-434">取得資訊障礙的概況</span><span class="sxs-lookup"><span data-stu-id="2adf4-434">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="2adf4-435">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="2adf4-435">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="2adf4-436">資訊障礙原則的屬性 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2adf4-436">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="2adf4-437">疑難排解資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2adf4-437">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
