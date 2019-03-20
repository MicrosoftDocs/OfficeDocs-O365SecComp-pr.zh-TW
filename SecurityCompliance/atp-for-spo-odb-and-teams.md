---
title: Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: 擴充 Office 365 進階威脅防護中 SharePoint Online、 商務用 OneDrive 和 Microsoft Teams 能夠為您的組織更安全的共同作業的檔案。
ms.openlocfilehash: 55bd613cd89819906773d663deb6278f804cb9de
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692442"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams 的概觀

定期人員共用檔案及共同作業使用 SharePoint、 OneDrive 及 Microsoft Teams。 使用[Office 365 進階威脅防護](office-365-atp.md)(ATP)，您的組織可以共同作業更安全的方式。 ATP 可協助偵測並封鎖會被識別為惡意小組網站和文件庫中的檔案。  
  
## <a name="how-it-works"></a>運作方式

當 SharePoint Online 中的檔案時，OneDrive for Business 和 Microsoft Teams 已識別為惡意，ATP 直接整合到鎖住該檔案的檔案存放區。 下圖顯示在文件庫中偵測到惡意檔案的範例。
  
[![檔案在商務用 OneDrive 中偵測到一個當做惡意攻擊](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
雖然封鎖的檔案仍會列在文件庫和 web，行動裝置，或桌面應用程式，封鎖的檔案無法開啟、 複製、 移動或共用。 人員可以不過，刪除封鎖的檔案。 以下使用者的行動裝置的這代表什麼意思範例如下所示：
  
[![從商務用 OneDrive 中刪除封鎖的檔案，從 OneDrive 行動應用程式](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
根據 Office 365 的設定方式，人員可能，或可能無法下載封鎖的檔案的能力。 以下是下載封鎖的檔案看起來像是使用者的行動裝置上：
  
[![下載 onedrive for Business 封鎖的檔案](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
若要深入了解，請參閱[開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)。
  
## <a name="keep-these-points-in-mind"></a>請記住以下幾點

- ATP 不會掃描每一個檔案中 SharePoint Online、 OneDrive 商務或 Microsoft Teams。 這是預設的設計。 掃描檔案有以非同步方式，透過使用以及智慧啟發和威脅訊號的共用和來賓活動事件來識別惡意檔案的程序。

- 請確定您的 SharePoint 網站已設定要使用[的新式體驗](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。 當檔案識別為惡意及封鎖時，使用者可以看到這已發生的新式體驗，但不是傳統檢視。 ATP 保護套用是否使用新式體驗或傳統檢視;不過，封鎖的檔案的視覺標記有只能在新式體驗。
    
- 會被識別為惡意 SharePoint Online 中的檔案，商務用 OneDrive 或 Microsoft Teams 會顯示在[Office 365 進階威脅防護的報告](view-reports-for-atp.md)和威脅總管 （ [Office 365 進階威脅防護計劃 2](office-365-ti.md)的一部分).
    
- ATP 是貴組織的整體威脅保護策略，其中包含反垃圾郵件和反惡意程式碼防護，以及安全連結和安全附件的一部分。 若要深入了解，請參閱 <<c0>針對 Office 365 中的威脅保護。
    
- SharePoint Online 系統管理員可以決定是否要讓使用者能夠下載偵測到為惡意的檔案。 這是藉由執行 Set-spotenant PowerShell cmdlet 使用 DisallowInfectedFileDownload 參數 （請參閱[在 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams 上開啟](turn-on-atp-for-spo-odb-and-teams.md)）。
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>隔離區中 ATP sharepoint Online、 商務用 OneDrive 和 Microsoft Teams

 從最遲 2018 年，[隔離](quarantine-email-messages.md)功能的安全性群組開始&amp;合規性中心會正在擴充至 ATP sharepoint Online、 商務用 OneDrive 和 Microsoft Teams。
  
當 SharePoint Online 中的檔案時，商務用 OneDrive 或 Microsoft Teams 識別為惡意，除了 ATP 封鎖開啟或共用檔案時，該檔案包含在被隔離的項目清單。 (安全性&amp;合規性中心，移至**威脅管理** \> **檢閱** \> **隔離**及**內容**篩選器。) 
  
如果您是貴組織的 Office 365 安全性小組的一部分，而且具有所需之[權限指派在 Office 365 安全性&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)，您可以下載、 版本、 報告及刪除會偵測 crypto ATP 為惡意的檔案從隔離區。
  
- **發佈並報告**檔案移除檔案 ATP 區塊各自的小組網站或文件庫中 SharePoint、 OneDrive 或 Microsoft Teams。 使用者就可以開啟、 共用及下載檔案。 然後將檔案選取 [**傳送報告給 Microsoft** ] 選項時，會向 Microsoft 報告為誤判。 
    
- **刪除檔案**從隔離區; 移除檔案不過，只有在所開啟或共用，仍有封鎖的檔案。 也必須在其各自的文件庫或小組網站 （SharePoint Online、 商務用 OneDrive 或 Microsoft Teams） 中刪除檔案。 
    
- **下載檔案**，可讓您下載並分析任何誤判的檔案。 
    
## <a name="next-steps"></a>後續步驟

1. [開啟 Office 365 ATP SharePoint、 OneDrive 及 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [檢視 SharePoint、 OneDrive 或 Microsoft Teams 中偵測到的惡意檔案的相關資訊](malicious-files-detected-in-spo-odb-or-teams.md)
    
