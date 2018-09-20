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
ms.openlocfilehash: 6494505554a02f005df8f45839c9575094acbf1a
ms.sourcegitcommit: d31904e81f81d0fba75309a2bc8bbfb05565a0b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2018
ms.locfileid: "24055248"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>在 Office 365 中設定權限的存取管理

> [!IMPORTANT]
> 本主題涵蓋功能僅在 Office 365 E5 和進階規範 Sku 中目前可用的部署和設定指導。

本主題將引導您完成啟用及設定 Office 365 組織中的權限的存取管理。您可以使用其中一個 Microsoft 365 系統管理中心或 Exchange Management PowerShell 來管理並使用特殊權限存取。 

## <a name="enable-and-configure-privileged-access-management"></a>啟用並設定權限的存取管理

請遵循下列步驟來設定和 Office 365 組織中使用特殊權限的存取：

- [步驟 1： 建立核准者群組](privileged-access-management-configuration.md#step1)

    在您開始使用最低權限存取之前，請決定誰將擁有的傳入要求提高權限與權限工作的存取權核准授權單位。任何已核准者的群組之一部分的使用者將能夠核准存取要求。這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。

- [步驟 2： 啟用權限的存取](privileged-access-management-configuration.md#step2)

    權限的存取必須明確開啟 Office 365 中使用的預設核准者群組與包括一組您想要排除的權限的存取管理存取控制的系統帳戶。

- [步驟 3： 建立存取原則](privileged-access-management-configuration.md#step3)

    建立核准原則可讓您定義在個別工作設定範圍的特定核准需求。核准類型選項會**自動**或**手動**。

- [步驟 4： 送出/核准權限的存取權要求](privileged-access-management-configuration.md#step4)

    一次啟用的權限存取需要核准在執行任何具有相關聯的核准原則所定義的工作。使用者執行工作包含在需要核准原則必須要求並以具有執行工作所需的權限授與存取權核准。

會授與核准之後，要求使用者可執行預定的工作及權限的存取將授權及使用者代理執行工作。核准保持有效的要求期間 （預設持續時間為 4 小時） 的期間要求者可執行預定的任務多次。所有這類執行記錄且可供安全性及規範稽核。 

> [!NOTE]
> 如果您想要使用 Exchange Management PowerShell 來啟用及設定權限的存取，請遵循[Connect to Exchange Online PowerShell 中使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)連線至您的 Office 365 與 Exchange Online PowerShell 中的步驟認證。您不需要啟用的 Office 365 組織使用的步驟來連線至 Exchange Online PowerShell 時啟用權限的存取多重要素驗證。以多重要素驗證連線建立簽署您要求的權限存取所使用的 OAuth 權杖。

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>步驟 1-建立核准者群組

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。

2. 在管理中心中，移至 [**群組** > **加入群組**。

3. 選取**啟用郵件功能的安全性群組**群組類型，然後完成 [新群組的**名稱**、**群組電子郵件地址**和**Description**欄位。

4. 儲存群組。可能需要幾分鐘的完整設定與顯示在 Office 365 系統管理中心中的群組。

5. 選取新核准者群組並選取 [**編輯**] 以將使用者新增至群組。

6. 儲存群組。

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>步驟 2-啟用權限的存取

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。

2. 在管理中心中，移至**設定 > 安全性與隱私權** > **權限的存取**。

3. 啟用**需要核准權限的存取**控制。

4. 指定您在做為**預設的核准者群組**的步驟 1 中建立核准者群組。

5. **儲存**並**關閉**。

### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

若要啟用權限的存取及核准者群組指派 Exchange Online PowerShell 中執行下列命令：
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
範例：
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> 功能可供以確保您的組織內特定 automations 系統帳戶可以不相依性運作權限存取、 但還是建議也是這類排除是例外以及那些允許應該核准和稽核定期。

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>步驟 3-建立存取原則

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取 [**設定的原則**，並選取 [**新增原則**。

5. 從下拉式欄位中，選取您的組織適當的值：
    
    **原則類型**： 任務、 角色或角色群組

    **原則範圍**： Exchange 或 Office 365

    **原則名稱**： 選取 [從可用的原則

    **核准類型**： 手動或自動

    **核准群組**： 選取 [在步驟 1 中建立核准者群組

6. 選取 [**建立**並再**關閉**。可能需要幾分鐘時間可完全設定並啟用原則。

### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

執行下列命令在 Exchange Online PowerShell 建立及定義核准原則：

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
範例：
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>步驟 4： 送出/核准權限的存取權要求

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>執行權限的工作要求的權限提高授權

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取**新的要求**。從下拉式欄位中，選取您的組織適當的值：

    **要求類型**： 任務、 角色或角色群組

    **要求範圍**： Exchange

    **要求**： 選取 [從可用的原則

    **持續時間 （小時）**： 要求存取權的時數

    **註解**： 存取要求相關的註解的文字欄位

5. 選取 [**儲存**並再**關閉**。您的要求會傳送到透過電子郵件的核准者群組。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

執行下列命令在 Exchange Online PowerShell 建立並送出至核准者群組核准要求：
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
範例：
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>檢視權限提高要求的狀態
建立核准要求之後，可以在管理中心內檢閱提高權限要求狀態或 Exchange Management PowerShell 要求使用相關聯的識別碼。

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取 [**檢視****擱置**、**已核准**、**拒絕**、 或**客戶 Lockbox**狀態篩選已送出的要求。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

執行下列命令在 Exchange Online PowerShell 來檢視特定要求識別碼核准要求狀態：
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
範例：
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>核准權限提高授權要求
相關的核准者群組的成員時建立核准要求時，會收到的電子郵件通知與可核准要求識別碼相關聯的要求要求者將收到的要求核准或拒絕透過電子郵件通知。

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您的認證。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取 [檢視詳細資料並採取動作要求所列的要求。

5. 選取 [**核准**核准要求或選取 [**拒絕**] 拒絕要求。先前已核准的要求可以撤銷選取**撤消**存取。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

執行下列命令在 Exchange Online PowerShell 核准權限提高授權要求：

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
範例：
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

執行下列命令在 Exchange Online PowerShell 拒絕權限提高授權要求：

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
範例：
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="disable-privileged-access-in-office-365"></a>停用 Office 365 中的權限的存取

必要時，您可以停用貴組織權限的存取管理。停用權限存取不會刪除任何相關聯的核准原則或核准者群組。

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用您組織中的管理帳戶的認證。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 啟用**需要核准權限的存取**控制。

### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

執行下列命令在 Exchange Online Powershell 來停用權限的存取：

```
Disable-ElevatedAccessControl
```