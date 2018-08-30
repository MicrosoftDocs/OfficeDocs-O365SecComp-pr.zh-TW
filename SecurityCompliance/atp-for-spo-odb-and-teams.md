---
title: 適用於 SharePoint、OneDrive 及 Microsoft Teams 的Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: 擴充 Office 365 進階威脅保護 SharePoint Online、 OneDrive for Business 和 Microsoft 小組以啟用更安全共同作業您的組織中的檔案。
ms.openlocfilehash: ea1c77273be70ce27f60bfaeae3544d605553a32
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "22527176"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>適用於 SharePoint、OneDrive 及 Microsoft Teams 的Office 365 ATP

定期人員共用檔案並使用 SharePoint、 OneDrive 及 Microsoft 小組共同作業。[Office 365 進階威脅保護](office-365-atp.md)(ATP)，與您的組織共同作業更安全的方式。ATP 協助偵測和封鎖識別為惡意小組網站和文件庫中的檔案。閱讀本篇文章以概略 ATP SharePoint Online、 OneDrive for Business 和 Microsoft 小組並再執行您下一個步驟。 
  
> [!TIP]
> 若要執行本文所述的工作，您必須是 Office 365 全域管理員或安全性管理員。請參閱[中的 Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="how-it-works"></a>運作方式

當 SharePoint Online 中的檔案時、 OneDrive for Business 和 Microsoft 小組已識別為惡意、 ATP 直接整合搭配鎖定該檔案的檔案存放區。下圖顯示在文件庫中偵測到惡意檔案的範例。
  
[![檔案的 onedrive for Business 與一個偵測到為惡意的螢幕擷取畫面](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
雖然封鎖的檔案仍會列在文件庫和 web、 手機或桌面應用程式中封鎖的檔案不能是開啟、 複製、 移動或共用。人員可以，但刪除封鎖的檔案。以下使用者的行動裝置的哪些的範例看起來像：
  
[![封鎖的檔案的 OneDrive for Business 刪除 OneDrive 行動裝置應用程式的螢幕擷取畫面](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
根據 Office 365 的設定方式的人員可能或可能沒有能夠下載封鎖的檔案。以下是使用者的行動裝置上下載封鎖的檔案新外觀：
  
[![下載的 onedrive for Business 封鎖的檔案的螢幕擷取畫面](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
若要深入了解，請參閱[開啟 Office 365 ATP for SharePoint、 OneDrive 及 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)。
  
### <a name="keep-the-following-points-in-mind"></a>請記住下列重點

- ATP 不會掃描 SharePoint Online、 OneDrive 中每一個單一檔案商務或 Microsoft 小組。這是根據設計。掃描檔案有以非同步方式，透過使用智慧 heuristics 和威脅有空的共用和來賓活動事件來識別惡意檔案的程序。
    
- 會被識別為惡意 SharePoint Online 中的檔案、 OneDrive for Business 或 Microsoft 小組會顯示在[Office 365 進階威脅 Protection 的報告](view-reports-for-atp.md)及威脅 Explorer （ [Office 365 威脅智慧](office-365-ti.md)的一部分）。
    
- ATP 屬於貴組織的整體威脅保護策略中，包含反垃圾郵件和反惡意程式防護，以及安全的連結和安全的附件。若要深入了解，請參閱[Office 365 中的威脅的保護](protect-against-threats.md)。
    
- SharePoint Online 系統管理員可以決定是否要讓使用者能夠下載偵測到為惡意的檔案。做法是執行 Set-spotenant PowerShell 指令程式使用 DisallowInfectedFileDownload 參數 （請參閱[開啟 SharePoint、 OneDrive 及 Microsoft 小組的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)）。
    
## <a name="new-quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>（新增 ！）隔離區中 ATP for SharePoint Online、 OneDrive for Business 和 Microsoft 小組

 * * 開始落後 5 2018、 安全性[隔離](quarantine-email-messages.md)功能的&amp;規範中心會被擴充至 ATP for SharePoint Online、 OneDrive for Business 和 Microsoft 小組。 **
  
當 SharePoint Online 中的檔案時、 OneDrive for Business 或 Microsoft 小組識別為惡意除了 ATP 封鎖防止開啟或共用檔案時，該檔案包含在隔離的項目清單。(安全性&amp;規範管理中心，移至**威脅管理** \> **檢閱** \> **隔離**及內容的篩選。) 
  
如果您正在貴組織的 Office 365 安全性小組的一部分，且必須必要[權限指派在 Office 365 安全性&amp;規範中心](permissions-in-the-security-and-compliance-center.md)，您可以下載、 版本、 報告及刪除已偵測到為惡意的 ATP 的檔案從隔離區。
  
- **發佈和報告**檔案移除檔案的 ATP 區塊各自的小組網站或文件庫中 SharePoint、 OneDrive 或 Microsoft 小組。使用者是然後能夠開啟、 分享和下載檔案。然後將檔案**傳送報告給 Microsoft**選取選項時，會向 Microsoft 報告為誤判。 
    
- **刪除檔案**從隔離; 移除檔案不過，只有在正在開啟或共用，仍有封鎖的檔案。檔案必須也會刪除其各自的文件庫或小組網站 （SharePoint Online、 OneDrive for Business 或 Microsoft 小組） 中。 
    
- **下載檔案**可讓您下載及分析之檔案的任何誤判。 
    
## <a name="next-steps"></a>後續步驟

- [在 Office 365 ATP 開啟 SharePoint、 OneDrive 及 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)
    
- [檢視 SharePoint、 OneDrive 或 Microsoft 小組中偵測到惡意檔案的資訊](malicious-files-detected-in-spo-odb-or-teams.md)
    
## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 進階威脅保護的檢視報告](view-reports-for-atp.md)
  
[Office 365 安全性權限&amp;規範中心](permissions-in-the-security-and-compliance-center.md)
  

