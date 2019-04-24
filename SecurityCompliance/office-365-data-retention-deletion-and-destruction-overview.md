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
description: Office 365 的相關資料保留、 刪除及毀損的 Microsoft 原則概觀。
ms.openlocfilehash: fcae11f10278f1357a68ea3f9a1178da97322775
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262835"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 中的資料保留、刪除及毀損

Microsoft 已指定客戶資料之後要刪除的保留多久的 Office 365 的資料處理標準的原則。 通常有兩個客戶資料都會被刪除的案例：

- **作用中刪除**租用戶已訂閱和使用者刪除資料，或由系統管理員刪除使用者所提供的資料。
- **被動刪除**租用戶訂閱結束。

## <a name="data-retention"></a>資料保留

針對每個這些案例中刪除下, 表顯示的最大資料保留期間，資料分類和分類：

| 資料分類 | 資料分類 | 描述 | 範例 | 保留期間 |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| 客戶資料 | 客戶內容| 直接提供/建立由系統管理員和使用者的內容 <br><br> 這包括所有的文字、 音效、 視訊及影像檔案，以及軟體建立，並且儲存在 Microsoft 資料中心時使用 Office 365 中的服務 | 範例的最常用的 Office 365 應用程式可讓作者資料的使用者包括 Word、 Excel、 PowerPoint、 Outlook 和 OneNote <br><br> 客戶內容也包含客戶擁有/提供機密資料 （密碼、 憑證、 加密金鑰、 存放裝置金鑰） | **作用中刪除案例：** 最多 30 天 <br><br> **被動刪除案例：** 最 180 天 |
| 客戶資料 | 使用者識別資訊 (EUII) | 識別或無法用來識別使用者的 Microsoft 服務的資料。 EUII 不包含客戶內容 | 使用者名稱或顯示名稱 （網域 \ 使用者名稱） <br><br> 使用者主要名稱 (name@domain) <br><br>  使用者特定 IP 位址 | **作用中刪除案例：** 最 180 天 （僅限租用戶系統管理員動作） <br><br> **被動刪除案例：** 最 180 天 |
| 個人資料 <br> （未包含客戶資料中的資料） | 使用者假名化識別碼 (EUPI) | Microsoft 繫結至 Microsoft 服務的使用者所建立的識別碼。 當 EUPI 結合其他資訊，例如對應表格，它會識別使用者 <br><br> EUPI 不包含上傳，或是建立由客戶資訊 | 使用者的 Guid、 PUIDs 或 Sid <br><br> 工作階段識別碼 | **作用中刪除案例：** 最多 30 天 <br><br> **被動刪除案例：** 最 180 天 |

## <a name="subscription-retention"></a>訂閱保留

At 所有時間期間內的作用中的訂閱，訂閱者可以存取、 擷取，或刪除 Office 365 中儲存的客戶資料。 如果付費的訂閱結束或已終止，Microsoft 會保留在 90 天的時間可以啟用 「 訂閱者 」 來擷取資料的有限函數帳戶儲存在 Office 365 的客戶資料。 90 天保留期間結束後，Microsoft 將會停用帳戶，並刪除客戶資料。 不能超過 180 天之後到期或 Office 365 訂閱的終止 Microsoft 將停用帳戶，並刪除帳戶中的所有客戶資料。 一旦經過任何資料的最長保留期間，資料會呈現商業無法復原。

若是免費試用版，您的帳戶會移動到寬限期狀態 30 天大部分的國家和地區。 這段期間寬限期，您必須購買 Office 365 的選項。 如果您決定不要購買 Office 365，您可以取消試用版，或讓過期，在寬限期內，將會刪除您的試用帳戶資訊及資料。

## <a name="expedited-deletion"></a>快速的刪除
At 所有時間期間內的任何訂閱，訂閱者可以連絡 Microsoft 支援服務與要求快速撤銷訂閱。 在此程序，所有使用者資料，包括中 SharePoint Online、 Exchange Online 可能會在下的資料會保留，或儲存在非使用中信箱，是已刪除的三天後系統管理員進入 Microsoft 所提供的鎖定程式碼。 如需有關快速撤銷的詳細資訊，請參閱[取消 Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)。

## <a name="related-links"></a>相關連結
- [資料毀損](office-365-data-destruction.md)
- [Office 365 中的不變性](office-365-data-immutability.md)
- [Exchange Online 資料刪除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online 資料刪除](office-365-sharepoint-online-data-deletion.md)
- [商務用 Skype 資料刪除](office-365-skype-data-deletion.md)