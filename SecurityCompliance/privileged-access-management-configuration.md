---
title: 在 Office 365 中設定權限的存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入了解 Office 365 中設定權限的存取管理使用本主題
ms.openlocfilehash: 47cae93a41b0fd60645021f6f299645777a9a2e1
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011839"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="d10ec-103">在 Office 365 中設定權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="d10ec-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d10ec-104">本主題涵蓋功能僅在 Office 365 E5 和進階規範 Sku 中目前可用的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="d10ec-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="d10ec-p101">本主題將引導您完成啟用及設定 Office 365 組織中的權限的存取管理。您可以使用其中一個 Microsoft 365 系統管理中心或 Exchange Management PowerShell 來管理並使用特殊權限存取。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="d10ec-107">啟用並設定權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="d10ec-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="d10ec-108">請遵循下列步驟來設定和 Office 365 組織中使用特殊權限的存取：</span><span class="sxs-lookup"><span data-stu-id="d10ec-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="d10ec-109">步驟 1： 建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="d10ec-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="d10ec-p102">在您開始使用最低權限存取之前，請決定誰將擁有的傳入要求提高權限與權限工作的存取權核准授權單位。任何已核准者的群組之一部分的使用者將能夠核准存取要求。這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="d10ec-113">步驟 2： 啟用權限的存取</span><span class="sxs-lookup"><span data-stu-id="d10ec-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="d10ec-114">權限的存取必須明確開啟 Office 365 中使用的預設核准者群組與包括一組您想要排除的權限的存取管理存取控制的系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="d10ec-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="d10ec-115">步驟 3： 建立存取原則</span><span class="sxs-lookup"><span data-stu-id="d10ec-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="d10ec-p103">建立核准原則可讓您定義在個別工作設定範圍的特定核准需求。核准類型選項會**自動**或**手動**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="d10ec-118">步驟 4： 送出/核准權限的存取權要求</span><span class="sxs-lookup"><span data-stu-id="d10ec-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="d10ec-p104">一次啟用的權限存取需要核准在執行任何具有相關聯的核准原則所定義的工作。使用者執行工作包含在需要核准原則必須要求並以具有執行工作所需的權限授與存取權核准。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="d10ec-p105">會授與核准之後，要求使用者可執行預定的工作及權限的存取將授權及使用者代理執行工作。核准保持有效的要求期間 （預設持續時間為 4 小時） 的期間要求者可執行預定的任務多次。所有這類執行記錄且可供安全性及規範稽核。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="d10ec-p106">如果您想要使用 Exchange Management PowerShell 來啟用及設定權限的存取，請遵循[Connect to Exchange Online PowerShell 中使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)連線至您的 Office 365 與 Exchange Online PowerShell 中的步驟認證。您不需要啟用的 Office 365 組織使用的步驟來連線至 Exchange Online PowerShell 時啟用權限的存取多重要素驗證。以多重要素驗證連線建立簽署您要求的權限存取所使用的 OAuth 權杖。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="d10ec-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="d10ec-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="d10ec-128">步驟 1-建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="d10ec-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="d10ec-129">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d10ec-130">在管理中心中，移至 [**群組** > **加入群組**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="d10ec-131">選取**啟用郵件功能的安全性群組**群組類型，然後完成 [新群組的**名稱**、**群組電子郵件地址**和**Description**欄位。</span><span class="sxs-lookup"><span data-stu-id="d10ec-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="d10ec-p107">儲存群組。可能需要幾分鐘的完整設定與顯示在 Office 365 系統管理中心中的群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="d10ec-134">選取新核准者群組並選取 [**編輯**] 以將使用者新增至群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="d10ec-135">儲存群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-135">Save the group.</span></span>

