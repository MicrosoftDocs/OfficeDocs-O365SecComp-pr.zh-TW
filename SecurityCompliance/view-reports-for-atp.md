---
title: Office 365 進階威脅保護的檢視報告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection: M365-security-compliance
description: 了解如何尋找及使用報表的 Office 365 進階威脅保護安全性&amp;規範中心。
ms.openlocfilehash: a27fdf6c7d04a2526873047d4e2a33bb283878b3
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995224"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 進階威脅保護的檢視報告

如果您的組織具有[Office 365 進階威脅保護](office-365-atp.md)(ATP) 且您具有[必要權限](#what-permissions-are-needed-to-view-these-reports)，您可以使用數個 ATP 報告安全性&amp;規範中心。(請移至**報表** \> **儀表板**。)
  
![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP 報告包含[威脅保護狀態報表](#threat-protection-status-report)、 [ATP 檔案類型的報告](#atp-file-types-report)及[ATP 郵件處理報告](#atp-message-disposition-report)。本文說明 ATP 報告並包含連結至[其他報表檢視](#additional-reports-to-view)。
  
## <a name="threat-protection-status-report"></a>威脅保護狀態報表

**威脅保護狀態**報表是結合惡意內容及惡意電子郵件偵測和封鎖的[Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) 和[Office 365 ATP](office-365-atp.md)的相關資訊的單一檢視。此報表提供彙總惡意內容 （檔案或網站位址 (Url)） 封鎖的反惡意程式碼引擎、[零小時自動清除 (ZAP)](zero-hour-auto-purge.md)，與 ATP 功能，例如[ATP 安全連結](atp-safe-links.md)、 [ATP 安全的唯一的電子郵件數附件](atp-safe-attachments.md)，與[ATP 反網路釣魚功能](atp-anti-phishing.md)。

> [!NOTE]
> 威脅保護狀態報表是供使用者具有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP);不過，ATP 客戶的威脅保護狀態報表中所顯示的資訊可能會包含超過 EOP 客戶可以看到不同的資料。例如，ATP 客戶的威脅保護狀態報表會包含[SharePoint Online、 OneDrive 或 Microsoft 小組中偵測到惡意檔案](atp-for-spo-odb-and-teams.md)的相關資訊。這類資訊是專屬於 ATP、，因此有 EOP，但不是 ATP 的客戶不會看到這些其威脅保護狀態報告的詳細資訊。
  
若要檢視中的潛在威脅保護狀態報表[安全性&amp;規範中心](https://protection.office.com)、 移至 [**報表** \> **儀表板** \> **威脅保護狀態**。
  
![ATP 威脅保護狀態報表](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
若要取得一天的詳細的狀態，將滑鼠停留在圖形。
  
![工作日的 ATP 威脅保護狀態資料](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
根據預設，威脅保護狀態報表會顯示過去 7 天的資料。不過，您可以選擇 [**篩選器**並變更至 90 天的檢視資料的日期範圍。 
  
![ATP 威脅保護狀態篩選](media/4f703369-642b-402b-9758-b9c828283410.png)
  
您也可以使用 [**檢視資料**] 功能表來變更報表中所顯示的資訊。 
  
![檢視 ATP 威脅保護狀態報表的選項](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP 檔案類型的報告

**ATP 檔案類型**報表顯示偵測到為惡意的[ATP 安全附件](atp-safe-attachments.md)的檔案類型。
  
若要檢視中的這份報告，[安全性&amp;規範中心](https://protection.office.com)、 移至 [**報表** \> **儀表板** \> **ATP 檔案類型**。
  
![ATP 檔案類型的報告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
當您將滑鼠停留在特定的日子時，您可以看到分解為惡意已偵測到的[ATP 安全附件](atp-safe-attachments.md)的檔案類型及[反垃圾郵件&amp;Office 365 中的反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。
  
![ATP 檔案類型的一天的報告資料](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP 郵件處理報告

**ATP 郵件處理**報告顯示的電子郵件訊息所偵測到為具有惡意內容所採取的動作。 
  
若要檢視中的這份報告，[安全性&amp;規範中心](https://protection.office.com)、 移至 [**報表** \> **儀表板** \> **ATP 郵件處理**。
  
![ATP 郵件處理報告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
當您將滑鼠停留在圖表中的列時，您可以看到動作已偵測到的電子郵件採取的那天。
  
![工作日的 ATP 郵件處理報告資料](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>若要檢視其他報告

除了本文所述 ATP 報告、 數個其他報告可用，如下表所述：

|報告類型  |深入了解  |
|---------|---------|
|**電子郵件安全性報表**，例如頂端的寄件者和收件者報告、 詐騙郵件報表及垃圾郵件偵測] 報告。 | [在 [安全性] 中檢視電子郵件安全性報表&amp;規範中心](view-email-security-reports.md)        |
|**瀏覽器**（也稱為威脅瀏覽器，這包含在[Office 365 威脅智慧](office-365-ti.md)）     | [使用瀏覽器安全性&amp;規範中心](use-explorer-in-security-and-compliance.md)        |
|**EOP 和 ATP 結果**（這是您透過 PowerShell 產生自訂報告）。這份報告包含的資訊，例如網域、 日期、 事件類型、 Direction、 動作和訊息計數。  | [取得 MailTrafficATPReport 指令程式參考 （英文)](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**EOP 和 ATP 偵測**（這是您透過 PowerShell 產生自訂報告）。這份報告包含惡意檔案或 Url、 網路釣魚嘗試、 模擬、 及其他電子郵件或檔案中的潛在威脅詳細資料。   | [取得 MailDetailATPReport 指令程式參考 （英文)](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>若要檢視 ATP 報告需要哪些權限？

若要檢視和使用本文所述的報告**您必須具有適當的角色指派給這兩種安全性&amp;規範中心及 Exchange 系統管理中心**。

- Security&amp;規範中心，您必須具備一個指派的下列角色：
    - 組織管理
    - 安全性管理員 (這可被指派在 Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))
    - 安全性讀者

- Exchange online，您必須具備一個指派 Exchange 系統管理中心中的下列角色 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或使用 PowerShell cmdlet (請參閱[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))：
    - 組織管理
    - 僅檢視組織管理
    - 僅檢視收件者角色
    - 合規性管理

若要深入了解，請參閱下列資源：

- [Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果報表不顯示資料吗？

如果您看不見資料 ATP 報告中，再次檢查您的原則已正確設定。您的組織必須[ATP 安全連結原則](set-up-atp-safe-links-policies.md)和[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)定義 ATP protection 順序設為就地。另請參閱 ＜ [Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相關主題

[報告與 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)
  
[在 [安全性] 中建立報表的排程&amp;規範中心](create-a-schedule-for-a-report.md)
  
[設定並下載安全性的自訂報告&amp;規範中心](set-up-and-download-a-custom-report.md)
  

