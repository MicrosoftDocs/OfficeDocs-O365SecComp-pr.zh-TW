---
title: 處置檢閱概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: 當您建立會保留在 Office 365 中的內容的標籤時，您可以選擇觸發結尾處的保留期間處理檢閱。
ms.openlocfilehash: 0948d61131595d4111f656c385c58258c5cce99c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215003"
---
# <a name="overview-of-disposition-reviews"></a>處置檢閱概觀

當內容達到其保留期間的結尾時，原因有幾個原因可能會想要檢閱以決定是否它可以安全地刪除該內容 （"處置"）。例如，您可能需要：
  
- 擱置相關的內容發生訴訟暫止或稽核時的刪除 （"處理"）。
    
- 移除內容處理清單中來儲存封存的內容是否研究 （英文） 或歷程記錄的值。
    
- 如果原始的原則是暫時性或暫時性解決方案，內容、 指派不同的保留期間。
    
- 將內容傳回給用戶端或將它轉接至另一個組織。
    
當您建立會保留在 Office 365 中的內容的標籤時，您可以選擇觸發結尾處的保留期間處理檢閱。在處理檢閱： 中
  
- 您選擇的人員接收其內容可供檢閱的電子郵件通知。這些檢閱者可以是個別使用者、 通訊群組或安全性群組或 Office 365 群組。請注意每週為基礎傳送通知。
    
- 檢閱者移至 [**處理**] 頁面上的 [安全性]&amp;規範中心以檢閱的內容。 
    
- 每份文件、 檢閱者可以：
    
  - 適用於不同的標籤。
    
  - 擴充其保留期間。
    
  - 永久刪除它。
    
- 檢閱者可以檢視擱置或歷史配置，並將該清單匯出成.csv 檔案。
    
請注意，處理檢閱 （英文） 需要 Office 365 企業版 E5 訂閱。
  
處理檢閱可以將內容包含在 Exchange 信箱、 SharePoint 網站、 OneDrive 帳戶及 Office 365 群組。等待處理檢閱這些位置中的內容會刪除後檢閱者選擇 [永久刪除內容。
  
![處理] 頁面](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>設定處理檢閱所建立的標籤

這是用於設定處理檢閱的基本工作流程。請注意此流程顯示標籤正在發佈和手動套用由使用者;或者，會觸發處理檢閱標籤可以為自動套用至內容。
  
![圖表顯示流量處理的運作方式](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
處理檢閱 Office 365 中建立的標籤時的選項。請注意此選項並不提供但只在含有保留設定的標籤中的保留原則。
  
如需標籤的詳細資訊，請參閱[標籤概觀](labels.md)。
  
![Label 的保留設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>處置內容

當檢閱者會收到通知電子郵件的內容是否已準備好可供檢閱、 他們可以移至 [**處理**] 頁面上的 [安全性]&amp;規範中心及選取的一或多個項目。然後可以檢閱者： 
  
- 適用於不同的標籤。
    
- 擴充的保留期間。
    
- 永久刪除項目。
    
檢閱者可用於連結檢視其原始位置中的文件檢閱者是否該位置的權限。期間處理檢閱、 內容永遠不會移動從其原始位置及永遠不會刪除之前檢閱者選擇這麼做。
  
請注意每週為基礎的檢閱者以自動傳送電子郵件通知。因此，當內容達到其保留期間的結尾，可能需要最多可有七天的檢閱者來接收電子郵件通知的內容已釋放處理。
  
也請注意的稽核處理的所有動作。若要確保這，您必須開啟稽核功能至少前一天的第一個處理巨集指令-如需詳細資訊，請參閱[Office 365 安全性搜尋稽核記錄&amp;規範中心](search-the-audit-log-in-security-and-compliance.md)。 
  
![文件的配置選項](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>處理的權限

若要存取 [**處理**] 頁面上的，請檢閱者必須是**處理管理**角色和 「**僅檢視稽核記錄**」 角色的成員。建議您建立新的角色群組呼叫處理檢閱者、 將這兩個角色新增至該角色群組，並再新增成員至角色群組。 
  
如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性&amp;規範中心](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>處置的內容會永久刪除之前的時間長度

等待處理檢閱的內容會刪除後檢閱者選擇 [永久刪除內容。檢閱者選擇這個選項時, 的 SharePoint 網站或 OneDrive 帳戶中的內容會變成適合本節所述的標準的清除程序：[原有內容的保留原則的運作方式](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。
  
這表示：
  
- 文件庫中的內容會移至第一階段資源回收筒**內 7 天**的處理，且再之後會永久刪除**93 天**。資源回收筒未編製索引的搜尋與因此不提供至 eDiscovery 保留其內容。 
    
- 內容中保留保留文件庫將會永久刪除**7 天內**的處理。 
    
## <a name="view-pending-and-completed-dispositions"></a>檢視擱置及完成的配置

在 [**處理**] 頁面上的 [安全性]&amp;規範中心，您可以檢視擱置和完成配置： 
  
- **擱置**的配置已達到其保留期限結束且需要處理檢閱。檢閱每個項目之後, 決定要對其套用的不同標籤、 擴充其保留期間，或永久刪除它。 
    
- **已完成**配置已核准的期間處理檢閱刪除，現在程序會永久刪除。有不同的標籤套用或延伸為組件的檢閱將不會出現在這裡其保留期限的項目。 
    
### <a name="filter-the-disposition-views"></a>篩選處理檢視

您可以篩選這些檢視的標籤或時間範圍。擱置的配置，時間範圍為根據的到期日期。歷史配置的時間範圍根據刪除日期。
  
![在 [處理] 頁面上的篩選選項](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>匯出處理項目

此外，您可以將其中一個檢視中的項目匯出成.csv 檔案，您可以在 Excel 中開啟。
  
![在 Excel 中匯出的處理資料](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

