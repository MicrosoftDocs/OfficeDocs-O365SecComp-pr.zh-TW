---
title: Office 365 中的資料保留、刪除及毀損
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Overview of Office 365 資料保留、 刪除、 和解構有關的 Microsoft 的原則。
ms.openlocfilehash: 8a773ebafba0d7cdd36b9da30878dcc487685846
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2019
ms.locfileid: "24961569"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 中的資料保留、刪除及毀損

Microsoft Office 365 的客戶資料之後要刪除的保留期限會指定具有資料處理標準的原則。通常有兩種情況客戶資料都會被刪除：

- **作用中刪除**承租人具有作用中的訂閱與使用者刪除資料，或由系統管理員刪除使用者所提供的資料。
- **被動刪除**租用戶訂閱綵帶橫幅。

## <a name="data-retention"></a>資料保留

每個這些刪除案例下, 表會顯示由資料類別與分類的最大資料保留期間：

| 資料類別 | 資料分類 | 描述 | 範例 | 保留期間 |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| 客戶資料 | 客戶的內容| 建立的內容直接提供/由系統管理員和使用者 <br><br> 這包括所有文字、 聲音、 視訊及圖像檔案和軟體建立並儲存在 Microsoft 資料中心時使用 Office 365 中的服務 | 範例的最常用的 Office 365 應用程式可讓使用者在作者資料包括 Word、 Excel、 PowerPoint、 Outlook 及 OneNote <br><br> 客戶內容也包含客戶擁有/提供機密資料 （密碼、 憑證、 加密金鑰和儲存機碼） | **作用中刪除案例：** 最 30 天 <br><br> **被動刪除案例：** 最 180 天 |
| 客戶資料 | 一般使用者識別資訊 (EUII) | 識別或無法用來識別使用者的 Microsoft 服務的資料。EUII 不包含客戶內容 | 使用者名稱或顯示名稱 (DOMAIN\UserName) <br><br> 使用者主要名稱 (name@domain) <br><br>  使用者專用的 IP 位址 | **作用中刪除案例：** 最 180 天 （僅限租用戶系統管理員動作） <br><br> **被動刪除案例：** 最 180 天 |
| 個人資料 <br> （不包含客戶資料的資料） | 一般使用者 Pseudonymous 識別碼 (EUPI) | Microsoft 繫結至 Microsoft 服務的使用者所建立的識別碼。當 EUPI 結合其他資訊，例如對應表，它會識別使用者 <br><br> EUPI 不包含上傳或建立由客戶資訊 | 使用者的 Guid、 PUIDs、 或 Sid <br><br> 工作階段識別碼 | **作用中刪除案例：** 最 30 天 <br><br> **被動刪除案例：** 最 180 天 |

## <a name="subscription-retention"></a>訂閱保留

作用中的訂閱的所有的時間期間字詞 at、 訂閱者可以存取、 「 解壓縮 」 或刪除儲存在 Office 365 的客戶資料。如果付費的訂閱結束或已終止、 Microsoft 將保留中啟用擷取資料訂戶 90 天的限制函數帳戶儲存在 Office 365 的客戶資料。90 天保留期間結束後，Microsoft 將會停用帳戶並刪除客戶資料。不得超過 180 天之後到期日或 Office 365 訂閱的終止 Microsoft 會停用帳戶及帳戶中刪除所有的客戶資料。一旦經過任何資料的最大的保留期間，資料會呈現商業上無法復原。

但如果是免費的試用版，您的帳戶會移動到寬限期狀態 30 天的大部分的國家和地區。在此寬限期間，您必須購買 Office 365 選項。如果您決定不要購買 Office 365，您可以取消您的試用版或讓寬限期間到期，並將刪除您的試用帳戶資訊和資料。

## <a name="expedited-deletion"></a>加速的刪除
任何訂閱的所有的時間期間字詞 at、 訂閱者都可以連絡 Microsoft 支援和快速式要求訂閱佈建。在此程序，所有使用者資料，包括資料的 SharePoint Online、 Exchange Online 下可能會保留或非使用中信箱中儲存為已刪除的三天後管理員進入 Microsoft 提供的鎖定程式碼。如需有關加速佈建的詳細資訊，請參閱[取消 Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)。

## <a name="related-links"></a>相關的連結
- [資料毀損](office-365-data-destruction.md)
- [Office 365 中的不變性](office-365-data-immutability.md)
- [Exchange Online 資料刪除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online 資料刪除](office-365-sharepoint-online-data-deletion.md)
- [商務用 Skype 資料刪除](office-365-skype-data-deletion.md)