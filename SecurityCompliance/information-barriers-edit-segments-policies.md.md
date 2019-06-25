---
title: 編輯或移除資訊障礙原則
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 瞭解如何編輯或移除資訊障礙的原則。
ms.openlocfilehash: e6bed4df2329d426f86bd4cde07bdc7d1a2792cd
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "35215646"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a>編輯或移除資訊障礙原則 (預覽)

## <a name="overview"></a>概觀

[定義資訊屏障原則](information-barriers-policies.md)之後, 您可能需要變更這些原則或使用者區段, 做為[疑難排解](information-barriers-troubleshooting.md)或定期維護的一部分。 請使用本文做為指南。

> [!IMPORTANT]
> 若要執行本文所述的工作, 您必須被指派適當的角色, 例如下列其中一項:<br/>-Microsoft 365 企業通用系統管理員<br/>-Office 365 全域系統管理員<br/>-合規性管理員<br/>-IB 規範管理 (這是新的角色!)<p>若要深入瞭解資訊障礙的必要條件, 請參閱[必要條件 (適用于資訊屏障原則)](information-barriers-policies.md#prerequisites)。<p>請務必連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="edit-user-account-attributes"></a>編輯使用者帳戶屬性

使用此程式可編輯分割使用者所使用的屬性。 

例如, 如果您使用的是部門屬性, 且有一或多個使用者帳戶目前未列出部門的任何值, 則必須編輯這些使用者帳戶, 以包含部門資訊。 

使用者帳戶屬性可用來定義資料段, 以便指派資訊屏障原則。

1. 若要查看特定使用者帳戶的詳細資料, 例如屬性值和指派的區段, 請使用 InformationBarrierRecipientStatus 指令**程式**搭配 Identity 參數。 

   句法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 
    
   您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。 
    
   範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 
    
   在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。 
    
   (您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`) 
    
2. 決定您要為使用者帳戶設定檔編輯的屬性。 如需詳細資訊, 請參閱[資訊障礙原則 (預覽) 的屬性](information-barriers-attributes.md)。 

3. 編輯一或多個使用者帳戶, 以包含您在上一個步驟中選取之屬性的值。 若要這麼做, 請使用下列其中一個程式:

    - 若要編輯單一帳戶, 請參閱[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

    - 若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶), 請參閱使用[Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。

## <a name="edit-a-segment"></a>編輯區段

使用此程式編輯使用者區段的定義。 例如, 您可能會變更某段的名稱, 或用來判斷該區段中所包含之人員的篩選。

1. 若要查看所有現有的區段, 請使用**OrganizationSegment 指令程式**。
    
    句法`Get-OrganizationSegment`

    您會看到每個區段和詳細資料的清單, 例如區段類型、其 UserGroupFilter 值、建立日期或上次修改者、GUID 等等。

    > [!TIP]
    > 列印或儲存您的區段清單供日後參考。 例如, 如果您想要編輯某個區段, 您將需要知道其名稱或識別值 (這會與 Identity 參數搭配使用)。

2. 若要編輯區段, 請使用**OrganizationSegment 指令程式**搭配**Identity**參數及相關的詳細資料。 

    句法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`

    範例： `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`

    在此範例中, 針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的區段, 我們會將部門名稱更新為 "HRDept"。

當您完成組織的資料段編輯時, 您可以[定義](information-barriers-policies.md#part-2-define-information-barrier-policies)或[編輯](#edit-a-policy)資訊障礙原則。

## <a name="edit-a-policy"></a>編輯原則

1. 若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。

    句法`Get-InformationBarrierPolicy`

    在結果清單中, 識別您要變更的原則。 記下原則的 GUID 和名稱。

2. 使用**InformationBarrierPolicy**指令程式搭配**Identity**參數, 並指定您想要進行的變更。

    範例: 假設已定義原則來封鎖*研究*資料段與*銷售*和*行銷*資料段的通訊。 原則是使用此 Cmdlet 定義的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    假設我們想要變更它, 讓*研究*部門中的人員只能與*HR*區段中的人通訊。 若要進行這種變更, 我們會使用此 Cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    在此範例中, 我們將 "SegmentsBlocked" 變更為 "SegmentsAllowed", 並指定*HR*區段。

3. 當您完成編輯原則時, 請務必套用您的變更。 (請參閱套用[資訊屏障原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)。)

## <a name="set-a-policy-to-inactive-status"></a>將原則設定為非使用中狀態

1. 若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。

    句法`Get-InformationBarrierPolicy`

    在結果清單中, 識別您要變更 (或移除) 的原則。 記下原則的 GUID 和名稱。

2. 若要將原則的狀態設定為非使用中, 請使用**InformationBarrierPolicy**指令程式搭配 Identity 參數, 並將 State 參數設為非使用中。

    句法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    在此範例中, 我們將*43c37853-ea10-4b90-a23d-ab8c9377247*的資訊屏障原則設定為非使用中狀態。

3. 若要套用您的變更, 請使用**InformationBarrierPoliciesApplication 指令程式**。

    句法`Start-InformationBarrierPoliciesApplication`

    針對您的組織, 會套用使用者的變更。 如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。 (一般來說, 處理5000使用者帳戶需要大約一小時的時間。)

此時, 一或多個資訊屏障原則會設為非使用中狀態。 從這裡, 您可以執行下列任何一項操作:
- 保留原樣 (原則設定為非作用中的狀態對使用者不會有任何影響)
- [編輯原則](#edit-a-policy) 
- [移除原則](#remove-a-policy)

## <a name="remove-a-policy"></a>移除原則

1. 若要查看目前資訊屏障原則的清單, 請使用**InformationBarrierPolicy 指令程式**。

    句法`Get-InformationBarrierPolicy`

    在結果清單中, 識別您要移除的原則。 記下原則的 GUID 和名稱。 請確定原則設定為非使用中狀態。

2. 使用**InformationBarrierPolicy**指令程式搭配 Identity 參數。

    句法`Remove-InformationBarrierPolicy -Identity GUID`

    範例: 假設我們想要移除 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*的原則。 若要這麼做, 我們會使用此 Cmdlet:
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    出現提示時, 請確認變更。

3. 針對您要移除的每個原則, 重複步驟1-2。

4. 當您完成移除原則時, 請套用您的變更。 若要這麼做, 請使用**InformationBarrierPoliciesApplication 指令程式**。

    句法`Start-InformationBarrierPoliciesApplication`

    針對您的組織, 會套用使用者的變更。 如果您的組織很大, 可能需要24小時 (或更多), 才能完成此程式。

## <a name="stop-a-policy-application"></a>停止原則應用程式

如果您已開始套用資訊屏障原則, 而您想要停止套用這些原則, 請使用下列程式。 請記住, 此程式會花大約30-35 分鐘的時間來開始。

1. 若要查看最新資訊屏障原則應用程式的狀態, 請使用**InformationBarrierPoliciesApplicationStatus**指令程式。

    句法`Get-InformationBarrierPoliciesApplicationStatus`

    記下應用程式的 GUID。

2. 使用**InformationBarrierPoliciesApplication**指令程式搭配 Identity 參數。

    句法`Stop-InformationBarrierPoliciesApplication -Identity GUID`

    範例： `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`

    在此範例中, 我們將停止套用資訊屏障原則。

## <a name="related-articles"></a>相關文章

[取得資訊障礙的概況](information-barriers.md)

[定義資訊障礙的原則 (預覽)](information-barriers-policies.md)

[深入瞭解 Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[資訊障礙原則的屬性 (預覽)](information-barriers-attributes.md)

[疑難排解資訊障礙 (預覽)](information-barriers-troubleshooting.md)
