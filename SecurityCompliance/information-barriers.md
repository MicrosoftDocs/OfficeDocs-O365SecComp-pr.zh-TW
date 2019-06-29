---
title: 資訊障礙概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用資訊障礙, 以確保在組織內使用 Microsoft 小組來進行通訊合規性。
ms.openlocfilehash: 9750eab3c91b40cc96e16a386dbf59ba767ae877
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394278"
---
# <a name="information-barriers-preview"></a>資訊障礙 (預覽)

## <a name="overview"></a>概觀

Microsoft 雲端服務包含強大的通訊和共同作業功能。 但是, 假設您想要限制兩個群組之間的通訊, 以避免組織中發生利益衝突的情況。 或者, 您可能想要限制組織內特定人員之間的通訊, 以保護內部資訊。 Microsoft 365 可跨群組和組織進行通訊與共同作業, 因此有一種方法可以限制特定使用者群組之間的通訊 (必要時)？ 有了資訊障礙, 您可以! 

資訊障礙現在是在預覽中, 從 Microsoft 團隊開始。 當您的組織可使用這些功能時, 合規性管理員或資訊障礙管理員可以定義原則, 以允許或防止 Microsoft 小組中的使用者群組之間的通訊。 資訊屏障原則可用於下列情況:

- 一天 trader 無法呼叫行銷小組中的人員
- 使用機密公司資訊的財務人員無法接收來自其組織內特定群組的通話
- 具有交易秘密材料的內部小組無法與組織內特定群組中的人員進行線上通話或聊天
- 研究小組只能與產品開發小組通話或聊天

針對上述所有範例案例 (以及更多), 您可以定義資訊屏障原則, 以防止或允許 Microsoft 小組中的通訊。 這類原則可防止使用者不應該呼叫或聊天, 或讓人員只能與 Microsoft 小組中的特定群組進行通訊。 在有效的資訊屏障原則中, 每當這些原則所涵蓋的使用者嘗試與 Microsoft 小組中的其他人通訊時, 就會進行檢查以防止 (或允許) 通訊 (如資訊屏障原則所定義)。 若要深入瞭解資訊障礙的使用者經驗, 請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 目前, 資訊障礙不適用於電子郵件通訊或透過 SharePoint Online 或 OneDrive 的檔案共用。 此外, 資訊障礙與[規範界限](set-up-compliance-boundaries.md)無關。<p>在您定義及套用資訊屏障原則之前, 請確定您的組織沒有生效的[Exchange 通訊錄原則](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies)。  

## <a name="what-happens-with-information-barriers"></a>資訊障礙會發生什麼事

當資訊屏障原則到位時, 不應該與其他特定使用者通訊的人員將無法找到、選取、聊天或呼叫這些使用者。 透過資訊障礙, 支票會就地保留以防止未經授權的通訊。

資訊障礙最初僅適用于 Microsoft 團隊聊天和通道。 在 Microsoft 小組中, 資訊屏障原則會決定並防止下列幾種未經授權的通訊:
- 搜尋使用者
- 將成員新增至小組
- 啟動與某人的交談會話
- 啟動群組聊天
- 邀請某人加入會議
- 共用螢幕
- 撥打電話 

如果參與的人員包含在資訊屏障原則中, 以防止活動, 他們將無法繼續。 此外, 資訊屏障原則中包含的每一個人都可能會封鎖與 Microsoft 小組中的其他人進行通訊。 受資訊障礙原則影響的人員是同一個小組或群組聊天的一部分, 他們可能會從交談會話中移除, 而且可能不允許與群組進行進一步的通訊。

若要深入瞭解資訊障礙的使用者經驗, 請參閱[Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>必要的授權和許可權

**目前資訊障礙是在預覽中**。 這些功能通常會包含在訂閱中, 例如:

- Microsoft 365 E5
- Office 365 E5
- Office 365 進階合規性
- Microsoft 365 E5 資訊保護和合規性

如需詳細資訊, 請參閱[規範解決方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。

若要[定義或編輯資訊屏障原則](information-barriers-policies.md), 您必須被指派下列其中一個角色:

- Microsoft 365 全域系統管理員
- Office 365 全域系統管理員
- 合規性系統管理員
- IB 規範管理 (這是新的角色!)

(若要深入瞭解角色和許可權, 請參閱[Office 365 安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。)

您必須熟悉 PowerShell Cmdlet, 才能定義、驗證或編輯資訊屏障原則。 雖然我們在操作[方法文章](information-barriers-policies.md)中提供了 PowerShell Cmdlet 的幾個範例, 但是您將需要瞭解組織的其他詳細資料, 例如參數。

## <a name="next-steps"></a>後續步驟

- [深入瞭解 Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [請參閱可用於資訊屏障原則的屬性](information-barriers-attributes.md)

- [定義資訊障礙的原則](information-barriers-policies.md)

- [編輯 (或移除) 資訊屏障原則 (預覽)](information-barriers-edit-segments-policies.md.md) 

