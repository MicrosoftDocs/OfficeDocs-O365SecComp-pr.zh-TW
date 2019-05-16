---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 04/04/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: 安全附件功能提供時間按一下 [驗證電子郵件附件。 使用安全附件以保護您的組織中的惡意檔案人員傳送或接收電子郵件中。
ms.openlocfilehash: fd3fc7f790870330f0f69fc4cca59e1b8c58ce00
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077529"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件

## <a name="overview-of-office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件的概觀

ATP 安全附件 （以及[ATP 安全連結](atp-safe-links.md)） 是[Office 365 進階威脅防護](office-365-atp.md)(ATP) 的一部分。 ATP 安全附件功能檢查電子郵件附件是否惡意，，，然後採取的動作來保護您的組織。 ATP 安全附件功能可以保護您的組織根據您的 Office 365 全域或安全性管理員所設定的[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)。 
  
ATP 保護也可以擴充檔案的 SharePoint Online、 OneDrive for Business 和 Microsoft Teams。 若要深入了解，請參閱 < <b0>Office 365 進階威脅防護 SharePoint、 OneDrive 及 Microsoft Teams</b0>。

## <a name="how-it-works"></a>運作方式

ATP 安全附件功能會檢查您的組織中的人員的電子郵件附件。 當 ATP 安全附件原則已經準備就緒且某人所涵蓋的原則，在 Office 365 中檢視他們的電子郵件時，就會檢查其電子郵件附件，並採取適當的動作，根據您的 ATP 安全附件原則。 根據您的原則定義的方式，人員可以繼續使用，完全不會知道他們所傳送的惡意檔案。
  
以下是兩個範例 ATP 安全附件的場所。
  
- **範例 1： 電子郵件附件**假設 Lee 收到具有附件的電子郵件訊息。 它不明顯地 Lee 是否是安全附件，或確實包含惡意程式碼為了竊取 Lee 的使用者認證。 Lee 的組織中的安全性管理員會定義 ATP 安全附件原則幾天。 ATP 安全附件功能，與電子郵件附件形式開啟且 Lee 收到它之前，在虛擬環境中測試。 如果附件決定要惡意，它將會自動移除。 安全附件時，它會開啟如預期般 Lee 按一下在其上時。

- **範例 2: SharePoint Online 中的檔案**假設 Jean 接收檔案，而傳至 SharePoint Online 中的文件庫。 Jean 共用檔案的連結與其他小組成員，不知道該檔案實際惡意。 幸好，[適用於 SharePoint、 OneDrive 及 Microsoft Teams ATP](atp-for-spo-odb-and-teams.md)會偵測惡意檔案，並且封鎖。 幾天之後，Chris 移至開啟的文件。 雖然 Chris 可以看到檔案已存在，但 Chris 無法開啟，或讓它，進而從惡意檔案保護 Chris 的電腦與其他人共用。

ATP 安全附件原則可以套用到特定人員或組織中的群組或整個網域。 此外，ATP 安全附件原則可以設定成使用預留位置附件，雖然會掃描實際的附件。 若要深入了解，請參閱 <<c0>設定 Office 365 中的 ATP 安全附件原則。

> [!NOTE]
> ATP 安全附件掃描採取放在您的 Office 365 資料所在的相同區域中。 如需有關資料中心地理位置的詳細資訊，請參閱 <<c0>其中是位於您資料？ 

  
## <a name="how-to-get-atp-safe-attachments"></a>如何取得 ATP 安全附件

首先，請確定您的訂閱包含[進階威脅防護](office-365-atp.md)。 ATP 隨附於在 [訂閱，例如[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企業版 E5、 Office 365 教育版 A5 等。如果貴組織擁有不包含 Office 365 ATP 的 Office 365 訂閱，您可能可以當作附加元件購買 ATP。 如需詳細資訊，請參閱[Office 365 進階威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection)和[Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

接下來，請確定您的 ATP 安全附件原則所定義。 （請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)）ATP 安全附件功能已啟用：
  
- ATP 安全附件原則設定。 （請參閱[設定 Office 365 中的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)）。

- 使用者已登入 Office 365 中，使用其公司或學校帳戶。 （請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。

若要定義 （或編輯） ATP 原則，您必須獲指派適當的角色。 下表說明一些範例：

|角色  |位置/方式指派  |
|---------|---------|
|Office 365 全域系統管理員 |若要購買 Office 365 註冊的人員是預設的全域系統管理員。 （請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)，以了解更多）。         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>如何知道 ATP 安全附件保護是否就緒

[定義 （或檢閱） ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)之後，若要瞭解服務的運作方式的一個好方法是藉由[檢視的進階威脅防護報告](view-reports-for-atp.md)。
  
下表說明幾個案例。 在所有這些情況下，我們假設該組織有包含進階威脅防護的 Office 365 訂閱。
  
|**範例案例**|**ATP 安全附件保護不會在此情況下套用嗎？**|
|:-----|:-----|
|Pat 的組織有 Office 365 企業版 E5，但沒有人有任何原則尚未定義的 ATP 安全附件。  <br/> |否。 雖然功能可供使用，至少一個 ATP 安全附件原則必須定義要就地 ATP 安全附件保護的順序。  <br/> |
|Lee 是在 contoso 公司銷售部門中的員工。 Lee 的組織已在適用於僅限財務員工的地方 ATP 安全附件原則。  <br/> |否。 在此情況下，finance 員工必須 ATP 安全附件保護，但其他員工，包括銷售部門中，會等到已定義包含這些群組的原則。  <br/> |
|昨天，Jean 的組織在 Office 365 系統管理員設定適用於所有員工 ATP 安全附件原則。 稍早今天 Jean 接收電子郵件訊息，其中包含附件。  <br/> |是。 在這個範例中，Jean 已授權的進階威脅防護，並且包含 Jean ATP 安全附件原則已定義。 它通常採用大約 30 分鐘，才會生效跨資料中心; 新的原則因為已在此情況下通過一天，該原則應生效。  <br/> |
|Chris 的組織中可以讓所有人組織中的 ATP 安全附件原則與具有 Office 365 企業版 E5。 Chris 會收到一封電子郵件附件，且會轉寄給其他人屬於組織外部的郵件。  <br/> |ATP 安全附件保護已就緒，Chris 接收的郵件。 如果收件者的組織也有 ATP 安全附件原則中的位置，然後 Chris 轉寄的郵件會受到那些原則轉寄的郵件送達時。  <br/> |
|李明組織已就緒，ATP 安全附件原則和已開啟[ATP SharePoint、 OneDrive 及 Microsoft Teams](atp-for-spo-odb-and-teams.md) 。 李明假設在 SharePoint Online 中的每個檔案已掃描，且安全地開啟或下載。  <br/> |ATP 安全附件防護是根據定義; 原則就地不過，這並不表示會掃描 SharePoint Online、 商務用 OneDrive 或 Microsoft Teams 中每一個檔案。 （若要深入了解，請參閱[適用於 SharePoint、 OneDrive 及 Microsoft Teams ATP](atp-for-spo-odb-and-teams.md)）。  <br/> |

## <a name="submitting-files-for-malware-analysis"></a>送出的惡意程式碼分析的檔案

- 如果您收到您想要詢問 Microsoft，以分析的檔案，請造訪[提交惡意程式碼分析的檔案](https://aka.ms/wdsi/submit)。

- 如果您收到電子郵件 （含或不含附件），您想要提交給 Microsoft 進行分析，請使用[報告訊息增益集](enable-the-report-message-add-in.md)。
