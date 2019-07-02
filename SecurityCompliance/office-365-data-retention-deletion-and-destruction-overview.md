---
title: Office 365 中的資料保留、刪除及毀損
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 有關資料保留、刪除和銷毀之 Office 365 的 Microsoft 原則概述。
ms.openlocfilehash: 79a58381892cfcb773f6e83f129075d6f2037304
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622483"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 中的資料保留、刪除及毀損

Microsoft 有 Office 365 的資料處理標準原則, 可指定在刪除後保留客戶資料的時間。 通常有兩種情況會刪除客戶資料:

- 使用中**刪除:** 租使用者有使用中的訂閱, 而且使用者會刪除資料, 或系統管理員刪除使用者所提供的資料。
- **被動刪除:** 租使用者訂閱會結束。

## <a name="data-retention"></a>資料保留

針對上述每個刪除案例, 下表會依資料類別和分類顯示資料保留期間上限:

| 資料類別 | 資料分類 | 描述 | 範例 | 保留期間 |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| 客戶資料 | 客戶內容| 由系統管理員和使用者直接提供或建立的內容 <br><br> 在使用 Office 365 中的服務時, 會包含所有文字、聲音、影片、圖像檔案, 以及 Microsoft 資料中心內所建立及儲存的軟體 | 最常使用的 Office 365 應用程式範例, 可讓使用者製作資料包含 Word、Excel、PowerPoint、Outlook 和 OneNote <br><br> 客戶內容也包括由客戶擁有/提供的機密 (密碼、憑證、加密金鑰、儲存金鑰) | **主動刪除案例:** 最多30天 <br><br> **被動刪除案例:** 最多180天 |
| 客戶資料 | 使用者身分識別資訊 (EUII) | 識別或可用來識別 Microsoft 服務使用者的資料。 EUII 不包含客戶內容 | 使用者名稱或顯示名稱 (網域 \ 使用者名稱) <br><br> 使用者主體名稱 (name @ domain) <br><br>  使用者特定的 IP 位址 | **主動刪除案例:** 最多180天 (只有租使用者系統管理員的動作) <br><br> **被動刪除案例:** 最多180天 |
| 個人資料 <br> (客戶資料中未包含的資料) | 使用者 Pseudonymous 識別碼 (EUPI) | 由 Microsoft 所建立的識別碼, 由 microsoft 服務的使用者所建立。 與其他資訊 (例如對應資料表) 合併時, EUPI 會識別使用者 <br><br> EUPI 不包含由客戶上傳或建立的資訊 | 使用者 Guid、PUIDs 或 Sid <br><br> 會話識別碼 | **主動刪除案例:** 最多30天 <br><br> **被動刪除案例:** 最多180天 |

## <a name="subscription-retention"></a>訂閱保留

在使用中訂閱的期限內, 訂閱者可以存取、解壓縮或刪除儲存在 Office 365 中的客戶資料。 如果付費訂閱結束或終止, Microsoft 會將 Office 365 中儲存的客戶資料保留在90天的有限功能帳戶中, 讓訂閱者能夠解開資料。 在90天的保留期間結束之後, Microsoft 會停用帳戶, 並刪除客戶資料。 到期或終止 Office 365 訂閱後, 不得超過180天, Microsoft 會停用帳戶, 並從帳戶中刪除所有客戶資料。 一旦所有資料的保留期間都已過, 資料就會無法取得正式的復原。

對於免費試用版, 您的帳戶在大部分的國家和地區中會移到30天的寬限狀態。 在此寬限期期間, 您可以購買 Office 365。 如果您決定不購買 Office 365, 您可以取消試用版或讓寬限時間到期, 並刪除您的試用帳戶資訊和資料。

## <a name="expedited-deletion"></a>加急刪除

對於任何訂閱, 訂閱者都可以聯繫 Microsoft 支援服務, 並要求進行快速訂閱取消布建。 在此程式中, 系統管理員輸入 Microsoft 所提供的封鎖程式碼之後, 就會刪除三天的所有使用者資料。 這包括 SharePoint Online 和 Exchange Online 中保留或儲存在非使用中信箱中的資料。

如需更快速的解除提供的詳細資訊, 請參閱[取消 Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)。

## <a name="related-links"></a>相關連結
- [資料毀損](office-365-data-destruction.md)
- [Office 365 中的不變性](office-365-data-immutability.md)
- [Exchange Online 資料刪除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online 資料刪除](office-365-sharepoint-online-data-deletion.md)
- [商務用 Skype 資料刪除](office-365-skype-data-deletion.md)