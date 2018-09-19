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
ms.openlocfilehash: bb038f8bd8e3f0286ea7d673e5e286bdc4a9677d
ms.sourcegitcommit: 1bccdaacf358505604c9cf422cb1e272aefae19d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "23999144"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 中的資料保留、刪除及毀損

## <a name="introduction"></a>簡介
Microsoft Office 365 的客戶資料之後要刪除的保留期限會指定具有資料處理標準的原則。一般而言，Office 365 中有兩種案例客戶資料都會被刪除：
- **作用中刪除**使用者刪除資料，或私人給使用者的資料會刪除該使用者會由作用中的租用戶系統管理員在刪除之後。
- **被動刪除**租用戶訂閱綵帶橫幅。

Microsoft Office 365 的資料處理標準原則會指定資料在每個這些案例中的保留期限。下列各節說明類別的資料 （根據 Microsoft Office 365 資產分類標準） 和主動與被動刪除案例的保留期間。

## <a name="active-deletion-retention"></a>作用中刪除保留

| 資料類別 | 至少保留 | 最多只保留 |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| 存取控制資料 | 不適用 | 不適用 |
| 客戶的內容 | 7 天 | 30 天 |
| 使用者識別資訊 | 90 天 | 180 天 |
| 帳戶資料 | 1 年 | 3 年 |
| 組織識別資訊 | 90 天 | 180 天 |
| 系統的中繼資料 | 請參閱安全性記錄檔 | 請參閱安全性記錄檔 |
| 安全性記錄檔 | Min 1 年 | 最大 1 年 |
| Exchange Online 封存記錄檔 | Min 3 年 | 最大 3 年 |

## <a name="passive-deletion-retention"></a>被動刪除保留

| 資料類別 | 至少保留 | 最多只保留 |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| 存取控制資料 | 90 天 （適用於內容復原） | 180 天 （適用於內容復原） |
| 客戶的內容 | 90 天 （有限函數帳戶） | 180 天 |
| 使用者識別資訊 | 90 天 | 180 天 |
| 帳戶資料 | 1 年 | 3 年 |
| 組織識別資訊 | 90 天 | 180 天 |
| 系統的中繼資料 | 請參閱安全性記錄檔 | 請參閱安全性記錄檔 |
| 安全性記錄檔 | Min 1 年 | 最大 1 年 |
| Exchange Online 封存記錄檔 | Min 3 年 | 最大 3 年 |

## <a name="subscription-rentention"></a>訂閱 Rentention

客戶的內容會定義為 Exchange Online 信箱內容 (電子郵件內文、 行事曆項目和電子郵件附件的內容及如果有的話，Skype 商務內容)、 SharePoint Online 網站內容儲存在網站中的檔案與檔案上傳至 OneDrive 商務或 Skype for Business。

訂閱的所有的時間期間字詞 at、 訂閱者可以存取並擷取儲存在 Office 365 的客戶資料。除了免費試用版和 LinkedIn 服務，Microsoft 保留客戶資料儲存在 Office 365 中限制函數帳戶 90 天的到期日或訂閱啟用訂閱者擷取資料的終止之後。（但如果是免費的試用版，當試用版到期時，它將移入寬限期給予購買 Office 365 的 30 天 （適用於大部分試用版，在大部分的國家和地區）。如果您決定不要購買 Office 365，您可以讓您試用版到期或取消該程序。推出 30 天寬限期間之後，您的試用帳戶資訊和資料是永久清除。）

90 天保留期間結束之後，Microsoft 帳戶會停用和刪除客戶資料。不得超過 180 天之後到期日或 Office 365 訂閱的終止 Microsoft 會停用帳戶及帳戶中刪除所有的客戶資料。一旦經過任何資料的最大的保留期間，資料會呈現商業上無法復原。

Microsoft 也有位址回收和處置磁碟機和失敗或淘汰伺服器的資料處理標準原則。然後再重新使用 Office 365 內任何磁碟機，Microsoft 會執行與 NIST SP 800 88 相容的實體的病毒掃描程序。不能重複使用的磁碟機都會予以處置所執行含有正在終結磁碟的資料中心內的離站實際銷毀程序。依 Microsoft Cloud 基礎結構及操作 (MCIO) 會執行這些程序。如需詳細資訊，請參閱稽核報告在[服務信任預覽](https://aka.ms/STP)MCIO。

## <a name="expedited-deletion"></a>加速的刪除
訂閱的所有的時間期間字詞 at、 訂閱者都可以連絡 Microsoft 支援和快速式要求訂閱佈建。在此程序，所有使用者資料，包括資料的 SharePoint Online、 Exchange Online 下可能會保留或非使用中信箱中儲存為已刪除的三天後管理員進入 Microsoft 提供的鎖定程式碼。如需有關加速佈建的詳細資訊，請參閱[取消 Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)。

## <a name="related-links"></a>相關的連結
- [Exchange Online 資料刪除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online 資料刪除](office-365-sharepoint-online-data-deletion.md)
- [商務用 Skype 資料刪除](office-365-skype-data-deletion.md)
- [Office 365 中的不變性](office-365-data-immutability.md)
- [資料毀損](office-365-data-destruction.md)