<span data-ttu-id="d10ec-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="d10ec-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="d10ec-137">步驟 2-啟用權限的存取</span><span class="sxs-lookup"><span data-stu-id="d10ec-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-138">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-139">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d10ec-140">在管理中心中，移至**設定 > 安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-141">啟用**需要核准權限的存取**控制。</span><span class="sxs-lookup"><span data-stu-id="d10ec-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="d10ec-142">指定您在做為**預設的核准者群組**的步驟 1 中建立核准者群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="d10ec-143">**儲存**並**關閉**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-144">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-145">若要啟用權限的存取及核准者群組指派 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d10ec-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="d10ec-146">範例：</span><span class="sxs-lookup"><span data-stu-id="d10ec-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="d10ec-147">功能可供以確保您的組織內特定 automations 系統帳戶可以不相依性運作權限存取、 但還是建議也是這類排除是例外以及那些允許應該核准和稽核定期。</span><span class="sxs-lookup"><span data-stu-id="d10ec-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="d10ec-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="d10ec-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="d10ec-149">步驟 3-建立存取原則</span><span class="sxs-lookup"><span data-stu-id="d10ec-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="d10ec-150">您可以建立及設定 Office 365 組織最多 30 個權限的存取原則。</span><span class="sxs-lookup"><span data-stu-id="d10ec-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-151">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-152">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d10ec-153">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-154">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d10ec-155">選取 [**設定的原則**，並選取 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="d10ec-156">從下拉式欄位中，選取您的組織適當的值：</span><span class="sxs-lookup"><span data-stu-id="d10ec-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="d10ec-157">**原則類型**： 任務、 角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="d10ec-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="d10ec-158">**原則範圍**： Exchange 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="d10ec-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="d10ec-159">**原則名稱**： 選取 [從可用的原則</span><span class="sxs-lookup"><span data-stu-id="d10ec-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="d10ec-160">**核准類型**： 手動或自動</span><span class="sxs-lookup"><span data-stu-id="d10ec-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="d10ec-161">**核准群組**： 選取 [在步驟 1 中建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="d10ec-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="d10ec-p108">選取 [**建立**並再**關閉**。可能需要幾分鐘時間可完全設定並啟用原則。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-164">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-165">執行下列命令在 Exchange Online PowerShell 建立及定義核准原則：</span><span class="sxs-lookup"><span data-stu-id="d10ec-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="d10ec-166">範例：</span><span class="sxs-lookup"><span data-stu-id="d10ec-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="d10ec-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="d10ec-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="d10ec-168">步驟 4： 送出/核准權限的存取權要求</span><span class="sxs-lookup"><span data-stu-id="d10ec-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="d10ec-169">執行權限的工作要求的權限提高授權</span><span class="sxs-lookup"><span data-stu-id="d10ec-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="d10ec-p109">最多 24 小時之後送出要求權限存取要求已有效。如果不核准或拒絕，要求過期和存取未核准。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-172">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-173">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="d10ec-174">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-175">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d10ec-p110">選取**新的要求**。從下拉式欄位中，選取您的組織適當的值：</span><span class="sxs-lookup"><span data-stu-id="d10ec-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="d10ec-178">**要求類型**： 任務、 角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="d10ec-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="d10ec-179">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="d10ec-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="d10ec-180">**要求**： 選取 [從可用的原則</span><span class="sxs-lookup"><span data-stu-id="d10ec-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="d10ec-p111">**持續時間 （小時）**： 要求存取權的時數。您可以要求的時數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="d10ec-183">**註解**： 存取要求相關的註解的文字欄位</span><span class="sxs-lookup"><span data-stu-id="d10ec-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="d10ec-p112">選取 [**儲存**並再**關閉**。您的要求會傳送到透過電子郵件的核准者群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-186">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-187">執行下列命令在 Exchange Online PowerShell 建立並送出至核准者群組核准要求：</span><span class="sxs-lookup"><span data-stu-id="d10ec-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="d10ec-188">範例：</span><span class="sxs-lookup"><span data-stu-id="d10ec-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="d10ec-189">檢視權限提高要求的狀態</span><span class="sxs-lookup"><span data-stu-id="d10ec-189">View status of elevation requests</span></span>
<span data-ttu-id="d10ec-190">建立核准要求之後，可以在管理中心內檢閱提高權限要求狀態或 Exchange Management PowerShell 要求使用相關聯的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d10ec-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-191">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-192">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="d10ec-193">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-194">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d10ec-195">選取 [**檢視\*\*\*\*擱置**、**已核准**、**拒絕**、 或**客戶 Lockbox**狀態篩選已送出的要求。</span><span class="sxs-lookup"><span data-stu-id="d10ec-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-196">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-197">執行下列命令在 Exchange Online PowerShell 來檢視特定要求識別碼核准要求狀態：</span><span class="sxs-lookup"><span data-stu-id="d10ec-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="d10ec-198">範例：</span><span class="sxs-lookup"><span data-stu-id="d10ec-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="d10ec-199">核准權限提高授權要求</span><span class="sxs-lookup"><span data-stu-id="d10ec-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="d10ec-p113">相關的核准者群組的成員時建立核准要求時，會收到的電子郵件通知與可核准要求識別碼相關聯的要求要求者將收到的要求核准或拒絕透過電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-202">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-203">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="d10ec-204">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-205">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d10ec-206">選取 [檢視詳細資料並採取動作要求所列的要求。</span><span class="sxs-lookup"><span data-stu-id="d10ec-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="d10ec-p114">選取 [**核准**核准要求或選取 [**拒絕**] 拒絕要求。先前已核准的要求可以撤銷選取**撤消**存取。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-209">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-210">執行下列命令在 Exchange Online PowerShell 核准權限提高授權要求：</span><span class="sxs-lookup"><span data-stu-id="d10ec-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="d10ec-211">範例：</span><span class="sxs-lookup"><span data-stu-id="d10ec-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="d10ec-212">執行下列命令在 Exchange Online PowerShell 拒絕權限提高授權要求：</span><span class="sxs-lookup"><span data-stu-id="d10ec-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="d10ec-213">範例：</span><span class="sxs-lookup"><span data-stu-id="d10ec-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="d10ec-214">刪除 Office 365 中的權限的存取原則</span><span class="sxs-lookup"><span data-stu-id="d10ec-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="d10ec-215">您可以刪除權限的存取原則如果不再需要在組織中。</span><span class="sxs-lookup"><span data-stu-id="d10ec-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-216">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-217">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d10ec-218">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-219">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d10ec-220">選取 [**設定的原則**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="d10ec-221">選取您要刪除之的原則然後選取 [**移除原則**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="d10ec-222">選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d10ec-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-223">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-224">執行下列命令在 Exchange Online Powershell 刪除權限的存取原則：</span><span class="sxs-lookup"><span data-stu-id="d10ec-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="d10ec-225">停用 Office 365 中的權限的存取</span><span class="sxs-lookup"><span data-stu-id="d10ec-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="d10ec-p115">必要時，您可以停用貴組織權限的存取管理。停用權限存取不會刪除任何相關聯的核准原則或核准者群組。</span><span class="sxs-lookup"><span data-stu-id="d10ec-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d10ec-228">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d10ec-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d10ec-229">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="d10ec-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d10ec-230">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="d10ec-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d10ec-231">啟用**需要核准權限的存取**控制。</span><span class="sxs-lookup"><span data-stu-id="d10ec-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d10ec-232">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d10ec-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d10ec-233">執行下列命令在 Exchange Online Powershell 來停用權限的存取：</span><span class="sxs-lookup"><span data-stu-id="d10ec-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```