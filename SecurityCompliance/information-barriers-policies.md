---
title: 定義資訊屏障原則
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
description: 瞭解如何在 Microsoft 小組中定義資訊障礙的原則。
ms.openlocfilehash: 4f63d79f59741f74d2ac8167a8cd86717c6f9ec4
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131377"
---
# <a name="define-policies-for-information-barriers-preview"></a><span data-ttu-id="e97b1-103">定義資訊障礙的原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="e97b1-103">Define policies for information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="e97b1-104">概觀</span><span class="sxs-lookup"><span data-stu-id="e97b1-104">Overview</span></span>

<span data-ttu-id="e97b1-105">有了資訊障礙, 您可以定義原則, 以防止特定的使用者區段相互通訊, 或允許特定的區段只能與特定的其他區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-105">With information barriers, you can define policies that are designed to prevent certain segments of users from communicating with each other, or allow specific segments to communicate only with certain other segments.</span></span> <span data-ttu-id="e97b1-106">資訊屏障原則可協助您的組織維持相關行業標準與法規的合規性, 並避免潛在的利益衝突。</span><span class="sxs-lookup"><span data-stu-id="e97b1-106">Information barrier policies can help your organization maintain compliance with relevant industry standards and regulations, and avoid potential conflicts of interest.</span></span> <span data-ttu-id="e97b1-107">若要深入瞭解, 請參閱[資訊障礙 (預覽)](information-barriers.md)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-107">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span> 

