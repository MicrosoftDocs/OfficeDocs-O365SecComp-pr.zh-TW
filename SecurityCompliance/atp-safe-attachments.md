---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: '[安全附件] 功能可提供電子郵件附件的按一下時間驗證。 使用安全附件來保護您的組織, 防止他人以電子郵件傳送或接收的惡意檔案。'
ms.openlocfilehash: 2980349eaec22f1e67206f96b8ed22df539cdba7
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652616"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件

## <a name="overview-of-office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件概述

ATP 安全附件 (搭配[ATP 安全連結](atp-safe-links.md)) 是[Office 365 高級威脅防護](office-365-atp.md)(ATP) 的一部分。 ATP 安全附件功能會檢查電子郵件附件是否為惡意的, 然後採取動作來保護您的組織。 ATP 安全附件功能會根據您的 Office 365 全域或安全性系統管理員所設定的[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md), 來保護您的組織。 
  
ATP 保護也可以擴充至 SharePoint Online、商務用 OneDrive 和 Microsoft 團隊中的檔案。 若要深入瞭解, 請參閱[適用于 SharePoint、OneDrive 及 Microsoft 團隊的 Office 365 高級威脅防護](atp-for-spo-odb-and-teams.md)。
  
## <a name="how-to-get-atp-safe-attachments"></a>如何取得 ATP 安全附件

首先, 請確定您的訂閱包含[高級威脅防護](office-365-atp.md)。 在訂閱中包含 ATP, 例如[microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商務](https://www.microsoft.com/microsoft-365/business)版、Office 365 E5、office 365 A5 等等。如果您的組織有不含 Office 365 ATP 的 Office 365 訂閱, 您可能會將 ATP 作為附加元件購買。 如需詳細資訊, 請參閱[office 365 高級威脅防護方案和價格](https://products.office.com/exchange/advance-threat-protection), 以及[Office 365 的高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

接下來, 請確定已定義 ATP 安全附件原則。 (請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md))ATP 安全附件功能在下列情況中為作用中:
  
- 已設定 ATP 安全附件原則。 (請參閱[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)。)

- 使用者使用他們的公司或學校帳戶登入 Office 365。 (請參閱登[入 office 或 office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)。)

若要定義 (或編輯) ATP 原則, 您必須獲指派適當的角色。 下表說明一些範例:

|角色  |指派的位置/方式  |
|---------|---------|
|Office 365 全域系統管理員 |註冊購買 Office 365 的人員預設為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入瞭解。)         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>如何知道 ATP 安全附件保護是否已準備就緒

在您[定義 (或查看) ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)之後, 若要查看服務的運作方式, 有一個很好的方法, 就是[查看高級威脅防護的報告](view-reports-for-atp.md)。
  
下表說明一些範例案例。 在這些情況下, 我們假設組織有 Office 365 訂閱, 其中包含了高級威脅防護。
  
|**範例案例**|**在這種情況下, ATP 安全附件保護是否適用？**|
|:-----|:-----|
|Pat 的組織有 Office 365 E5, 但尚未定義 ATP 安全附件的任何原則。  <br/> |否。 雖然此功能可供使用, 但至少必須定義一個 ATP 安全附件原則, 才能讓 ATP 安全附件保護生效。  <br/> |
|先生是在 Contoso 的銷售部門中的員工。 先生/她的組織有一個僅適用于財務員工的 ATP 安全附件原則。  <br/> |否。 在這種情況下, 財務員工會有 ATP 安全附件保護, 但其他員工 (包括銷售部門) 將不會等到包含這些群組的原則已定義為止。  <br/> |
|昨天, Jean-francois 組織的 Office 365 系統管理員會設定適用于所有員工的 ATP 安全附件原則。 在今天, Jean-francois 收到包含附件的電子郵件。  <br/> |是。 在此範例中, Jean-francois 具有高級威脅防護的授權, 而且已定義包含 Jean-francois 的 ATP 安全附件原則。 新原則通常需要30分鐘的時間, 才會在資料中心之間生效。由於在此情況下已超過一天, 因此原則應該生效。  <br/> |
|Chris 的組織有 Office 365 E5, 且組織中的每個人都有 ATP 安全附件原則。 Chris 會收到具有附件的電子郵件, 並將郵件轉寄給組織外部的其他人。  <br/> |ATP 安全附件保護目前在 Chris 收到的郵件中。 如果收件者的組織也有 ATP 安全附件原則, 則當所轉寄的郵件到達時, Chris 轉寄的郵件會受到這些原則的影響。  <br/> |
|曉明的組織已就地有 ATP 安全附件原則, 且已開啟與[SharePoint、OneDrive 及 Microsoft 小組的 atp](atp-for-spo-odb-and-teams.md) 。 曉明假設已掃描 SharePoint Online 中的每個檔案, 且可以安全地開啟或下載。  <br/> |ATP 安全附件保護是根據定義的原則進行不過, 這並不表示會掃描 SharePoint Online、商務用 OneDrive 或 Microsoft 團隊中的每個單一檔案。 (若要深入瞭解, 請參閱[ATP For SharePoint、OneDrive 及 Microsoft 團隊](atp-for-spo-odb-and-teams.md)。)  <br/> |

## <a name="submitting-files-for-malware-analysis"></a>提交檔案以進行惡意程式碼分析

- 如果您收到要要求 Microsoft 進行分析的檔案, 請造訪提交檔案[以進行惡意程式碼分析](https://aka.ms/wdsi/submit)。

- 如果您收到一封電子郵件 (包含或不含附件), 您想要提交給 Microsoft 進行分析, 請使用[報告訊息增益集](enable-the-report-message-add-in.md)。
