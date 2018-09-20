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
ms.openlocfilehash: b2b6ab18687617c0da3425f4ee60cf81074f6f69
ms.sourcegitcommit: 15dfa0c83aa88816c18e30a44a49e36e733d952c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021397"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="473d0-103">在 Office 365 中設定權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="473d0-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="473d0-104">本主題涵蓋功能僅在 Office 365 E5 和進階規範 Sku 中目前可用的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="473d0-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="473d0-p101">本主題將引導您完成啟用及設定 Office 365 組織中的權限的存取管理。您可以使用其中一個 Microsoft 365 系統管理中心或 Exchange Management PowerShell 來管理並使用特殊權限存取。</span><span class="sxs-lookup"><span data-stu-id="473d0-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="473d0-107">啟用並設定權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="473d0-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="473d0-108">請遵循下列步驟來設定和 Office 365 組織中使用特殊權限的存取：</span><span class="sxs-lookup"><span data-stu-id="473d0-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="473d0-109">步驟 1： 建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="473d0-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="473d0-p102">在您開始使用最低權限存取之前，請決定誰將擁有的傳入要求提高權限與權限工作的存取權核准授權單位。任何已核准者的群組之一部分的使用者將能夠核准存取要求。這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="473d0-113">步驟 2： 啟用權限的存取</span><span class="sxs-lookup"><span data-stu-id="473d0-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="473d0-114">權限的存取必須明確開啟 Office 365 中使用的預設核准者群組與包括一組您想要排除的權限的存取管理存取控制的系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="473d0-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="473d0-115">步驟 3： 建立存取原則</span><span class="sxs-lookup"><span data-stu-id="473d0-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="473d0-p103">建立核准原則可讓您定義在個別工作設定範圍的特定核准需求。核准類型選項會**自動**或**手動**。</span><span class="sxs-lookup"><span data-stu-id="473d0-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="473d0-118">步驟 4： 送出/核准權限的存取權要求</span><span class="sxs-lookup"><span data-stu-id="473d0-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="473d0-p104">一次啟用的權限存取需要核准在執行任何具有相關聯的核准原則所定義的工作。使用者執行工作包含在需要核准原則必須要求並以具有執行工作所需的權限授與存取權核准。</span><span class="sxs-lookup"><span data-stu-id="473d0-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="473d0-p105">會授與核准之後，要求使用者可執行預定的工作及權限的存取將授權及使用者代理執行工作。核准保持有效的要求期間 （預設持續時間為 4 小時） 的期間要求者可執行預定的任務多次。所有這類執行記錄且可供安全性及規範稽核。</span><span class="sxs-lookup"><span data-stu-id="473d0-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="473d0-p106">如果您想要使用 Exchange Management PowerShell 來啟用及設定權限的存取，請遵循[Connect to Exchange Online PowerShell 中使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)連線至您的 Office 365 與 Exchange Online PowerShell 中的步驟認證。您不需要啟用的 Office 365 組織使用的步驟來連線至 Exchange Online PowerShell 時啟用權限的存取多重要素驗證。以多重要素驗證連線建立簽署您要求的權限存取所使用的 OAuth 權杖。</span><span class="sxs-lookup"><span data-stu-id="473d0-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="473d0-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="473d0-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="473d0-128">步驟 1-建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="473d0-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="473d0-129">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="473d0-130">在管理中心中，移至 [**群組** > **加入群組**。</span><span class="sxs-lookup"><span data-stu-id="473d0-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="473d0-131">選取**啟用郵件功能的安全性群組**群組類型，然後完成 [新群組的**名稱**、**群組電子郵件地址**和**Description**欄位。</span><span class="sxs-lookup"><span data-stu-id="473d0-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="473d0-p107">儲存群組。可能需要幾分鐘的完整設定與顯示在 Office 365 系統管理中心中的群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="473d0-134">選取新核准者群組並選取 [**編輯**] 以將使用者新增至群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="473d0-135">儲存群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-135">Save the group.</span></span>

<span data-ttu-id="473d0-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="473d0-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="473d0-137">步驟 2-啟用權限的存取</span><span class="sxs-lookup"><span data-stu-id="473d0-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="473d0-138">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="473d0-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="473d0-139">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="473d0-140">在管理中心中，移至**設定 > 安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="473d0-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="473d0-141">啟用**需要核准權限的存取**控制。</span><span class="sxs-lookup"><span data-stu-id="473d0-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="473d0-142">指定您在做為**預設的核准者群組**的步驟 1 中建立核准者群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="473d0-143">**儲存**並**關閉**。</span><span class="sxs-lookup"><span data-stu-id="473d0-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="473d0-144">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="473d0-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="473d0-145">若要啟用權限的存取及核准者群組指派 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="473d0-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="473d0-146">範例：</span><span class="sxs-lookup"><span data-stu-id="473d0-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="473d0-147">功能可供以確保您的組織內特定 automations 系統帳戶可以不相依性運作權限存取、 但還是建議也是這類排除是例外以及那些允許應該核准和稽核定期。</span><span class="sxs-lookup"><span data-stu-id="473d0-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="473d0-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="473d0-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="473d0-149">步驟 3-建立存取原則</span><span class="sxs-lookup"><span data-stu-id="473d0-149">Step 3 - Create an access policy</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="473d0-150">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="473d0-150">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="473d0-151">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-151">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="473d0-152">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="473d0-152">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="473d0-153">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="473d0-153">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="473d0-154">選取 [**設定的原則**，並選取 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="473d0-154">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="473d0-155">從下拉式欄位中，選取您的組織適當的值：</span><span class="sxs-lookup"><span data-stu-id="473d0-155">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="473d0-156">**原則類型**： 任務、 角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="473d0-156">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="473d0-157">**原則範圍**： Exchange 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="473d0-157">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="473d0-158">**原則名稱**： 選取 [從可用的原則</span><span class="sxs-lookup"><span data-stu-id="473d0-158">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="473d0-159">**核准類型**： 手動或自動</span><span class="sxs-lookup"><span data-stu-id="473d0-159">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="473d0-160">**核准群組**： 選取 [在步驟 1 中建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="473d0-160">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="473d0-p108">選取 [**建立**並再**關閉**。可能需要幾分鐘時間可完全設定並啟用原則。</span><span class="sxs-lookup"><span data-stu-id="473d0-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="473d0-163">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="473d0-163">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="473d0-164">執行下列命令在 Exchange Online PowerShell 建立及定義核准原則：</span><span class="sxs-lookup"><span data-stu-id="473d0-164">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="473d0-165">範例：</span><span class="sxs-lookup"><span data-stu-id="473d0-165">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="473d0-166"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="473d0-166"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="473d0-167">步驟 4： 送出/核准權限的存取權要求</span><span class="sxs-lookup"><span data-stu-id="473d0-167">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="473d0-168">執行權限的工作要求的權限提高授權</span><span class="sxs-lookup"><span data-stu-id="473d0-168">Requesting elevation authorization to execute privileged tasks</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="473d0-169">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="473d0-169">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="473d0-170">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-170">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="473d0-171">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="473d0-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="473d0-172">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="473d0-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="473d0-p109">選取**新的要求**。從下拉式欄位中，選取您的組織適當的值：</span><span class="sxs-lookup"><span data-stu-id="473d0-p109">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="473d0-175">**要求類型**： 任務、 角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="473d0-175">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="473d0-176">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="473d0-176">**Request scope**: Exchange</span></span>

    <span data-ttu-id="473d0-177">**要求**： 選取 [從可用的原則</span><span class="sxs-lookup"><span data-stu-id="473d0-177">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="473d0-178">**持續時間 （小時）**： 要求存取權的時數</span><span class="sxs-lookup"><span data-stu-id="473d0-178">**Duration (hours)**: Number of hours of requested access</span></span>

    <span data-ttu-id="473d0-179">**註解**： 存取要求相關的註解的文字欄位</span><span class="sxs-lookup"><span data-stu-id="473d0-179">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="473d0-p110">選取 [**儲存**並再**關閉**。您的要求會傳送到透過電子郵件的核准者群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-p110">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="473d0-182">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="473d0-182">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="473d0-183">執行下列命令在 Exchange Online PowerShell 建立並送出至核准者群組核准要求：</span><span class="sxs-lookup"><span data-stu-id="473d0-183">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="473d0-184">範例：</span><span class="sxs-lookup"><span data-stu-id="473d0-184">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="473d0-185">檢視權限提高要求的狀態</span><span class="sxs-lookup"><span data-stu-id="473d0-185">View status of elevation requests</span></span>
<span data-ttu-id="473d0-186">建立核准要求之後，可以在管理中心內檢閱提高權限要求狀態或 Exchange Management PowerShell 要求使用相關聯的識別碼。</span><span class="sxs-lookup"><span data-stu-id="473d0-186">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="473d0-187">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="473d0-187">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="473d0-188">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-188">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="473d0-189">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="473d0-189">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="473d0-190">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="473d0-190">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="473d0-191">選取 [**檢視\*\*\*\*擱置**、**已核准**、**拒絕**、 或**客戶 Lockbox**狀態篩選已送出的要求。</span><span class="sxs-lookup"><span data-stu-id="473d0-191">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="473d0-192">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="473d0-192">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="473d0-193">執行下列命令在 Exchange Online PowerShell 來檢視特定要求識別碼核准要求狀態：</span><span class="sxs-lookup"><span data-stu-id="473d0-193">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="473d0-194">範例：</span><span class="sxs-lookup"><span data-stu-id="473d0-194">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="473d0-195">核准權限提高授權要求</span><span class="sxs-lookup"><span data-stu-id="473d0-195">Approving an elevation authorization request</span></span>
<span data-ttu-id="473d0-196">相關的核准者群組的成員時建立核准要求時，會收到的電子郵件通知與可核准要求識別碼相關聯的要求</span><span class="sxs-lookup"><span data-stu-id="473d0-196">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="473d0-197">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="473d0-197">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="473d0-198">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-198">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="473d0-199">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="473d0-199">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="473d0-200">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="473d0-200">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="473d0-201">選取 [檢視詳細資料並採取動作要求所列的要求。</span><span class="sxs-lookup"><span data-stu-id="473d0-201">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="473d0-p111">選取 [**核准**核准要求或選取 [**拒絕**] 拒絕要求。先前已核准的要求可以撤銷選取**撤消**存取。</span><span class="sxs-lookup"><span data-stu-id="473d0-p111">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="473d0-204">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="473d0-204">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="473d0-205">執行下列命令在 Exchange Online PowerShell 核准權限提高授權要求：</span><span class="sxs-lookup"><span data-stu-id="473d0-205">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="473d0-206">範例：</span><span class="sxs-lookup"><span data-stu-id="473d0-206">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="473d0-207">執行下列命令在 Exchange Online PowerShell 拒絕權限提高授權要求：</span><span class="sxs-lookup"><span data-stu-id="473d0-207">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="473d0-208">範例：</span><span class="sxs-lookup"><span data-stu-id="473d0-208">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="473d0-209">停用 Office 365 中的權限的存取</span><span class="sxs-lookup"><span data-stu-id="473d0-209">Disable privileged access in Office 365</span></span>

<span data-ttu-id="473d0-p112">必要時，您可以停用貴組織權限的存取管理。停用權限存取不會刪除任何相關聯的核准原則或核准者群組。</span><span class="sxs-lookup"><span data-stu-id="473d0-p112">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="473d0-212">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="473d0-212">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="473d0-213">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="473d0-213">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="473d0-214">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="473d0-214">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="473d0-215">啟用**需要核准權限的存取**控制。</span><span class="sxs-lookup"><span data-stu-id="473d0-215">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="473d0-216">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="473d0-216">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="473d0-217">執行下列命令在 Exchange Online Powershell 來停用權限的存取：</span><span class="sxs-lookup"><span data-stu-id="473d0-217">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```