<span data-ttu-id="e97b1-108">本文說明如何規劃、定義、實施及管理資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-108">This article describes how to plan, define, implement, and manage information barrier policies.</span></span> <span data-ttu-id="e97b1-109">涉及數個步驟, 工作流程分成數個部分。</span><span class="sxs-lookup"><span data-stu-id="e97b1-109">Several steps are involved, and the work flow is divided into several parts.</span></span> <span data-ttu-id="e97b1-110">請務必先閱讀[必要條件](#prerequisites)和整個程式, 再開始定義 (或編輯) 資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-110">Make sure to read through the [prerequisites](#prerequisites) and the entire process before you begin defining (or editing) information barrier policies.</span></span>

> [!TIP]
> <span data-ttu-id="e97b1-111">本文包含一個[範例案例](#example-contosos-departments-segments-and-policies)和一個[可下載的 Excel 活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx), 可協助您規劃及定義資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-111">This article includes an [example scenario](#example-contosos-departments-segments-and-policies) and a [downloadable Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) to help you plan and define your information barrier policies.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="e97b1-112">資訊障礙原則的概念</span><span class="sxs-lookup"><span data-stu-id="e97b1-112">Concepts of information barrier policies</span></span>

<span data-ttu-id="e97b1-113">瞭解資訊屏障原則的基礎概念會很有説明:</span><span class="sxs-lookup"><span data-stu-id="e97b1-113">It's helpful to know the underlying concepts of information barrier policies:</span></span>

- <span data-ttu-id="e97b1-114">**使用者帳戶屬性**是在 Azure Active Directory (或 Exchange Online) 中定義的。</span><span class="sxs-lookup"><span data-stu-id="e97b1-114">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="e97b1-115">這些屬性可以包括部門、職稱、位置、小組名稱及其他工作設定檔詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e97b1-115">These attributes can include department, job title, location, team name, and other job profile details.</span></span> 

- <span data-ttu-id="e97b1-116">**區段**是使用選取的**使用者帳戶屬性**, 在 [Office 365 安全性 & 合規性中心] 中定義的使用者集合。</span><span class="sxs-lookup"><span data-stu-id="e97b1-116">**Segments** are sets of users that are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**.</span></span> <span data-ttu-id="e97b1-117">(請參閱[支援的屬性清單](information-barriers-attributes.md))。</span><span class="sxs-lookup"><span data-stu-id="e97b1-117">(See the [list of supported attributes](information-barriers-attributes.md).)</span></span> 

- <span data-ttu-id="e97b1-118">**資訊屏障原則**會決定通訊限制或限制。</span><span class="sxs-lookup"><span data-stu-id="e97b1-118">**Information barrier policies** determine communication limits or restrictions.</span></span> <span data-ttu-id="e97b1-119">當您定義資訊屏障原則時, 您可以選擇兩種原則:</span><span class="sxs-lookup"><span data-stu-id="e97b1-119">When you define information barrier policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="e97b1-120">「封鎖」原則會防止一個區段與另一個區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-120">"Block" policies prevent one segment from communicating with another segment.</span></span>
    - <span data-ttu-id="e97b1-121">「允許」原則允許一段時間只與特定的其他區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-121">"Allow" policies allow one segment to communicate with only certain other segments.</span></span>

- <span data-ttu-id="e97b1-122">**原則應用程式**是在定義所有資訊屏障原則之後完成, 而且您已準備好將它們套用到您的組織中。</span><span class="sxs-lookup"><span data-stu-id="e97b1-122">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="e97b1-123">工作流程概覽</span><span class="sxs-lookup"><span data-stu-id="e97b1-123">The work flow at a glance</span></span>

|<span data-ttu-id="e97b1-124">階段</span><span class="sxs-lookup"><span data-stu-id="e97b1-124">Phase</span></span>    |<span data-ttu-id="e97b1-125">涉及的專案</span><span class="sxs-lookup"><span data-stu-id="e97b1-125">What's involved</span></span>  |
|---------|---------|
|[<span data-ttu-id="e97b1-126">確定符合必要條件</span><span class="sxs-lookup"><span data-stu-id="e97b1-126">Make sure prerequisites are met</span></span>](#prerequisites)     |<span data-ttu-id="e97b1-127">-確認您具備必要的[授權和許可權](information-barriers.md#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="e97b1-127">- Verify that you have the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions)</span></span><br/><span data-ttu-id="e97b1-128">-確認您的目錄包含分割使用者的資料</span><span class="sxs-lookup"><span data-stu-id="e97b1-128">- Verify that your directory includes data for segmenting users</span></span><br/><span data-ttu-id="e97b1-129">-啟用 Microsoft 小組的範圍目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="e97b1-129">- Enable scoped directory search for Microsoft Teams</span></span><br/><span data-ttu-id="e97b1-130">-請確定已開啟審核記錄</span><span class="sxs-lookup"><span data-stu-id="e97b1-130">- Make sure audit logging is turned on</span></span><br/><span data-ttu-id="e97b1-131">-使用 PowerShell (提供範例)</span><span class="sxs-lookup"><span data-stu-id="e97b1-131">- Use PowerShell (examples are provided)</span></span><br/><span data-ttu-id="e97b1-132">-提供 Microsoft 小組的系統管理員同意 (包括步驟)</span><span class="sxs-lookup"><span data-stu-id="e97b1-132">- Provide admin consent for Microsoft Teams (steps are included)</span></span>          |
|[<span data-ttu-id="e97b1-133">第1部分: 分割組織中的使用者</span><span class="sxs-lookup"><span data-stu-id="e97b1-133">Part 1: Segment users in your organization</span></span>](#part-1-segment-users)     |<span data-ttu-id="e97b1-134">-決定所需的原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-134">- Determine what policies are needed</span></span><br/><span data-ttu-id="e97b1-135">-建立要定義的區段清單</span><span class="sxs-lookup"><span data-stu-id="e97b1-135">- Make a list of segments to define</span></span><br/><span data-ttu-id="e97b1-136">-識別要使用的屬性</span><span class="sxs-lookup"><span data-stu-id="e97b1-136">- Identify which attributes to use</span></span><br/><span data-ttu-id="e97b1-137">-以原則篩選的條款定義區段</span><span class="sxs-lookup"><span data-stu-id="e97b1-137">- Define segments in terms of policy filters</span></span>        |
|[<span data-ttu-id="e97b1-138">第2部分: 定義資訊障礙原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-138">Part 2: Define information barrier policies</span></span>](#part-2-define-information-barrier-policies)     |<span data-ttu-id="e97b1-139">-定義您的原則 (尚不適用)</span><span class="sxs-lookup"><span data-stu-id="e97b1-139">- Define your policies (do not apply yet)</span></span><br/><span data-ttu-id="e97b1-140">-選擇兩種類型 (封鎖或允許)</span><span class="sxs-lookup"><span data-stu-id="e97b1-140">- Choose from two kinds (block or allow)</span></span> |
|[<span data-ttu-id="e97b1-141">第3部分: 套用資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-141">Part 3: Apply information barrier policies</span></span>](#part-3-apply-information-barrier-policies)     |<span data-ttu-id="e97b1-142">-將原則設為主動狀態</span><span class="sxs-lookup"><span data-stu-id="e97b1-142">- Set policies to active status</span></span><br/><span data-ttu-id="e97b1-143">-執行原則應用程式</span><span class="sxs-lookup"><span data-stu-id="e97b1-143">- Run the policy application</span></span><br/><span data-ttu-id="e97b1-144">-查看原則狀態</span><span class="sxs-lookup"><span data-stu-id="e97b1-144">- View policy status</span></span>         |
|<span data-ttu-id="e97b1-145">(視需要而來)[編輯區段或原則](#edit-a-segment-or-a-policy)</span><span class="sxs-lookup"><span data-stu-id="e97b1-145">(As needed) [Edit a segment or a policy](#edit-a-segment-or-a-policy)</span></span>     |<span data-ttu-id="e97b1-146">-編輯區段</span><span class="sxs-lookup"><span data-stu-id="e97b1-146">- Edit a segment</span></span><br/><span data-ttu-id="e97b1-147">-編輯或移除原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-147">- Edit or remove a policy</span></span><br/><span data-ttu-id="e97b1-148">-執行原則應用程式</span><span class="sxs-lookup"><span data-stu-id="e97b1-148">- Run the policy application</span></span><br/><span data-ttu-id="e97b1-149">-查看原則狀態</span><span class="sxs-lookup"><span data-stu-id="e97b1-149">- View policy status</span></span>         |
|<span data-ttu-id="e97b1-150">(視需要而來)[疑難排解](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="e97b1-150">(As needed) [Troubleshooting](information-barriers-troubleshooting.md)</span></span>|<span data-ttu-id="e97b1-151">-當事物未如預期運作時採取動作</span><span class="sxs-lookup"><span data-stu-id="e97b1-151">- Take action when things are not working as expected</span></span>|

## <a name="prerequisites"></a><span data-ttu-id="e97b1-152">必要條件</span><span class="sxs-lookup"><span data-stu-id="e97b1-152">Prerequisites</span></span>

<span data-ttu-id="e97b1-153">除了[必要的授權和許可權](information-barriers.md#required-licenses-and-permissions)之外, 請確定符合下列需求:</span><span class="sxs-lookup"><span data-stu-id="e97b1-153">In addition to the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions), make sure that the following requirements are met:</span></span> 
     
- <span data-ttu-id="e97b1-154">**目錄資料**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-154">**Directory data**.</span></span> <span data-ttu-id="e97b1-155">請確定您組織的結構反映在目錄資料中。</span><span class="sxs-lookup"><span data-stu-id="e97b1-155">Make sure that your organization's structure is reflected in directory data.</span></span> <span data-ttu-id="e97b1-156">若要這麼做, 請確定在 Azure Active Directory (或 Exchange Online) 中正確填入使用者帳戶屬性, 例如群組成員資格、部門名稱等等。</span><span class="sxs-lookup"><span data-stu-id="e97b1-156">To do this, make sure that user account attributes, such as group membership, department name, etc. are populated correctly in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="e97b1-157">若要深入瞭解, 請參閱下列資源:</span><span class="sxs-lookup"><span data-stu-id="e97b1-157">To learn more, see the following resources:</span></span>
  - [<span data-ttu-id="e97b1-158">資訊障礙原則的屬性 (預覽)</span><span class="sxs-lookup"><span data-stu-id="e97b1-158">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)
  - [<span data-ttu-id="e97b1-159">使用 Azure Active Directory 新增或更新使用者的設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-159">Add or update a user's profile information using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [<span data-ttu-id="e97b1-160">使用 Office 365 PowerShell 中設定使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="e97b1-160">Configure user account properties with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- <span data-ttu-id="e97b1-161">**範圍目錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-161">**Scoped directory search**.</span></span> <span data-ttu-id="e97b1-162">在您定義組織的第一個資訊屏障原則之前, 您必須[在 Microsoft 小組中啟用範圍目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-162">Before you define your organization's first information barrier policy, you must [enable scoped directory search in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search).</span></span> <span data-ttu-id="e97b1-163">在您設定或定義資訊屏障原則之前, 請至少等候24小時之後啟用範圍目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="e97b1-163">Wait at least 24 hours after enabling scoped directory search before you set up or define information barrier policies.</span></span>

- <span data-ttu-id="e97b1-164">**審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-164">**Audit logging**.</span></span> <span data-ttu-id="e97b1-165">為了查詢原則應用程式的狀態, 必須開啟 audit 記錄。</span><span class="sxs-lookup"><span data-stu-id="e97b1-165">In order to look up the status of a policy application, audit logging must be turned on.</span></span> <span data-ttu-id="e97b1-166">在您開始定義區段或原則之前, 我們建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="e97b1-166">We recommend doing this before you begin to define segments or policies.</span></span> <span data-ttu-id="e97b1-167">若要深入瞭解, 請參閱[開啟或關閉 Office 365 audit log search](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-167">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="e97b1-168">**PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-168">**PowerShell**.</span></span> <span data-ttu-id="e97b1-169">目前, 資訊屏障原則是在 Office 365 安全性 & 合規性中心使用 PowerShell Cmdlet 來定義及管理。</span><span class="sxs-lookup"><span data-stu-id="e97b1-169">Currently, information barrier policies are defined and managed in the Office 365 Security & Compliance Center using PowerShell cmdlets.</span></span> <span data-ttu-id="e97b1-170">雖然本文提供了數個範例, 但是您必須熟悉 PowerShell Cmdlet 和參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-170">Although several examples are provided in this article, you'll need to be familiar with PowerShell cmdlets and parameters.</span></span> <span data-ttu-id="e97b1-171">連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-171">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="e97b1-172">**Microsoft 小組中資訊障礙的系統管理員同意**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-172">**Admin consent for information barriers in Microsoft Teams**.</span></span> <span data-ttu-id="e97b1-173">當您的原則就緒時, 資訊障礙就可以從交談會話中移除他們不應該在交談中的人員。</span><span class="sxs-lookup"><span data-stu-id="e97b1-173">When your policies are in place, information barriers can remove people from chat sessions they are not supposed to be in.</span></span> <span data-ttu-id="e97b1-174">這有助於確保您的組織符合原則和規定。</span><span class="sxs-lookup"><span data-stu-id="e97b1-174">This helps ensure your organization remains compliant with policies and regulations.</span></span> <span data-ttu-id="e97b1-175">使用下列程式可讓資訊障礙原則在 Microsoft 小組中如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="e97b1-175">Use the following procedure to enable information barrier policies to work as expected in Microsoft Teams.</span></span> 

   1. <span data-ttu-id="e97b1-176">執行下列 PowerShell Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e97b1-176">Run the following PowerShell cmdlets:</span></span>

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. <span data-ttu-id="e97b1-177">出現提示時, 使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e97b1-177">When prompted, sign in using your work or school account for Office 365.</span></span>

   3. <span data-ttu-id="e97b1-178">在 [**要求的許可權**] 對話方塊中, 查看資訊, 然後選擇 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="e97b1-178">In the **Permissions requested** dialog box, review the information, and then choose **Accept**.</span></span>

<span data-ttu-id="e97b1-179">當符合所有必要條件時, 請繼續進行下一節。</span><span class="sxs-lookup"><span data-stu-id="e97b1-179">When all the prerequisites are met, proceed to the next section.</span></span>

> [!TIP]
> <span data-ttu-id="e97b1-180">為協助您準備方案, 本文包含範例案例。</span><span class="sxs-lookup"><span data-stu-id="e97b1-180">To help you prepare your plan, an example scenario is included in this article.</span></span> <span data-ttu-id="e97b1-181">[請參閱 Contoso 的部門、區段及原則](#example-contosos-departments-segments-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-181">[See Contoso's departments, segments, and policies](#example-contosos-departments-segments-and-policies).</span></span><p><span data-ttu-id="e97b1-182">此外, 也可以使用可下載的 Excel 活頁簿, 協助您規劃及定義您的區段和原則 (以及建立您的 PowerShell Cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-182">In addition, a downloadable Excel workbook is available to help you plan and define your segments and policies (and create your PowerShell cmdlets).</span></span> <span data-ttu-id="e97b1-183">[取得活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-183">[Get the workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).</span></span> 

## <a name="part-1-segment-users"></a><span data-ttu-id="e97b1-184">第1部分: 分割使用者</span><span class="sxs-lookup"><span data-stu-id="e97b1-184">Part 1: Segment users</span></span>

<span data-ttu-id="e97b1-185">在這個階段中, 您可以決定所需的資訊屏障原則、建立區段清單以定義, 然後定義您的區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-185">During this phase, you determine what information barrier policies are needed, make a list of segments to define, and then define your segments.</span></span>

### <a name="determine-what-policies-are-needed"></a><span data-ttu-id="e97b1-186">決定所需的原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-186">Determine what policies are needed</span></span>

<span data-ttu-id="e97b1-187">考慮法律和行業法規, 誰是貴組織內需要資訊障礙原則的群組？</span><span class="sxs-lookup"><span data-stu-id="e97b1-187">Considering legal and industry regulations, who are the groups within your organization who will need information barrier policies?</span></span> <span data-ttu-id="e97b1-188">建立清單。</span><span class="sxs-lookup"><span data-stu-id="e97b1-188">Make a list.</span></span> <span data-ttu-id="e97b1-189">是否有任何群組應該防止與其他群組通訊？</span><span class="sxs-lookup"><span data-stu-id="e97b1-189">Are there any groups who should be prevented from communicating with another group?</span></span> <span data-ttu-id="e97b1-190">是否有任何群組應該允許只與一或兩個其他群組通訊？</span><span class="sxs-lookup"><span data-stu-id="e97b1-190">Are there any groups that should be allowed to communicate only with one or two other groups?</span></span> <span data-ttu-id="e97b1-191">請考慮您所需的原則屬於下列兩個群組之一:</span><span class="sxs-lookup"><span data-stu-id="e97b1-191">Think about the policies you need as belonging to one of two groups:</span></span>
- <span data-ttu-id="e97b1-192">「封鎖」原則防止一個群組與另一個群組通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-192">"Block" policies prevent one group from communicating with another group.</span></span>
- <span data-ttu-id="e97b1-193">「允許」原則允許群組僅與特定的其他特定群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-193">"Allow" policies allow a group to communicate with only certain other, specific groups.</span></span>

<span data-ttu-id="e97b1-194">當您擁有群組和原則的初始清單時, 請繼續識別您將需要的區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-194">When you have your initial list of groups and policies, proceed to identify the segments you'll need.</span></span> 

### <a name="identify-segments"></a><span data-ttu-id="e97b1-195">識別區段</span><span class="sxs-lookup"><span data-stu-id="e97b1-195">Identify segments</span></span>

<span data-ttu-id="e97b1-196">除了您的初始原則清單之外, 請列出您組織的區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-196">In addition to your initial list of policies, make a list of segments for your organization.</span></span> <span data-ttu-id="e97b1-197">將包含在資訊屏障原則中的使用者應該屬於某個區段, 而且使用者不應屬於兩個或多個區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-197">Users who will be included in information barrier policies should belong to a segment, and no user should belong to two or more segments.</span></span> <span data-ttu-id="e97b1-198">每個區段只能套用一個資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-198">Each segment can have only one information barrier policy applied.</span></span> 

<span data-ttu-id="e97b1-199">決定您要用來定義資料段的組織目錄資料中的哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="e97b1-199">Determine which attributes in your organization's directory data you'll use to define segments.</span></span> <span data-ttu-id="e97b1-200">您可以使用*部門*、 *MemberOf*或任何支援的屬性。</span><span class="sxs-lookup"><span data-stu-id="e97b1-200">You can use *Department*, *MemberOf*, or any of the supported attributes.</span></span> <span data-ttu-id="e97b1-201">請確定您為使用者選取的屬性中有值。</span><span class="sxs-lookup"><span data-stu-id="e97b1-201">Make sure that you have values in the attribute you select for users.</span></span> <span data-ttu-id="e97b1-202">[請參閱資訊障礙 (預覽) 支援的屬性清單](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-202">[See the list of supported attributes for information barriers (Preview)](information-barriers-attributes.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e97b1-203">在**繼續下一節之前, 請確定您的目錄資料具有可用來定義資料段的屬性值**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-203">**Before you proceed to the next section, make sure your directory data has values for attributes that you can use to define segments**.</span></span> <span data-ttu-id="e97b1-204">如果您的目錄資料沒有您要使用之屬性的值, 則在繼續進行資訊障礙之前, 必須更新使用者帳戶以包含該資訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-204">If your directory data does not have values for the attributes you want to use, then the user accounts must be updated to include that information before you proceed with information barriers.</span></span> <span data-ttu-id="e97b1-205">若要取得這項協助, 請參閱下列資源:</span><span class="sxs-lookup"><span data-stu-id="e97b1-205">To get help with this, see the following resources:</span></span><br/><span data-ttu-id="e97b1-206">- [使用 Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e97b1-206">- [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span></span><br/><span data-ttu-id="e97b1-207">- [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="e97b1-207">- [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span></span>

### <a name="define-segments-using-powershell"></a><span data-ttu-id="e97b1-208">使用 PowerShell 定義線段</span><span class="sxs-lookup"><span data-stu-id="e97b1-208">Define segments using PowerShell</span></span>

<span data-ttu-id="e97b1-209">定義區段不會影響使用者;它只會設定要定義並套用的資訊屏障原則階段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-209">Defining segments does not effect users; it just sets the stage for information barrier policies to be defined and then applied.</span></span>

<span data-ttu-id="e97b1-210">若要定義組織區段, 請使用**OrganizationSegment 指令程式**搭配**UserGroupFilter**參數, 該參數對應至您要使用的[屬性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-210">To define an organizational segment, use the **New-OrganizationSegment** cmdlet with the **UserGroupFilter** parameter that corresponds to the [attribute](information-barriers-attributes.md) you want to use.</span></span>

<span data-ttu-id="e97b1-211">句法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-211">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

<span data-ttu-id="e97b1-212">範例： `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-212">Example: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span></span>

<span data-ttu-id="e97b1-213">在此範例中, 名為*hr*的區段是使用*Hr*、[*部門*] 屬性中的值來定義。</span><span class="sxs-lookup"><span data-stu-id="e97b1-213">In this example, a segment called *HR* is defined using *HR*, a value in the *Department* attribute.</span></span> <span data-ttu-id="e97b1-214">Cmdlet 的 "-eq" 部分是指 "等於"。</span><span class="sxs-lookup"><span data-stu-id="e97b1-214">The "-eq" portion of the cmdlet refers to "equals."</span></span>

<span data-ttu-id="e97b1-215">請針對您要定義的每個區段重複此程式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-215">Repeat this process for each segment you want to define.</span></span>

<span data-ttu-id="e97b1-216">在執行每個 Cmdlet 之後, 您應該會看到有關新線段的詳細資料清單。</span><span class="sxs-lookup"><span data-stu-id="e97b1-216">After you run each cmdlet, you should see a list of details about the new segment.</span></span> <span data-ttu-id="e97b1-217">詳細資料包含區段的類型、建立或上次修改的日期, 等等。</span><span class="sxs-lookup"><span data-stu-id="e97b1-217">Details include the segment's type, who created or last modified it, and so on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e97b1-218">**請確定您的區段沒有重迭**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-218">**Make sure that your segments do not overlap**.</span></span> <span data-ttu-id="e97b1-219">將受到資訊障礙影響的每個使用者都應屬於一個 (且只有一個) 區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-219">Each user who will be affected by information barriers should belong to one (and only one) segment.</span></span> <span data-ttu-id="e97b1-220">任何使用者都不應該屬於兩個或多個區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-220">No user should belong to two or more segments.</span></span> <span data-ttu-id="e97b1-221">(請參閱[範例: Contoso](#contosos-defined-segments)在本文中定義的區段。)</span><span class="sxs-lookup"><span data-stu-id="e97b1-221">(See [Example: Contoso's defined segments](#contosos-defined-segments) in this article.)</span></span>

<span data-ttu-id="e97b1-222">定義您的區段之後, 請繼續定義資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-222">After you have defined your segments, proceed to define information barrier policies.</span></span>

### <a name="using-equals-and-not-equals-in-segment-definitions"></a><span data-ttu-id="e97b1-223">在區段定義中使用「等於」和「不等於」</span><span class="sxs-lookup"><span data-stu-id="e97b1-223">Using "equals" and "not equals" in segment definitions</span></span>

<span data-ttu-id="e97b1-224">在上方顯示的第一個範例中, 我們定義了「部門等於人力資源」的區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-224">In the first example shown above, we defined a segment such that "Department equals HR."</span></span> <span data-ttu-id="e97b1-225">該線段包含 "等於" 參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-225">That segment included an "equals" parameter.</span></span> <span data-ttu-id="e97b1-226">您也可以使用 "not 等於" 參數來定義線段, 如下列範例所示:</span><span class="sxs-lookup"><span data-stu-id="e97b1-226">You can also define segments using a "not equals" parameter, as shown in the following example:</span></span>

<span data-ttu-id="e97b1-227">句法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-227">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`</span></span>

<span data-ttu-id="e97b1-228">範例： `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-228">Example: `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`</span></span>

<span data-ttu-id="e97b1-229">在此範例中, 我們定義了一個稱為 NotSales 的區段, 其中包含不在銷售的任何人。</span><span class="sxs-lookup"><span data-stu-id="e97b1-229">In this example, we defined a segment called NotSales that includes everyone who is not in Sales.</span></span> <span data-ttu-id="e97b1-230">Cmdlet 的 "-ne" 部分是指 "not equals"。</span><span class="sxs-lookup"><span data-stu-id="e97b1-230">The "-ne" portion of the cmdlet refers to "not equals."</span></span>

<span data-ttu-id="e97b1-231">此外, 您可以使用 "等於" 和 "not =" 參數來定義區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-231">In addition, you can define a segment using both "equals" and "not equals" parameters.</span></span>

<span data-ttu-id="e97b1-232">範例： `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-232">Example: `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`</span></span>

<span data-ttu-id="e97b1-233">在這個範例中, 我們定義了一個稱為*LocalFTE*的區段, 其中包括位於本機的人員, 且其位置未列為*暫時*。</span><span class="sxs-lookup"><span data-stu-id="e97b1-233">In this example, we defined a segment called *LocalFTE* that includes people who are locally located and whose positions are not listed as *Temporary*.</span></span>

## <a name="part-2-define-information-barrier-policies"></a><span data-ttu-id="e97b1-234">第2部分: 定義資訊障礙原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-234">Part 2: Define information barrier policies</span></span>

<span data-ttu-id="e97b1-235">決定您是否需要防止特定區段之間的通訊, 或限制特定區段的通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-235">Determine whether you need to prevent communications between certain segments, or limit communications to certain segments.</span></span> <span data-ttu-id="e97b1-236">理想情況下, 您會使用最小的原則數目, 以確保您的組織符合法律和行業的需求。</span><span class="sxs-lookup"><span data-stu-id="e97b1-236">Ideally, you'll use the minimum number of policies to ensure your organization is compliant with legal and industry requirements.</span></span>

<span data-ttu-id="e97b1-237">使用您的使用者區段清單, 以及您想要定義的資訊屏障原則, 選取案例, 然後依照步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e97b1-237">With your list of user segments and the information barrier policies you want to define, select a scenario, and then follow the steps.</span></span> 

- [<span data-ttu-id="e97b1-238">案例 1: 封鎖區段之間的通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-238">Scenario 1: Block communications between segments</span></span>](#scenario-1-block-communications-between-segments)
- [<span data-ttu-id="e97b1-239">案例 2: 允許區段只與一個其他區段通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-239">Scenario 2: Allow a segment to communicate only with one other segment</span></span>](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> <span data-ttu-id="e97b1-240">請**確定您在定義原則時, 不會將多個原則指派**給一個區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-240">**Make sure that as you define policies, you do not assign more than one policy to a segment**.</span></span> <span data-ttu-id="e97b1-241">例如, 如果您為名為*sales*的部門定義一個原則, 請不要為*sales*定義額外的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-241">For example, if you define one policy for a segment called *Sales*, do not define an additional policy for *Sales*.</span></span><p><span data-ttu-id="e97b1-242">此外, 當您定義資訊屏障原則時, 請務必將這些原則設定為非使用中狀態, 直到您準備好要套用這些原則為止。</span><span class="sxs-lookup"><span data-stu-id="e97b1-242">In addition, as you define information barrier policies, make sure to set those policies to inactive status until you are ready to apply them.</span></span> <span data-ttu-id="e97b1-243">定義 (或編輯) 原則不會影響使用者, 直到這些原則設定為 [作用中] 狀態, 然後套用為止。</span><span class="sxs-lookup"><span data-stu-id="e97b1-243">Defining (or editing) policies does not affect users until those policies are set to active status and then applied.</span></span>

<span data-ttu-id="e97b1-244">(請參閱[範例: Contoso 的資訊屏障原則](#contosos-information-barrier-policies)在本文中)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-244">(See [Example: Contoso's information barrier policies](#contosos-information-barrier-policies) in this article.)</span></span>

### <a name="scenario-1-block-communications-between-segments"></a><span data-ttu-id="e97b1-245">案例 1: 封鎖區段之間的通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-245">Scenario 1: Block communications between segments</span></span>

<span data-ttu-id="e97b1-246">當您想要封鎖多個片段之間的通訊時, 您會定義兩個原則: 一個用於每個方向。</span><span class="sxs-lookup"><span data-stu-id="e97b1-246">When you want to block segments from communicating with each other, you define two policies: one for each direction.</span></span> <span data-ttu-id="e97b1-247">每個原則只會封鎖通訊一種方式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-247">Each policy blocks communication one way only.</span></span>

<span data-ttu-id="e97b1-248">例如, 假設您想要封鎖區段 A 與區段 B 之間的通訊。在這種情況下, 您可以定義一個原則, 讓區段 A 無法與欄位 B 通訊, 然後定義第二個原則, 以防止段 B 與區段 A 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-248">For example, suppose you want to block communications between Segment A and Segment B. In this case, you define one policy preventing Segment A from communicating with Segment B, and then define a second policy to prevent Segment B from communicating with Segment A.</span></span>

1. <span data-ttu-id="e97b1-249">若要定義您的第一個封鎖原則, 請使用**InformationBarrierPolicy 指令程式**搭配**SegmentsBlocked**參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-249">To define your first blocking policy, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter.</span></span> 

    <span data-ttu-id="e97b1-250">句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-250">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`</span></span>

    <span data-ttu-id="e97b1-251">範例： `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="e97b1-251">Example: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span></span>

    <span data-ttu-id="e97b1-252">在此範例中, 我們為名為*sales*的部門定義一個名為「*銷售-調研*」的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-252">In this example, we defined a policy called *Sales-Research* for a segment called *Sales*.</span></span> <span data-ttu-id="e97b1-253">使用中和套用時, 此原則可防止*銷售*人員與「*調查*」區段中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-253">When active and applied, this policy prevents people in *Sales* from communicating with people in a segment called *Research*.</span></span>

2. <span data-ttu-id="e97b1-254">若要定義第二個封鎖區段, 請再次使用**InformationBarrierPolicy 指令程式**搭配**SegmentsBlocked**參數, 這段時間會將分次還原。</span><span class="sxs-lookup"><span data-stu-id="e97b1-254">To define your second blocking segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter again, this time with the segments reversed.</span></span>

    <span data-ttu-id="e97b1-255">範例： `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="e97b1-255">Example: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span></span>

    <span data-ttu-id="e97b1-256">在此範例中, 我們定義了一個稱為「*調查-銷售*」的原則, 以防止與*銷售*通訊的*資訊檢索*。</span><span class="sxs-lookup"><span data-stu-id="e97b1-256">In this example, we defined a policy called *Research-Sales* to prevent *Research* from communicating with *Sales*.</span></span>
 
2. <span data-ttu-id="e97b1-257">請繼續執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="e97b1-257">Proceed to one of the following:</span></span>

   - <span data-ttu-id="e97b1-258">(如有需要)[定義原則以允許區段只與一個其他的區段進行通訊](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span><span class="sxs-lookup"><span data-stu-id="e97b1-258">(If needed) [Define a policy to allow a segment to communicate only with one other segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span></span> 
   - <span data-ttu-id="e97b1-259">(在定義所有原則之後)套用[資訊屏障原則](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="e97b1-259">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a><span data-ttu-id="e97b1-260">案例 2: 允許區段只與一個其他區段通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-260">Scenario 2: Allow a segment to communicate only with one other segment</span></span>

1. <span data-ttu-id="e97b1-261">若要允許一個區段只與一個其他區段通訊, 請使用**InformationBarrierPolicy 指令程式**搭配**SegmentsAllowed**參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-261">To allow one segment to communicate with only one other segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsAllowed** parameter.</span></span> 

    <span data-ttu-id="e97b1-262">句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-262">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`</span></span>

    <span data-ttu-id="e97b1-263">範例： `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="e97b1-263">Example: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span></span>

    <span data-ttu-id="e97b1-264">在此範例中, 我們定義了一個名為「製造 *-HR* 」 \*\* 的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-264">In this example, we defined a policy called *Manufacturing-HR* for a segment called *Manufacturing*.</span></span> <span data-ttu-id="e97b1-265">使用中和套用時, 此原則可讓*製造*人員只能與稱為*HR*的部門中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-265">When active and applied, this policy allows people in *Manufacturing* to communicate only with people in a segment called *HR*.</span></span> <span data-ttu-id="e97b1-266">(在此情況下,*製造*無法與不屬於*HR*的使用者通訊。)</span><span class="sxs-lookup"><span data-stu-id="e97b1-266">(In this case, *Manufacturing* cannot communicate with users who are not part of *HR*.)</span></span>

    <span data-ttu-id="e97b1-267">**如有需要, 您可以使用此 Cmdlet 指定多個區段, 如下列範例所示。**</span><span class="sxs-lookup"><span data-stu-id="e97b1-267">**If needed, you can specify multiple segments with this cmdlet, as shown in the following example.**</span></span>

    <span data-ttu-id="e97b1-268">句法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-268">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`</span></span>

    <span data-ttu-id="e97b1-269">**範例 2: 定義原則以允許區段只與其他兩個區段進行通訊**</span><span class="sxs-lookup"><span data-stu-id="e97b1-269">**Example 2: Define a policy to allow a segment to communicate with only two other segments**</span></span>    

    `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive`

    <span data-ttu-id="e97b1-270">在此範例中, 我們定義了一個原則, 讓*調研*區段只能與*HR*和*製造公司*通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-270">In this example, we defined a policy that allows the *Research* segment to communicate with only *HR* and *Manufacturing*.</span></span>

    <span data-ttu-id="e97b1-271">針對您要定義的每個原則, 重複此步驟, 讓特定的區段只能與特定的特定區段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-271">Repeat this step for each policy you want to define to allow specific segments to communicate with only certain other specific segments.</span></span>

2. <span data-ttu-id="e97b1-272">請繼續執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="e97b1-272">Proceed to one of the following:</span></span>

   - <span data-ttu-id="e97b1-273">(如有需要)[定義原則以封鎖區段之間的通訊](#scenario-1-block-communications-between-segments)</span><span class="sxs-lookup"><span data-stu-id="e97b1-273">(If needed) [Define a policy to block communications between segments](#scenario-1-block-communications-between-segments)</span></span> 
   - <span data-ttu-id="e97b1-274">(在定義所有原則之後)套用[資訊屏障原則](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="e97b1-274">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

## <a name="part-3-apply-information-barrier-policies"></a><span data-ttu-id="e97b1-275">第3部分: 套用資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-275">Part 3: Apply information barrier policies</span></span>

<span data-ttu-id="e97b1-276">資訊屏障原則在您將其設為 [作用中] 狀態後, 才會生效, 然後套用原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-276">Information barrier policies are not in effect until you set them to active status, and then apply the policies.</span></span>

1. <span data-ttu-id="e97b1-277">使用**InformationBarrierPolicy**指令程式來查看已定義的原則清單。</span><span class="sxs-lookup"><span data-stu-id="e97b1-277">Use the **Get-InformationBarrierPolicy** cmdlet to see a list of policies that have been defined.</span></span> <span data-ttu-id="e97b1-278">記下每個原則的狀態和身分識別 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-278">Note the status and identity (GUID) of each policy.</span></span>

    <span data-ttu-id="e97b1-279">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e97b1-279">Syntax: `Get-InformationBarrierPolicy`</span></span>

2. <span data-ttu-id="e97b1-280">若要將原則設定為 [使用中] 狀態, 請使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並將**State**參數\*\*\*\* 設為 [作用中]。</span><span class="sxs-lookup"><span data-stu-id="e97b1-280">To set a policy to active status, use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and the **State** parameter set to **Active**.</span></span> 

    <span data-ttu-id="e97b1-281">句法`Set-InformationBarrierPolicy -Identity GUID -State Active`</span><span class="sxs-lookup"><span data-stu-id="e97b1-281">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Active`</span></span>

    <span data-ttu-id="e97b1-282">範例： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span><span class="sxs-lookup"><span data-stu-id="e97b1-282">Example: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span></span>
    
    <span data-ttu-id="e97b1-283">在此範例中, 我們設定了 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*為 [使用中] 狀態的資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-283">In this example, we set an information barrier policy that has the GUID *43c37853-ea10-4b90-a23d-ab8c93772471* to active status.</span></span>

    <span data-ttu-id="e97b1-284">請視需要對每個原則重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="e97b1-284">Repeat this step as appropriate for each policy.</span></span>

3. <span data-ttu-id="e97b1-285">當您完成將資訊關卡原則設定為 [作用中] 狀態時, 請使用 Office 365 安全性 & 規範中心內的 **「開始-InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e97b1-285">When you have finished setting your information barrier policies to active status, use the **Start-InformationBarrierPoliciesApplication** cmdlet in the Office 365 Security & Compliance Center.</span></span>

    <span data-ttu-id="e97b1-286">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="e97b1-286">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="e97b1-287">在大約半小時之後, 您組織的原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="e97b1-287">After approximately a half hour, policies are applied, user by user, for your organization.</span></span> <span data-ttu-id="e97b1-288">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-288">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="e97b1-289">(一般來說, 處理5000使用者帳戶需要大約一小時的時間。)</span><span class="sxs-lookup"><span data-stu-id="e97b1-289">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a><span data-ttu-id="e97b1-290">查看使用者帳戶、區段、原則或原則應用程式的狀態</span><span class="sxs-lookup"><span data-stu-id="e97b1-290">View status of user accounts, segments, policies, or policy application</span></span>

<span data-ttu-id="e97b1-291">您可以使用 PowerShell 來查看使用者帳戶、區段、原則和原則應用程式的狀態, 如下表所列。</span><span class="sxs-lookup"><span data-stu-id="e97b1-291">With PowerShell, you can view status of user accounts, segments, policies, and policy application, as listed in the following table.</span></span>

|<span data-ttu-id="e97b1-292">若要查看此</span><span class="sxs-lookup"><span data-stu-id="e97b1-292">To view this</span></span>  |<span data-ttu-id="e97b1-293">執行</span><span class="sxs-lookup"><span data-stu-id="e97b1-293">Do this</span></span>  |
|---------|---------|
|<span data-ttu-id="e97b1-294">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e97b1-294">User accounts</span></span>     |<span data-ttu-id="e97b1-295">使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-295">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <p><span data-ttu-id="e97b1-296">句法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="e97b1-296">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> <p><span data-ttu-id="e97b1-297">您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="e97b1-297">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p><span data-ttu-id="e97b1-298">範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="e97b1-298">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> <p><span data-ttu-id="e97b1-299">在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="e97b1-299">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> <p><span data-ttu-id="e97b1-300">(您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="e97b1-300">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> <p><span data-ttu-id="e97b1-301">此 Cmdlet 會傳回使用者的相關資訊, 例如屬性值以及所套用的任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-301">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>|
|<span data-ttu-id="e97b1-302">細分</span><span class="sxs-lookup"><span data-stu-id="e97b1-302">Segments</span></span>     |<span data-ttu-id="e97b1-303">使用**OrganizationSegment 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-303">Use the **Get-OrganizationSegment** cmdlet.</span></span><p><span data-ttu-id="e97b1-304">句法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="e97b1-304">Syntax: `Get-OrganizationSegment`</span></span> <p><span data-ttu-id="e97b1-305">這會顯示針對您組織所定義之所有區段的清單。</span><span class="sxs-lookup"><span data-stu-id="e97b1-305">This will display a list of all segments defined for your organization.</span></span>         |
|<span data-ttu-id="e97b1-306">資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-306">Information barrier policies</span></span>     |<span data-ttu-id="e97b1-307">使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-307">Use the **Get-InformationBarrierPolicy** cmdlet.</span></span> <p> <span data-ttu-id="e97b1-308">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e97b1-308">Syntax: `Get-InformationBarrierPolicy`</span></span> <p><span data-ttu-id="e97b1-309">這會顯示已定義的資訊屏障原則及其狀態的清單。</span><span class="sxs-lookup"><span data-stu-id="e97b1-309">This will display a list of information barrier policies that were defined, and their status.</span></span>       |
|<span data-ttu-id="e97b1-310">最新的資訊屏障原則應用程式</span><span class="sxs-lookup"><span data-stu-id="e97b1-310">The most recent information barrier policy application</span></span>     | <span data-ttu-id="e97b1-311">使用**InformationBarrierPoliciesApplicationStatus 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-311">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span> <p><span data-ttu-id="e97b1-312">句法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="e97b1-312">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span><p>    <span data-ttu-id="e97b1-313">這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-313">This will display information about whether policy application completed, failed, or is in progress.</span></span>       |
|<span data-ttu-id="e97b1-314">所有資訊屏障原則應用程式</span><span class="sxs-lookup"><span data-stu-id="e97b1-314">All information barrier policy applications</span></span>|<span data-ttu-id="e97b1-315">執行`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="e97b1-315">Use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span><p><span data-ttu-id="e97b1-316">這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-316">This will display information about whether policy application completed, failed, or is in progress.</span></span>|

## <a name="stop-a-policy-application"></a><span data-ttu-id="e97b1-317">停止原則應用程式</span><span class="sxs-lookup"><span data-stu-id="e97b1-317">Stop a policy application</span></span>

<span data-ttu-id="e97b1-318">如果您已開始套用資訊屏障原則, 而您想要停止套用這些原則, 請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-318">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="e97b1-319">請記住, 此程式會花大約30-35 分鐘的時間來開始。</span><span class="sxs-lookup"><span data-stu-id="e97b1-319">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="e97b1-320">若要查看最新資訊屏障原則應用程式的狀態, 請使用**InformationBarrierPoliciesApplicationStatus**指令程式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-320">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="e97b1-321">句法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="e97b1-321">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="e97b1-322">記下應用程式的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e97b1-322">Note the application's GUID.</span></span>

2. <span data-ttu-id="e97b1-323">使用**InformationBarrierPoliciesApplication**指令程式搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-323">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="e97b1-324">句法`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="e97b1-324">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="e97b1-325">範例： `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="e97b1-325">Example: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

    <span data-ttu-id="e97b1-326">在此範例中, 我們將停止套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-326">In this example, we are stopping information barrier policies from being applied.</span></span>

## <a name="edit-a-segment-or-a-policy"></a><span data-ttu-id="e97b1-327">編輯區段或原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-327">Edit a segment or a policy</span></span>

### <a name="edit-a-segment"></a><span data-ttu-id="e97b1-328">編輯區段</span><span class="sxs-lookup"><span data-stu-id="e97b1-328">Edit a segment</span></span>

1. <span data-ttu-id="e97b1-329">若要查看所有現有的區段, 請使用**OrganizationSegment 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-329">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="e97b1-330">句法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="e97b1-330">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="e97b1-331">您會看到每個區段和詳細資料的清單, 例如區段類型、其 UserGroupFilter 值、建立日期或上次修改者、GUID 等等。</span><span class="sxs-lookup"><span data-stu-id="e97b1-331">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="e97b1-332">列印或儲存您的區段清單供日後參考。</span><span class="sxs-lookup"><span data-stu-id="e97b1-332">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="e97b1-333">例如, 如果您想要編輯某個區段, 您將需要知道其名稱或識別值 (這會與 Identity 參數搭配使用)。</span><span class="sxs-lookup"><span data-stu-id="e97b1-333">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="e97b1-334">若要編輯區段, 請使用**OrganizationSegment 指令程式**搭配**Identity**參數及相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e97b1-334">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="e97b1-335">句法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-335">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="e97b1-336">範例： `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-336">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="e97b1-337">在此範例中, 針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的區段, 我們會將部門名稱更新為 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="e97b1-337">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="e97b1-338">當您完成組織的資料段編輯後, 您可以繼續[定義](#part-2-define-information-barrier-policies)或[編輯](#edit-a-policy)資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-338">When you have finished editing segments for your organization, you can proceed to [define](#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

### <a name="edit-a-policy"></a><span data-ttu-id="e97b1-339">編輯原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-339">Edit a policy</span></span>

1. <span data-ttu-id="e97b1-340">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-340">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="e97b1-341">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e97b1-341">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="e97b1-342">在結果清單中, 識別您要變更的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-342">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="e97b1-343">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="e97b1-343">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="e97b1-344">使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並指定您想要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="e97b1-344">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="e97b1-345">範例: 假設已定義原則來封鎖*研究*資料段與*銷售*和*行銷*資料段的通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-345">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="e97b1-346">原則是使用此 Cmdlet 定義的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-346">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="e97b1-347">假設我們想要變更它, 讓*研究*部門中的人員只能與*HR*區段中的人通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-347">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="e97b1-348">若要進行這種變更, 我們會使用此 Cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="e97b1-348">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="e97b1-349">在此範例中, 我們將 "SegmentsBlocked" 變更為 "SegmentsAllowed", 並指定*HR*區段。</span><span class="sxs-lookup"><span data-stu-id="e97b1-349">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="e97b1-350">當您完成編輯原則時, 請務必套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="e97b1-350">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="e97b1-351">(請參閱套用[資訊屏障原則](#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="e97b1-351">(See [Apply information barrier policies](#part-3-apply-information-barrier-policies).)</span></span>

### <a name="remove-a-policy"></a><span data-ttu-id="e97b1-352">移除原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-352">Remove a policy</span></span>

1. <span data-ttu-id="e97b1-353">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-353">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="e97b1-354">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e97b1-354">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="e97b1-355">在結果清單中, 識別您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-355">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="e97b1-356">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="e97b1-356">Note the policy's GUID and name.</span></span> <span data-ttu-id="e97b1-357">請確定原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="e97b1-357">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="e97b1-358">使用**InformationBarrierPolicy**指令程式搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="e97b1-358">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="e97b1-359">句法`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="e97b1-359">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="e97b1-360">範例: 假設我們想要移除 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-360">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="e97b1-361">若要這麼做, 我們會使用此 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e97b1-361">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="e97b1-362">出現提示時, 請確認變更。</span><span class="sxs-lookup"><span data-stu-id="e97b1-362">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="e97b1-363">針對您要移除的每個原則, 重複步驟1-2。</span><span class="sxs-lookup"><span data-stu-id="e97b1-363">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="e97b1-364">當您完成移除原則時, 請套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="e97b1-364">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="e97b1-365">若要這麼做, 請使用**InformationBarrierPoliciesApplication 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-365">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="e97b1-366">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="e97b1-366">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="e97b1-367">針對您的組織, 會套用使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="e97b1-367">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="e97b1-368">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-368">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

### <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="e97b1-369">將原則設定為非使用中狀態</span><span class="sxs-lookup"><span data-stu-id="e97b1-369">Set a policy to inactive status</span></span>

1. <span data-ttu-id="e97b1-370">若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-370">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="e97b1-371">句法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e97b1-371">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="e97b1-372">在結果清單中, 識別您要變更 (或移除) 的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-372">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="e97b1-373">記下原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="e97b1-373">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="e97b1-374">若要將原則的狀態設定為非使用中, 請使用**InformationBarrierPolicy**指令程式搭配 Identity 參數, 並將 State 參數設為非使用中。</span><span class="sxs-lookup"><span data-stu-id="e97b1-374">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="e97b1-375">句法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="e97b1-375">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="e97b1-376">在此範例中, 我們將*43c37853-ea10-4b90-a23d-ab8c9377247*的資訊屏障原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="e97b1-376">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="e97b1-377">若要套用您的變更, 請使用**InformationBarrierPoliciesApplication 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="e97b1-377">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="e97b1-378">句法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="e97b1-378">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="e97b1-379">針對您的組織, 會套用使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="e97b1-379">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="e97b1-380">如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="e97b1-380">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="e97b1-381">(一般來說, 處理5000使用者帳戶需要大約一小時的時間。)</span><span class="sxs-lookup"><span data-stu-id="e97b1-381">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="e97b1-382">此時, 一或多個資訊屏障原則會設為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="e97b1-382">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="e97b1-383">從這裡, 您可以執行下列任何一項操作:</span><span class="sxs-lookup"><span data-stu-id="e97b1-383">From here, you can do any of the following:</span></span>
- <span data-ttu-id="e97b1-384">保留原樣 (原則設定為非作用中的狀態對使用者不會有任何影響)</span><span class="sxs-lookup"><span data-stu-id="e97b1-384">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="e97b1-385">編輯原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-385">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="e97b1-386">移除原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-386">Remove a policy</span></span>](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a><span data-ttu-id="e97b1-387">範例: Contoso 的部門、區段和原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-387">Example: Contoso's departments, segments, and policies</span></span>

<span data-ttu-id="e97b1-388">若要查看組織如何定義區段和原則的方法, 請考慮下列範例。</span><span class="sxs-lookup"><span data-stu-id="e97b1-388">To see how an organization might approach defining segments and policies, consider the following example.</span></span>

### <a name="contosos-departments-and-plan"></a><span data-ttu-id="e97b1-389">Contoso 的部門與計畫</span><span class="sxs-lookup"><span data-stu-id="e97b1-389">Contoso's departments and plan</span></span>

<span data-ttu-id="e97b1-390">Contoso 有五個部門: HR、銷售、行銷、調研和製造。</span><span class="sxs-lookup"><span data-stu-id="e97b1-390">Contoso has five departments: HR, Sales, Marketing, Research, and Manufacturing.</span></span> <span data-ttu-id="e97b1-391">為了維持與業界法規的相容性, 某些部門中的人員不應該與其他部門通訊, 如下表所列:</span><span class="sxs-lookup"><span data-stu-id="e97b1-391">In order to remain compliant with industry regulations, people in some departments are not supposed to communicate with other departments, as listed in the following table:</span></span>

|<span data-ttu-id="e97b1-392">部分</span><span class="sxs-lookup"><span data-stu-id="e97b1-392">Segment</span></span>  |<span data-ttu-id="e97b1-393">可以交談</span><span class="sxs-lookup"><span data-stu-id="e97b1-393">Can talk to</span></span>  |<span data-ttu-id="e97b1-394">無法交談</span><span class="sxs-lookup"><span data-stu-id="e97b1-394">Cannot talk to</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e97b1-395">人力資源</span><span class="sxs-lookup"><span data-stu-id="e97b1-395">HR</span></span>     |<span data-ttu-id="e97b1-396">所有人</span><span class="sxs-lookup"><span data-stu-id="e97b1-396">Everyone</span></span>         |<span data-ttu-id="e97b1-397">(無限制)</span><span class="sxs-lookup"><span data-stu-id="e97b1-397">(no restrictions)</span></span>         |
|<span data-ttu-id="e97b1-398">銷售量</span><span class="sxs-lookup"><span data-stu-id="e97b1-398">Sales</span></span>     |<span data-ttu-id="e97b1-399">HR、行銷、製造業</span><span class="sxs-lookup"><span data-stu-id="e97b1-399">HR, Marketing, Manufacturing</span></span>         |<span data-ttu-id="e97b1-400">參考資料</span><span class="sxs-lookup"><span data-stu-id="e97b1-400">Research</span></span>         |
|<span data-ttu-id="e97b1-401">行銷</span><span class="sxs-lookup"><span data-stu-id="e97b1-401">Marketing</span></span>     |<span data-ttu-id="e97b1-402">所有人</span><span class="sxs-lookup"><span data-stu-id="e97b1-402">Everyone</span></span>         |<span data-ttu-id="e97b1-403">(無限制)</span><span class="sxs-lookup"><span data-stu-id="e97b1-403">(no restrictions)</span></span>         |
|<span data-ttu-id="e97b1-404">參考資料</span><span class="sxs-lookup"><span data-stu-id="e97b1-404">Research</span></span>     |<span data-ttu-id="e97b1-405">HR、行銷、製造業</span><span class="sxs-lookup"><span data-stu-id="e97b1-405">HR, Marketing, Manufacturing</span></span>        |<span data-ttu-id="e97b1-406">銷售量</span><span class="sxs-lookup"><span data-stu-id="e97b1-406">Sales</span></span>     |
|<span data-ttu-id="e97b1-407">製造</span><span class="sxs-lookup"><span data-stu-id="e97b1-407">Manufacturing</span></span> |<span data-ttu-id="e97b1-408">人力資源、行銷</span><span class="sxs-lookup"><span data-stu-id="e97b1-408">HR, Marketing</span></span> |<span data-ttu-id="e97b1-409">非 HR 或 Marketing 以外的任何人</span><span class="sxs-lookup"><span data-stu-id="e97b1-409">Anyone other than HR or Marketing</span></span> |

<span data-ttu-id="e97b1-410">考慮到這一點, Contoso 的計畫包含三種資訊屏障原則:</span><span class="sxs-lookup"><span data-stu-id="e97b1-410">With this in mind, Contoso's plan includes three information barrier policies:</span></span>

1. <span data-ttu-id="e97b1-411">旨在防止銷售人員與調查進行通訊的原則 (和另一個原則, 以防止與銷售通訊的資訊檢索)</span><span class="sxs-lookup"><span data-stu-id="e97b1-411">A policy designed to prevent Sales from communicating with Research (and another policy to prevent Research from communicating with Sales)</span></span>
2. <span data-ttu-id="e97b1-412">一種原則, 其設計目的是讓製造業只能與 HR 和 Marketing 通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-412">A policy designed to allow Manufacturing to communicate with HR and Marketing only</span></span> 

<span data-ttu-id="e97b1-413">您不需要定義 HR 或 Marketing 的原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-413">It's not necessary to define policies for HR or Marketing.</span></span>

### <a name="contosos-defined-segments"></a><span data-ttu-id="e97b1-414">Contoso 的定義區段</span><span class="sxs-lookup"><span data-stu-id="e97b1-414">Contoso's defined segments</span></span>

<span data-ttu-id="e97b1-415">Contoso 會使用 Azure Active Directory 中的部門屬性來定義區段, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="e97b1-415">Contoso will use the Department attribute in Azure Active Directory to define segments, as follows:</span></span>

|<span data-ttu-id="e97b1-416">部門</span><span class="sxs-lookup"><span data-stu-id="e97b1-416">Department</span></span>  |<span data-ttu-id="e97b1-417">區段定義</span><span class="sxs-lookup"><span data-stu-id="e97b1-417">Segment Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="e97b1-418">人力資源</span><span class="sxs-lookup"><span data-stu-id="e97b1-418">HR</span></span>     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|<span data-ttu-id="e97b1-419">銷售量</span><span class="sxs-lookup"><span data-stu-id="e97b1-419">Sales</span></span>     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|<span data-ttu-id="e97b1-420">行銷</span><span class="sxs-lookup"><span data-stu-id="e97b1-420">Marketing</span></span>     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|<span data-ttu-id="e97b1-421">參考資料</span><span class="sxs-lookup"><span data-stu-id="e97b1-421">Research</span></span>     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|<span data-ttu-id="e97b1-422">製造</span><span class="sxs-lookup"><span data-stu-id="e97b1-422">Manufacturing</span></span>     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

<span data-ttu-id="e97b1-423">在定義的區段中, Contoso 會繼續定義原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-423">With the segments defined, Contoso proceeds to define policies.</span></span> 

### <a name="contosos-information-barrier-policies"></a><span data-ttu-id="e97b1-424">Contoso 的資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-424">Contoso's information barrier policies</span></span>

<span data-ttu-id="e97b1-425">Contoso 會定義三個原則, 如下表所述:</span><span class="sxs-lookup"><span data-stu-id="e97b1-425">Contoso defines three polices, as described in the following table:</span></span>

|<span data-ttu-id="e97b1-426">原則</span><span class="sxs-lookup"><span data-stu-id="e97b1-426">Policy</span></span>  |<span data-ttu-id="e97b1-427">原則定義</span><span class="sxs-lookup"><span data-stu-id="e97b1-427">Policy Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="e97b1-428">原則 1: 防止銷售與資訊檢索進行通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-428">Policy 1: Prevent Sales from communicating with Research</span></span>     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> <span data-ttu-id="e97b1-429">在此範例中, 資訊屏障原則稱為「*銷售-研究*」。</span><span class="sxs-lookup"><span data-stu-id="e97b1-429">In this example, the information barrier policy is called *Sales-Research*.</span></span> <span data-ttu-id="e97b1-430">使用且套用此原則時, 將有助於防止銷售部門中的使用者與研究資料段中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-430">When this policy is active and applied, it will help prevent users who are in the Sales segment from communicating with users in the Research segment.</span></span> <span data-ttu-id="e97b1-431">這是單向原則;它不會防止研究與銷售進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-431">This is a one-way policy; it won't prevent Research from communicating with Sales.</span></span> <span data-ttu-id="e97b1-432">為此, 需要原則2。</span><span class="sxs-lookup"><span data-stu-id="e97b1-432">For that, Policy 2 is needed.</span></span>      |
|<span data-ttu-id="e97b1-433">原則 2: 防止與銷售通訊的調研</span><span class="sxs-lookup"><span data-stu-id="e97b1-433">Policy 2: Prevent Research from communicating with Sales</span></span>     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> <span data-ttu-id="e97b1-434">在此範例中, 資訊屏障原則稱為「*調研-銷售*」。</span><span class="sxs-lookup"><span data-stu-id="e97b1-434">In this example, the information barrier policy is called *Research-Sales*.</span></span> <span data-ttu-id="e97b1-435">使用且套用此原則時, 將有助於防止研究資料段中的使用者與銷售部門中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-435">When this policy is active and applied, it will help prevent users who are in the Research segment from communicating with users in the Sales segment.</span></span>       |
|<span data-ttu-id="e97b1-436">原則 3: 允許製造業僅與 HR 和 Marketing 通訊</span><span class="sxs-lookup"><span data-stu-id="e97b1-436">Policy 3: Allow Manufacturing to communicate with HR and Marketing only</span></span>     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p><span data-ttu-id="e97b1-437">在這種情況下, 資訊屏障原則稱為*車間-HRMarketing*。</span><span class="sxs-lookup"><span data-stu-id="e97b1-437">In this case, the information barrier policy is called *Manufacturing-HRMarketing*.</span></span> <span data-ttu-id="e97b1-438">使用且套用此原則時, 製造業只能與 HR 和 Marketing 通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-438">When this policy is active and applied, Manufacturing can communicate only with HR and Marketing.</span></span> <span data-ttu-id="e97b1-439">請注意, HR 和 Marketing 不會受到限制, 無法與其他段進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e97b1-439">Note that HR and Marketing are not restricted from communicating with other segments.</span></span> |

<span data-ttu-id="e97b1-440">根據定義的區段和原則, Contoso 會執行**InformationBarrierPoliciesApplication**指令程式, 以套用原則。</span><span class="sxs-lookup"><span data-stu-id="e97b1-440">With segments and policies defined, Contoso applies the policies by running the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span> 

<span data-ttu-id="e97b1-441">完成後, Contoso 就符合法律和行業的需求。</span><span class="sxs-lookup"><span data-stu-id="e97b1-441">When that finishes, Contoso is compliant with legal and industry requirements.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e97b1-442">相關文章</span><span class="sxs-lookup"><span data-stu-id="e97b1-442">Related articles</span></span>

[<span data-ttu-id="e97b1-443">取得資訊障礙的概況</span><span class="sxs-lookup"><span data-stu-id="e97b1-443">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="e97b1-444">深入瞭解 Microsoft 小組中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="e97b1-444">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="e97b1-445">資訊障礙原則的屬性 (預覽)</span><span class="sxs-lookup"><span data-stu-id="e97b1-445">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="e97b1-446">疑難排解資訊障礙 (預覽)</span><span class="sxs-lookup"><span data-stu-id="e97b1-446">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
