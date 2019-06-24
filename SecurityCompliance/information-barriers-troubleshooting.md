---
title: 疑難排解資訊障礙
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
description: 使用本文做為疑難排解資訊障礙的指南。
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131347"
---
# <a name="troubleshooting-information-barriers-preview"></a>疑難排解資訊障礙 (預覽)

[資訊障礙 (預覽)](information-barriers.md)可協助您的組織遵守法律需求和行業規定。 例如, 透過資訊障礙, 您可以限制特定使用者群組之間的通訊, 以避免利益衝突或其他問題。 (若要深入瞭解如何設定資訊障礙, 請參閱[定義資訊障礙的原則 (預覽)](information-barriers-policies.md)。)

如果人員在資訊障礙即將發生時遇到意外的問題, 您可以採取一些步驟來解決這些問題。 請使用本文做為指南。


## <a name="before-you-begin"></a>開始之前 .。。

若要執行本文所述的工作, 您必須被指派適當的角色, 例如下列其中一項:
- Microsoft 365 企業版全域系統管理員
- Office 365 全域系統管理員
- 合規性系統管理員
- IB 規範管理 (這是新的角色!)

若要深入瞭解資訊障礙的必要條件, 請參閱[必要條件 (適用于資訊屏障原則)](information-barriers-policies.md#prerequisites)。

請務必連線[至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: 仍允許在 Microsoft 小組中封鎖的使用者之間進行通訊

在這種情況下, 雖然資訊屏障已定義、使用中且已套用, 但是應該防止相互通訊的人員仍然可以在 Microsoft 小組中進行通訊。

### <a name="what-to-do"></a>待辦事項

確認有問題的使用者包含在資訊屏障原則中。 使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。

句法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 

您可以使用唯一識別每個使用者的任何值, 例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。 

範例： `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 

在此範例中, 我們會參考 Office 365 中的兩個使用者帳戶: *meganb* for *Megan*, 以及*alexw* for *Alex*。 

(您也可以將此 Cmdlet 用於單一使用者: `Get-InformationBarrierRecipientStatus -Identity <value>`) 此 Cmdlet 會傳回使用者的相關資訊, 例如屬性值以及所套用的任何資訊屏障原則。


|結果  |後續步驟  |
|---------|---------|
|沒有列出所選使用者的區段     |執行下列其中一項動作：<br/>-在 Azure Active Directory 中編輯使用者設定檔, 以將使用者指派至現有的區段<br/>-使用[支援的資訊障礙屬性來](information-barriers-attributes.md)定義區段         |
|會列出區段, 但不會將資訊屏障原則指派給這些區段     |執行下列其中一項動作：<br/>- 為問題的每個區段[定義資訊障礙原則](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- [編輯資訊障礙原則](information-barriers-policies.md#edit-a-policy), 並將其指派給正確的網段         |
|列出區段, 每個區段都包含在資訊屏障原則中     |-執行`Get-InformationBarrierPolicy` Cmdlet 以確認資訊屏障原則已啟用<br/>-執行`Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 以確認原則已套用<br/>-執行`Start-InformationBarrierPoliciesApplication` Cmdlet 以套用所有使用中的資訊屏障原則          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>問題: Microsoft 小組中意外封鎖人員進行通訊 

在這種情況下, 人員會報告在 Microsoft 小組中進行通訊的意外問題。 範例:
- 使用者無法找到或與 Microsoft 小組中的另一位使用者通訊。
- 使用者無法在 Microsoft 小組中看到或選取另一個使用者。
- 使用者可以看到另一位使用者, 但無法選取或傳送郵件給 Microsoft 小組中的其他使用者。

### <a name="what-to-do"></a>待辦事項

1. 決定使用者是否受到資訊屏障原則的影響。 若要這麼做, 請使用**InformationBarrierRecipientStatus 指令程式**搭配 Identity 參數。 

    語法為`Get-InformationBarrierRecipientStatus -Identity`

    您可以使用唯一識別每個收件者的任何識別值, 例如名稱、別名、辨別名稱 (DN)、正常化 DN、電子郵件地址或 GUID。

    範例： `Get-InformationBarrierRecipientStatus -Identity meganb`

    在此範例中, 我們使用了 Identity 參數的別名 (*meganb*)。 此 Cmdlet 會傳回信息, 指出使用者是否受到資訊屏障原則的影響。 (請參閱 * ExoPolicyId: \<GUID>。)

    如果資訊屏障原則中未包含使用者, 請與支援人員聯繫。 否則，請繼續進行下一個步驟。

2. 找出資訊屏障原則中所包含的區段。 若要這麼做, 請`Get-InformationBarrierPolicy`搭配 Identity 參數使用 Cmdlet。 使用詳細資料, 例如您在上一個步驟中收到的原則 GUID (ExoPolicyId) 做為 identity 值。

    範例： `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`

    在此範例中, 我們將取得有關 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*的資訊屏障原則的詳細資訊。
    
    執行 Cmdlet 之後, 請在 [結果] 中, 尋找**AssignedSegment**、 **SegmentsAllowed**及**SegmentsBlocked**值。

    範例: 執行`Get-InformationBarrierPolicy` Cmdlet 之後, 我們在結果清單中看到下列內容:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    在這種情況下, 我們可以看到資訊障礙原則會影響銷售和研究資料段中的人員。 在這種情況下, 銷售人員會無法與「調查」中的人員進行通訊。 如果看起來正確, 則資訊壁壘會如預期般運作。 如果不是, 請繼續進行下一個步驟。

4. 請確定已正確定義您的區段。 若要這麼做, 請`Get-OrganizationSegment`使用 Cmdlet, 並查看結果清單。 

    若要查看特定區段的詳細資料, 請`Get-OrganizationSegment`使用 Cmdlet 搭配 Identity 參數。 

    範例： `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`

    在此範例中, 我們會取得 GUID 為*c96e0837-c232-4a8a-841e-ef45787d8fcd*之區段的相關資訊。

    查看區段的詳細資料。 如有必要, 請[編輯區段](information-barriers-policies.md#edit-a-segment), 然後重新使用`Start-InformationBarrierPoliciesApplication` Cmdlet。

    如果您仍然遇到資訊屏障原則的問題, 請與支援人員聯繫。
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題: 資訊屏障應用程式花費的時間太長

執行**InformationBarrierPoliciesApplication** Cmdlet 之後, 程式會花很長的時間才能完成。

### <a name="what-to-do"></a>待辦事項

請記住, 當您執行原則應用程式 Cmdlet 時, 系統會為組織中的所有帳戶套用 (或移除) 資訊屏障原則。 如果您有許多使用者, 將需要一段時間進行處理。 (一般來說, 處理5000使用者帳戶需要大約一小時的時間。)

1. 使用**InformationBarrierPoliciesApplicationStatus**指令程式來確認最近原則應用程式的狀態。

    句法`Get-InformationBarrierPoliciesApplicationStatus`

    (若要顯示*所有*資訊屏障原則應用程式的狀態, 請使用此 Cmdlet:<br/>
    `Get-InformationBarrierPoliciesApplicationStatus -All $true`)

    這會顯示原則應用程式是否已完成、失敗或正在進行中的資訊。

2. 根據上一個步驟的結果, 執行下列其中一個步驟:
  
    |狀態  |下一步  |
    |---------|---------|
    |**尚未啟動**     |如果在執行**InformationBarrierPoliciesApplication**指令程式後已超過45分鐘, 請檢查您的 audit 記錄檔, 以查看原則定義中是否有任何錯誤, 或應用程式尚未啟動的其他原因。 |
    |**失敗**     |如果應用程式失敗, 請檢查您的審核記錄檔。 此外, 請參閱您的部門和原則。 是否有任何使用者被指派至多個區段？ 是否有任何區段被指派一個以上的 poliicy？ 如有必要, 請[編輯區段](information-barriers-policies.md#edit-a-segment)和 (或)[編輯原則](information-barriers-policies.md#edit-a-policy), 然後再次執行**InformationBarrierPoliciesApplication** Cmdlet。  |
    |**進行中。**     |如果應用程式仍在進行中, 則允許更多時間完成。 如果有數天, 請收集您的審查記錄檔, 然後與支援人員聯繫。 |

## <a name="related-topics"></a>相關主題

[定義 Microsoft 團隊中資訊障礙的原則 (預覽)](information-barriers-policies.md)

[資訊障礙 (預覽)](information-barriers.md)



