---
title: Office 365 進階威脅保護的檢視報告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 了解如何尋找及使用報表的 Office 365 進階威脅保護安全性&amp;規範中心。
ms.openlocfilehash: 4a76c6a5b888142dc4c35af432fa61916145d648
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454300"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 進階威脅保護的檢視報告

如果您的組織具有[Office 365 進階威脅保護](office-365-atp.md)(ATP) 且您具有[必要權限](#what-permissions-are-needed-to-view-these-reports)，您可以使用數個 ATP 報告安全性&amp;規範中心。(請移至**報表** \> **儀表板**。)
  
![安全性&amp;規範中心儀表板可協助您看到其用於進階威脅保護](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP 報告包含[威脅保護狀態報表](#threat-protection-status-report)、 [ATP 檔案類型的報告](#atp-file-types-report)及[ATP 郵件處理報告](#atp-message-disposition-report)。本文說明 ATP 報告並包含連結至[其他報表檢視](#additional-reports-to-view)。
  
## <a name="threat-protection-status-report"></a>威脅保護狀態報表

**威脅保護狀態**報表是結合惡意內容及惡意電子郵件偵測和封鎖的 Exchange Online 與進階威脅保護的相關資訊的單一檢視。此報表提供惡意內容 （檔案或 Url） 反惡意程式碼引擎、[零小時自動清除 (ZAP)](zero-hour-auto-purge.md)，與進階威脅保護功能，例如[ATP 安全連結](atp-safe-links.md)、 [ATP 所封鎖的唯一的電子郵件訊息的彙總的計數安全的附件](atp-safe-attachments.md)，與[Office 365 的 ATP 反網路釣魚功能](atp-anti-phishing.md)。
  
若要檢視安全性威脅保護狀態報表&amp;規範管理中心，移至**報表** \> **儀表板** \> **威脅保護狀態**。
  
![ATP 威脅保護狀態報表](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
若要取得一天的詳細的狀態，將滑鼠停留在圖形。
  
![工作日的 ATP 威脅保護狀態資料](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
根據預設，威脅保護狀態報表會顯示過去 7 天的資料。不過，您可以選擇 [**篩選器**並變更至 90 天的檢視資料的日期範圍。 
  
![ATP 威脅保護狀態篩選](media/4f703369-642b-402b-9758-b9c828283410.png)
  
您也可以使用 [**檢視資料**] 功能表來變更報表中所顯示的資訊。 
  
![檢視 ATP 威脅保護狀態報表的選項](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP 檔案類型的報告

**ATP 檔案類型**報表顯示偵測到為惡意的[ATP 安全附件](atp-safe-attachments.md)的檔案類型。
  
若要檢視這份報告，安全性&amp;規範管理中心，移至**報表** \> **儀表板** \> **ATP 檔案類型**。
  
![ATP 檔案類型的報告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
當您將滑鼠停留在特定的日子時，您可以看到分解為惡意已偵測到的[ATP 安全附件](atp-safe-attachments.md)的檔案類型及[反垃圾郵件&amp;Office 365 中的反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。
  
![ATP 檔案類型的一天的報告資料](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP 郵件處理報告

**ATP 郵件處理**報告顯示的電子郵件訊息所偵測到為具有惡意內容所採取的動作。 
  
若要檢視這份報告，安全性&amp;規範管理中心，移至**報表** \> **儀表板** \> **ATP 郵件處理**。
  
![ATP 郵件處理報告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
當您將滑鼠停留在圖表中的列時，您可以看到動作已偵測到的電子郵件採取的那天。
  
![工作日的 ATP 郵件處理報告資料](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>若要檢視其他報告

除了本文所述 ATP 報告[電子郵件安全性報告](view-email-security-reports.md)中可用的安全性&amp;規範中心。電子郵件安全性報告包含[頂端的寄件者和收件者報告](view-email-security-reports.md#top-senders-and-recipients-report)、[詐騙郵件報告](view-email-security-reports.md#spoof-mail-report)、[垃圾郵件偵測] 報告](view-email-security-reports.md#spam-detections-report)及更多。
  
與您的組織有[Office 365 威脅智慧](office-365-ti.md)，如果您也可以[使用瀏覽器安全性&amp;規範中心](use-explorer-in-security-and-compliance.md)。
  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>若要檢視 ATP 報告需要哪些權限？

若要檢視及使用本文所述的報告，您必須具備適當的角色指派安全性&amp;規範中心及 Exchange 系統管理中心中。
  
|**角色群組**|**其中指派**|**深入了解**|
|:-----|:-----|:-----|
| 下列其中之一：  <br/>  組織管理  <br/>  安全性管理員  <br/>  安全性讀者  <br/> |安全性&amp;規範中心  <br/> |[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md) <br/> |
| 下列其中之一：  <br/>  組織管理  <br/>  僅限檢視組織管理  <br/>  僅檢視收件者角色  <br/>  規範管理  <br/> |Exchange 系統管理中心  <br/> |[Exchange Online 中的功能權限](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果報表不顯示資料吗？

如果您看不見的資料在報告中，再次檢查您的原則已正確設定。您的組織必須[ATP 安全連結原則](set-up-atp-safe-links-policies.md)和[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)定義 ATP protection 順序設為就地。另請參閱 ＜ [Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相關主題

[報告與 Office 365 安全性前瞻&amp;規範中心](reports-and-insights-in-security-and-compliance.md)
  
[在 [安全性] 中建立報表的排程&amp;規範中心](create-a-schedule-for-a-report.md)
  
[設定並下載安全性的自訂報告&amp;規範中心](set-up-and-download-a-custom-report.md)
  

